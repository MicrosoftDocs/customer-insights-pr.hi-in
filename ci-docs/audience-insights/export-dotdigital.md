---
title: DotDigital को Customer Insights डेटा निर्यात करें
description: DotDigital के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269102"
---
# <a name="connector-for-dotdigital-preview"></a>DotDigital के लिए संबंधक (पूर्वावलोकन)

एकीकृत ग्राहक प्रोफाइल के निर्यात सेगमेंट DotDigital पता पुस्तकों के लिए और उन्हें अभियानों, ईमेल विपणन के लिए उपयोग करते हैं, और DotDigital के साथ ग्राहक वाले सेगमेंटों का निर्माण करने के लिए. 

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

-   आपके पास [DotDigital खाता](https://dotdigital.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.
-   DotDigital और संबंधित AD में मौजूदा पते की किताबें हैं. पता बुक सिलने और खोलने पर ID यूआरएल में मिल सकती है. अधिक जानकारी के लिए देखें [DotDigital पता किताबें](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.
-   निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.

## <a name="connect-to-dotdigital"></a>DotDigital से कनेक्ट करें

1. **व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.

1. **DotDigital** के तहत, **सेट अप** का चयन करें.

1. अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital निर्यात के लिए कॉन्फ़िगरेशन फलक.":::

1. अपना **DotDigital उपयोगकर्ता नाम और पासवर्ड** दर्ज करें.

1. अपने **[DotDigital पता पुस्तक ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** दर्ज करें .

1. **डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.

1. DotDigital के लिए कनेक्शन शुरू करने के लिए **कनेक्ट** चुनें.

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.

## <a name="configure-the-connector"></a>कनेक्टर कॉन्फ़िगर करें

1. **डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है. अन्य वैकल्पिक फ़ील्ड जैसे **फर्स्ट नाम**, **अंतिम नाम**, **पूरा नाम**, **लिंग**, और **पोस्ट कोड** के लिए भी यही कदम दोहराएं.

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं. आप कुल मिलाकर 1 मिलियन ग्राहक प्रोफाइल को DotDigital में निर्यात कर सकते हैं.

1. **सहेजें** चुनें.

## <a name="export-the-data"></a>डेटा निर्यात करें

आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं. निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab). DotDigital में, अब आप [DotDigital पता किताबें](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) में अपने खंडों पा सकते हैं .

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- DotDigital को प्रति निर्यात 1 मिलियन प्रोफाइल तक.
- DotDigital को निर्यात करना खंडों तक सीमित है.
- प्रदाता पक्ष पर सीमाओं के कारण कुल 1 मिलियन प्रोफाइल वाले निर्यात खंडों में 3 घंटे तक का समय लग सकता है. 
- DotDigital को निर्यात किए जा रहे प्रोफाइल की संख्या DotDigital के साथ आपके अनुबंध पर निर्भर और सीमित है.

## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को DotDigital में डेटा संचारित करने में सक्षम बनाते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं. Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि DotDigital आपके किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करे. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.
आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.


[!INCLUDE[footer-include](../includes/footer-banner.md)]