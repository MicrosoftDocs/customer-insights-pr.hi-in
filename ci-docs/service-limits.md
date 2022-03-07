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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350409"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights क्षमताएँ में सेवा सीमाएँ

यह आलेख Customer Insights Service में उन अंतर्निहित सीमाओं का वर्णन करता है, जिन्हें सेवा की विश्वसनीयता और स्थिरता सुनिश्चित करने के लिए डिज़ाइन किया गया है. परिवर्तनों के लिए किसी भी अनुरोधों को [विचार फ़ोरम](https://go.microsoft.com/fwlink/?linkid=2074172) के माध्यम से बनाया जा सकता है. 

## <a name="audience-insights"></a>ऑडिएंस इनसाइट

| क्षेत्र  | सीमाएँ  | नोट्स |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| खंड, उपाय और भविष्यवाणियां | 300  | की कुल संख्या[खंडों](audience-insights/segments.md),[उपायों](audience-insights/measures.md), तथा[भविष्यवाणियों](audience-insights/predictions.md) संयुक्त 300 से अधिक नहीं हो सकता।  |
| संबंध | निकाय पथों में संबंधों पर गहराई के 20 स्तर. | बिल्डर इंटरफ़ेस का उपयोग करते हुए [सेगमेंट](audience-insights/segments.md) या [उपाय](audience-insights/measures.md) बनाते समय, निकाय पथ में प्रारंभ निकाय और लक्ष्य निकाय के बीच अधिकतम 20 संबंध हो सकते हैं.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
