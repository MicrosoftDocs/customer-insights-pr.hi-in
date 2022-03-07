---
title: पूर्वानुमान आउटपुट के आधार पर सेगमेंट
description: पूर्वानुमान मॉडल के आउटपुट निकाय के आधार पर सेगमेंट बनाएं.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741431"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>पूर्वानुमान मॉडल (पूर्वावलोकन) के आधार पर एक सेगमेंट बनाएं

पूर्वानुमानों के परिणाम कभी-कभी केवल आपके ग्राहकों के सबसेट पर लागू होते हैं. पूर्वानुमान मॉडल के परिणामों से सेगमेंट बनाकर अनुशंसाओं के व्यक्तिकरण को बढ़ाएं. उदाहरण के लिए, आप उन ग्राहकों को विशिष्ट अनुशंसाएं दे सकते हैं जो एक निश्चित प्रकार की सेवा को वरीयता देते हैं. 

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- Customer Insights में कम से कम [योगदानकर्ता की अनुमतियां](permissions.md).

- एक प्रोडक्ट की अनुशंसा, ट्रांज़ैक्शनल चर्ण, सब्स्क्रिप्शन चर्ण या ग्राहक के लिए लाइफटाइम वैल्यू मॉडल Customer Insights में कॉन्फ़िगर किया गया है. विभिन्न मॉडल को सेट करने के लिए आवश्यकताओं की समीक्षा करें:

  - [उत्पाद सुझाव मॉडल](predict-product-recommendation.md)
  - [सब्स्क्रिप्शन चर्ण मॉडल](predict-subscription-churn.md)
  - [ट्रांज़ैक्शनल चर्ण मॉडल](predict-transactional-churn.md)
  - [ग्राहक के लिए लाइफटाइम वैल्यू मॉडल](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>पूर्वानुमानों के आधार पर ग्राहक के सेगमेंट बनाएं

1. **इंटेलिजेंस** > **पूर्वानुमानों** पर जाएं और **मेरे पूर्वानुमान** टैब का चयन करें.

1. आप जिस मॉडल की समीक्षा करना चाहते हैं उसके बगल में वर्टिकल एलिप्सिस का चयन करें और **देखें** का चयन करें.

1. परिणाम पृष्ठ पर, **सेगमेंट बनाएं** चुनें. परिणाम पृष्ठ के बारे में अधिक जानकारी के लिए, मॉडल से जुड़े लेख की समीक्षा करें.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="सेगमेंट बनाएं कार्रवाई को उजागर करते हुए पूर्वानुमान के परिणाम पृष्ठ का स्क्रीनशॉट.":::

1. चयनित मॉडल की आउटपुट निकाय के आधार पर एक नया सेगमेंट बनाएं. अधिक जानकारी के लिए, [अनुभाग बनाएँ और प्रबंधित करें](segments.md) देखें.