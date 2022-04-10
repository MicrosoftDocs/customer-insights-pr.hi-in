---
title: अज्ञात से ज्ञात के साथ पूर्व में प्रमाणित विज़िटर के वेब इवेंट की पहचान करें
description: अज्ञात से ज्ञात विशेषता की मदद से आप किसी वेबसाइट पर पहले से प्रमाणित किए गए विज़िटर के साथ इवेंट को संबद्ध कर सकते हैं.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230682"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>पहले से प्रमाणित विज़िटर के वेब इवेंट को पहचानें

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

सहभागिता इनसाइट्स क्षमता में **अज्ञात से ज्ञात** विशेषता वेबसाइट पर इवेंट को उन विज़िटर के साथ संबद्ध करती है, जो पहले प्रमाणित हुए थे. यदि सुविधा अक्षम है, तो वे विज़िटर जो पिछली विज़िट के दौरान प्रमाणित करते हैं और फिर चले जाते हैं, उनकी तब पहचान नहीं की जाती है यदि वे वापस आने पर फिर से प्रमाणित नहीं किए जाते हैं. 

उदाहरण के लिए, कोई व्यक्ति पिछले सप्ताह किसी वेबसाइट पर गया, साइट पर अपने उपयोगकर्ता खाते में साइन इन किया और उत्पाद कैटलॉग को ब्राउज़ किया. वह व्यक्ति अपने खाते में साइन इन किए बिना अधिक उत्पादों को ब्राउज़ करने के लिए अगले सप्ताह लौटता है. **अज्ञात से ज्ञात** सुविधा का उपयोग करने वाले साइट मालिक को पता चल जाएगा कि वही व्यक्ति वापस आ गया है और उसने साइट पर क्या किया है. यह वेबसाइट गतिविधियों की अधिक सटीक रिपोर्टिंग और विश्लेषण की अनुमति देता है.

## <a name="enable-unknown-to-known"></a>अज्ञात को ज्ञात में सक्षम करें

इस सुविधा को सक्षम करने के लिए आपको [कार्यस्थान व्यवस्थापक](user-roles.md) होना चाहिए. 

1. सहभागिता जानकारी में, **व्यवस्थापक** > **कार्यस्थान** पर जाएँ. 
2. **सेटिंग** टैब का चयन करें
3. **अज्ञात से ज्ञात** अनुभाग में, टॉगल को **सक्षम** पर सेट करें.

![अज्ञात को ज्ञात में सक्षम करें](media/U2Ktoggle.png "अज्ञात को ज्ञात में सक्षम करें")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>अपनी साइट के ट्रैकिंग स्निपेट में JavaScript कोड जोड़ना

एक वेबसाइट [सहभागिता इनसाइट्स वेब SDK](advanced-SDK-implementation.md) का उपयोग करके निम्नलिखित JavaScript नमूने के साथ **उपयोगकर्ता authId** कैप्चर कर सकती है. **अज्ञात से ज्ञात** सुविधा के काम करने के लिए, आपको अपने JavaScript स्निपेट में authId को कैपचर करने *और* userMapping:True को सक्षम करने की आवश्यकता है जैसा कि नीचे दिए गए नमूने में है.

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
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
