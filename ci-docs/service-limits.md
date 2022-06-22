---
title: Customer Insights में सेवा सीमाएं
description: Customer Insights SaaS सेवा में सीमाओं और प्रतिबंधों को समझें।
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940670"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights में सेवा सीमाएं

यह आलेख Customer Insights Service में उन अंतर्निहित सीमाओं का वर्णन करता है, जिन्हें सेवा की विश्वसनीयता और स्थिरता सुनिश्चित करने के लिए डिज़ाइन किया गया है. परिवर्तनों के लिए किसी भी अनुरोधों को [विचार फ़ोरम](https://go.microsoft.com/fwlink/?linkid=2074172) के माध्यम से बनाया जा सकता है.

## <a name="customer-insights"></a>Customer Insights

| क्षेत्र  | सीमाएँ  | नोट्स |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| खंड, उपाय और भविष्यवाणियां | 300  | की कुल संख्या[खंडों](segments.md),[पैमाने](measures.md), तथा[भविष्यवाणियों](predictions.md) संयुक्त 300 से अधिक नहीं हो सकता।  |
| संबंध | निकाय पथों में संबंधों पर गहराई के 20 स्तर. | बिल्डर इंटरफ़ेस का उपयोग करते हुए [सेगमेंट](segments.md) या [उपाय](measures.md) बनाते समय, निकाय पथ में प्रारंभ निकाय और लक्ष्य निकाय के बीच अधिकतम 20 संबंध हो सकते हैं.  |

## <a name="fair-scheduling-of-jobs"></a>नौकरियों का उचित समय निर्धारण

Customer Insights एक SaaS सेवा है जो साझा Azure संसाधनों का उपयोग करती है। ग्राहकों के पास परिवर्तनशील तीव्रता और अलग-अलग शेड्यूल पर कार्यभार होता है। अंतर्निहित संसाधनों तक उचित पहुंच सुनिश्चित करने के लिए, हम सुनिश्चित करते हैं कि सिस्टम प्रक्रियाओं को उचित क्रम में निष्पादित किया जाता है। सिस्टम प्रक्रियाओं के उदाहरण डेटा एकीकरण, खंड अद्यतन, या माप गणना से संबंधित कार्य हैं। उचित समय-निर्धारण आपको संसाधनों के लिए कतार में लगने से बचाता है यदि अनुरोधित कार्यों की संख्या में वृद्धि होती है। साथ ही, Customer Insights इस बात की गारंटी नहीं देता कि आपके द्वारा कतारबद्ध सभी कार्यों को समानांतर में संसाधित किया जाता है।

[!INCLUDE [footer-include](includes/footer-banner.md)]
