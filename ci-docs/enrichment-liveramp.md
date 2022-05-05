---
title: LiveRamp पहचान डेटा संवर्धन
description: LiveRamp डेटा के साथ ग्राहक प्रोफाइल को समृद्ध करें।
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642567"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>LiveRamp (पूर्वावलोकन) से पहचान डेटा के साथ ग्राहक प्रोफाइल को समृद्ध करें 

LiveRamp नियतात्मक ऑफ़लाइन पहचान समाधान और ग्राहक डेटा का समेकन प्रदान करता है। आप अपने ग्राहक डेटा में व्यक्तिगत पहचानकर्ताओं को एबिलीटेक पहचान ग्राफ में मैप कर सकते हैं और एबिलीटेक आईडी प्राप्त कर सकते हैं। फिर आप अपने ग्राहक डेटा के बेहतर एकीकरण के लिए इन आईडी का उपयोग कर सकते हैं। 

## <a name="prerequisites"></a>पूर्वावश्यकताएँ 

संवर्धन को कॉन्फ़िगर करने के लिए, निम्नलिखित पूर्वापेक्षाएँ पूरी होनी चाहिए: 

- आपके पास एक सक्रिय LiveRamp सदस्यता है। सदस्यता प्राप्त करने के लिए, अपनी LiveRamp खाता टीम से संपर्क करें या[dynamics@liveramp.com](mailto:dynamics@liveramp.com) अधिक जानकारी के लिए।   

- क्लाइंट आईडी के साथ एक सक्रिय एबिलीटेक सदस्यता और एपीआई तक पहुंचने के लिए गुप्त। अधिक जानकारी के लिए देखें [एबिलीटेक एपीआई डेवलपर हब।](https://developers.liveramp.com/abilitec-api/) 

## <a name="supported-countriesregions"></a>समर्थित देश/क्षेत्र 

वर्तमान में हम केवल युनाइटेड स्टेट्स में LiveRamp डेटा के साथ ग्राहक प्रोफाइल को समृद्ध बनाने का समर्थन करते हैं। 

## <a name="configure-the-enrichment"></a>एनरिचमेंट को कॉन्फ़िगर करें 

1. **डेटा** > **समृद्ध** पर जाएं और **खोजें** टैब का चयन करें. 

1. चुनना**मेरा डेटा समृद्ध करें** पर **पहचान** टाइल 

   :::image type="content" source="media/liveramp-tile.png" alt-text="संवर्धन अवलोकन पृष्ठ में पहचान टाइल।":::

1. ड्राप-डाउन सूची से [कनेक्शन](connections.md) चुनें। यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें. यदि आप एक व्यवस्थापक हैं, तो आप चयन करके एक कनेक्शन बना सकते हैं **कनेक्शन जोड़ें**. चुनना**लाइव रैंप** ड्रॉपडाउन सूची से। 

1. चुनना**अगला** और चुनें **ग्राहक डेटा सेट** आप LiveRamp से पहचान डेटा के साथ समृद्ध करना चाहते हैं। आप का चयन कर सकते हैं *ग्राहक* आपके सभी ग्राहक प्रोफाइल को समृद्ध करने के लिए या एक का चयन करने के लिए निकाय *खंड* इकाई केवल उस सेगमेंट में निहित ग्राहक प्रोफाइल को समृद्ध करने के लिए। 

1. चुनना**अगला** और परिभाषित करें कि LiveRamp से मिलते-जुलते पहचान डेटा को देखने के लिए आपकी एकीकृत प्रोफ़ाइल से किस प्रकार के फ़ील्ड का उपयोग किया जाना चाहिए। कम से कम एक फ़ील्ड **नाम और पता**, **ोन**, या**ईमेल** आवश्यक है। 

   > [!TIP]
   > आप जितने अधिक प्रमुख पहचानकर्ता और फ़ील्ड मैप करेंगे, उच्च मिलान दर की संभावना उतनी ही अधिक होगी 

1. अपने एकीकृत . से फ़ील्ड को मैप करें *ग्राहक* इकाई जिसका उपयोग LiveRamp के एबिलिटेक आईडी ग्राफ के साथ मिलान के लिए किया जाएगा। 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp संवर्धन के लिए डेटा मैपिंग विकल्प।":::

1. फील्ड मैपिंग को पूरा करने के लिए **अगला** चुनें. 

1. प्रदान करें एक **नाम** संवर्धन के लिए और **आउटपुट इकाई**. 

1. अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** चुनें. 

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp के लिए कनेक्शन कॉन्फ़िगर करें 

आपको एक व्यवस्थापक होने की आवश्यकता है [कनेक्शन कॉन्फ़िगर करें](connections.md). चुनना**कनेक्शन जोड़ें** संवर्धन को कॉन्फ़िगर करते समय या पर जाएं **व्यवस्थापक** > **सम्बन्ध** और चुनें **स्थापित करना** पर **लाइव रैंप** टाइल 

:::image type="content" source="media/liveramp-connection.png" alt-text="LiveRamp AbiliTec सेवा से कनेक्शन सेट करने के लिए कॉन्फ़िगरेशन फलक।":::

1. के लिए **प्रदर्शन नाम**, कनेक्शन का नाम दर्ज करें। 

1. एक मान्य LiveRamp क्लाइंट आईडी और एक रहस्य प्रदान करें। 

1. समीक्षा करें और **डेटा गोपनीयता और अनुपालन** के लिए **मैं सहमत हूं** चेकबॉक्स का चयन करके अपनी सहमति प्रदान करें. 

1. कॉन्फ़िगरेशन को मान्य करने के लिए **सत्यापित** चुनें. 

1. कनेक्शन पूरा करने के लिए, चुनें **बचाना**. 

## <a name="enrichment-results"></a>संवर्धन के परिणाम 

संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से चलाएँ चुनें. आप सिस्टम को a . के भाग के रूप में स्वचालित रूप से संवर्धन चलाने दे सकते हैं [शेड्यूल्ड रिफ्रेश](system.md#schedule-tab). प्रोसेसिंग समय आपके ग्राहक डेटा के आकार पर निर्भर करता है. 

संवर्धन प्रक्रिया पूरी होने के बाद, आप के तहत नए समृद्ध ग्राहक प्रोफाइल डेटा की समीक्षा कर सकते हैं **मेरी समृद्धि**. इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी. 

आप चुनकर प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत दृश्य तक पहुंच सकते हैं **समृद्ध देखें** जानकारी। 

## <a name="next-steps"></a>अगले कदम

अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं. ग्राहक प्रोफाइल को एक व्यक्ति-आधारित दृश्य में समेकित करने के लिए एबिलीटेक आईडी का उपयोग करें। 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन 

जब आप सक्षम करते हैं Dynamics 365 Customer Insights LiveRamp को डेटा संचारित करने के लिए, आप अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं Dynamics 365 Customer Insights, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं। Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन यह सुनिश्चित करने के लिए आप ज़िम्मेदार हैं कि LiveRamp आपके किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है। अधिक जानकारी के लिए, समीक्षा करें [माइक्रोसॉफ्ट गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732). आपका Dynamics 365 Customer Insights प्रशासक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस एनरिचमेंट को हटा सकता है. 


[!INCLUDE [footer-include](includes/footer-banner.md)]