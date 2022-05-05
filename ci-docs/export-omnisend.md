---
title: Customer Insights डेटा को Omnisend में निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Omnisend में निर्यात करने का तरीका जानें.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 70bd94ea5e4060094c3d215e3fc263a98df51229
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642797"
---
# <a name="export-segments-to-omnisend-preview"></a>Omnisend में अनुभाग निर्यात करें (पूर्वावलोकन)

Omnisend में एकीकृत ग्राहक प्रोफ़ाइल के अनुभाग निर्यात करें और मार्केटिंग सें जुड़ी गतिविधियों के लिए उनका उपयोग करें.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

-   आपके पास एक [Omnisend खाता](https://www.omnisend.com/) और संबंधित व्यवस्थापक क्रेडेंशियल्स हैं.
-   आपके पास [कॉन्फ़िगर किए गए खंड](segments.md) ग्राहक अंतर्दृष्टि में।
-   निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- आपको Omnisend में प्रति निर्यात 1 मिलियन ग्राहक प्रोफ़ाइल तक निर्यात करने में 4 घंटे तक का समय लग सकता है.
- Omnisend को निर्यात करना सेगमेंट तक ही सीमित है.
- Omnisend में निर्यात करने योग्य, ग्राहक प्रोफ़ाइल की संख्या, Omnisend के साथ आपके अनुबंध पर निर्भर करती है.

## <a name="set-up-connection-to-omnisend"></a>Omnisend में कनेक्शन सेट अप करें

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. **कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Omnisend** चुनें.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपनी [Omnisend API कुंजी](https://support.omnisend.com/en/articles/1061890-generating-api-key) दर्ज करें.

1. **डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.

1. Omnisend से कनेक्शन शुरू करने के लिए **कनेक्ट करें** चुनें.

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** फ़ील्ड में, Omnisend सेक्शन से एक कनेक्शन का चयन करें. यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.

1. **डेटा मिलान** सेक्शन में, **ईमेल** फ़ील्ड में, वह फ़ील्ड चुनें जो ग्राहक के ईमेल पते को दर्शाती है. Omnisend करने के लिए अनुभाग का निर्यात करना आवश्यक है. वैकल्पिक रूप से, आप अधिक व्यक्तिगत ईमेल बनाने के लिए प्रथम नाम, अंतिम नाम, पता, देश/प्रांत, शहर, राज्य, और पोस्ट कोड निर्यात कर सकते हैं. इन फ़ील्ड को मैप करने के लिए **जोड़ें विशेषता** चुनें.

1. **सहेजें** चुनें.

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है. आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं. 


## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को Ommisend में डेटा प्रसारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के ट्रांसफ़र की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं. Microsoft आपके निर्देश पर ऐसे डेटा को ट्रांसफ़र करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि Omnisend आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.

आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.