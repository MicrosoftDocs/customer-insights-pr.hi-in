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
# <a name="data-unification-overview"></a><span data-ttu-id="097ca-103">डेटा एकीकरण अवलोकन</span><span class="sxs-lookup"><span data-stu-id="097ca-103">Data unification overview</span></span>

<span data-ttu-id="097ca-104">[डेटा स्रोतों को स्थापित करने](data-sources.md) के बाद, आप डेटा को एकजुट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="097ca-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="097ca-105">डेटा एकीकरण में तीन चरण शामिल हैं: **नक्शा**, **मिलान**, और **विलीन**।</span><span class="sxs-lookup"><span data-stu-id="097ca-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="097ca-106">डेटा एकीकरण प्रक्रिया आपको एकल मास्टर डेटासेट में एक बार डेटा स्रोतों को एकीकृत करने की सुविधा देती है जो आपके ग्राहकों के लिए एकीकृत दृश्य प्रदान करता है।</span><span class="sxs-lookup"><span data-stu-id="097ca-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="097ca-107">एकीकरण चरण अनिवार्य हैं, और निम्न क्रम में किए गए हैं:</span><span class="sxs-lookup"><span data-stu-id="097ca-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="097ca-108">मैप</span><span class="sxs-lookup"><span data-stu-id="097ca-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="097ca-109">Match</span><span class="sxs-lookup"><span data-stu-id="097ca-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="097ca-110">मर्ज करें</span><span class="sxs-lookup"><span data-stu-id="097ca-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="097ca-111">डेटा एकीकरण पूरा करने के बाद, आप वैकल्पिक रूप से</span><span class="sxs-lookup"><span data-stu-id="097ca-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="097ca-112">परिष्कृत सेगमेंट बनाने के लिए [निकायों के बीच संबंध स्थापित करें](relationships.md)</span><span class="sxs-lookup"><span data-stu-id="097ca-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="097ca-113">[अपने डेटा को समृद्ध करें](enrichment-hub.md) अपने ग्राहकों के बारे में व्यापक जानकारी प्राप्त करने के लिए</span><span class="sxs-lookup"><span data-stu-id="097ca-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="097ca-114">कुछ इन्जेस्ट किए गए विशेषताओं से [गतिविधियों को परिभाषित करें](activities.md)</span><span class="sxs-lookup"><span data-stu-id="097ca-114">[define activities](activities.md) from some of the ingested attributes</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]