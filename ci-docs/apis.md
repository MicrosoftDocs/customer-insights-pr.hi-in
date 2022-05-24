---
title: API के साथ काम करें
description: API का उपयोग करें और सीमाओं को समझें.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: a460ec87ec85f0614f944d352588d4ca899f8120
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755452"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API के साथ काम करें

Dynamics 365 Customer Insights, Customer Insights में आपके डेटा के आधार पर आपके स्वयं के अनुप्रयोग बनाने के लिए API प्रदान करता है.

> [!IMPORTANT]
> इन API के विवरण, [Customer Insights API संदर्भ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) पर सूचीबद्ध हैं। उनमें परिचालनों, मापदंडों और प्रतिक्रियाओं के बारे में अतिरिक्त जानकारी शामिल हैं.

यह आलेख वर्णन करता है कि Customer Insights API तक कैसे पहुँचें, Azure ऐप पंजीकरण कैसे बनाएँ, और क्लाइंट लाइब्रेरी के साथ आरंभ करें।

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API आज़माना शुरू करें

1. Customer Insights से [साइन-इन](https://home.ci.ai.dynamics.com) करें. यदि आपके पास अभी तक कोई सदस्यता नहीं है, तो [Customer Insights के परीक्षण के लिए साइन अप करें](https://aka.ms/tryci).

1. अपने Customer Insights परिवेश में API को सक्षम करने के लिए, **व्यवस्थापक** > **अनुमतियाँ** पर जाएं. आपको ऐसा करने के लिए व्यवस्थापक अनुमतियाँ चाहिए होगी.

1. **API** टैब पर जाएं और **सक्षम करें** बटन चुनें.    
 
   API को सक्षम करना आपके उदाहरण के लिए प्राथमिक और द्वितीयक सदस्यता कुंजी बनाता है, जिनको API अनुरोधों में उपयोग किया जाता है. आप **व्यवस्थापक** > **अनुमतियाँ** > **API** में **प्राइमरी रीजेनरेट करें** या **सेकेंडरी रीजेनरेट करें** का चयन करके कुंजियों को फिर से हासिल कर सकते हैं.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. **API आजमाएं** के लिए [हमारे API एक्सप्लोर करें](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) चुनें.

1. एक API परिचालन चुनें और **इसे आज़माएं** चुनें.

1. बगल के फलक में, मान को **अंतर्निहित** करने के लिए **अधिकृत करें** ड्रॉपडाउन मेनू में सेट करें. `Authorization` हेडर एक बियरर टोकन के साथ जुड़ जाता है। आपकी सदस्यता कुंजी स्वचालित रूप से पाप्यूलेट हो जाएगी.
  
1. वैकल्पिक रूप से, सभी आवश्यक क्वेरी मापदंड जोड़ें.

1. साइड फलक के नीचे स्क्रॉल करें और **भेजें** चुनें.

जल्द ही HTTP प्रतिक्रिया नीचे दिखाई देगी.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure पोर्टल में एक नया अनुप्रयोग पंजीकरण बनाएं

ये चरण आपको सौंपी गईं अनुमतियों का उपयोग करके Azure अनुप्रयोग में Customer Insights API का उपयोग शुरू करने में मदद करते हैं. पहले [अनुभाग आरंभ करना](#get-started-trying-the-customer-insights-apis) को पूरा करना सुनिश्चित करें.

1. उस खाते के साथ [Azure पोर्टल](https://portal.azure.com) में साइन इन करें जो Customer Insights डेटा तक पहुंच सकता है.

1. बाईं ओर, **अनुप्रयोग पंजीकरण** चुनें.

1. **नया पंजीकरण** चुनें, एक अनुप्रयोग का नाम दें और खाता प्रकार चुनें.
 
   वैकल्पिक रूप से, एक रीडायरेक्ट URL जोड़ें. http://localhost आपके स्थानीय कंप्यूटर पर अनुप्रयोग बनाने के लिए पर्याप्त है.

1. अपने नए अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. **एक अनुमति जोड़ें** चुनें और साइड फलक में **Customer Insights** का चयन करें.

1. **अनुमति प्रकार** के लिये, **सौंपी गई अनुमतियाँ** चुनें और फिर **उपयोगकर्ता_प्रतिरूपण** अनुमति चुनें.

1. **अनुमतियाँ जोड़ें** चयन करें. यदि आपको उपयोगकर्ता द्वारा साइन इन किए बिना API तक पहुंचने की आवश्यकता है, तो [सर्वर-से-सर्वर अनुप्रयोग अनुमतियाँ](#server-to-server-application-permissions) अनुभाग की समीक्षा करें.

1. अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.

आप API में अपने अनुरोध के साथ बीयरर टोकन प्राप्त करने के लिए Microsoft Authentication Library (MSAL) के साथ इस अनुप्रयोग पंजीकरण के लिए अनुप्रयोग/क्लाइंट ID का उपयोग कर सकते हैं.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

MSAL के बारे में अधिक जानकारी के लिए, [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) देखें.

Azure में ऐप पंजीकरण के बारे में अधिक जानकारी के लिए, [एक अनुप्रयोग पंजीकृत करें](/graph/auth-register-app-v2) देखें.

हमारे क्लाइंट लाइब्रेरी में API का उपयोग करने के बारे में जानकारी के लिए, [Customer Insights क्लाइंट लाइब्रेरी](#customer-insights-client-libraries) देखें.

### <a name="server-to-server-application-permissions"></a>सर्वर-से-सर्वर अनुप्रयोग अनुमतियाँ

[अनुप्रयोग पंजीकरण अनुभाग](#create-a-new-app-registration-in-the-azure-portal) यह बताता है कि ऐसे अनुप्रयोग को कैसे पंजीकृत करना है जो प्रमाणीकरण के लिए उपयोगकर्ता को साइन इन करना आवश्यक करता है. जानें कि ऐसा ऐप पंजीकरण कैसे बनाया जाता है जिसमें उपयोगकर्ता सहभागिता की आवश्यकता नहीं होती है और इसे सर्वर पर चलाया जा सकता है।

1. Azure पोर्टल में अपने अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.

1. **अनुमति जोड़ें** चुनें. 

1. **मेरे संगठन द्वारा उपयोग किए जाने वाले API** टैब चुनें और सूची से **Customer Insights के  लिए Dynamics 365 AI** चुनें. 

1. **अनुमति प्रकार** के लिये, **अनुप्रयोग अनुमतियाँ** चुनें और फिर **CustomerInsights.Api.All** अनुमति चुनें.

1. **अनुमतियाँ जोड़ें** चयन करें.

1. अपने अनुप्रयोग पंजीकरण के लिए **API अनुमतियाँ** पर वापस जाएं.

1. अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. पूरा करने के लिए, हमें Customer Insights में अनुप्रयोग पंजीकरण का नाम एक उपयोगकर्ता के रूप में जोड़ना होगा.  
   
   Customer Insights खोलें, **व्यवस्थापक** > **अनुमतियाँ** पर जाएं और **उपयोगकर्ता जोड़ें** चुनें.

1. अपने अनुप्रयोग पंजीकरण के नाम को खोजें, इसे खोज परिणामों से चुनें, और **सहेजें** चुनें.

## <a name="sample-queries"></a>नमूना प्रश्न

हमने एपीआई के साथ काम करने के लिए ओडाटा नमूना प्रश्नों की एक छोटी सूची संकलित की है: [ओडाटा क्वेरी उदाहरण।](odata-examples.md)

## <a name="customer-insights-client-libraries"></a>Customer Insights क्‍लाइंट लाइब्रेरी

यह अनुभाग आपको Customer Insights API के लिए उपलब्ध क्लाइंट लाइब्रेरी इस्तेमाल करने में मदद करता है. सभी लाइब्रेरी स्रोत कोड और नमूना एप्लिकेशन [Customer Insights GitHub पेज](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) पर देखे जा सकते हैं. 

### <a name="c-nuget"></a>C# NuGet

NuGet.org से C# क्लाइंट लाइब्रेरी का उपयोग शुरू करने का तरीका जानें. NuGet पैकेज के बारे में अधिक जानकारी के लिए, [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) देखें. फिलहाल, यह पैकेज netstandard2.0 और netcoreapp2.0 फ्रेमवर्क को लक्षित करता है.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# क्लाइंट लाइब्रेरी को C# प्रोजेक्ट में जोड़ें

1. Visual Studio में, अपने प्रोजेक्ट के लिए **NuGet पैकेज प्रबंधक** खोलें.

1. **Microsoft.Dynamics.CustomerInsights.Api** को खोजें.

1. प्रोजेक्ट में पैकेज जोड़ने के लिए **इंस्टॉल करें** का चयन करें.
 
   वैकल्पिक रूप से, इस कमांड को **NuGet पैकेज प्रबंधक कंसोल में चलाएं**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>C# क्लाइंट लाइब्रेरी का उपयोग करें

1. अपने मौजूदा [Azure अनुप्रयोग पंजीकरण](#create-a-new-app-registration-in-the-azure-portal) का उपयोग करके `AccessToken` पाने के लिए [Microsoft प्रमाणीकरण लाइब्रेरी(MSAL)](/azure/active-directory/develop/msal-overview) का उपयोग करें.

1. टोकन को सफलतापूर्वक प्रमाणित करने और प्राप्त करने के बाद, एक नया निर्माण करें या किसी मौजूदा का उपयोग करें`HttpClient` उसके साथ **DefaultRequestHeaders "प्राधिकरण"** करने के लिए सेट **वाहक "पहुँच टोकन"** और **Ocp-Apim-सदस्यता-कुंजी** पर सेट करें [**सदस्यता कुंजी** आपके Customer Insights परिवेश से](#get-started-trying-the-customer-insights-apis).   
 
   उपयुक्त होने पर **प्राधिकरण** हेडर को रीसेट करें. उदाहरण के लिए, जब टोकन समाप्त हो गया है.

1. इस `HttpClient` को `CustomerInsights` क्लाइंट के निर्माण में पास करें.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. "एक्सटेंशन विधियों" के लिए क्लाइंट के साथ कॉल करें"—उदाहरण के लिए, `GetAllInstancesAsync`. यदि अंतर्निहित `Microsoft.Rest.HttpOperationResponse` को एक्सेस करने को प्राथमिकता दी जाती है, तो "http संदेश विधियों" का उपयोग करें"—उदाहरण के लिए, `GetAllInstancesWithHttpMessagesAsync`।

1. प्रतिक्रिया शायद `object` प्रकार की होगी, क्योंकि विधि कई प्रकारों को लौटा सकती है (उदाहरण के लिए, `IList<InstanceInfo>` and ``ApiErrorResult`). रिटर्न प्रकार की जांच करने के लिए, आप निर्दिष्ट प्रतिक्रिया प्रकारों में वस्तुओं का उपयोग करते हैं [एपीआई विवरण पृष्ठ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) उस ऑपरेशन के लिए।    
   
   यदि अनुरोध पर अधिक जानकारी चाहिए, तो अधूरी प्रतिक्रिया ऑब्जेक्ट तक पहुंचने के लिए **http संदेश विधियों** का उपयोग करें.

### <a name="nodejs-package"></a>NodeJS पैकेज

NPM के जरिए उपलब्ध NodeJS क्लाइंट लाइब्रेरी का उपयोग करें: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python पैकेज

PyPi के जरिए Python क्लाइंट लाइब्रेरी को उपयोग करें: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
