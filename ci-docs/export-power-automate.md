---
title: Power Automate कनेक्टर | Microsoft Docs
description: Dynamics 365 Customer Insights से Microsoft Power Automate में प्रवाह बनाएं.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741181"
---
# <a name="power-automate-connector-preview"></a>Power Automate कनेक्टर (पूर्वावलोकन)

जब आपके डेटा में परिवर्तन होता है तो स्वचलित रूप से होने वाली विशिष्ट इवेंट स्वतः होने लगती हैं और [Power Automate](https://flow.microsoft.com/) में होने वाले प्रत्यक्ष जटिल प्रवाह को प्रबंधित करती हैं.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- आप प्रति 60 सेकंड में अधिकतम 100 कॉल कर सकते हैं। आप $स्किप पैरामीटर का उपयोग करके API एंडपॉइंट को कई बार कॉल कर सकते हैं। [$स्किप पैरामीटर के बारे में और जानें।](/connectors/customerinsights/#get-items-from-an-entity)

## <a name="power-automate-triggers"></a>Power Automate ट्रिगर्स

क्लाउड प्रवाह बनाने के लिए ट्रिगर का उपयोग करें और बार-बार किए जाने वाले कार्यों को स्वचालित करें, जैसे सूचनाएं या अधिक एडवांस्ड एक्शन.

- ट्रिगर जब डेटा स्रोत रिफ़्रेश विफल रहता है.
- ट्रिगर जब डेटा स्रोत रिफ़्रेश सफल होता है.
- ट्रिगर जब अनुभाग की सीमा पार की जाती है. ट्रिगर सीमा के ऊपर जाने तक सीमित है.
- ट्रिगर जब व्यावसायिक उपाय सीमा के पार हो जाता है. केवल बिना आयाम वाले व्यावसायिक उपाय समर्थित हैं. ट्रिगर सीमा के ऊपर जाने तक सीमित है.
- ट्रिगर करें, जब (डेटा स्रोतों, खंडों, साधनों, ...) का पूरा रिफ़्रेश पूरा हो जाता है.
- एकीकरण प्रक्रिया का एक ताज़ा पूरा होने पर ट्रिगर करें।

[Power Automate में अपने ट्रिगर कॉन्फ़िगर करें।](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate कार्रवाइयां

Power Automate कनेक्टर उपलब्ध ट्रिगर्स से अलग कार्रवाइयां प्रदान करता है. अधिक जानकारी के लिए, [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/) देखें.

## <a name="create-a-power-automate-flow"></a>एक Power Automate प्रवाह बनाएँ

1. **व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.

1. **Power Automate** टाइल पर, **सेट अप** का चयन करें.

1. Power Automate में Customer Insights कनेक्टर (पूर्वावलोकन) खुलता है. Power Automate से **साइन इन** करें.

1. उपलब्ध ट्रिगर में से किसी एक को चुनें और अपने नए प्रवाह में और चरण जोड़ें. अधिक जानकारी के लिए, [Power Automate में क्लाउड प्रवाह बनाएं](/power-automate/get-started-logic-flow) देखें.

प्रवाह का उपयोग करने के उदाहरण: 
- यदि डेटा स्रोत रीफ्रेश विफल रहता है, तो Microsoft Teams चैनल पर एक संदेश पोस्ट करें. 
- जब एक सेगमेंट पर सीमा पार हो जाती है, तो डेटा मालिकों को एक ईमेल भेजें.



[!INCLUDE [footer-include](includes/footer-banner.md)]
