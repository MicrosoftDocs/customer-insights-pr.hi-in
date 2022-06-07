---
title: Dynamics 365 Marketing में एकीकृत प्रोफ़ाइल का उपयोग करें
description: डायनामिक्स 365 मार्केटिंग के साथ एकीकृत प्रोफ़ाइल और सेगमेंट को एकीकृत करने का तरीका जानें।
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833310"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Dynamics 365 Marketing में एकीकृत ग्राहक प्रोफ़ाइल के साथ कार्य करें

[डायनेमिक्स 365 मार्केटिंग](/dynamics365/marketing/overview) ग्राहकों के अनुभवों को बढ़ाता है, जिससे आप संबंध को मजबूत करने और वफादारी अर्जित करने के लिए सभी टचपॉइंट पर वैयक्तिकृत यात्राओं को व्यवस्थित कर सकते हैं। Dynamics 365 Marketing ऐप, Dynamics 365 Sales के साथ निर्बाध रूप से काम करता है,Dynamics 365 Customer Insights,Microsoft Teams, और अन्य उत्पाद और आपको डेटा और AI की शक्ति का उपयोग करके तेज़ और बेहतर निर्णय लेने की अनुमति देता है।

Customer Insights डेटा को मार्केटिंग से जोड़कर, आप यह कर सकते हैं:

- एकीकृत ग्राहक प्रोफाइल और खंडों को लक्षित करें। यह आपको ग्राहक के डेटा के स्थान की परवाह किए बिना प्रत्येक ग्राहक को संलग्न करने में सक्षम बनाता है।
- ईमेल, एसएमएस में गतिशील सामग्री (जैसे वैयक्तिकृत टोकन), और लॉयल्टी स्थिति, सदस्यता नवीनीकरण तिथि, पैरेंट खाता, या एकीकृत Customer Insights प्रोफ़ाइल में आपके द्वारा कैप्चर किए गए किसी अन्य उपाय जैसे उपायों पर पुश सूचनाओं को आधार बनाएं।
- मार्केटिंग से Customer Insights में डेटा लोड करें और इसे अन्य स्रोतों से ग्राहक डेटा के साथ संयोजित करें।
- Customer Insights डेटा क्लींजिंग, संवर्धन, और फ़ज़ी मैचिंग टूल लागू करें।

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>रीयल-टाइम मार्केटिंग में समृद्ध ग्राहक प्रोफ़ाइल का उपयोग करें

रीयल-टाइम मार्केटिंग आपको बनाने की अनुमति देता है [कस्टम ट्रिगर](/dynamics365/marketing/real-time-marketing-custom-triggers) जो किसी भी ग्राहक कार्रवाई के आधार पर ग्राहक यात्रा शुरू करता है। आपका डेटा जितना अधिक वैयक्तिकृत होगा, आपकी यात्राएं उतनी ही प्रासंगिक और वैयक्तिकृत होंगी। यही बात मार्केटिंग और ग्राहक अंतर्दृष्टि के संयोजन को इतना शक्तिशाली बनाती है। तुम कर सकते हो[डेटा को एकीकृत करें](data-unification.md) किसी भी स्रोत से, फिर इसका उपयोग हाइपर-पर्सनलाइज्ड ग्राहक यात्रा को बढ़ावा देने के लिए करें।

और अधिक जानें: [रीयल-टाइम मार्केटिंग में Customer Insights प्रोफ़ाइल और सेगमेंट का उपयोग करें](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>आउटबाउंड ग्राहक यात्राओं के साथ एकीकृत खंडों का उपयोग करें

Customer Insights की सहायता से आप कई स्रोतों से डेटा परिशोधित कर सकते हैं और इसे समेकित ग्राहक खंडों में संयोजित कर सकते हैं। द्वारा[Customer Insights को आउटबाउंड मार्केटिंग से जोड़ना](export-dynamics365-marketing.md), ये खंड अपने आप दिखाई देंगे *तथा* ग्राहक यात्रा डिज़ाइनर में स्वचालित रूप से रीफ़्रेश करें.

और अधिक जानें: [से सेगमेंट का उपयोग करें Dynamics 365 Customer Insights डायनेमिक्स 365 मार्केटिंग के साथ](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>अपने आप से डेटा खींचोAzure Data Lake Storage

यदि आप मार्केटिंग के साथ Customer Insights डेटा का उपयोग करना चाहते हैं तो आप क्लाउड स्टोरेज तक सीमित नहीं हैं। यदि आपके पास पहले से ही अपना है Azure Data Lake Storage सेट अप करने के बाद, आप Customer Insights से जुड़ सकते हैं, फिर डेटा को मार्केटिंग ऐप के साथ वैसे ही साझा कर सकते हैं जैसे आप क्लाउड-आधारित सेटअप के साथ करते हैं।

और अधिक जानें: [के साथ डेटा साझाकरण सक्षम करें Dataverse अपने से Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
