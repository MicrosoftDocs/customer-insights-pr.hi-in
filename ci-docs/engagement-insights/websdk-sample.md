---
title: वेब SDK नमूना चलाएँ
description: वेब SDK नमूना को वैयक्तिकृत करने और चलाने का तरीका जानें.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606219"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Dynamics 365 Customer Insights एंगेजमेन्ट इनसाइट क्षमता के लिए वेब SDK नमूना चलाएँ

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

एंगेजमेन्ट इनसाइट क्षमता वेब SDK लाइब्रेरी एक नमूना कोड के साथ JavaScript लाइब्रेरी है जिसका उपयोग आप अपनी वेबसाइट पर कर सकते हैं.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- [Visual Studio कोड](https://code.visualstudio.com/) इंस्टॉल करें.
- Visual Studio कोड में [लाइव सर्वर एक्सटेंशन इंस्टॉल करें](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) और लाइव सर्वर को चलाने के तरीके से परिचित हों.
- आपके पास [एंगेजमेंट इनसाइट्स कार्यक्षेत्र](create-workspace.md) होना चाहिए.

## <a name="run-sample"></a>नमूना चलाएं

1. [वेब SDK नमूना डाउनलोड करें](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. कम्प्रेस्ड फ़ाइल `ei_websdk_sample.zip` को अनज़िप करें.

1. Visual Studio कोड में अनज़िप्ड फ़ोल्डर खोलें.

1. अपने कार्यक्षेत्र के लिए एंगेजमेंट इनसाइट्स पोर्टल पर जाएँ. **व्यवस्थापक** > **कार्यस्थान** और फिर **इंस्टॉलेशन गाइड** चुनें. पहले विकल्प का पालन करें और JavaScript कोड स्निपेट को कॉपी करने के लिए **कोड कॉपी** करें चुनें.

1. `ei_websdk_sample.html` फ़ाइल में, वह कोड स्निपेट पेस्ट करें जिसे आपने अभी इस लाइन के नीचे से कॉपी किया है:

   - <-- एन्गेजमेन्ट इनसाइट्स पोर्टल से JAVASCRIPT कोड स्निपेट इस लाइन के नीचे पेस्ट करें -->

1. Visual Studio कोड में लाइव सर्वर का उपयोग करते हुए स्टेटस बार से **लाइव जाएं** का चयन करके `ei_websdk_sample.html` फ़ाइल खोलें.

1. पृष्ठ खोलने पर, एक व्यू इवेन्ट स्वचालित रूप से भेजी जानी चाहिए. पृष्ठ के किसी भी बटन पर क्लिक करने से एक्शन इवेंट्स भेजे जाएंगे. **ईवेंट्स ट्रैक करें** बटन कस्टम ईवेंट्स भी भेजेगा. **Bing पर जाएं** बटन का चयन करने से बिंग वेबसाइट पर नेविगेट करने से पहले एक एक्शन इवेंट भेजा जाएगा.

1. जब आप अपने कार्यक्षेत्र में नेविगेट करते हैं, तो प्रवाहित होने वाले इवेन्ट्स को देखें. यह कार्यस्थान चरण 4 में दर्ज की गई इनजेशन की से संबद्ध है.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
