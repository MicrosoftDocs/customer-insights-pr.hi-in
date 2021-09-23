---
title: सेवा प्रमुख का उपयोग करके किसी Azure Data Lake Storage खाते से कनेक्ट करें
description: अपने खुद के data lake से कनेक्ट करने के लिए Azure सेवा प्रमुख का उपयोग करें.
ms.date: 09/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b96c7f580b4067e059e00a9cdb4e872e9acd4a5c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483527"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure सेवा प्रमुख का उपयोग करके किसी Azure Data Lake Storage खाते से कनेक्ट करें

Azure सेवाओं का उपयोग करने वाले स्वचालित उपकरणों में हमेशा प्रतिबंधित अनुमतियां होनी चाहिए. एक पूरी तरह से विशेषाधिकार प्राप्त उपयोगकर्ता के रूप में एप्लिकेशन पर हस्ताक्षर करने के बजाय, Azure सर्विस प्रिंसिपल्स को प्रदान करता है. संग्रहण खाता कुंजियों के बजाय किसी Azure सेवा प्रमुख का उपयोग करके Dynamics 365 Customer Insights को Azure Data Lake Storage खाते से कनेक्ट करने का तरीका जानने के लिए आगे पढ़ें. 

आप सेवा प्रमुख को सुरक्षित रूप से [डेटा स्रोत के रूप में एक सामान्य डेटा मॉडल फ़ोल्डर जोड़ें या संपादित करें](connect-common-data-model.md), या [परिवेश बनाएँ या अपडेट करें](get-started-paid.md) के लिए उपयोग कर सकते हैं.

> [!IMPORTANT]
> - Data Lake Storage खाता जो सर्विस प्रिंसिपल का उपयोग करेगा, उसमें [पदानुक्रमित नामस्थान सक्षम](/azure/storage/blobs/data-lake-storage-namespace) होना चाहिए.
> - आपको सर्विस प्रिंसिपल बनाने के लिए अपनी Azure सदस्यता के लिए व्यवस्थापक अनुमतियों की आवश्यकता है.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights के लिए Azure सेवा प्रमुख बनाएँ

ऑडिएंस इनसाइट्स या सहभागिता इनसाइट्स के लिए नया सेवा प्रमुख बनाने से पहले, जांचें कि यह आपके संगठन में पहले से मौजूद है या नहीं.

### <a name="look-for-an-existing-service-principal"></a>एक मौजूदा सेवा प्रिंसिपल की तलाश करें

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं और अपने संगठन में हस्ताक्षर करें.

2. **Azure सेवाएं** से **Azure Active Directory** चुनें.

3. **प्रबंधित करें** के अंतर्गत, **एंटरप्राइज़ अनुप्रयोग** चुनें.

4. Microsoft अनुप्रयोग ID खोजें:
   - ऑडियंस इनसाइट: नाम `Dynamics 365 AI for Customer Insights` के साथ `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`
   - सहभागिता इनसाइट्स: नाम `Dynamics 365 AI for Customer Insights engagement insights` के साथ `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd`

5. यदि आपको मैचिंग रिकॉर्ड मिलता है, तो इसका मतलब है कि सेवा प्रमुख पहले से मौजूद है. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="स्क्रीनशॉट एक मौजूदा सेवा प्रमुख दिखा रहा है.":::
   
6. यदि कोई परिणाम वापस नहीं आता है, तो एक नया सर्विस प्रिंसिपल बनाएं.

>[!NOTE]
>Dynamics 365 Customer Insights की पूरी शक्ति का उपयोग करने के लिए, हमारा सुझाव है कि आप दोनों ऐप को सेवा प्रमुख में जोड़ें.

### <a name="create-a-new-service-principal"></a>नया सर्विस प्रिंसिपल बनाएँ

1. ग्राफ़ के लिए Azure Active Directory PowerShell का नवीनतम संस्करण इंस्टॉल करें. अधिक जानकारी के लिए, [Azure Active Directory PowerShell for Graph इंस्टॉल करें](/powershell/azure/active-directory/install-adv2) पर जाएँ.

   1. अपने PC पर, अपने कीबोर्ड पर Windows बटन का चयन करें और **Windows PowerShell** खोजें और **व्यवस्थापक के रूप में चलाएं** चुनें.
   
   1. खुले PowerShell विंडो में, `Install-Module AzureAD` दर्ज करें.

2. Azure AD PowerShell मॉड्यूल के साथ Customer Insights के लिए सेवा प्रमुख बनाएँ.

   1. PowerShell विंडो में, `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`दर्ज करें. *[अपनी टेनेंट ID]* को अपने टेनेंट की वास्तविक ID से बदलें, जहां आप सर्विस प्रिंसिपल बनाना चाहते हैं. परिवेश नाम पैरामीटर, `AzureEnvironmentName`, वैकल्पिक है.
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`दर्ज करें. यह आदेश चयनित टेनेंट पर ऑडियंस इनसाइट्स के लिए सर्विस प्रिंसिपल बनाता है. 

   1. `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`दर्ज करें. यह आदेश चयनित टेनेंट पर Engagement इनसाइट्स के लिए सर्विस प्रिंसिपल बनाता है.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>स्टोरेज खाते तक पहुंचने के लिए सर्विस प्रिंसिपल को अनुमति प्रदान करें

ऑडियंस इनसाइट्स में अपने मनचाहे स्टोरेज खाते का उपयोग करने हेतु सर्विस प्रिंसिपल को अनुमति देने के लिए Azure पोर्टल पर जाएं.

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं और अपने संगठन में हस्ताक्षर करें.

1. वह स्टोरेज खाता खोलें जिसकी आप ऑडियंस इनसाइट्स के लिए सर्विस प्रिंसिपल तक पहुंच चाहते हो.

1. बाएँ फलक पर, **पहुँच नियंत्रण (IAM)** चुनें और फिर **जोड़ें** > **भूमिका असाइनमेंट जोड़ें** चुनें.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="भूमिका असाइनमेंट जोड़ते समय Azure पोर्टल दिखाने वाला स्क्रीनशॉट.":::

1. **भूमिका असाइनमेंट जोड़ें** फलक पर, निम्न गुण सेट करें:
   - भूमिका: **स्टोरेज ब्लॉब डेटा योगदानकर्ता**
   - एक्सेस असाइन करें: **उपयोगकर्ता, समूह या सर्विस प्रिंसिपल** को
   - चुनें: **Dynamics 365 AI for Customer Insights** और **Dynamics 365 AI for Customer Insights सहभागिता इनसाइट्स** (वे दो [सेवा प्रमुख](#create-a-new-service-principal) जिनको आपने पहले इस प्रक्रिया में बनाया था)

1.  **सहेजें** चुनें.

बदलावों के प्रचार-प्रसार में 15 मिनट तक का समय लग सकता है.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>ऑडियंस इनसाइट्स के लिए स्टोरेज खाता संलग्नक में Azure संसाधन ID या Azure सदस्यता विवरण दर्ज करें

आप [स्टोर आउटपुट डेटा](manage-environments.md) या [इसे डेटा स्रोत के रूप में उपयोग करें](connect-common-data-service-lake.md) में ऑडियंस इनसाइट्स में Data Lake Storage खाता संलग्न कर सकते हैं. यह विकल्प आपको संसाधन-आधारित या सदस्यता-आधारित दृष्टिकोण के बीच चयन करने देता है. आपके द्वारा चुने गए दृष्टिकोण के आधार पर, निम्न अनुभागों में से किसी एक में प्रक्रिया का पालन करें.

### <a name="resource-based-storage-account-connection"></a>संसाधन-आधारित स्टोरेज खाता कनेक्शन

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं, अपनी सदस्यता, पर साइन इन करें और स्टोरेज खाता खोलें.

1. बाएँ फलक पर, **सेटिंग्स** > **गुण** पर जाएँ.

1. स्टोरेज खाता के संसाधन ID मान को कॉपी करें.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="स्टोरेज खाता के संसाधन ID को कॉपी करें.":::

1. ऑडियंस इनसाइट्स में, संग्रहण खाता कनेक्शन स्क्रीन पर प्रदर्शित संसाधन फ़ील्ड में संसाधन ID डालें.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="स्टोरेज खाता के संसाधन ID सूचना को दर्ज करें.":::   

1. स्टोरेज खाता को संलग्न करने के लिए ऑडियंस इनसाइट्स में बचे हुए चरण जारी रखें.

### <a name="subscription-based-storage-account-connection"></a>सदस्यता आधारित स्टोरेज खाता कनेक्शन

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं, अपनी सदस्यता, पर साइन इन करें और स्टोरेज खाता खोलें.

1. बाएँ फलक पर, **सेटिंग्स** > **गुण** पर जाएँ.

1. स्टोरेज खाते के **सदस्यता**, **संसाधन समूह**, और **नाम** की समीक्षा करें ताकि यह सुनिश्चित किया जा सके कि आप ऑडियंस इनसाइट्स में सही मानों का चयन करते हैं.

1. ऑडिएंस इनसाइट्स में, संग्रहण खाता अटैच करते समय संबंधित फ़ील्ड के लिए मान चुनें.

1. स्टोरेज खाता को संलग्न करने के लिए ऑडियंस इनसाइट्स में बचे हुए चरण जारी रखें.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
