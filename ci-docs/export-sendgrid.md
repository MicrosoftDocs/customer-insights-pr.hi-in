---
title: SendGrid को निर्यात खंड (पूर्वावलोकन)
description: कनेक्शन को कॉन्फ़िगर करने और SendGrid को निर्यात करने का तरीका जानें.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724850"
---
# <a name="export-segments-to-sendgrid-preview"></a>SendGrid को निर्यात खंड (पूर्वावलोकन)

एकीकृत ग्राहक प्रोफ़ाइल के सेगमेंट SendGrid संपर्क सूचियों में निर्यात करें और उन्हें SendGrid में अभियानों और ईमेल मार्केटिंग के लिए उपयोग करें.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- ए [सेंडग्रिड खाता](https://sendgrid.com/) और संबंधित व्यवस्थापक क्रेडेंशियल।
- [SendGrid में मौजूदा संपर्क सूचियाँ](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) और संबंधित आईडी।
- ए [सेंडग्रिड एपीआई कुंजी।](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)
- [कॉन्फ़िगर किए गए खंड](segments.md) ग्राहक अंतर्दृष्टि में।
- निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- ब्रिंग योर ओन स्टोरेज (बीओओएस) के संयोजन में निजी लिंक समर्थित नहीं है।
- SendGrid में कुल 100,000 ग्राहक प्रोफ़ाइल तक, जिसे पूरा होने में कुछ घंटे तक लग सकते हैं। ग्राहक प्रोफ़ाइल की संख्या जिसे आप SendGrid को निर्यात कर सकते हैं, आपके SendGrid के साथ अनुबंध पर निर्भर करता है।
- केवल खंड।

## <a name="set-up-connection-to-sendgrid"></a>SendGrid में कनेक्शन सेट अप करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **सेंडग्रिड**.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपना भरें **सेंडग्रिड एपीआई कुंजी**.

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. चुनना**जुडिये** कनेक्शन शुरू करने के लिए।

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** में, SendGrid अनुभाग से एक कनेक्शन का चयन करें. यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. अपना भरें **सेंडग्रिड सूची आईडी**.

1. **डेटा मिलान** सेक्शन में, **ईमेल** फ़ील्ड में, वह फ़ील्ड चुनें जो ग्राहक के ईमेल पते को दर्शाती है.

1. वैकल्पिक रूप से, जैसे फ़ील्ड चुनें **प्रथम नाम**, **िम नाम**, **/क्षेत्र**, **ाज्य**, **·**, तथा**पोस्ट कोड**.

1. ज्ञात सीमाओं का पालन करते हुए उन खंडों का चयन करें जिन्हें आप निर्यात करना चाहते हैं।

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
