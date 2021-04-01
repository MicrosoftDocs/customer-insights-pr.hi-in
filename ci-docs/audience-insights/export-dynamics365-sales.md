---
title: Dynamics 365 Sales के लिए Customer Insights डेटा निर्यात करें
description: Dynamics 365 Sales से कनेक्शन कॉन्फ़िगर करना सीखें.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598111"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Sales के लिए कनेक्टर (पूर्वावलोकन)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

अपने ग्राहक डेटा को मार्केटिंग सूची बनाने, कार्यप्रवाह के फ़ॉलो अप और Dynamics 365 Sales के साथ प्रचार भेजने के लिए इस्तेमाल करें.

## <a name="prerequisite"></a>पूर्वावश्यकता

1. इससे पहले कि आप Customer Insights से विक्रय में सेगमेंट निर्यात करें, संपर्क रिकॉर्ड Dynamics 365 Sales में मौजूद होने चाहिए. [Common Data Services का उपयोग करके Dynamics 365 Sales](connect-power-query.md) में संपर्क कैसे अंतर्ग्रहण करने हैं, पर अधिक पढ़ें.

   > [!NOTE]
   > ऑडियंस इनसाइट्स से विक्रय में सेगमेंट को निर्यात करने से विक्रय इंस्टेंस में नए संपर्क रिकॉर्ड नहीं बनेंगे. विक्रय से संपर्क रिकॉर्ड ऑडियंस इनसाइट्स में निहित होना चाहिए और डेटा स्रोत के रूप में उपयोग किए जाने चाहिए. सेगमेंट को निर्यात करने से पहले ID से संपर्क करने के लिए ग्राहक ID को मैप करने के लिए उन्हें एकीकृत ग्राहक निकाय में शामिल करने की भी ज़रूरत है.

## <a name="configure-the-connector-for-sales"></a>विक्रय के लिए कनेक्टर कॉन्फ़िगर करें

1. ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.

1. **Dynamics 365 Sales** के तहत, **सेट करें** चुनें.

1. अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.

1. **सर्वर का पता** फ़ील्ड में अपने संगठन का बिक्री URL दर्ज करें.

1. **सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Sales खाता चुनें.

1. Dynamics 365 कॉन्टैक्ट ID पर ग्राहक ID फ़ील्ड का मैप करें.

1. **अगला** चुनें.

1. एक या अधिक सेगमेंट चुनें.

1. **सहेजें** चुनें.

## <a name="export-the-data"></a>डेटा निर्यात करें

आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं. निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]