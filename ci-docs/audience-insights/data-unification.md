---
title: डेटा एकीकरण
description: इन्जेस्ट किए गए डेटा को एकजुट करने का तरीका जानें.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 44f97696ec91dc488dd6a7528e186abb99c8288b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269654"
---
# <a name="data-unification-overview"></a>डेटा एकीकरण अवलोकन

[डेटा स्रोतों को स्थापित करने](data-sources.md) के बाद, आप डेटा को एकजुट कर सकते हैं. डेटा एकीकरण में तीन चरण शामिल हैं: **नक्शा**, **मिलान**, और **विलीन**।

डेटा एकीकरण प्रक्रिया आपको एकल मास्टर डेटासेट में एक बार डेटा स्रोतों को एकीकृत करने की सुविधा देती है जो आपके ग्राहकों के लिए एकीकृत दृश्य प्रदान करता है। एकीकरण चरण अनिवार्य हैं, और निम्न क्रम में किए गए हैं:

1. [मैप](map-entities.md)
2. [Match](match-entities.md)
3. [मर्ज करें](merge-entities.md)

डेटा एकीकरण पूरा करने के बाद, आप वैकल्पिक रूप से

- परिष्कृत सेगमेंट बनाने के लिए [निकायों के बीच संबंध स्थापित करें](relationships.md)
- [अपने डेटा को समृद्ध करें](enrichment-hub.md) अपने ग्राहकों के बारे में व्यापक जानकारी प्राप्त करने के लिए
- कुछ इन्जेस्ट किए गए विशेषताओं से [गतिविधियों को परिभाषित करें](activities.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]