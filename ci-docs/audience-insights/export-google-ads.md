---
title: Google Ads के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Google Ads को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976320"
---
# <a name="export-segments-to-google-ads-preview"></a>Google Ads (पूर्वावलोकन) में निर्यात अनुभाग

Google Ads ऑडियंस सूची में एकीकृत ग्राहक प्रोफ़ाइल के निर्यात सेगमेंट और Google खोज, जीमेल, YouTube और Google डिस्प्ले नेटवर्क पर AD देने के लिए उनका उपयोग करते हैं. 

## <a name="prerequisites-for-connection"></a>कनेक्शन के लिए पहले से ज़रूरी चीजें

-   आपके पास [Google Ads खाता](https://ads.google.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.
-   आपके पास एक [अनुमोदित Google Ads डेवलपर टोकन](https://developers.google.com/google-ads/api/docs/first-call/dev-token) है 
-   आप [ग्राहक मिलान नीति](https://support.google.com/adspolicy/answer/6299717) की आवश्यकताओं को पूरा करते हैं
-   आप [रीमार्केटिंग सूची के आकार](https://support.google.com/google-ads/answer/7558048) की आवश्यकताओं को पूरा करते हैं 

-   Google Ads और संबंधित आईडी में मौजूदा ऑडियंस हैं. अधिक जानकारी के लिए, [Google Ads ऑडिएंस](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) देखें.
-   आपके पास [कॉन्फ़िगर सेगमेंट](segments.md) है
-   निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते, पहला नाम और अंतिम नाम का प्रतिनिधित्व करने वाले क्षेत्र होते हैं

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- Google Ads को प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक.
- Google Ads को निर्यात करना सेगमेंटों तक सीमित है.
- प्रदाता पक्ष पर सीमाओं के कारण कुल 1 मिलियन प्रोफाइल वाले निर्यात खंडों में 5 मिनट तक का समय लग सकता है. 
- Google Ads में मिलान में 48 घंटे तक का समय लग सकता है.

## <a name="set-up-connection-to-google-ads"></a>Google Ads के लिए कनेक्शन सेट करें

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. **कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Google Ads** चुनें.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपनी **[Google Ads ग्राहक ID](https://support.google.com/google-ads/answer/1704344)** दर्ज करें.

1. अपने **[Google AD अनुमोदित डेवलपर टोकन](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** दर्ज करें.

1. **डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.

1. **Google Ads के साथ प्रमाणीकरण** चुनें और अपने Google Ads परिचय पत्र प्रदान करें.

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें. 

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** में, Google Ads अनुभाग से एक कनेक्शन का चयन करें. यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.

1. अपने **[Google Ads ऑडियंस ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** और Google Ads से कनेक्शन शुरू करने के लिए **कनेक्ट** चुनें.

1. **डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है. **पहले नाम** और **अंतिम नाम** फ़ील्ड के लिए एक ही कदम दोहराएं.

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं. आप कुल मिलाकर 1 मिलियन ग्राहक प्रोफ़ाइल को Google Ads में निर्यात कर सकते हैं.

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है. आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं. 

## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को Google Ads पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं. Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Google Ads विज्ञापन आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.
आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
