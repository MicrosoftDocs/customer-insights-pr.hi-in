---
title: ग्राहक की प्रोफाइल देखें
description: अपने एकीकृत ग्राहक डेटा का संयुक्त दृश्य प्राप्त करें.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596869"
---
# <a name="customer-profiles"></a><span data-ttu-id="4d74a-103">ग्राहक के प्रोफाइल</span><span class="sxs-lookup"><span data-stu-id="4d74a-103">Customer profiles</span></span>

<span data-ttu-id="4d74a-104">[सभी डेटा स्रोत](data-sources.md) से एकत्र किए गए प्रोफ़ाइल डेटा के आधार पर **ग्राहक** पेज आपके ग्राहकों का संयुक्त दृश्य दिखाता है.</span><span class="sxs-lookup"><span data-stu-id="4d74a-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="4d74a-105">आपके द्वारा [create the unified Customer entity](data-unification.md) करने के बाद ग्राहक प्रोफ़ाइल उपलब्ध हो जाती हैं.</span><span class="sxs-lookup"><span data-stu-id="4d74a-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="4d74a-106">सुनिश्चित करें कि आप अपने ग्राहकों के बेहतर दृश्य प्राप्त करने के लिए एकीकरण प्रक्रिया पूरी कर लेते हैं.</span><span class="sxs-lookup"><span data-stu-id="4d74a-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="4d74a-107">पेज से आप ग्राहकों की खोज भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="4d74a-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="4d74a-108">ग्राहक, व्यक्ति या संगठन (पूर्वावलोकन करें) हो सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="4d74a-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="4d74a-109">हर एक ग्राहक या संगठन प्रोफ़ाइल को टाइल द्वारा प्रदर्शित किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="4d74a-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="4d74a-110">उस ख़ास ग्राहक या संगठन के बारे में और जानकारी देखने के लिए किसी टाइल का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="4d74a-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="4d74a-111">पेज के निचले भाग में दिए गए पेजिनेशन नियंत्रणों का उपयोग अतिरिक्त रिकॉर्ड देखने के लिए करें.</span><span class="sxs-lookup"><span data-stu-id="4d74a-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="4d74a-112">![B2C ग्राहक की प्रोफाइलें](media/profiles-customers.png "B2C ग्राहक की प्रोफाइलें")</span><span class="sxs-lookup"><span data-stu-id="4d74a-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="4d74a-113">संगठन (पूर्वावलोकन करें)</span><span class="sxs-lookup"><span data-stu-id="4d74a-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="4d74a-114">![B2B ग्राहक की प्रोफाइलें](media/profile-customers-b2b.png "B2B ग्राहक की प्रोफाइलें")</span><span class="sxs-lookup"><span data-stu-id="4d74a-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="4d74a-115">यदि आप नेविगेशन में **ग्राहक** का चयन करते समय टाइल्स नहीं देख सकते हैं, तो आपके व्यवस्थापक को **खोज और फ़िल्टर इंडेक्स** पर [कम से कम एक खोज योग्य एट्रिब्यूट निर्धारित करने की आवश्यकता है](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="4d74a-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="4d74a-116">ग्राहक के लिए खोजें</span><span class="sxs-lookup"><span data-stu-id="4d74a-116">Search for customers</span></span>

<span data-ttu-id="4d74a-117">खोज बॉक्स में कोई नाम या कुछ अन्य विशेषता दर्ज करके ग्राहकों के लिए खोज करें.</span><span class="sxs-lookup"><span data-stu-id="4d74a-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="4d74a-118">खोज केवल डेटा एकीकरण प्रक्रिया के दौरान बनाई गई ग्राहक प्रोफ़ाइल इकाई के अंतर्गत ही काम करती है.</span><span class="sxs-lookup"><span data-stu-id="4d74a-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="4d74a-119">व्यवस्थापक के तौर पर, आप **इंडेक्स खोजें और फिल्टर करें** पेज का उपयोग करके खोजने योग्य विशेषताओं को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="4d74a-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="4d74a-120">अधिक जानकारी के लिए, [खोजें और फ़िल्टर इंडेक्स प्रबंधित करें](search-filter-index.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="4d74a-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="4d74a-121">फ़िल्टर ग्राहक</span><span class="sxs-lookup"><span data-stu-id="4d74a-121">Filter customers</span></span>

<span data-ttu-id="4d74a-122">आप ग्राहक प्रोफ़ाइल इकाई फ़ील्ड के अनुसार ग्राहकों को फ़िल्टर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="4d74a-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="4d74a-123">खोज के समान ही, आपके व्यवस्थापक को पहले **इंडेक्स खोजें और फिल्टर करें** पेज का उपयोग करके फ़ील्ड को फ़िल्टर करने योग्य के तौर पर निर्धारित करना होगा.</span><span class="sxs-lookup"><span data-stu-id="4d74a-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="4d74a-124">**ग्राहक** पेज पर **फ़िल्टर** चुनें.</span><span class="sxs-lookup"><span data-stu-id="4d74a-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="4d74a-125">उन विशेषताओं के आगे दिए गए बॉक्सेस को चेक करें जिनके अनुसार आप ग्राहकों को फ़िल्टर करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="4d74a-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="4d74a-126">![ग्राहक के प्रोफाइल](media/profiles-customers3.png "ग्राहक के प्रोफाइल")</span><span class="sxs-lookup"><span data-stu-id="4d74a-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="4d74a-127">**ग्राहक** पेज पर **फ़िल्टर साफ करें** का चयन करके अपने फ़िल्टर हटाएं.</span><span class="sxs-lookup"><span data-stu-id="4d74a-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="4d74a-128">ग्राहक विवरण पृष्ठ</span><span class="sxs-lookup"><span data-stu-id="4d74a-128">Customer details page</span></span>

<span data-ttu-id="4d74a-129">**ग्राहक विवरण पेज** खोलने के लिए किसी भी ग्राहक टाइल्स का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="4d74a-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="4d74a-130">इस दृश्य में चयनित ग्राहक के लिए एकीकृत जानकारी शामिल है.</span><span class="sxs-lookup"><span data-stu-id="4d74a-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="4d74a-131">ग्राहक विवरण में शामिल हैं:</span><span class="sxs-lookup"><span data-stu-id="4d74a-131">Customer details include:</span></span>

-   <span data-ttu-id="4d74a-132">**ग्राहक की प्रोफ़ाइल टाइल:** यह टाइल एकीकृत ग्राहक प्रोफ़ाइल निकाय से विभिन्न मानों को दर्शाता है.</span><span class="sxs-lookup"><span data-stu-id="4d74a-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="4d74a-133">इन विवरणों में ईमेल पता, नाम, शहर आदि शामिल हो सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="4d74a-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="4d74a-134">**संभावित रुचियां, संभावित ब्रांड:** यदि आपने पहले पक्ष के एनरिचमेंट को कॉन्फ़िगर किया है तो दिखाता है.</span><span class="sxs-lookup"><span data-stu-id="4d74a-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="4d74a-135">यह इस ग्राहक के समान प्रोफ़ाइल वाले ग्राहक ब्रांडों के लिए संभावित हितों और आकर्षणों का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="4d74a-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="4d74a-136">अधिक जानकारी के लिए [ब्रांड और रुचि घनिष्‍ठताओं के साथ ग्राहक प्रोफ़ाइल को समृद्ध बनाएँ](enrichment-microsoft-graph.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="4d74a-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="4d74a-137">**साधन:** यदि आप किसी विशिष्ट प्रकार के एक या अधिक साधनों को कॉन्फ़िगर करते हैं: ग्राहक विशेषता के साधन,तो दिखाता है.</span><span class="sxs-lookup"><span data-stu-id="4d74a-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="4d74a-138">वे व्यक्तिगत ग्राहक स्तर पर आपके ग्राहकों के आसपास की गणना की गई KPI शामिल करते हैं.</span><span class="sxs-lookup"><span data-stu-id="4d74a-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="4d74a-139">अधिक जानकारी के लिए, [साधनों को परिभाषित और प्रबंधित करें](measures.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="4d74a-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="4d74a-140">**गतिविधि टाइमलाइन:** अगर आपने कॉन्फ़िगर की गई गतिविधियां हैं, तो दिखाता है.</span><span class="sxs-lookup"><span data-stu-id="4d74a-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="4d74a-141">टाइमलाइन व्यू में सबसे हालिया गतिविधि से शुरू होकर इस ग्राहक की क्रोनोलॉजिकल क्रमबद्ध गतिविधियां शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="4d74a-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="4d74a-142">अधिक जानकारी के लिए, [ग्राहक गतिविधियाँ](activities.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="4d74a-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="4d74a-143">ग्राहक खोज पेज पर लौटने के लिए **ग्राहक की ओर वापस** चुनें.</span><span class="sxs-lookup"><span data-stu-id="4d74a-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d74a-144">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="4d74a-144">Next steps</span></span>

<span data-ttu-id="4d74a-145">[अधिक डेटा स्रोत जोड़ें](data-sources.md) या [ग्राहक खंड बनाएं](segments.md).</span><span class="sxs-lookup"><span data-stu-id="4d74a-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]