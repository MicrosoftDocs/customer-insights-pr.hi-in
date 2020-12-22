---
title: Power क्वेरी-आधारित डेटा स्रोतों के लिए वृद्धिशील रिफ़्रेश
description: Power Query पर आधारित बड़े डेटा स्रोतों के लिए नए और अद्यतन किए गए डेटा को रीफ़्रेश करें.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405956"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="ba9cd-103">Power Query पर आधारित डेटा स्रोतों के लिए वृद्धिशील रीफ़्रेश</span><span class="sxs-lookup"><span data-stu-id="ba9cd-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="ba9cd-104">डेटा स्रोतों के लिए वृद्धिशील रीफ़्रेश निम्न लाभ प्रदान करता है:</span><span class="sxs-lookup"><span data-stu-id="ba9cd-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="ba9cd-105">**तीव्र रिफ़्रेश** - केवल बदला गया डेटा रीफ़्रेश हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="ba9cd-106">उदाहरण के लिए, आप एक ऐतिहासिक डेटासेट के केवल पिछले पांच दिनों को रीफ़्रेश कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="ba9cd-107">**बढ़ी हुई विश्वसनीयता** - छोटे रीफ़्रेश के साथ, आपको कनेक्शन के मुद्दों के जोखिम को कम करने के लिए लंबे समय तक अस्थिर स्रोत प्रणालियों से कनेक्शन बनाए रखने की आवश्यकता नहीं है.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="ba9cd-108">**कम हुई संसाधन खपत** - आपके कुल डेटा का केवल एक सबसेट रीफ़्रेश करने से कंप्यूटिंग संसाधनों का अधिक कुशल उपयोग होता है और पर्यावरणीय पदचिह्न कम हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="ba9cd-109">इंक्रीमेंटल रिफ्रेश को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="ba9cd-109">Configure incremental refresh</span></span>

<span data-ttu-id="ba9cd-110">ऑडियंस इनसाइट्स Power क्वेरी के माध्यम से आयातित डेटा स्रोतों के लिए वृद्धिशील रिफ़्रेश की अनुमति देता है जो वृद्धिशील अंतर्ग्रहण का समर्थन करते हैं.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="ba9cd-111">उदाहरण के लिए, दिनांक और समय फ़ील्ड वाले Azure SQL डेटाबेस, जो दर्शाते हैं कि डेटा रिकॉर्ड अंतिम रूप से अपडेट किए गए थे.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="ba9cd-112">[Power Query पर आधारित नया डेटा स्रोत बनाएँ](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ba9cd-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="ba9cd-113">डेटा स्रोत के लिए नाम विवरण करें.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="ba9cd-114">एक डेटा स्रोत चुनें जो वृद्धिशील रीफ़्रेश का समर्थन करता है, जैसे कि Azure SQL डेटाबेस.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="ba9cd-115">इंजेस्ट करने के लिए निकायों या तालिकाओं का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="ba9cd-116">परिवर्तन चरणों को पूरा करें और **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="ba9cd-117">**वृद्धिशील रिफ़्रेश सेट अप** संवाद बॉक्स में, **वृद्धिशील रीफ़्रेश सेटिंग्स** खोलने के लिए **सेट अप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="ba9cd-118">यदि आप **छोड़ें** चुनते हैं, तो डेटा स्रोत संपूर्ण डेटा सेट को रीफ़्रेश करेगा.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="ba9cd-119">आप किसी मौजूदा डेटा स्रोत को संपादित करके बाद में वृद्धिशील रीफ़्रेश भी लागू कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="ba9cd-120">**वृद्धिशील रिफ़्रेश सेटिंग्स** पर, आप डेटा स्रोत बनाते समय आपके द्वारा चयनित सभी निकायों के लिए वृद्धिशील रीफ़्रेश कॉन्फ़िगर करेंगे.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba9cd-121">![वृद्धिशील रीफ़्रेश के लिए डेटा स्रोत में निकायों को कॉन्फ़िगर करें](media/incremental-refresh-settings.png "इन्क्रीमेंटल रीफ्रेश करने के लिए डेटा स्रोत में संस्थाओं को कॉन्फ़िगर करें")</span><span class="sxs-lookup"><span data-stu-id="ba9cd-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="ba9cd-122">एक निकाय चुनें और निम्नलिखित विवरण प्रदान करें:</span><span class="sxs-lookup"><span data-stu-id="ba9cd-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="ba9cd-123">**प्राथमिक कुंजी परिभाषित करें**: निकाय या तालिका के लिए प्राथमिक कुंजी चुनें.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="ba9cd-124">**अंतिम अपडेट" फ़ील्ड को परिभाषित करें**: यह फ़ील्ड केवल प्रकार दिनांक या समय की विशेषताओं को प्रदर्शित करेगी.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="ba9cd-125">एक विशेषता चुनें जो दर्शाती है कि रिकॉर्ड अंतिम बार कब अपडेट किए गए थे.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="ba9cd-126">इसका उपयोग वृद्धिशील रीफ़्रेश अवधि के भीतर आने वाले रिकॉर्ड की पहचान करने के लिए किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="ba9cd-127">**हर अपडेट के लिए जांच करें**: निर्दिष्ट करें कि आप किस समय तक वृद्धिशील रीफ़्रेश समय सीमा चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="ba9cd-128">डेटा स्रोत के निर्माण को पूरा करने के लिए **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="ba9cd-129">प्रारंभिक डेटा रीफ़्रेश पूरा रिफ़्रेश होगा.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="ba9cd-130">बाद में, वृद्धिशील डेटा रीफ़्रेश होता है जैसा कि पिछले चरण में कॉन्फ़िगर किया गया था.</span><span class="sxs-lookup"><span data-stu-id="ba9cd-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
