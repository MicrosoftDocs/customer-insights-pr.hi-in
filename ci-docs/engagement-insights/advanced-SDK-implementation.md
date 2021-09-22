---
title: उन्नत वेब SDK परिदृश्य
description: SDK के साथ अपनी वेबसाइट को तैयार करते समय विचार करने के लिए उन्नत परिदृश्य.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036330"
---
# <a name="advanced-web-sdk-instrumentation"></a>उन्नत वेब SDK इंस्ट्रूमेंटेशन

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

यह लेख आपको उन्नत परिदृश्यों के बारे में मार्गदर्शन करता है, जब एक Dynamics 365 Customer Insights सहभागिता अंतर्दृष्टि क्षमता SDK के साथ [अपनी वेबसाइट को यंत्रीकृत करना](instrument-website.md) पर विचार करें.

## <a name="setting-user-details-for-your-event"></a>अपने ईवेंट के लिए उपयोगकर्ता विवरण सेट करना

SDK आपको वह उपयोगकर्ता जानकारी को परिभाषित करने देता है जिसे हर इवेन्ट के साथ भेजा जा सकता है. आप कोड स्निपेट कॉन्फ़िगरेशन में `src`, `name` और `cfg` के समान `user` नामक गुण में उपयोगकर्ता विवरण निर्दिष्ट कर सकते हैं (इस गुण के लिए अपेक्षित डेटा `IUser` ऑब्जेक्ट है).

`IUser` ऑब्जेक्ट में निम्नलिखित स्ट्रिंग गुण हैं:

- **localId**: उपयोगकर्ता की स्थानीय ID.
- **authId**: प्रमाणित उपयोगकर्ता ID.
- **authType**: प्रमाणित उपयोगकर्ता ID पाने के लिए प्रमाणीकरण प्रकार का उपयोग किया जाता है.
- **नाम**: उपयोगकर्ता का नाम.
- **ईमेल**: उपयोगकर्ता का ईमेल पता.
    
निम्न उदाहरण उपयोगकर्ता जानकारी भेजता हुआ एक कोड स्निपेट दिखाता है. जहां आप * द्वारा दर्शाए गए फ़ंक्शन देखते हैं, इसे उन मानों को बुलाने के अपने कार्यान्वयन से बदलें:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

आप SDK पर `setUser(user: IUser)` API को कॉल करके भी उपयोगकर्ता जानकारी निर्दिष्ट कर सकते हैं. `setUser API` को कॉल करने के बाद भेजी गई टेलीमेट्री में उपयोगकर्ता की जानकारी होगी.

## <a name="adding-custom-properties-for-each-event"></a>प्रत्येक ईवेंट के लिए कस्टम गुण जोड़ना

SDK आपको कस्टम गुण निर्दिष्ट करने देता है जिन्हें प्रत्येक ईवेंट के साथ भेजा जा सकता है. आप कस्टम गुणों को की-वैल्यू जोड़े वाले वस्तु के रूप में निर्दिष्ट कर सकते हैं (मान `string | number | boolean` प्रकार का हो सकता है). वस्तु को कोड स्निपेट कॉन्फ़िगरेशन में `src`, `name`, और `cfg` के समान `props` नामक गुण में जोड़ा जा सकता है. 

निम्न उदाहरण कस्टम गुण भेजता हुआ एक कोड स्निपेट दिखाता है:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

आप SDK पर `setProperty(name: string, value: string | number | boolean)` API को कॉल करके व्यक्तिगत रूप से कस्टम गुण निर्दिष्ट कर सकते हैं.

## <a name="sending-custom-events"></a>कस्टम ईवेंट भेजना

आप कस्टम ईवेंट भेजने के लिए SDK का उपयोग कर सकते हैं. आपको ईवेंट के साथ भेजे जाने वाले ईवेंट और प्रॉपर्टी के लिए एक नाम निर्दिष्ट करना होगा.

निम्न उदाहरण किसी कस्टम ईवेंट को ट्रैक करता एक कोड स्निपेट दिखाता है. स्निपेट कॉन्फ़िगरेशन में `name` की में `name` मान है. यह विंडो की वस्तु में चर नाम भी है जहां SDK लोड किया जाता है.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]