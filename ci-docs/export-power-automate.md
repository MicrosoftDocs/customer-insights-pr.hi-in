---
title: Power Automate कनेक्टर (पूर्वावलोकन) | माइक्रोसॉफ्ट डॉक्स
description: Dynamics 365 Customer Insights से Microsoft Power Automate में प्रवाह बनाएं.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196120"
---
# <a name="power-automate-connector-preview"></a>Power Automate कनेक्टर (पूर्वावलोकन)

जब आपके डेटा में परिवर्तन होता है तो स्वचलित रूप से होने वाली विशिष्ट इवेंट स्वतः होने लगती हैं और [Microsoft Power Automate](https://flow.microsoft.com/) में होने वाले प्रत्यक्ष जटिल प्रवाह को प्रबंधित करती हैं.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- प्रति 60 सेकंड में अधिकतम 100 कॉल। उपयोग [$स्किप पैरामीटर](/connectors/customerinsights/#get-items-from-an-entity) एपीआई एंडपॉइंट को कई बार कॉल करने के लिए।

## <a name="power-automate-triggers"></a>Power Automate ट्रिगर्स

क्लाउड प्रवाह बनाने के लिए ट्रिगर का उपयोग करें और बार-बार किए जाने वाले कार्यों को स्वचालित करें, जैसे सूचनाएं या अधिक एडवांस्ड एक्शन. ट्रिगर का उपयोग करें जब:

- एक डेटा स्रोत रीफ़्रेश विफल हो जाता है।
- एक डेटा स्रोत रिफ्रेश सफल होता है।
- एक खंड पर एक सीमा पार की जाती है। ट्रिगर सीमा के ऊपर जाने तक सीमित है.
- एक व्यावसायिक उपाय पर एक सीमा पार की जाती है। केवल बिना आयाम वाले व्यावसायिक उपाय समर्थित हैं. ट्रिगर सीमा के ऊपर जाने तक सीमित है.
- एक पूर्ण शेड्यूल्ड रीफ़्रेश पूरा हो गया है। यह ट्रिगर मैन्युअल रूप से शुरू किए गए रीफ़्रेश के लिए काम नहीं करता है।
- एकीकरण प्रक्रिया का एक ताज़ा पूरा हो गया है।

[Power Automate में अपने ट्रिगर कॉन्फ़िगर करें।](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate कार्रवाइयां

Power Automate कनेक्टर उपलब्ध ट्रिगर्स से अलग कार्रवाइयां प्रदान करता है. अधिक जानकारी के लिए, [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/) देखें.

## <a name="create-a-power-automate-flow"></a>एक Power Automate प्रवाह बनाएँ

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. **Power Automate** टाइल पर, **सेट अप** का चयन करें.

1. Power Automate में Customer Insights कनेक्टर (पूर्वावलोकन) खुलता है. Power Automate से **साइन इन** करें.

1. उपलब्ध ट्रिगर में से किसी एक को चुनें और अपने नए प्रवाह में और चरण जोड़ें. अधिक जानकारी के लिए, [Power Automate में क्लाउड प्रवाह बनाएं](/power-automate/get-started-logic-flow) देखें.

प्रवाह का उपयोग करने के उदाहरण: 
- यदि डेटा स्रोत रीफ्रेश विफल रहता है, तो Microsoft Teams चैनल पर एक संदेश पोस्ट करें. 
- जब एक सेगमेंट पर सीमा पार हो जाती है, तो डेटा मालिकों को एक ईमेल भेजें.

[!INCLUDE [footer-include](includes/footer-banner.md)]
