---
title: Google Ads के लिए Customer Insights डेटा निर्यात करें
description: Google Ads के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268964"
---
# <a name="connector-for-google-ads-preview"></a>Google Ads के लिए कनेक्टर (पूर्वावलोकन)

Google Ads ऑडियंस सूची में एकीकृत ग्राहक प्रोफ़ाइल के निर्यात सेगमेंट और Google खोज, जीमेल, YouTube और Google डिस्प्ले नेटवर्क पर AD देने के लिए उनका उपयोग करते हैं. 

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

-   आपके पास [Google Ads खाता](https://ads.google.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.
-   Google Ads और संबंधित आईडी में मौजूदा ऑडियंस हैं. अधिक जानकारी के लिए, [Google Ads ऑडिएंस](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) देखें.
-   आपके पास [कॉन्फ़िगर सेगमेंट](segments.md) है
-   निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते, पहला नाम और अंतिम नाम का प्रतिनिधित्व करने वाले क्षेत्र होते हैं

## <a name="connect-to-google-ads"></a>Google Ads से कनेक्ट करें

1. **व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.

1. **Google Ads** अंतर्गत, **सेट अप** चुनें.

1. अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.

1. अपनी **[Google Ads ग्राहक ID](https://support.google.com/google-ads/answer/1704344)** दर्ज करें.

1. अपने **[Google AD अनुमोदित डेवलपर टोकन](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** दर्ज करें.

1. **डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.

1. अपने **[Google Ads ऑडियंस ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** और Google Ads से कनेक्शन शुरू करने के लिए **कनेक्ट** चुनें.

1. **Google Ads के साथ प्रमाणीकरण** चुनें और अपने Google Ads परिचय पत्र प्रदान करें.

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Google Ads कनेक्शन के लिए निर्यात स्क्रीनशॉट":::

1. निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.

## <a name="configure-the-connector"></a>कनेक्टर कॉन्फ़िगर करें

1. **डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है. **पहले नाम** और **अंतिम नाम** फ़ील्ड के लिए एक ही कदम दोहराएं.

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं. आप कुल मिलाकर 1 मिलियन ग्राहक प्रोफ़ाइल को Google Ads में निर्यात कर सकते हैं.

1. **सहेजें** चुनें.

## <a name="export-the-data"></a>डेटा निर्यात करें

आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं. निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab). Google Ads में अब आप [Google Ads ऑडियंस](https://support.google.com/google-ads/answer/7558048?hl=en/) के तहत अपने सेगमेंट पा सकते हैं.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- Google Ads को प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक.
- Google Ads को निर्यात करना सेगमेंटों तक सीमित है.
- प्रदाता पक्ष पर सीमाओं के कारण कुल 1 मिलियन प्रोफाइल वाले निर्यात खंडों में 5 मिनट तक का समय लग सकता है. 
- Google Ads में मिलान में 48 घंटे तक का समय लग सकता है.

## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को Google Ads पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं. Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Google Ads विज्ञापन आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.
आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.


[!INCLUDE[footer-include](../includes/footer-banner.md)]