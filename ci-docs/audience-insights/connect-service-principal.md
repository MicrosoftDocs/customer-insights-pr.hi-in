---
title: एक सर्विस प्रिंसिपल के साथ एक Azure Data Lake Storage Gen2 खाते से कनेक्ट करें
description: ऑडिएंस इनसाइट्स से जुड़ते समय अपने खुद के Data Lake से कनेक्ट करने के लिए ऑडिएंस इनसाइट्स के लिए एक Azure service principal का उपयोग करें.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267724"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>ऑडियंस इनसाइट्स के लिए एक Azure service principal के साथ एक Azure Data Lake Storage Gen2 खाते से कनेक्ट करें

Azure सेवाओं का उपयोग करने वाले स्वचालित उपकरणों में हमेशा प्रतिबंधित अनुमतियां होनी चाहिए. एक पूरी तरह से विशेषाधिकार प्राप्त उपयोगकर्ता के रूप में एप्लिकेशन पर हस्ताक्षर करने के बजाय, Azure सर्विस प्रिंसिपल्स को प्रदान करता है. स्टोरेज खाते की कुंजी के बजाय एक Azure service principal का उपयोग करके एक Azure Data Lake Storage Gen2 खाते के साथ ऑडियंस इनसाइट्स को जोड़ने के तरीके जानने के लिए, पढ़ें. 

आप सर्विस प्रिंसिपल का उपयोग सुरक्षित रूप से [डेटा स्रोत के रूप में एक सामान्य डेटा मॉडल फ़ोल्डर को जोड़ें या संपादित करें](connect-common-data-model.md) या [एक नया बनाएं या मौजूदा परिवेश को अपडेट करें](manage-environments.md#create-an-environment-in-an-existing-organization) करने के लिए कर सकते हैं.

> [!IMPORTANT]
> - Azure Data Lake Gen2 स्टोरेज खाता, जो सेवा सिद्धांत का उपयोग करने का इरादा रखता है, उसके पास [पदानुक्रमित नाम स्थान (HNS) सक्षम होना चाहिए](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).
> - आपको सर्विस प्रिंसिपल बनाने के लिए अपनी Azure सदस्यता के लिए व्यवस्थापक अनुमतियों की आवश्यकता है.

## <a name="create-azure-service-principal-for-audience-insights"></a>ऑडियंस इनसाइट्स के लिए Azure service principal बनाएं

ऑडियंस इनसाइट्स के लिए एक नया सर्विस प्रिंसिपल बनाने से पहले, यह जांच लें कि क्या यह आपके संगठन में पहले से मौजूद है.

### <a name="look-for-an-existing-service-principal"></a>एक मौजूदा सेवा प्रिंसिपल की तलाश करें

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं और अपने संगठन में हस्ताक्षर करें.

2. Azure सेवाओं से **Azure Active Directory** का चयन करें.

3. **प्रबंधित करें** के अंतर्गत, **एंटरप्राइज़ अनुप्रयोग** चुनें.

4. ऑडियंस इनसाइट्स की पहली पार्टी एप्लिकेशन ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` या `Dynamics 365 AI for Customer Insights`' के लिए नाम को खोजें.

5. अगर आपको कोई मिलता-जुलता रिकॉर्ड मिलता है, तो इसका मतलब है कि ऑडियंस इनसाइट्स के लिए सर्विस प्रिंसिपल मौजूद है. आपको इसे फिर से बनाने की आवश्यकता नहीं है.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="मौजूदा सर्विस प्रिंसिपल दिखाता स्क्रीनशॉट.":::
   
6. यदि कोई परिणाम वापस नहीं आता है, तो एक नया सर्विस प्रिंसिपल बनाएं.

### <a name="create-a-new-service-principal"></a>नया सर्विस प्रिंसिपल बनाएँ

1. **ग्राफ के लिए Azure Active Directory PowerShell** का नवीनतम संस्करण इंस्टॉल करें. अधिक जानकारी के लिए, देखें [ग्राफ के लिए Azure Active Directory PowerShell इंस्टॉल करें](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - अपने पीसी पर, अपने कीबोर्ड पर विंडोज कुंजी का चयन करें और **विंडोज PowerShell** और **प्रशासक के रूप में चलाएं** के लिए खोज करें.
   
   - खुले PowerShell विंडो में, `Install-Module AzureAD` दर्ज करें.

2. Azure AD PowerShell मॉड्यूल के साथ ऑडियंस इनसाइट्स के लिए सर्विस प्रिंसिपल बनाएं.
   - PowerShell विंडो में, `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`दर्ज करें. "अपनी टेनेंट ID" को अपने टेनेंट की वास्तविक ID से बदलें जहां आप सर्विस प्रिंसिपल बनाना चाहते हैं. परिवेश नाम पैरामीटर `AzureEnvironmentName` वैकल्पिक है.
  
   - `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`दर्ज करें. यह आदेश चयनित टेनेंट पर ऑडियंस इनसाइट्स के लिए सर्विस प्रिंसिपल बनाता है.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>स्टोरेज खाते तक पहुंचने के लिए सर्विस प्रिंसिपल को अनुमति प्रदान करें

ऑडियंस इनसाइट्स में अपने मनचाहे स्टोरेज खाते का उपयोग करने हेतु सर्विस प्रिंसिपल को अनुमति देने के लिए Azure पोर्टल पर जाएं.

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं और अपने संगठन में हस्ताक्षर करें.

1. वह स्टोरेज खाता खोलें जिसकी आप ऑडियंस इनसाइट्स के लिए सर्विस प्रिंसिपल तक पहुंच चाहते हो.

1. नेविगेशन फलक से **एक्सेस कंट्रोल (IAM)** चुनें और **जोड़ें** > **भूमिका असाइनमेंट जोड़ें** चुनें.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="भूमिका असाइनमेंट जोड़ते समय Azure पोर्टल दिखाता स्क्रिनशॉट.":::
   
1. **भूमिका असाइनमेंट को जोड़ें** फलक में, निम्नलिखित गुणों को सेट करें:
   - भूमिका: *स्टोरेज ब्लॉब डेटा योगदानकर्ता*
   - एक्सेस असाइन करें: *उपयोगकर्ता, समूह या सर्विस प्रिंसिपल* को
   - चुनें: *Customer Insights के लिए Dynamics 365 AI* ( [आपके द्वारा बनाए गए सर्विस प्रिंसिपल](#create-a-new-service-principal))

1.  **सहेजें** चुनें.

बदलावों के प्रचार-प्रसार में 15 मिनट तक का समय लग सकता है.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>ऑडियंस इनसाइट्स के लिए स्टोरेज खाता संलग्नक में Azure संसाधन ID या Azure सदस्यता विवरण दर्ज करें.

ऑडियंस इनसाइट्स में एक Azure Data Lake स्टोरेज खाता संलग्न करें [स्टोर आउटपुट डेटा](manage-environments.md) या [इसे डेटा स्रोत के रूप में उपयोग करें](connect-common-data-service-lake.md). Azure Data Lake विकल्प चुनने से आप संसाधन-आधारित या सदस्यता-आधारित दृष्टिकोण के बीच चयन कर सकते हैं.

चयनित दृष्टिकोण के बारे में आवश्यक जानकारी प्रदान करने के लिए नीचे दिए गए चरणों का पालन करें.

### <a name="resource-based-storage-account-connection"></a>संसाधन-आधारित स्टोरेज खाता कनेक्शन

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं, अपनी सदस्यता पर साइन इन करें और स्टोरेज खाता खोलें.

1. नेविगेशन फलक पर **सेटिंग्स** > **गुण** पर जाएं.

1. स्टोरेज खाता के संसाधन ID मान को कॉपी करें.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="स्टोरेज खाता के संसाधन ID को कॉपी करें.":::

1. ऑडियंस इनसाइट्स में, स्टोरेज खाता कनेक्शन स्क्रीन में प्रदर्शित संसाधन फ़ील्ड में संसाधन ID डालें.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="स्टोरेज खाता के संसाधन ID सूचना को दर्ज करें.":::   
   
1. स्टोरेज खाता को संलग्न करने के लिए ऑडियंस इनसाइट्स में बचे हुए चरण जारी रखें.

### <a name="subscription-based-storage-account-connection"></a>सदस्यता आधारित स्टोरेज खाता कनेक्शन

1. [Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं, अपनी सदस्यता पर साइन इन करें और स्टोरेज खाता खोलें.

1. नेविगेशन फलक पर **सेटिंग्स** > **गुण** पर जाएं.

1. स्टोरेज खाते के **सदस्यता**, **संसाधन समूह**, और **नाम** की समीक्षा करें ताकि यह सुनिश्चित किया जा सके कि आप ऑडियंस इनसाइट्स में सही मानों का चयन करते हैं.

1. ऑडियंस इनसाइट्स में, स्टोरेज खाता संलग्न करते समय मानों या संबंधित फ़ील्ड के लिए चुनाव करें.
   
1. स्टोरेज खाता को संलग्न करने के लिए ऑडियंस इनसाइट्स में बचे हुए चरण जारी रखें.


[!INCLUDE[footer-include](../includes/footer-banner.md)]