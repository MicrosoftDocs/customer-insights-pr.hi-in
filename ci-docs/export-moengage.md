---
title: MoEngage को निर्यात खंड
description: कनेक्शन को कॉन्फ़िगर करने और MoEngage को निर्यात करने का तरीका जानें।
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725268"
---
# <a name="export-segments-to-moengage-preview"></a>MoEngage को निर्यात खंड (पूर्वावलोकन)

MoEngage को एकीकृत ग्राहक प्रोफाइल के सेगमेंट निर्यात करें और MoEngage में ईमेल मार्केटिंग के लिए उनका उपयोग करें।

## <a name="prerequisites-for-a-connection"></a>कनेक्शन के लिए पहले से ज़रूरी चीजें

- [मो एंगेज अकाउंट](https://www.moengage.com/) और संबंधित व्यवस्थापक क्रेडेंशियल।
- MoEngage API कुंजी सेटिंग > API MoEngage से।
- [कॉन्फ़िगर किए गए खंड](segments.md) ग्राहक अंतर्दृष्टि में।

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- ब्रिंग योर ओन स्टोरेज (बीओओएस) के संयोजन में निजी लिंक समर्थित नहीं है।
- MoEngage को प्रति निर्यात 100'000 ग्राहक प्रोफ़ाइल तक, जिसमें 15 मिनट तक का समय लग सकता है। आप MoEngage को कितने ग्राहक प्रोफ़ाइल निर्यात कर सकते हैं, यह MoEngage के साथ आपके अनुबंध पर निर्भर करता है।
- केवल खंड।

## <a name="set-up-connection-to-moengage"></a>MoEngage से कनेक्शन सेट करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **मो एंगेज** कनेक्शन को कॉन्फ़िगर करने के लिए।

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपना भरें [MoEngage डेटा एपीआई आईडी और एपीआई कुंजी।](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY)

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. चुनना**जुडिये** MoEngage से कनेक्शन आरंभ करने के लिए।

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **निर्यात जोड़ें** का चयन करें.

1. में **निर्यात के लिए कनेक्शन** फ़ील्ड, MoEngage अनुभाग से एक कनेक्शन चुनें। यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.

1. **डेटा मिलान** सेक्शन में, **ईमेल** फ़ील्ड में, वह फ़ील्ड चुनें जो ग्राहक के ईमेल पते को दर्शाती है. अन्य वैकल्पिक क्षेत्रों के लिए समान चरणों को दोहराएं।

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं. हम MoEngage के अंतर्गत चयनित सेगमेंट के समान नाम वाले एक या अधिक सेगमेंट बनाएंगे **सेगमेंट** > **कस्टम सेगमेंट**.

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
