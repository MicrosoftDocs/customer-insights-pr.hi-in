---
title: Power Automate कनेक्टर | Microsoft Docs
description: Dynamics 365 Customer Insights से Microsoft Power Automate में प्रवाह बनाएं.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405921"
---
# <a name="power-automate-connector-preview"></a>Power Automate कनेक्टर (पूर्वावलोकन)

जब आपके डेटा में परिवर्तन होता है तो स्वचलित रूप से होने वाली विशिष्ट इवेंट स्वतः होने लगती हैं और [Power Automate](https://flow.microsoft.com/) में होने वाले प्रत्यक्ष जटिल प्रवाह को प्रबंधित करती हैं.

## <a name="power-automate-triggers"></a>Power Automate ट्रिगर्स

आप विभिन्न प्रकार के ट्रिगर्स का उपयोग कर सकते हैं जो आपको दोहराए जाने वाले कार्यों को स्वचालित करने के लिए फ़्लो बनाने की अनुमति देते हैं, जैसे कि अधिसूचनाएं या अधिक उन्नत क्रियाएं. 

- ट्रिगर जब डेटा स्रोत रिफ़्रेश विफल रहता है. 
- ट्रिगर जब डेटा स्रोत रिफ़्रेश सफल होता है.
- ट्रिगर जब अनुभाग की सीमा पार की जाती है. ट्रिगर सीमा के ऊपर जाने तक सीमित है.
- ट्रिगर जब व्यावसायिक उपाय सीमा के पार हो जाता है. ट्रिगर सीमा के ऊपर जाने तक सीमित है.
- ट्रिगर जब (डेटा स्रोतों, खंडों, साधनों,...) का पूरा रिफ़्रेश पूरा हो जाता है.
- जब एकीकरण प्रक्रिया (मानचित्र, मिलान, मर्ज) का रिफ्रेश पूरा होता है तब ट्रिगर करें.

[Power Automate में अपने ट्रिगर कॉन्फ़िगर करें](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate कार्रवाइयां
Power Automate कनेक्टर उपलब्ध ट्रिगर्स से अलग कार्रवाइयां प्रदान करता है. अधिक जानकारी के लिए, [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/) देखें.

## <a name="create-a-power-automate-flow-in-audience-insights"></a>ऑडियंस इनसाइट्स में एक Power Automate प्रवाह बनाएं

1. ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **सिस्टम** पर जाएं.

1. **सिस्टम** पेज पर, **स्थिति** टैब का चयन करें.

1. **डेटा स्रोत** खंड में, **प्रवाह** चुनें और ड्रॉपडाउन सूची से **एक प्रवाह बनाएँ** को चुनें.
   > [!div class="mx-imgBorder"]
   > ![Power Automate कनेक्टर फ़्लो क्रिया बनाएं दर्शा रहा है](media/power-automate-connector-create-flow.png "प्रवाह बनाएं कार्रवाई दर्शाता Power Automate कनेक्टर")

1. Power Automate में, अपना पसंदीदा प्रवाह बनाने के लिए उपलब्ध ट्रिगर में से एक को चुनें. यदि आप अपना पहला प्रवाह बना रहे हैं तो आपको पहले Power Automate कनेक्टर के साथ अनुप्रमाणन करना होगा.
