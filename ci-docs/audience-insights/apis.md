---
title: API के साथ काम करें
description: API का उपयोग करें और सीमाओं को समझें.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689132"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API के साथ काम करें

Dynamics 365 Customer Insights आपको Customer Insights में डेटा के आधार पर आपके स्वयं के अनुप्रयोग बनाने के लिए API देता है.

> [!IMPORTANT]
> इन API के विवरण, [Customer Insights API संदर्भ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) पर सूचीबद्ध हैं. उनमें परिचालनों, मापदंडों और प्रतिक्रियाओं के बारे में अतिरिक्त जानकारी शामिल हैं.

यह आलेख आपको Customer Insights API तक पहुंचने के लिए मार्गदर्शन करता है, Azure अनुप्रयोग पंजीकरण बनाता है, और उपलब्ध क्लाइंट लाइब्रेरी के साथ शुरू करने में आपकी सहायता करता है.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API आज़माना शुरू करें

1. Customer Insights से [साइन-इन](https://home.ci.ai.dynamics.com) करें. यदि आपके पास अभी तक कोई सदस्यता नहीं है, तो [Customer Insights के परीक्षण के लिए साइन अप करें](https://aka.ms/tryci).

1. अपने Customer Insights परिवेश में API को सक्षम करने के लिए, **व्यवस्थापक** >  **अनुमतियाँ** पर जाएं. आपको ऐसा करने के लिए व्यवस्थापक अनुमतियाँ चाहिए होगी.

1. **API** टैब पर जाएं और **सक्षम करें** बटन चुनें.    
   API को सक्षम करना आपके उदाहरण के लिए प्राथमिक और द्वितीयक सदस्यता कुंजी बनाता है, जिनको API अनुरोधों में उपयोग किया जाता है. आप **व्यवस्थापक** > **अनुमतियाँ** > **API** में **प्राइमरी रीजेनरेट करें** या **सेकेंडरी रीजेनरेट करें** का चयन करके कुंजियों को फिर से हासिल कर सकते हैं.

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights APIs सक्षम करें":::

1. API आज़माने के लिए **हमारे API की छानबीन करें** को चुनें.

1. एक API परिचालन चुनें और **इसे आज़माएं** चुनें.

1. साइड के फलक में, **निहित** करने के लिए मान को **प्राधिकरण** ड्रॉप-डाउन मेनू में सेट करें. `Authorization`प्राधिकरण` हेडर एक बीयरर टोकन के साथ जुड़ जाता है. आपकी सदस्यता कुंजी स्वचालित रूप से पाप्यूलेट हो जाएगी.
  
1. वैकल्पिक रूप से, सभी आवश्यक क्वेरी मापदंड जोड़ें.

1. साइड फलक के नीचे स्क्रॉल करें और **भेजें** चुनें.

जल्द ही HTTP प्रतिक्रिया नीचे दिखाई देगी.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure पोर्टल में एक नया अनुप्रयोग पंजीकरण बनाएं

ये चरण आपको Customer Insights API का उपयोग करके Azure अनुप्रयोग में प्रत्यायोजित अनुमतियों का उपयोग करना शुरू करने में मदद करते हैं. सुनिश्चित करें कि [शुरू करें अनुभाग](#get-started-trying-the-customer-insights-apis) पहले ही पूरा कर लिया जाता है.

1. उस खाते के साथ [Azure पोर्टल](https://portal.azure.com) में साइन इन करें जो Customer Insights डेटा तक पहुंच सकता है.

1. बाईं ओर, **अनुप्रयोग पंजीकरण** चुनें.

1. **नया पंजीकरण** चुनें एक एप्लिकेशन का नाम दें और खाता प्रकार चुनें.
   वैकल्पिक रूप से, एक रीडायरेक्ट URL जोड़ें. http://localhost आपके स्थानीय कंप्यूटर पर अनुप्रयोग बनाने के लिए पर्याप्त है.

1. अपने नए अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.

1. **एक अनुमति जोड़ें** चुनें और साइड फलक में **Customer Insights** का चयन करें.

1. **अनुमति प्रकार** के लिए, **मान्य अनुमतियाँ** का चयन करें और **user_impersonation** अनुमति का चयन करें.

1. **अनुमतियाँ जोड़ें** चयन करें. यदि आपको उपयोगकर्ता द्वारा साइन इन किए बिना API तक पहुंचने की आवश्यकता है, तो [सर्वर-से-सर्वर अनुप्रयोग अनुमतियाँ](#server-to-server-application-permissions) अनुभाग की समीक्षा करें.

1. अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.

आप API में अपने अनुरोध के साथ बीयरर टोकन प्राप्त करने के लिए Microsoft Authentication Library (MSAL) के साथ इस अनुप्रयोग पंजीकरण के लिए अनुप्रयोग/क्लाइंट ID का उपयोग कर सकते हैं.

MSAL के बारे में अधिक जानकारी के लिए, [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) देखें.

Azure में अनुप्रयोग पंजीकरण के बारे में अधिक जानकारी के लिए, [नया Azure पोर्टल अनुप्रयोग पंजीकरण अनुभव](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide) देखें.

API की हमारी क्लाइंट लाइब्रेरी का उपयोग करने के बारे में जानकारी के लिए, [Customer Insights क्लाइंट लाइब्रेरी](#customer-insights-client-libraries) देखें.

### <a name="server-to-server-application-permissions"></a>सर्वर-से-सर्वर अनुप्रयोग अनुमतियाँ

[अनुप्रयोग पंजीकरण अनुभाग](#create-a-new-app-registration-in-the-azure-portal) यह बताता है कि ऐसे अनुप्रयोग को कैसे पंजीकृत करना है जो प्रमाणीकरण के लिए उपयोगकर्ता को साइन इन करना आवश्यक करता है. ऐसा अनुप्रयोग पंजीकरण बनाना सीखें, जिसके लिए उपयोगकर्ता का इंटरेक्शन आवश्यक नहीं है और इसे सर्वर पर चलाया जा सकता है.

1. Azure पोर्टल में अपने अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.

1. **एक अनुमति जोड़ें** चुनें और साइड फलक में **Customer Insights** का चयन करें.

1. **अनुमति प्रकार** के लिए, **एप्लिकेशन अनुमतियाँ** का चयन करें और **CustomerInsights.Api.All** अनुमतियों को चुनें.

1. **अनुमतियाँ जोड़ें** चयन करें.

1. इस अनुप्रयोग की अनुमति पर व्यवस्थापक की सहमति देने के लिए, आपको एक सर्विस प्रिंसिपल को जोड़ना होगा.

   1. Azure Active Directory (AD) PowerShell मॉड्यूल स्थापित करें: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. अपने AD खाते से कनेक्ट करें: `Connect-AzureAD -TenantId <your tenant id>`. आप अपनी टेनेंट ID **अवलोकन** > **Azure Active Directory** पर पा सकते हैं.
   1. Azure AD सर्विस प्रिंसिपल को जोड़ने के लिए निम्नलिखित कमांड चलाएं: ``New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId मापदंड Customer Insights API अनुप्रयोग से संबंधित है.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="सर्विस प्रिंसिपल नमूना":::

1. अपने अनुप्रयोग पंजीकरण के लिए **API अनुमतियाँ** पर वापस जाएं.

1. अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.

1. पूरा करने के लिए, हमें Customer Insights में अनुप्रयोग पंजीकरण का नाम एक उपयोगकर्ता के रूप में जोड़ना होगा.    
   Customer Insights खोलें, **व्यवस्थापक** > **अनुमतियाँ** पर जाएं और **उपयोगकर्ता जोड़ें** चुनें.

1. अपने अनुप्रयोग पंजीकरण के नाम को खोजें, इसे खोज परिणामों से चुनें, और **सहेजें** चुनें.

## <a name="customer-insights-client-libraries"></a>Customer Insights क्‍लाइंट लाइब्रेरी

यह अनुभाग आपको Customer Insights API के लिए उपलब्ध क्लाइंट लाइब्रेरी इस्तेमाल करने में मदद करता है.

### <a name="c-nuget"></a>C# NuGet

NuGet.org से C# क्लाइंट लाइब्रेरी का उपयोग शुरू करने का तरीका जानें. NuGet पैकेज के बारे में अधिक जानकारी के लिए, [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) देखें. फिलहाल, यह पैकेज netstandard2.0 और netcoreapp2.0 फ्रेमवर्क को लक्षित करता है.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# क्लाइंट लाइब्रेरी को C# प्रोजेक्ट में जोड़ें

1. Visual Studio में, अपने प्रोजेक्ट के लिए **NuGet पैकेज प्रबंधक** खोलें.

1. **Microsoft.Dynamics.CustomerInsights.Api** को खोजें.

1. प्रोजेक्ट में पैकेज जोड़ने के लिए **इंस्टॉल करें** का चयन करें.
   वैकल्पिक रूप से, इस कमांड को **NuGet पैकेज प्रबंधक कंसोल में चलाएं**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Visual Studio प्रोजेक्ट में NuGet पैकेज जोड़ें":::

#### <a name="use-the-c-client-library"></a>C# क्लाइंट लाइब्रेरी का उपयोग करें

1. अपने मौजूदा [Azure अनुप्रयोग पंजीकरण](#create-a-new-app-registration-in-the-azure-portal) का उपयोग करके `AccessToken` पाने के लिए [Microsoft प्रमाणीकरण लाइब्रेरी(MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) का उपयोग करें.

1. एक टोकन को सफलतापूर्वक प्रमाणित करने और हासिल करने के बाद, एक नया बनाएं या मौजूदा `HttpClient` के साथ अतिरिक्त **DefaultRequestHeaders "प्राधिकरण"** सेट को **धारक <access token>** और **Ocp-Apim-Subscription-Key** सेट से [अपने Customer Insights परिवेश से **सदस्यता कुंजी**](#get-started-trying-the-customer-insights-apis) को उपयोग करें.    
   उपयुक्त होने पर **प्राधिकरण** हेडर को रीसेट करें. उदाहरण के लिए, जब टोकन समाप्त हो गया है.

1. इस `HttpClient` को `CustomerInsights` क्लाइंट के निर्माण में पास करें.

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient का नमूना":::

1. "एक्सटेंशन विधियों" के लिए क्लाइंट के साथ कॉल करें, उदाहरण के लिए, `GetAllInstancesAsync`. यदि अंतर्निहित `Microsoft.Rest.HttpOperationResponse` को एक्सेस करने को प्राथमिकता दी जाती है, तो "http संदेश विधियों" का उपयोग करें, उदाहरण के लिए `GetAllInstancesWithHttpMessagesAsync`.

1. प्रतिक्रिया शायद `object` प्रकार की होगी, क्योंकि विधि कई प्रकारों को लौटा सकती है (उदाहरण के लिए, `IList<InstanceInfo>` and ``ApiErrorResult`). लौटाने के प्रकार की जांच करने के लिए, आप उस परिचालन के लिए वस्तुओं को सुरक्षित रूप से [API विवरण पृष्ठ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) पर निर्दिष्ट प्रकारों में डाल सकते हैं.    
   यदि अनुरोध पर अधिक जानकारी चाहिए, तो अधूरी प्रतिक्रिया ऑब्जेक्ट तक पहुंचने के लिए **http संदेश विधियों** का उपयोग करें.
