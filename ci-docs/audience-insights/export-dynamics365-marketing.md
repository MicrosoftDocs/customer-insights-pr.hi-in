---
title: Dynamics 365 Marketing के लिए Customer Insights डेटा निर्यात करें
description: Dynamics 365 Marketing से कनेक्शन कॉन्फ़िगर करना सीखें.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643775"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing के लिए कनेक्टर (पूर्वावलोकन)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

अभियान उत्पन्न करने और Dynamics 365 Marketing वाले ग्राहकों के विशिष्ट समूहों से संपर्क करने के लिए [सेगमेंट](segments.md) का उपयोग करें. अधिक जानकारी के लिए, देखें [Dynamics 365 Customer Insights से Dynamics 365 Marketing का उपयोग करें](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>पूर्वावश्यकता

संपर्क रिकॉर्ड [Dynamics 365 Marketing से इन्जेस्ट किए गए Common Data Service](connect-power-query.md).

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
