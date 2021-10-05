---
title: Dynamics 365 Customer Insights में उपयोगकर्ता डेटा संग्रहीत करने के लिए कुकीज़ और उपयोगकर्ता सहमति प्रबंधित करें
description: समझें कि वेबसाइट पर आने वालों की पहचान करने के लिए कुकीज़ और उपयोगकर्ता सहमति का उपयोग कैसे किया जाता है.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558873"
---
# <a name="manage-cookies-and-user-consent"></a>कुकी और उपयोगकर्ता की सहमति प्रबंधित करें

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights एंगेजमेंट इनसाइट्स क्षमता वेबसाइट विज़िटर की पहचान करने के लिए कुकीज़ और (`localStorage`) कुंजियों का उपयोग करती है.

कुकीज़ छोटी फाइलें होती हैं जो वेबसाइट के साथ उपयोगकर्ता की परस्पर क्रियाओँ के बारे में जानकारी को संग्रहीत करती हैं. वे वेब ब्राउज़र में संग्रहीत किये जाते हैं. जब उपयोगकर्ता किसी वेबसाइट पर जाते हैं जिसके लिए आपके उपयोगकर्ताओं ने कुकीज़ संग्रहीत की हैं, तो ब्राउज़र उस जानकारी को सर्वर को भेजता है, जो उपयोगकर्ता के लिए अद्वितीय जानकारी भेजता है. यह वह तकनीक है जो, उदाहरण के लिए, एक ऑनलाइन शॉपिंग कार्ट में चयनित वस्तुओं को रखने की अनुमति देती है, भले ही कोई उपयोगकर्ता वेबसाइट से दूर चला जाए.

## <a name="user-consent"></a>उपयोगकर्ता सहमति

[सामान्य डेटा संरक्षण अधिनियम (GDPR)](/dynamics365/get-started/gdpr/) एक यूरोपीय संघ (EU) अधिनियम है जो यह अनिवार्य करता है कि संगठनों को अपने उपयोगकर्ताओं की गोपनीयता और सुरक्षा को कैसे संभालना चाहिए. कुकीज़ अक्सर "व्यक्तिगत डेटा" को संग्रहीत या एकत्र करते हैं, जैसे कि एक ऑनलाइन पहचानकर्ता, जो GDPR द्वारा कवर किया जाता है. यदि आपका व्यवसाय EU डेटा विषयों को नियोजित और/या बेचता है, तो GDPR आपको प्रभावित करता है. [इस बारे में अधिक जानें कि GDPR अनुपालन करने में Microsoft आपकी कैसे सहायता कर सकता है](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

एंगेजमेन्ट इनसाइट SDK को कुकीज़ या अन्य संवेदनशील जानकारी संग्रहीत करने की अनुमति देने के लिए, आपको यह निर्दिष्ट करना होगा कि आपके उपयोगकर्ताओं ने सहमति दे दी है या नहीं. यह कॉन्फ़िगरेशन में एक `userConsent` फ़ील्ड सेट करके SDK के प्रारंभ होने पर होता है.

यदि आप इंगित करते हैं कि कोई उपयोगकर्ता सहमति नहीं है, तो SDK कोई भी डेटा संग्रहीत नहीं करेगा, और ऐसे ईवेंट्स नहीं भेजेगा जिनका उपयोग उपयोगकर्ता के व्यवहार को ट्रैक करने के लिए किया जा सकता है. पहले से संग्रहीत कोई भी डेटा ब्राउज़र से हटा दिया जाएगा.

यदि कोई उपयोगकर्ता सहमति मान निर्दिष्ट नहीं है, तो SDK मान लेगा कि उपयोगकर्ता ने सहमति दे दी है. इसका मतलब यह है कि यदि आप (हमारे ग्राहक के रूप में) SDK में उपयोगकर्ता की सहमति के लिए कोई मान निर्दिष्ट नहीं करते हैं, तो डेटा एकत्र किया जाएगा. हालांकि, यदि आप निर्दिष्ट करते हैं कि उपयोगकर्ता सहमति के लिए मान "सत्य" होना चाहिए, तो उपयोगकर्ता द्वारा अस्वीकार किए जाने या स्पष्ट सहमति देने में विफल रहने पर डेटा एकत्र नहीं किया जाएगा.

उपयोगकर्ता की सहमति से वेब SDK को शुरू करने के लिए नीचे एक कोड स्निपेट दिया गया है:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>एंगेजमेन्ट इनसाइट क्षमता में आने वाले का डेटा संग्रहण

### <a name="cookies"></a>कुकीज़

- _msei
    - अनाम उपयोगकर्ता ID संग्रहीत करता है. यह कुकी ग्राहक डोमेन में सेट होती है और 365 दिनों में समाप्त हो जाती है.

### <a name="local-storage"></a>स्थानीय स्टोरेज

एंगेजमेंट इनसाइट्स क्षमता गैर-संवेदनशील डेटा को ट्रैक करने के लिए (`localStorage`) कुंजियों का उपयोग भी करती है. यह डेटा पूरी तरह से ब्राउज़र में ही संग्रहीत होता है, आपके सर्वर पर या उससे कोई ट्रैफ़िक नहीं भेजा जाता है.

- *EISession.Id*
    - चल रहे उपयोगकर्ता सत्र के बारे में जानकारी संग्रहीत करता है, जैसे सत्र ID, कब शुरू हुआ, और कब समाप्त हो जाएगा.
- *EISession.Previous*
    - वर्तमान सत्र में पहले देखे गए पृष्ठ के URL को संग्रहीत करता है.

स्थानीय संग्रहण में कुंजियां स्वचालित रूप से समाप्त नहीं होती हैं, और वे अगले SDK सत्र के दौरान रीसेट हो जाएंगी.

## <a name="deleting-cookies"></a>कुकीज़ हटाना

आपके ग्राहक अपने ब्राउज़र की सेटिंग के माध्यम से किसी भी समय कुकीज़ और स्थानीय संग्रहण कीज़ को मैन्युअल रूप से हटा सकते हैं.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
