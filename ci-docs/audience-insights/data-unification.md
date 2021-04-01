---
title: डेटा एकीकरण
description: इन्जेस्ट किए गए डेटा को एकजुट करने का तरीका जानें.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 73d8006c670268420f8cd6a2b37cb214ba1bbd6c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597881"
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