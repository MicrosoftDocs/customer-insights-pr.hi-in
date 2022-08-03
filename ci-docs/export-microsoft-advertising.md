---
title: Microsoft Advertising को सेगमेंट निर्यात करें (पूर्वावलोकन)
description: कनेक्शन को कॉन्फ़िगर करने और Microsoft Advertising को निर्यात करने का तरीका जानें.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196534"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Microsoft Advertising को सेगमेंट निर्यात करें (पूर्वावलोकन)

ग्राहक मिलान ऑडिएंस बनाने के लिए Customer Insights सेगमेंट को Microsoft Advertising में निर्यात करें. अपने विज्ञापन अभियानों के लिए इन ऑडिएंस का उपयोग करें.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- ए [माइक्रोसॉफ्ट विज्ञापन खाता](https://ads.microsoft.com/) और संबंधित व्यवस्थापक क्रेडेंशियल।
- Microsoft विज्ञापन ग्राहक आईडी और खाता आईडी। ग्राहक आईडी खोजें (`cid`) और खाता आईडी (`aid`) जब आप Microsoft विज्ञापन में लॉग इन होते हैं तो URL के पैरामीटर में।
- ग्राहक मिलान उपयोग की शर्तें स्वीकार की जाती हैं।
- [कॉन्फ़िगर किए गए खंड](segments.md) ग्राहक अंतर्दृष्टि में।
- निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- Microsoft विज्ञापन को प्रति निर्यात 500,000 ग्राहक प्रोफ़ाइल तक, जिसमें 10 मिनट तक का समय लग सकता है।
- केवल खंड।

## <a name="set-up-connection-to-microsoft-advertising"></a>Microsoft विज्ञापन से कनेक्शन सेट करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **माइक्रोसॉफ्ट विज्ञापन।**

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट व्यवस्थापक है. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. उसे दर्ज करें **माइक्रोसॉफ्ट विज्ञापन ग्राहक आईडी**.

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. चुनना**जुडिये** कनेक्शन शुरू करने के लिए।

1. **Microsoft Advertising के साथ प्रमाणित करें** चुनें और Microsoft Advertising के लिए अपने व्यवस्थापक क्रेडेंशियल्स प्रदान करें.

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** फ़ील्ड में, Microsoft Advertising सेक्शन से एक कनेक्शन का चयन करें. यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. निर्यात करने के लिए सेगमेंट चुनें. Microsoft विज्ञापन में ग्राहक मैच ऑडियंस निर्यात के लिए चयनित खंड के नाम के साथ स्वचालित रूप से बनाई जाती हैं. प्रत्येक अनुभाग के परिणामस्वरूप एक अलग ग्राहक मिलान ऑडिएंस होगी.

1. अपना **Microsoft विज्ञापन ग्राहक ID और खाता ID** दर्ज करें.

1. **ईमेल** फ़ील्ड में, **डेटा मिलान** सेक्शन में, ग्राहक के ईमेल पते वाली फ़ील्ड का चयन करें.

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
