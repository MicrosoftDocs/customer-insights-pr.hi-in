---
title: Customer Insights API के साथ काम करें
description: API का उपयोग करें और सीमाओं को समझें.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387342"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API के साथ काम करें

Dynamics 365 Customer Insights, Customer Insights में आपके डेटा के आधार पर आपके स्वयं के अनुप्रयोग बनाने के लिए API प्रदान करता है.

> [!IMPORTANT]
> इन API के विवरण, [Customer Insights API संदर्भ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) पर सूचीबद्ध हैं। उनमें परिचालनों, मापदंडों और प्रतिक्रियाओं के बारे में अतिरिक्त जानकारी शामिल हैं.

Customer Insights API आज़माएँ, Azure ऐप पंजीकरण बनाएँ, और क्लाइंट लाइब्रेरी के साथ शुरुआत करें।

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API आज़माना शुरू करें

Customer Insights API सक्षम करें और उन्हें आज़माएँ। Customer Insights व्यवस्थापक को Customer Insights के लिए API एक्सेस को सक्षम करना होगा। एक बार एक्सेस सक्षम हो जाने पर, कोई भी उपयोगकर्ता सब्सक्रिप्शन कुंजी के साथ एपीआई का उपयोग कर सकता है।

1. Customer Insights से [साइन-इन](https://home.ci.ai.dynamics.com) करें. यदि आपके पास अभी तक कोई सदस्यता नहीं है, तो [Customer Insights के परीक्षण के लिए साइन अप करें](https://aka.ms/tryci).

1. के लिए जाओ **व्यवस्थापक** > **सुरक्षा** और चुनें **शहद की मक्खी** टैब।

1. यदि पर्यावरण के लिए एपीआई एक्सेस सेट नहीं किया गया है, तो चुनें **सक्षम करना**.

   API को सक्षम करना आपके उदाहरण के लिए प्राथमिक और द्वितीयक सदस्यता कुंजी बनाता है, जिनको API अनुरोधों में उपयोग किया जाता है. कुंजियों को पुन: उत्पन्न करने के लिए, चुनें **प्राथमिक पुन: उत्पन्न करें** या**माध्यमिक पुन: उत्पन्न करें** पर **शहद की मक्खी** टैब।

1. चुनना[**हमारे एपीआई एक्सप्लोर करें**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) एपीआई की कोशिश करने के लिए।

1. एक एपीआई ऑपरेशन खोजें और चुनें और चुनें **इसे अजमाएं**.

   :::image type="content" source="media/try-api.png" alt-text="API का परीक्षण कैसे करें।":::

1. बगल के फलक में, मान को **अंतर्निहित** करने के लिए **अधिकृत करें** ड्रॉपडाउन मेनू में सेट करें. `Authorization` हेडर एक बियरर टोकन के साथ जुड़ जाता है। आपकी सदस्यता कुंजी स्वचालित रूप से पॉप्युलेट हो जाती है।
  
1. वैकल्पिक रूप से, सभी आवश्यक क्वेरी मापदंड जोड़ें.

1. साइड फलक के नीचे स्क्रॉल करें और **भेजें** चुनें.

   HTTP प्रतिक्रिया फलक के नीचे प्रदर्शित होती है।

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure पोर्टल में एक नया अनुप्रयोग पंजीकरण बनाएं

कोई नया बनाएं [ऐप पंजीकरण](/graph/auth-register-app-v2) प्रत्यायोजित अनुमतियों का उपयोग करके Azure एप्लिकेशन में Customer Insights API का उपयोग करने के लिए।

1. को पूर्ण करो[आरंभ करना अनुभाग](#get-started-trying-the-customer-insights-apis).

1. उस खाते के साथ [Azure पोर्टल](https://portal.azure.com) में साइन इन करें जो Customer Insights डेटा तक पहुंच सकता है.

1. खोजें और फिर चुनें **ऐप पंजीकरण**.

1. **नया पंजीकरण** चुनें, एक अनुप्रयोग का नाम दें और खाता प्रकार चुनें.

   वैकल्पिक रूप से, एक रीडायरेक्ट URL जोड़ें. http://localhost आपके स्थानीय कंप्यूटर पर अनुप्रयोग बनाने के लिए पर्याप्त है.

1. **पंजीकरण करें** चुनें.

1. अपने नए अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.

1. चुनना**अनुमति जोड़ें** और चुनें **Customer Insights के लिए Dynamics 365 AI** पार्श्व फलक में।

1. **अनुमति प्रकार** के लिये, **सौंपी गई अनुमतियाँ** चुनें और फिर **उपयोगकर्ता_प्रतिरूपण** अनुमति चुनें.

1. **अनुमतियाँ जोड़ें** चयन करें.

1. अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.

1. उपयोगकर्ता द्वारा लॉग इन किए बिना एपीआई तक पहुंचने के लिए, यहां जाएं [सर्वर-टू-सर्वर एप्लिकेशन अनुमतियां](#server-to-server-application-permissions).

आप इस ऐप पंजीकरण के लिए एप्लिकेशन/क्लाइंट आईडी का उपयोग कर सकते हैं [माइक्रोसॉफ्ट प्रमाणीकरण पुस्तकालय (एमएसएएल)](/azure/active-directory/develop/msal-overview) एपीआई को आपके अनुरोध के साथ भेजने के लिए एक वाहक टोकन प्राप्त करने के लिए।

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

हमारे क्लाइंट लाइब्रेरी में API का उपयोग करने के बारे में जानकारी के लिए, [Customer Insights क्लाइंट लाइब्रेरी](#customer-insights-client-libraries) देखें.

### <a name="server-to-server-application-permissions"></a>सर्वर-से-सर्वर अनुप्रयोग अनुमतियाँ

एक ऐप पंजीकरण बनाएं जिसमें उपयोगकर्ता सहभागिता की आवश्यकता न हो और इसे सर्वर पर चलाया जा सके।

1. Azure पोर्टल में अपने अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.

1. **अनुमति जोड़ें** चुनें.

1. **मेरे संगठन द्वारा उपयोग किए जाने वाले API** टैब चुनें और सूची से **Customer Insights के  लिए Dynamics 365 AI** चुनें.

1. **अनुमति प्रकार** के लिये, **अनुप्रयोग अनुमतियाँ** चुनें और फिर **CustomerInsights.Api.All** अनुमति चुनें.

1. **अनुमतियाँ जोड़ें** चयन करें.

1. अपने अनुप्रयोग पंजीकरण के लिए **API अनुमतियाँ** पर वापस जाएं.

1. अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Customer Insights में एक उपयोगकर्ता के रूप में ऐप पंजीकरण का नाम जोड़ें।

   1. Customer Insights खोलें, यहाँ जाएँ **व्यवस्थापक** > **सुरक्षा** और चुनें **उपयोगकर्ताओं को जोड़ें**.

   1. अपने अनुप्रयोग पंजीकरण के नाम को खोजें, इसे खोज परिणामों से चुनें, और **सहेजें** चुनें.

## <a name="sample-queries"></a>नमूना प्रश्न

एपीआई के साथ काम करने के लिए ओडाटा नमूना प्रश्नों की एक छोटी सूची के लिए, देखें [ओडाटा क्वेरी उदाहरण](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insights क्‍लाइंट लाइब्रेरी

Customer Insights API के लिए उपलब्ध क्लाइंट लाइब्रेरी का उपयोग करना शुरू करें। सभी लाइब्रेरी स्रोत कोड और नमूना एप्लिकेशन [Customer Insights GitHub पेज](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) पर देखे जा सकते हैं.

### <a name="c-nuget"></a>C# NuGet

से C# क्लाइंट लाइब्रेरी का उपयोग करें NuGet .org वर्तमान में, पैकेज netstandard2.0 और netcoreapp2.0 फ्रेमवर्क को लक्षित करता है। अधिक जानकारी के लिए NuGet पैकेज, देखें [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# क्लाइंट लाइब्रेरी को C# प्रोजेक्ट में जोड़ें

1. Visual Studio में, अपने प्रोजेक्ट के लिए **NuGet पैकेज प्रबंधक** खोलें.

1. **Microsoft.Dynamics.CustomerInsights.Api** को खोजें.

1. प्रोजेक्ट में पैकेज जोड़ने के लिए **इंस्टॉल करें** का चयन करें.

   वैकल्पिक रूप से, इस कमांड को **NuGet पैकेज प्रबंधक कंसोल में चलाएं**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>C# क्लाइंट लाइब्रेरी का उपयोग करें

1. अपने मौजूदा [Azure अनुप्रयोग पंजीकरण](#create-a-new-app-registration-in-the-azure-portal) का उपयोग करके `AccessToken` पाने के लिए [Microsoft प्रमाणीकरण लाइब्रेरी(MSAL)](/azure/active-directory/develop/msal-overview) का उपयोग करें.

1. टोकन को सफलतापूर्वक प्रमाणित करने और प्राप्त करने के बाद, एक नया निर्माण करें या किसी मौजूदा का उपयोग करें`HttpClient` साथ **DefaultRequestHeaders "प्राधिकरण"** करने के लिए सेट **वाहक "पहुँच टोकन"** तथा**Ocp-Apim-सदस्यता-कुंजी** पर सेट करें [**सदस्यता कुंजी** आपके Customer Insights परिवेश से](#get-started-trying-the-customer-insights-apis).   

   उपयुक्त होने पर **प्राधिकरण** हेडर को रीसेट करें. उदाहरण के लिए, जब टोकन समाप्त हो गया है.

1. इस `HttpClient` को `CustomerInsights` क्लाइंट के निर्माण में पास करें.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. "एक्सटेंशन विधियों" के लिए क्लाइंट के साथ कॉल करें, उदाहरण के लिए, `GetAllInstancesAsync`. यदि अंतर्निहित तक पहुंच`Microsoft.Rest.HttpOperationResponse` पसंद किया जाता है, उदाहरण के लिए, "http संदेश विधियों" का उपयोग करें,`GetAllInstancesWithHttpMessagesAsync`.

1. प्रतिक्रिया की संभावना है`object` टाइप करें क्योंकि विधि कई प्रकार लौटा सकती है (उदाहरण के लिए,`IList<InstanceInfo>` तथा`ApiErrorResult`) रिटर्न प्रकार की जांच करने के लिए, निर्दिष्ट प्रतिक्रिया प्रकारों में वस्तुओं का उपयोग करें [एपीआई विवरण पृष्ठ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) उस ऑपरेशन के लिए।

   यदि अनुरोध पर अधिक जानकारी चाहिए, तो अधूरी प्रतिक्रिया ऑब्जेक्ट तक पहुंचने के लिए **http संदेश विधियों** का उपयोग करें.

### <a name="nodejs-package"></a>NodeJS पैकेज

NPM के जरिए उपलब्ध NodeJS क्लाइंट लाइब्रेरी का उपयोग करें: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python पैकेज

PyPi के जरिए Python क्लाइंट लाइब्रेरी को उपयोग करें: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
