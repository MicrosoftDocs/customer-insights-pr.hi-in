---
title: सेगमेंट LinkedIn Ads (पूर्वावलोकन) में निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और LinkedIn Ads को निर्यात करने का तरीका जानें.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304705"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>सेगमेंट LinkedIn Ads (पूर्वावलोकन) में निर्यात करें

Matched Audiences बनाने के लिए एकीकृत ग्राहक प्रोफ़ाइल के सेगमेंट को LinkedIn Ads में निर्यात करें. कंपनी लक्ष्यीकरण और संपर्क लक्ष्यीकरण के लिए matched audiences का उपयोग करें.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- ए [LinkedIn Campaign Manager खाता](https://business.linkedin.com/marketing-solutions/ads) और संबंधित व्यवस्थापक क्रेडेंशियल।
- ए [LinkedIn Campaign Manager खाता पहचान।](https://www.linkedin.com/help/lms/answer/a424270)
- [कॉन्फ़िगर किए गए खंड](segments.md) ग्राहक अंतर्दृष्टि में।
- आप चुनते हैं या नहीं, इस पर निर्भर करते हुए निर्यात किए गए सेगमेंट को कम से कम एक विशिष्ट फ़ील्ड की आवश्यकता होती है [संपर्क लक्ष्यीकरण](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) या[कंपनी लक्ष्यीकरण](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) लिंक्डइन पर। संभावित फ़ील्ड में सूचीबद्ध हैं **डेटा मिलान** कदम जब [निर्यात को कॉन्फ़िगर करना](#configure-an-export).

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- लिंक्डइन विज्ञापनों में प्रति निर्यात 100,000 ग्राहक प्रोफाइल तक, जिसे पूरा होने में 10 मिनट तक का समय लग सकता है।
- केवल खंड। एक सेगमेंट में कम से कम 300 अद्वितीय प्रोफ़ाइल होनी चाहिए।

## <a name="set-up-connection-to-linkedin-ads"></a>लिंक्डइन विज्ञापनों से कनेक्शन सेट करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **लिंक्डइन विज्ञापन**.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपना प्रदान करें LinkedIn Campaign Manager खाता पहचान।

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. चुनना**जुडिये** कनेक्शन शुरू करने के लिए।

1. **LinkedIn के साथ प्रमाणित करें** चुनें और LinkedIn Campaign Manager के लिए अपने व्यवस्थापक क्रेडेंशियल्स प्रदान करें.

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** फ़ील्ड में, LinkedIn Ads सेक्शन से एक कनेक्शन का चयन करें. यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. चुनें कि आप LinkedIn पर [संपर्क लक्ष्य](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) के लिए डेटा निर्यात करना चाहते हैं या [कंपनी लक्ष्य](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) के लिए.

1. **डेटा मिलान** अनुभाग में, संपर्क लक्षीकरण के लिए, ग्राहक के ईमेल पते, Apple विज्ञापन ID, Google विज्ञापन ID, Google उपयोगकर्ता ID या प्रथम और अंतिम नाम दिखाने वाली कम से कम एक फ़ील्ड चुनें. अगर आप कंपनी लक्षीकरण चुनते हैं, तो कम से कम एक फ़ील्ड चुनें जो कंपनी का नाम, ईमेल डोमेन, LinkedIn पेज URL, स्टॉक प्रतीक, या वेबसाइट को दिखाती है.

1. वैकल्पिक रूप से, अपने निर्यात को और अधिक परिभाषित करने के लिए फ़ील्ड जोड़ें। इन फ़ील्ड को मैप करने के लिए **जोड़ें विशेषता** चुनें.

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं. LinkedIn Campaign Manager में matched audiences, निर्यात करने के लिए आपके द्वारा चुने गए सेगमेंट के नाम के साथ स्वचालित रूप से बन जाएगी. प्रत्येक सेगमेंट के परिणामस्वरूप एक अलग matched audience होगी.

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
