---
title: सेवा सीमाएँ
description: सीमाओं और प्रतिबंधों को समझें.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034866"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights में सेवा की सीमाएं ऑडियंस इनसाइट्स क्षमता को कम करती हैं

यह आलेख Customer Insights Service में उन अंतर्निहित सीमाओं का वर्णन करता है, जिन्हें सेवा की विश्वसनीयता और स्थिरता सुनिश्चित करने के लिए डिज़ाइन किया गया है. परिवर्तनों के लिए किसी भी अनुरोधों को [विचार फ़ोरम](https://go.microsoft.com/fwlink/?linkid=2074172) के माध्यम से बनाया जा सकता है. 
 
| क्षेत्र  | सीमाएँ  | नोट्स |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| खंड और माप | 100 सेगमेंट्स या उपाय. | सक्रिय [सेगमेंट्स](segments.md) और [उपाय](measures.md) की कुल संख्या 100 से अधिक नहीं हो सकती.  |
| संबंध | निकाय पथों में संबंधों पर गहराई के 20 स्तर. | बिल्डर इंटरफ़ेस का उपयोग करते हुए [सेगमेंट](segments.md) या [उपाय](measures.md) बनाते समय, निकाय पथ में प्रारंभ निकाय और लक्ष्य निकाय के बीच अधिकतम 20 संबंध हो सकते हैं.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]