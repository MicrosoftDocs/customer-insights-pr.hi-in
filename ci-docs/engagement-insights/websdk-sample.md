---
title: वेब SDK नमूना चलाएँ
description: वेब SDK नमूना को वैयक्तिकृत करने और चलाने का तरीका जानें.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036605"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Dynamics 365 Customer Insights एंगेजमेन्ट इनसाइट क्षमता के लिए वेब SDK नमूना चलाएँ

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

एंगेजमेन्ट इनसाइट क्षमता वेब SDK लाइब्रेरी एक नमूना कोड के साथ JavaScript लाइब्रेरी है जिसका उपयोग आप अपनी वेबसाइट पर कर सकते हैं.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- [Visual Studio कोड](https://code.visualstudio.com/) इंस्टॉल करें.
- Visual Studio कोड में [लाइव सर्वर एक्सटेंशन इंस्टॉल करें](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) और लाइव सर्वर को चलाने के तरीके से परिचित हों.
- आपके पास [अंतर्ग्रहण कुंजी](instrument-website.md) होना चाहिए.

## <a name="run-sample"></a>नमूना चलाएं

1. [वेब SDK नमूना डाउनलोड करें](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. कम्प्रेस्ड फ़ाइल `ei_websdk_sample.zip` को अनज़िप करें.

1. Visual Studio कोड में अनज़िप्ड फ़ोल्डर खोलें.

1. `ei_websdk_sample.html` फ़ाइल में, "INGESTION_KEY" स्ट्रिंग को एंगेजमेन्ट इनसाइट क्षमता पोर्टल से अपनी इनजेशन की से बदलें, और स्ट्रिंग "NAME" को उस वैश्विक नाम से बदलें जिसमें आप चाहते हैं कि SDK को दृष्टांतिकृत करना चाहते हैं. सुनिश्चित करें कि आप सभी घटनाओं को प्रतिस्थापित करते हैं.

1. Visual Studio कोड में लाइव सर्वर का उपयोग करते हुए स्टेटस बार से **लाइव जाएं** का चयन करके `ei_websdk_sample.html` फ़ाइल खोलें.

1. पृष्ठ खोलने पर, एक व्यू इवेन्ट स्वचालित रूप से भेजी जानी चाहिए. पृष्ठ के किसी भी बटन पर क्लिक करने से एक्शन इवेंट्स भेजे जाएंगे. **ईवेंट्स ट्रैक करें** बटन कस्टम ईवेंट्स भी भेजेगा. **Bing पर जाएं** बटन का चयन करने से बिंग वेबसाइट पर नेविगेट करने से पहले एक एक्शन इवेंट भेजा जाएगा.

1. जब आप अपने कार्यक्षेत्र में नेविगेट करते हैं, तो प्रवाहित होने वाले इवेन्ट्स को देखें. यह कार्यस्थान चरण 4 में दर्ज की गई इनजेशन की से संबद्ध है.


[!INCLUDE[footer-include](../includes/footer-banner.md)]