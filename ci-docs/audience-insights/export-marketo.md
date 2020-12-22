---
title: Marketo के लिए Customer Insights डेटा निर्यात करें
description: Marketo के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570405"
---
# <a name="connector-for-marketo-preview"></a>Marketo के लिए कनेक्ट (पूर्वावलोकन)

अभियान उत्पन्न करने, ईमेल मार्केटिंग प्रदान करने और Marketo के साथ ग्राहकों के विशिष्ट समूहों का उपयोग करने के लिए एकीकृत ग्राहक प्रोफाइल के निर्यात खंड.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

-   आपके पास [Marketo खाता](https://login.marketo.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.
-   Marketo और संबंधित ID में मौजूदा सूचियां हैं. अधिक जानकारी के लिए, [Marketo सूचियां](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) देखें.
-   आपके पास [कॉन्फ़िगर सेगमेंट](segments.md) है.
-   निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.

## <a name="connect-to-marketo"></a>Marketo से कनेक्ट करें

1. **व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.

1. **Marketo** के अंतर्गत, **सेट अप** चुनें.

1. अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.

1. अपने **[Marketo क्लाइंट ID, क्लाइंट सीक्रेट और रेस्ट एंडपॉइंट होस्टनेम](https://developers.marketo.com/rest-api/authentication/)** दर्ज करें .

1. अपनी **[Marketo सूची ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** दर्ज करें 

1. मैं **डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **सहमत हूं** चुनें और Marketo से कनेक्शन को शुरू करने के लिए **कनेक्ट** का चयन करें.

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Marketo कनेक्शन के लिए निर्यात स्क्रीनशॉट":::

1. निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.

## <a name="configure-the-connector"></a>कनेक्टर कॉन्फ़िगर करें

1. **डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है. 

1. वैकल्पिक रूप से, आप अधिक व्यक्तिगत ईमेल बनाने के लिए अतिरिक्त फ़ील्ड के रूप में **प्रथम नाम**, **अंतिम नाम**, **शहर**, **राज्य** और **देश/क्षेत्र** को निर्यात कर सकते हैं. इन फ़ील्ड को मैप करने के लिए **जोड़ें विशेषता** चुनें.

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं. आप कुल मिलाकर 1 मिलियन ग्राहक प्रोफ़ाइल को Marketo में निर्यात कर सकते हैं.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Marketo को निर्यात करने के लिए क्षेत्रों और खंडों का चयन करें":::

1. **सहेजें** चुनें.

## <a name="export-the-data"></a>डेटा निर्यात करें

आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं. निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab). Marketo में, अब आप [Marketo सूचियों](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) के तहत अपने सेगमेंट पा सकते हैं .

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- Marketo को प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक.
- Marketo को निर्यात करना सेगमेंटों तक सीमित है.
- कुल 1 मिलियन प्रोफाइल वाले निर्यात खंडों में 3 घंटे तक का समय लग सकता है. 
- Marketo को निर्यात किए जा रहे प्रोफ़ाइल की संख्या Marketo के साथ आपके अनुबंध पर निर्भर और सीमित है.

## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को Marketo पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं. Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Marketo आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.
आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.
