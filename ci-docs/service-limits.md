---
title: Dynamics 365 Customer Insights में सेवा-सीमाएँ
description: सीमाओं और प्रतिबंधों को समझें.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641764"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights में सेवा सीमाएं

यह आलेख Customer Insights Service में उन अंतर्निहित सीमाओं का वर्णन करता है, जिन्हें सेवा की विश्वसनीयता और स्थिरता सुनिश्चित करने के लिए डिज़ाइन किया गया है. परिवर्तनों के लिए किसी भी अनुरोधों को [विचार फ़ोरम](https://go.microsoft.com/fwlink/?linkid=2074172) के माध्यम से बनाया जा सकता है. 

## <a name="customer-insights"></a>Customer Insights

| क्षेत्र  | सीमाएँ  | नोट्स |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| खंड, उपाय और भविष्यवाणियां | 300  | की कुल संख्या[खंडों](segments.md),[पैमाने](measures.md), और [भविष्यवाणियों](predictions.md) संयुक्त 300 से अधिक नहीं हो सकता।  |
| संबंध | निकाय पथों में संबंधों पर गहराई के 20 स्तर. | बिल्डर इंटरफ़ेस का उपयोग करते हुए [सेगमेंट](segments.md) या [उपाय](measures.md) बनाते समय, निकाय पथ में प्रारंभ निकाय और लक्ष्य निकाय के बीच अधिकतम 20 संबंध हो सकते हैं.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
