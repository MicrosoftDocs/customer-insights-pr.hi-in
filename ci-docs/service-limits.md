---
title: Dynamics 365 Customer Insights में सेवा-सीमाएँ
description: सीमाओं और प्रतिबंधों को समझें.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483673"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights क्षमताएँ में सेवा सीमाएँ

यह आलेख Customer Insights Service में उन अंतर्निहित सीमाओं का वर्णन करता है, जिन्हें सेवा की विश्वसनीयता और स्थिरता सुनिश्चित करने के लिए डिज़ाइन किया गया है. परिवर्तनों के लिए किसी भी अनुरोधों को [विचार फ़ोरम](https://go.microsoft.com/fwlink/?linkid=2074172) के माध्यम से बनाया जा सकता है. 

## <a name="audience-insights"></a>ऑडिएंस इनसाइट

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights में सेवा की सीमाएं ऑडियंस इनसाइट्स क्षमता को कम करती हैं

| क्षेत्र  | सीमाएँ  | नोट्स |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| खंड और माप | 100 सेगमेंट्स या उपाय. | सक्रिय [सेगमेंट्स](audience-insights/segments.md) और [उपाय](audience-insights/measures.md) की कुल संख्या 100 से अधिक नहीं हो सकती.  |
| संबंध | निकाय पथों में संबंधों पर गहराई के 20 स्तर. | बिल्डर इंटरफ़ेस का उपयोग करते हुए [सेगमेंट](audience-insights/segments.md) या [उपाय](audience-insights/measures.md) बनाते समय, निकाय पथ में प्रारंभ निकाय और लक्ष्य निकाय के बीच अधिकतम 20 संबंध हो सकते हैं.  |


## <a name="engagement-insights"></a>एन्गेजमेन्ट इनसाइट्स

### <a name="workspace-and-event-quotas"></a>कार्यक्षेत्र और ईवेंट कोटा

एंगेजमेंट इनसाइट्स एक उच्च मापनीय अनुप्रयोग है जो प्रति सेकंड लाखों ईवेंट्स का समर्थन कर सकती है. सार्वजनिक पूर्वावलोकन में, ईवेंट्स की वॉल्यूम सीमा होती है. एक संगठन में कार्यक्षेत्रों की संख्या की भी एक सीमा होती है.

### <a name="engagement-insights-limits"></a>एंगेजमेंट इनसाइट सीमा

- प्रति कार्यक्षेत्र अधिकतम इवेंट वॉल्यूम = प्रति सेकंड 100 इवेंट्स

- प्रति संगठन कार्यक्षेत्रों की अधिकतम संख्या = 100

जब इवेंट्स सीमा से अधिक होते हैं, तो इससे उन इवेंट्स के आधार पर रिपोर्ट में डेटा की हानि हो जा सकती है. आप सीमा से अधिक होने से पहले वॉल्यूम बढ़ाने का अनुरोध करने के लिए [सहायता से संपर्क](https://go.microsoft.com/fwlink/?linkid=2145734) कर सकते हैं. हम आपके साथ वॉल्यूम बढ़ाने की आपकी जरुरत निर्धारित करने और आपके अनुरोध का समर्थन करने के लिए काम करेंगे.


[!INCLUDE[footer-include](includes/footer-banner.md)]