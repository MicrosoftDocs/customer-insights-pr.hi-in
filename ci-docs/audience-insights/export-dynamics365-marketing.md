---
title: Dynamics 365 Marketing के लिए Customer Insights डेटा निर्यात करें
description: Dynamics 365 Marketing से कनेक्शन कॉन्फ़िगर करना सीखें.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269056"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing के लिए कनेक्टर (पूर्वावलोकन)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

अभियान उत्पन्न करने और Dynamics 365 Marketing वाले ग्राहकों के विशिष्ट समूहों से संपर्क करने के लिए [सेगमेंट](segments.md) का उपयोग करें. अधिक जानकारी के लिए, देखें [Dynamics 365 Customer Insights से Dynamics 365 Marketing का उपयोग करें](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>पूर्वावश्यकता

- इससे पहले कि आप Customer Insights से मार्केटिंग में एक सेगमेंट निर्यात करें, संपर्क रिकॉर्ड Dynamics 365 Marketing में मौजूद होने चाहिए. [Common Data Services का उपयोग करके Dynamics 365 Marketing](connect-power-query.md) में संपर्कों को कैसे अंतर्ग्रहण करना है, पर अधिक पढ़ें.

  > [!NOTE]
  > ऑडियंस से मार्केटिंग तक सेगमेंट निर्यात करने से मार्केटिंग इंस्टेंस में नए संपर्क रिकॉर्ड नहीं बनेंगे. मार्केटिंग से संपर्क रिकॉर्ड ऑडियंस इनसाइट्स में निहित होना चाहिए और डेटा स्रोत के रूप में उपयोग किए जाने चाहिए. सेगमेंट को निर्यात करने से पहले ID से संपर्क करने के लिए ग्राहक ID को मैप करने के लिए उन्हें एकीकृत ग्राहक निकाय में शामिल करने की भी ज़रूरत है.

## <a name="configure-the-connector-for-marketing"></a>मार्केटिंग के लिए कनेक्टर कॉन्फ़िगर करें

1. ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.

1. **Dynamics 365 Marketing** के तहत, **सेट करें** चुनें.

1. अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.

1. **सर्वर का पता** फ़ील्ड में अपने संगठन का मार्केटिंग URL दर्ज करें.

1. **सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Marketing खाता चुनें.

1. Dynamics 365 कॉन्टैक्ट ID पर ग्राहक ID फ़ील्ड का मैप करें.

1. **अगला** चुनें.

1. एक या अधिक सेगमेंट चुनें.

1. **सहेजें** चुनें.

## <a name="export-the-data"></a>डेटा निर्यात करें

आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं. निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]