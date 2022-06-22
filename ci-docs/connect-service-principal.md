---
title: सेवा प्रमुख का उपयोग करके किसी Azure Data Lake Storage खाते से कनेक्ट करें
description: अपने खुद के data lake से कनेक्ट करने के लिए Azure सेवा प्रमुख का उपयोग करें.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 36ad957f59b23df6ee83d9d90898ef03ddfd320a
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011843"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure सेवा प्रमुख का उपयोग करके किसी Azure Data Lake Storage खाते से कनेक्ट करें

यह आलेख चर्चा करता है कि कैसे कनेक्ट करें Dynamics 365 Customer Insights एक साथ Azure Data Lake Storage एक Azure सेवा प्रिंसिपल के बजाय संग्रहण खाता कुंजियों का उपयोग करके खाता।

Azure सेवाओं का उपयोग करने वाले स्वचालित उपकरणों में हमेशा प्रतिबंधित अनुमतियां होनी चाहिए. एक पूरी तरह से विशेषाधिकार प्राप्त उपयोगकर्ता के रूप में एप्लिकेशन पर हस्ताक्षर करने के बजाय, Azure सर्विस प्रिंसिपल्स को प्रदान करता है. आप सुरक्षित रूप से सेवा प्रधानाचार्यों का उपयोग कर सकते हैं [एक सामान्य डेटा मॉडल फ़ोल्डर को डेटा स्रोत . के रूप में जोड़ें या संपादित करें](connect-common-data-model.md) या[परिवेश बनाना या अद्यतन करना।](create-environment.md)

> [!IMPORTANT]
>
> - डेटा लेक स्टोरेज खाता जो सर्विस प्रिंसिपल का उपयोग करेगा वह Gen2 होना चाहिए और उसके पास होना चाहिए [पदानुक्रमित नाम स्थान सक्षम है।](/azure/storage/blobs/data-lake-storage-namespace) Azure Data Lake Gen1 संग्रहण खाते समर्थित नहीं हैं।
> - सेवा प्रिंसिपल बनाने के लिए आपको अपने Azure टैनेंट के लिए व्यवस्थापक अनुमतियों की आवश्यकता है।

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights के लिए Azure सेवा प्रमुख बनाएँ

Customer Insights के लिए एक नया सेवा प्रिंसिपल बनाने से पहले, जांचें कि क्या यह आपके संगठन में पहले से मौजूद है।

### <a name="look-for-an-existing-service-principal"></a>एक मौजूदा सेवा प्रिंसिपल की तलाश करें

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं और अपने संगठन में हस्ताक्षर करें.

2. **Azure सेवाएं** से **Azure Active Directory** चुनें.

3. नीचे **प्रबंधित करना**, चुनते हैं **माइक्रोसॉफ्ट एप्लीकेशन**.

4. के लिए फ़िल्टर जोड़ें **आवेदन आईडी से शुरू होता है**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` या नाम खोजें`Dynamics 365 AI for Customer Insights`.

5. यदि आपको मैचिंग रिकॉर्ड मिलता है, तो इसका मतलब है कि सेवा प्रमुख पहले से मौजूद है.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="स्क्रीनशॉट एक मौजूदा सेवा प्रमुख दिखा रहा है.":::

6. यदि कोई परिणाम नहीं लौटाया जाता है, तो आप कर सकते हैं [एक नया सेवा प्रिंसिपल बनाएं](#create-a-new-service-principal). ज्यादातर मामलों में, यह पहले से मौजूद है और आपको केवल सर्विस प्रिंसिपल को स्टोरेज अकाउंट तक पहुंचने के लिए अनुमति देने की आवश्यकता है।

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>स्टोरेज खाते तक पहुंचने के लिए सर्विस प्रिंसिपल को अनुमति प्रदान करें

आप Customer Insights में जिस संग्रहण खाते का उपयोग करना चाहते हैं, उसके लिए सेवा प्रिंसिपल को अनुमतियाँ देने के लिए Azure पोर्टल पर जाएँ। निम्न भूमिकाओं में से एक को संग्रहण खाते या कंटेनर को असाइन किया जाना चाहिए:

|क्रेडेंशियल|आवश्यकताएँ|
|----------|------------|
|वर्तमान में लॉग इन उपयोगकर्ता|**भूमिका** : संग्रहण ब्लॉब डेटा रीडर, संग्रहण ब्लॉब सहयोगी, या संग्रहण ब्लॉब स्वामी।<br>**स्तर** : भंडारण खाते या कंटेनर पर अनुमतियां दी जा सकती हैं।</br>|
|Customer Insights Service प्रिंसिपल -<br>का उपयोग करते हुए Azure Data Lake Storage एक डेटा स्रोत . के रूप में</br>|विकल्प 1<ul><li>**भूमिका** : संग्रहण ब्लॉब डेटा रीडर, संग्रहण ब्लॉब डेटा सहयोगी, या संग्रहण ब्लॉब डेटा स्वामी.</li><li>**स्तर** : भंडारण खाते पर अनुमति दी जानी चाहिए।</li></ul>विकल्प 2 *(भंडारण खाते में सेवा प्रधान पहुंच साझा किए बिना)*<ul><li>**भूमिका 1** : संग्रहण ब्लॉब डेटा रीडर, संग्रहण ब्लॉब डेटा सहयोगी, या संग्रहण ब्लॉब डेटा स्वामी.</li><li>**स्तर** : कंटेनर पर अनुमति दी जानी चाहिए।</li><li>**भूमिका 2** : संग्रहण ब्लॉब डेटा प्रतिनिधि।</li><li>**स्तर** : भंडारण खाते पर अनुमति दी जानी चाहिए।</li></ul>|
|Customer Insights Service प्रिंसिपल - <br>का उपयोग करते हुए Azure Data Lake Storage आउटपुट या गंतव्य के रूप में</br>|विकल्प 1<ul><li>**भूमिका** : स्टोरेज ब्लॉब डेटा सहयोगी या स्टोरेज ब्लॉब ओनर।</li><li>**स्तर** : भंडारण खाते पर अनुमति दी जानी चाहिए।</li></ul>विकल्प 2 *(भंडारण खाते में सेवा प्रधान पहुंच साझा किए बिना)*<ul><li>**भूमिका** : स्टोरेज ब्लॉब डेटा सहयोगी या स्टोरेज ब्लॉब ओनर।</li><li>**स्तर** : कंटेनर पर अनुमति दी जानी चाहिए।</li><li>**भूमिका 2** : भंडारण ब्लॉब प्रतिनिधि।</li><li>**स्तर** : भंडारण खाते पर अनुमति दी जानी चाहिए।</li></ul>|

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं और अपने संगठन में हस्ताक्षर करें.

1. वह संग्रहण खाता खोलें, जिस तक आप Customer Insights के सेवा प्रिंसिपल की पहुंच चाहते हैं।

1. बाएँ फलक पर, **पहुँच नियंत्रण (IAM)** चुनें और फिर **जोड़ें** > **भूमिका असाइनमेंट जोड़ें** चुनें.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="भूमिका असाइनमेंट जोड़ते समय Azure पोर्टल दिखाने वाला स्क्रीनशॉट.":::

1. **भूमिका असाइनमेंट जोड़ें** फलक पर, निम्न गुण सेट करें:
   - भूमिका: स्टोरेज ब्लॉब डेटा रीडर, स्टोरेज ब्लॉब सहयोगी, या ऊपर सूचीबद्ध क्रेडेंशियल के आधार पर स्टोरेज ब्लॉब स्वामी।
   - एक्सेस असाइन करें: **उपयोगकर्ता, समूह या सर्विस प्रिंसिपल** को
   - सदस्यों का चयन करें: **Customer Insights के लिए Dynamics 365 AI** (द [सेवा प्रधान](#create-a-new-service-principal) आपने इस प्रक्रिया में पहले देखा था)

1. चुनना**समीक्षा + असाइन करें**.

बदलावों के प्रचार-प्रसार में 15 मिनट तक का समय लग सकता है.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Customer Insights के संग्रहण खाता अनुलग्नक में Azure संसाधन ID या Azure सदस्यता विवरण दर्ज करें

आप Customer Insights में Data Lake Storage खाते को इसमें संलग्न कर सकते हैं [आउटपुट डेटा स्टोर करें](manage-environments.md) या[इसे डेटा स्रोत . के रूप में उपयोग करें](connect-dataverse-managed-lake.md). यह विकल्प आपको संसाधन-आधारित या सदस्यता-आधारित दृष्टिकोण के बीच चयन करने देता है. आपके द्वारा चुने गए दृष्टिकोण के आधार पर, निम्न अनुभागों में से किसी एक में प्रक्रिया का पालन करें.

### <a name="resource-based-storage-account-connection"></a>संसाधन-आधारित स्टोरेज खाता कनेक्शन

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं, अपनी सदस्यता, पर साइन इन करें और स्टोरेज खाता खोलें.

1. बाएँ फलक पर जाएँ **समायोजन** > **अंतिमबिंदुओं**.

1. स्टोरेज खाता के संसाधन ID मान को कॉपी करें.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="स्टोरेज खाता के संसाधन ID को कॉपी करें.":::

1. Customer Insights में, संग्रहण खाता कनेक्शन स्क्रीन पर प्रदर्शित संसाधन फ़ील्ड में संसाधन ID डालें।

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="स्टोरेज खाता के संसाधन ID सूचना को दर्ज करें.":::   

1. संग्रहण खाता संलग्न करने के लिए Customer Insights में शेष चरणों के साथ जारी रखें।

### <a name="subscription-based-storage-account-connection"></a>सदस्यता आधारित स्टोरेज खाता कनेक्शन

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं, अपनी सदस्यता, पर साइन इन करें और स्टोरेज खाता खोलें.

1. बाएँ फलक पर, **सेटिंग्स** > **गुण** पर जाएँ.

1. की समीक्षा करें **अंशदान**, **ाधन समूह**, और यह **नाम** यह सुनिश्चित करने के लिए कि आपने Customer Insights में सही मानों का चयन किया है।

1. Customer Insights में, संग्रहण खाता संलग्न करते समय संबंधित फ़ील्ड के लिए मान चुनें।

1. संग्रहण खाता संलग्न करने के लिए Customer Insights में शेष चरणों के साथ जारी रखें।

### <a name="create-a-new-service-principal"></a>नया सर्विस प्रिंसिपल बनाएँ

1. ग्राफ़ के लिए Azure Active Directory PowerShell का नवीनतम संस्करण इंस्टॉल करें. अधिक जानकारी के लिए, [Azure Active Directory PowerShell for Graph इंस्टॉल करें](/powershell/azure/active-directory/install-adv2) पर जाएँ.

   1. अपने पीसी पर, अपने कीबोर्ड पर विंडोज की दबाएं और खोजें **विंडोज पावरशेल** और चुनें **व्यवस्थापक के रूप में चलाओ**.

   1. खुले PowerShell विंडो में, `Install-Module AzureAD` दर्ज करें.

2. Azure AD PowerShell मॉड्यूल के साथ Customer Insights के लिए सेवा प्रमुख बनाएँ.

   1. PowerShell विंडो में, `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`दर्ज करें. बदलने के *[आपकी निर्देशिका आईडी]* अपनी Azure सदस्यता की वास्तविक निर्देशिका आईडी के साथ जहाँ आप सेवा प्रिंसिपल बनाना चाहते हैं। परिवेश नाम पैरामीटर, `AzureEnvironmentName`, वैकल्पिक है.
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`दर्ज करें. यह आदेश चयनित Azure सदस्यता पर Customer Insights के लिए सेवा प्रिंसिपल बनाता है।

[!INCLUDE [footer-include](includes/footer-banner.md)]
