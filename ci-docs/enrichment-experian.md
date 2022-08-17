---
title: Experian से जनसांख्यिकी के साथ ग्राहक प्रोफाइल को बेहतर बनाएँ (पूर्वावलोकन)
description: Experian तीसरे पक्ष का संवर्धन के बारे में सामान्य जानकारी।
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237998"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Experian से जनसांख्यिकी के साथ ग्राहक प्रोफाइल को बेहतर बनाएँ (पूर्वावलोकन)

Experian, उपभोक्ता और व्यापार क्रेडिट रिपोर्टिंग और विपणन सेवाओं में एक वैश्विक लीडर है। Experian की डेटा संवर्धन सेवाओं के साथ, आप अपने ग्राहक प्रोफाइल को जनसांख्यिकीय डेटा जैसे घरेलू आकार, आय, और बहुत कुछ के साथ समृद्ध करके अपने ग्राहकों की गहरी समझ बना सकते हैं।

## <a name="supported-countriesregions"></a>समर्थित देश/क्षेत्र

वर्तमान में हम केवल युनाइटेड स्टेट्स में ग्राहक प्रोफाइल को समृद्ध करने का समर्थन करते हैं।

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- सक्रिय Experian अंशदान। सदस्यता प्राप्त करने के लिए, सीधे [Experian](https://www.experian.com/marketing-services/contact) से संपर्क करें। [Experian डेटा संवर्द्धन के बारे में अधिक जानें](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)।

- एक Experian [संबंध](connections.md) है [कॉन्फ़िगर किया गया](#configure-the-connection-for-experian) एक व्यवस्थापक द्वारा।

- Experian आपके एसएसएच-सक्षम सिक्योर ट्रांसपोर्ट (एसटी) खाते के लिए यूजर आईडी, पार्टी आईडी और मॉडल नंबर किExperian आपके लिए बनाया गया है।

## <a name="configure-the-connection-for-experian"></a>Experian के लिए कनेक्शन कॉन्फ़िगर करें

आप एक होना चाहिए [प्रशासक](permissions.md#admin) Customer Insights में और एक Experian यूजर आईडी, पार्टी आईडी और मॉडल नंबर।

1. चुनना**कनेक्शन जोड़ें** किसी संवर्धन को कॉन्फ़िगर करते समय, या यहां जाएं **व्यवस्थापक** > **सम्बन्ध** और चुनें **स्थापित करना** पर Experian टाइल

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experianकनेक्शन कॉन्फिगरेशन फलक.":::

1. कनेक्शन के लिए एक नाम और आपके लिए एक वैध यूजर आईडी, पार्टी आईडी और मॉडल नंबर दर्ज करें Experian सुरक्षित परिवहन खाता।

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. चुनना**सत्यापित करना** कॉन्फ़िगरेशन को सत्यापित करने के लिए और फिर चुनें **बचाना**.

## <a name="configure-the-enrichment"></a>एनरिचमेंट को कॉन्फ़िगर करें

1. **डेटा** > **समृद्ध** पर जाएं और **खोजें** टैब का चयन करें.

1. चुनना**मेरा डेटा समृद्ध करें** पर **जनसांख्यिकी** से Experian टाइल

   :::image type="content" source="media/experian-tile.png" alt-text="Experian संवर्धन अवलोकन पृष्ठ में टाइल।":::

1. ओवरव्यू की समीक्षा करें और फिर चुनें **अगला**.

1. कनेक्शन का चयन करें। यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. **अगला** चुनें.

1. को चुनिए **ग्राहक डेटा सेट** और वह प्रोफ़ाइल या सेगमेंट चुनें, जिसे आप जनसांख्यिकी डेटा से समृद्ध करना चाहते हैं Experian. *ग्राहक* इकाई आपके सभी ग्राहक प्रोफाइल को समृद्ध करती है जबकि एक सेगमेंट केवल उस सेगमेंट में निहित ग्राहक प्रोफाइल को समृद्ध करता है।

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="ग्राहक डेटा सेट चुनते समय का स्क्रीनशॉट.":::

1. परिभाषित करें कि आपकी एकीकृत प्रोफ़ाइल से किस प्रकार के फ़ील्ड का उपयोग जनसांख्यिकी डेटा के मिलान के लिए किया जाए Experian. कम से कम एक फ़ील्ड **नाम और पता**, **फ़ोन**, या **ईमेल** की ज़रूरत है. उच्च मिलान सटीकता के लिए, अन्य फ़ील्ड जोड़ें। **अगला** चुनें.

1. जनसांख्यिकीय डेटा से अपने फ़ील्ड को मैप करें Experian.

1. फील्ड मैपिंग को पूरा करने के लिए **अगला** चुनें.

1. प्रदान करें एक **नाम** संवर्धन के लिए और **आउटपुट इकाई का नाम**.

1. अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** चुनें.

1. चुनना**दौड़ना** संवर्धन प्रक्रिया शुरू करने के लिए या वापस लौटने के करीब **संवर्धन** पृष्ठ।

## <a name="view-enrichment-results"></a>संवर्धन परिणाम देखें

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**क्षेत्र द्वारा समृद्ध ग्राहकों की संख्या** प्रत्येक समृद्ध क्षेत्र के कवरेज में एक ड्रिल-डाउन प्रदान करता है।

## <a name="next-steps"></a>अगले कदम

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
