---
title: Dynamics 365 Marketing के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Dynamics 365 Marketing को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976802"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing (पूर्वावलोकन) में सेगमेंट का उपयोग करें

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

अभियान उत्पन्न करने और Dynamics 365 Marketing वाले ग्राहकों के विशिष्ट समूहों से संपर्क करने के लिए [सेगमेंट](segments.md) का उपयोग करें. अधिक जानकारी के लिए, देखें [Dynamics 365 Customer Insights से Dynamics 365 Marketing का उपयोग करें](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite-for-a-connection"></a>कनेक्शन के लिए पहले से ज़रूरी चीजें

- इससे पहले कि आप Customer Insights से मार्केटिंग में एक सेगमेंट निर्यात करें, संपर्क रिकॉर्ड Dynamics 365 Marketing में मौजूद होने चाहिए. [Common Data Services का उपयोग करके Dynamics 365 Marketing](connect-power-query.md) में संपर्कों को कैसे अंतर्ग्रहण करना है, पर अधिक पढ़ें.

  > [!NOTE]
  > ऑडियंस से मार्केटिंग तक सेगमेंट निर्यात करने से मार्केटिंग इंस्टेंस में नए संपर्क रिकॉर्ड नहीं बनेंगे. मार्केटिंग से संपर्क रिकॉर्ड ऑडियंस इनसाइट्स में निहित होना चाहिए और डेटा स्रोत के रूप में उपयोग किए जाने चाहिए. सेगमेंट को निर्यात करने से पहले ID से संपर्क करने के लिए ग्राहक ID को मैप करने के लिए उन्हें एकीकृत ग्राहक निकाय में शामिल करने की भी ज़रूरत है.

## <a name="set-up-connection-to-marketing"></a>मार्केटिंग में कनेक्शन सेट अप करें

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. **कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Dynamics 365 Marketing** चुनें.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **सर्वर का पता** फ़ील्ड में अपने संगठन का मार्केटिंग URL दर्ज करें.

1. **सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Marketing खाता चुनें.

1. Dynamics 365 कॉन्टैक्ट ID पर ग्राहक ID फ़ील्ड का मैप करें.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें. 

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** में, Dynamics 365 Marketing अनुभाग से एक कनेक्शन का चयन करें. यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.

1. एक या अधिक सेगमेंट चुनें.

1. **सहेजें** चुनें.

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है. आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
