---
title: सेगमेंट को DotDigital (पूर्वावलोकन) में निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और DotDigital को निर्यात करने का तरीका जानें.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196074"
---
# <a name="export-segments-to-dotdigital-preview"></a>सेगमेंट को DotDigital (पूर्वावलोकन) में निर्यात करें

एकीकृत ग्राहक प्रोफाइल के निर्यात सेगमेंट DotDigital पता पुस्तकों के लिए और उन्हें अभियानों, ईमेल विपणन के लिए उपयोग करते हैं, और DotDigital के साथ ग्राहक वाले सेगमेंटों का निर्माण करने के लिए.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- ए [डॉट डिजिटल अकाउंट](https://dotdigital.com/) और एक [एपीआई उपयोगकर्ता।](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user)
- A . से एक डॉटडिजिटल आईडी[नया](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) या DotDigital में मौजूदा पता पुस्तिका। पता बुक सिलने और खोलने पर ID यूआरएल में मिल सकती है.
- [कॉन्फ़िगर किए गए खंड](segments.md) ग्राहक अंतर्दृष्टि में।
- निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- DotDigital को प्रति निर्यात 1 मिलियन ग्राहक प्रोफाइल तक, जिसे प्रदाता पक्ष की सीमाओं के कारण पूरा होने में तीन घंटे तक का समय लग सकता है। ग्राहक प्रोफाइल की संख्या जिसे आप डॉटडिजिटल को निर्यात कर सकते हैं, डॉटडिजिटल के साथ आपके अनुबंध पर निर्भर करता है।
- केवल खंड।

## <a name="set-up-connection-to-dotdigital"></a>DotDigital में कनेक्शन सेट अप करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **डॉट डिजिटल**.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपना **DotDigital API उपयोगकर्ता नाम और पासवर्ड** दर्ज करें.

1. अपना भरें **डॉट डिजिटल एड्रेस बुक आईडी**.

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. चुनना**जुडिये** कनेक्शन शुरू करने के लिए।

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** में, DotDigital अनुभाग से एक कनेक्शन का चयन करें. यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. **डेटा मिलान** सेक्शन में, **ईमेल** फ़ील्ड में, वह फ़ील्ड चुनें जो ग्राहक के ईमेल पते को दर्शाती है.

1. वैकल्पिक रूप से, निर्यात करें **प्रथम नाम**, **िम नाम**, **ा नाम**, **िंग**, तथा**पोस्ट कोड**.

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

DotDigital में, अपने सेगमेंट ढूंढें [डॉट डिजिटल एड्रेस बुक्स](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
