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
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405929"
---
# <a name="data-unification"></a><span data-ttu-id="96abe-103">डेटा एकीकरण</span><span class="sxs-lookup"><span data-stu-id="96abe-103">Data unification</span></span>

<span data-ttu-id="96abe-104">[डेटा स्रोतों को स्थापित करने](data-sources.md) के बाद, आप डेटा को एकजुट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="96abe-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="96abe-105">डेटा एकीकरण में तीन चरण शामिल हैं: **नक्शा**, **मिलान**, और **विलीन**।</span><span class="sxs-lookup"><span data-stu-id="96abe-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="96abe-106">डेटा एकीकरण प्रक्रिया आपको एकल मास्टर डेटासेट में एक बार डेटा स्रोतों को एकीकृत करने की सुविधा देती है जो आपके ग्राहकों के लिए एकीकृत दृश्य प्रदान करता है।</span><span class="sxs-lookup"><span data-stu-id="96abe-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="96abe-107">एकीकरण चरण अनिवार्य हैं, और निम्न क्रम में किए गए हैं:</span><span class="sxs-lookup"><span data-stu-id="96abe-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="96abe-108">मैप</span><span class="sxs-lookup"><span data-stu-id="96abe-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="96abe-109">Match</span><span class="sxs-lookup"><span data-stu-id="96abe-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="96abe-110">मर्ज करें</span><span class="sxs-lookup"><span data-stu-id="96abe-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="96abe-111">डेटा एकीकरण पूरा करने के बाद, आप वैकल्पिक रूप से</span><span class="sxs-lookup"><span data-stu-id="96abe-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="96abe-112">परिष्कृत सेगमेंट बनाने के लिए [निकायों के बीच संबंध स्थापित करें](relationships.md)</span><span class="sxs-lookup"><span data-stu-id="96abe-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="96abe-113">[अपने डेटा को समृद्ध करें](enrichment-hub.md) अपने ग्राहकों के बारे में व्यापक जानकारी प्राप्त करने के लिए</span><span class="sxs-lookup"><span data-stu-id="96abe-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="96abe-114">कुछ इन्जेस्ट किए गए विशेषताओं से [गतिविधियों को परिभाषित करें](activities.md)</span><span class="sxs-lookup"><span data-stu-id="96abe-114">[define activities](activities.md) from some of the ingested attributes</span></span>
