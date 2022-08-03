---
title: सेगमेंट को Iterable में निर्यात करें (पूर्वावलोकन)
description: कनेक्शन को कॉन्फ़िगर करने और Iterable को निर्यात करने का तरीका जानें।
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195431"
---
# <a name="export-segments-to-iterable-preview"></a>सेगमेंट को Iterable में निर्यात करें (पूर्वावलोकन)

एकीकृत ग्राहक प्रोफाइल के सेगमेंट को Iterable में निर्यात करें और मार्केटिंग गतिविधियों के लिए उनका उपयोग करें।

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- एक [चलने योग्य खाता](https://iterable.com/) और संबंधित व्यवस्थापक क्रेडेंशियल।
- एक [चलने योग्य एपीआई कुंजी](https://support.iterable.com/hc/en-us/articles/360043464871)
- [कॉन्फ़िगर किए गए खंड](segments.md) ग्राहक अंतर्दृष्टि में।
- निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- Iterable में 1 मिलियन ग्राहक प्रोफाइल तक, जिसे पूरा होने में 30 मिनट तक का समय लग सकता है। ग्राहक प्रोफाइल की संख्या जिसे आप Iterable को निर्यात कर सकते हैं, Iterable के साथ आपके अनुबंध पर निर्भर करता है।
- केवल खंड।

## <a name="set-up-connection-to-iterable"></a>Iterable से कनेक्शन सेट करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **चलने योग्य।**

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. लॉग इन करना जारी रखने के लिए अपनी Iterable API कुंजी प्रदान करें।

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. चुनना**जुडिये** कनेक्शन शुरू करने के लिए।

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. में **निर्यात के लिए कनेक्शन** फ़ील्ड, Iterable अनुभाग से एक कनेक्शन चुनें। यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. **डेटा मिलान** सेक्शन में, **ईमेल** फ़ील्ड में, वह फ़ील्ड चुनें जो ग्राहक के ईमेल पते को दर्शाती है. Iterable में बनाई गई सूची को ठीक वही नाम प्राप्त होगा जो आपके खंड के नाम में है Dynamics 365 Customer Insights.

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
