---
title: Google Ads (पूर्वावलोकन) में निर्यात अनुभाग
description: कनेक्शन को कॉन्फ़िगर करने और Google Ads को निर्यात करने का तरीका जानें.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725080"
---
# <a name="export-segments-to-google-ads-preview"></a>Google Ads (पूर्वावलोकन) में निर्यात अनुभाग

एकीकृत ग्राहक प्रोफ़ाइल के अनुभाग को Google Ads ऑडिएंस सूची में निर्यात करें और Google खोज, Gmail, YouTube, और Google प्रदर्शन नेटवर्क पर विज्ञापन देने के लिए उनका उपयोग करें।

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- ए [गूगल विज्ञापन खाता](https://ads.google.com/) और संबंधित व्यवस्थापक क्रेडेंशियल।
- ए [Google Ads ग्राहक आईडी](https://support.google.com/google-ads/answer/1704344).
- की आवश्यकताएं [ग्राहक मिलान नीति](https://support.google.com/adspolicy/answer/6299717) पूरा किया गया है।
- की आवश्यकताएं [रीमार्केटिंग सूची आकार](https://support.google.com/google-ads/answer/7558048) पूरा किया गया है।
- [कॉन्फ़िगर किए गए खंड](segments.md).
- निर्यात किए गए सेगमेंट में एकीकृत ग्राहक प्रोफ़ाइल में ईमेल पता, फ़ोन, मोबाइल विज्ञापनदाता आईडी, तृतीय-पक्ष उपयोगकर्ता आईडी या पते का प्रतिनिधित्व करने वाले फ़ील्ड होते हैं।

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- ब्रिंग योर ओन स्टोरेज (बीओओएस) के संयोजन में निजी लिंक समर्थित नहीं है।
- Google Ads को प्रति निर्यात 1 मिलियन ग्राहक प्रोफ़ाइल निर्यात करें, जिसे प्रदाता पक्ष की सीमाओं के कारण पूरा होने में 30 मिनट तक का समय लग सकता है।
- केवल खंड।
- Google Ads में मिलान में 48 घंटे तक लग सकते हैं.

## <a name="set-up-connection-to-google-ads"></a>Google Ads के लिए कनेक्शन सेट करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **गूगल विज्ञापन**.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपना Google Ads ग्राहक आईडी डालें.

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. **Google Ads के साथ प्रमाणीकरण** चुनें और अपने Google Ads परिचय पत्र प्रदान करें.

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** में, Google Ads अनुभाग से एक कनेक्शन का चयन करें. यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. चुनें कि मौजूदा ऑडिएंस का उपयोग करना है या एक नया बनाना है:
   - मौजूदा Google Ads ऑडिएंस को अपडेट करने के लिए, अपना दर्ज करें [गूगल विज्ञापन ऑडिएंस आईडी](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - एक नया ऑडिएंस बनाने के लिए, Google ऑडिएंस आईडी फ़ील्ड खाली छोड़ दें। Customer Insights आपके Google Ads खाते में स्वचालित रूप से एक नया ऑडिएंस बनाएगी और निर्यात किए गए सेगमेंट के नाम का उपयोग करेगी।

1. में **डेटा मिलान** अनुभाग में, निर्यात करने के लिए एक या अधिक डेटा फ़ील्ड का चयन करें, और उस फ़ील्ड का चयन करें जो Customer Insights में संबंधित डेटा फ़ील्ड का प्रतिनिधित्व करती है।

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
