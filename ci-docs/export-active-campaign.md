---
title: ActiveCampaign में सेगमेंट निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और ActiveCampaign को निर्यात करने का तरीका जानें।
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725402"
---
# <a name="export-segments-to-activecampaign-preview"></a>ActiveCampaign में अनुभाग निर्यात करें (पूर्वावलोकन)

एकीकृत ग्राहक प्रोफाइल के अनुभाग को ActiveCampaign में निर्यात करें और मार्केटिंग गतिविधियों के लिए उनका उपयोग करें।

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- एक [सक्रिय अभियान खाता](https://www.activecampaign.com/) और संबंधित व्यवस्थापक क्रेडेंशियल।
- एक [सक्रिय अभियान सूची आईडी।](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign)
- एक [सक्रिय अभियान एपीआई कुंजी](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) और बाकी एंडपॉइंट होस्टनाम।
- [कॉन्फ़िगर किए गए खंड](segments.md) ग्राहक अंतर्दृष्टि में।
- निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- ब्रिंग योर ओन स्टोरेज (बीओओएस) के संयोजन में निजी लिंक समर्थित नहीं है।
- ActiveCampaign को प्रति निर्यात 1 मिलियन ग्राहक प्रोफ़ाइल तक, जिसे पूरा होने में 90 मिनट तक का समय लग सकता है। आपके द्वारा ActiveCampaign में निर्यात करने योग्य ग्राहक प्रोफ़ाइलों की संख्या, ActiveCampaign के साथ आपके अनुबंध पर निर्भर करती है.
- केवल खंड।

## <a name="set-up-connection-to-activecampaign"></a>ActiveCampaign में कनेक्शन सेट अप करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **सक्रिय अभियान**.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपना ActiveCampaign API कुंजी और REST समाप्ति बिंदु होस्टनेम डालें. REST समापन बिंदु होस्टनाम केवल https://के बिना, होस्टनाम है.

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. चुनना**जुडिये** कनेक्शन शुरू करने के लिए।

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** फ़ील्ड में, ActiveCampaign सेक्शन से एक कनेक्शन चुनें। यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. अपना भरें **सक्रिय अभियान सूची आईडी**.

1. **डेटा मिलान** सेक्शन में, **ईमेल** फ़ील्ड में, वह फ़ील्ड चुनें जो ग्राहक के ईमेल पते को दर्शाती है.

1. वैकल्पिक रूप से, निर्यात करें **प्रथम नाम**, **िम नाम**, तथा**फ़ोन** अधिक व्यक्तिगत ईमेल बनाने के लिए। इन फ़ील्ड को मैप करने के लिए **जोड़ें विशेषता** चुनें.

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
