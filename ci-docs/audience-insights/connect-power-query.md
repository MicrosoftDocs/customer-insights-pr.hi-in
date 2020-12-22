---
title: Power क्वेरी कनेक्टर के माध्यम से डेटा को इन्जेस्ट करें
description: Power Query पर आधारित डेटा स्रोतों के लिए कनेक्टर.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405945"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="d3721-103">Power Query डेटा स्रोत से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="d3721-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="d3721-104">Power Query डेटा इंजेस्ट करने के लिए कनेक्टर का एक व्यापक सेट प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="d3721-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="d3721-105">इनमें से अधिकांश कनेक्टर Dynamics 365 Customer Insights द्वारा समर्थित हैं.</span><span class="sxs-lookup"><span data-stu-id="d3721-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="d3721-106">Power Query कनेक्टर पर आधारित डेटा स्रोतों को जोड़ना आम तौर पर अगले भाग में उल्लिखित चरणों का पालन करता है.</span><span class="sxs-lookup"><span data-stu-id="d3721-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="d3721-107">हालांकि, आपके द्वारा उपयोग किए जाने वाले कनेक्टर के आधार पर, विभिन्न जानकारी की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="d3721-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="d3721-108">अधिक जानकारी के लिए, [Power Query कनेक्टर संदर्भ](https://docs.microsoft.com/power-query/connectors/) में व्यक्तिगत कनेक्टर के बारे में दस्तावेज़ देखें.</span><span class="sxs-lookup"><span data-stu-id="d3721-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="d3721-109">नया डेटा स्रोत बनाएँ</span><span class="sxs-lookup"><span data-stu-id="d3721-109">Create a new data source</span></span>

1. <span data-ttu-id="d3721-110">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="d3721-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="d3721-111">**डेटा स्रोत जोड़ें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="d3721-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="d3721-112">**डेटा आयात करें** विधि चुनें और **अगला** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d3721-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="d3721-113">डेटा स्रोत के लिए एक **नाम** प्रदान करें और डेटा स्रोत बनाने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d3721-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="d3721-114">[उपलब्ध कनेक्टरों](#available-power-query-data-sources) में से एक चुनें.</span><span class="sxs-lookup"><span data-stu-id="d3721-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="d3721-115">इस उदाहरण के लिए, हमने **पाठ/CSV** कनेक्टर चुना है.</span><span class="sxs-lookup"><span data-stu-id="d3721-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d3721-116">चयनित कनेक्टर के लिए **कनेक्शन सेटिंग** में आवश्यक विवरण दर्ज करें और डेटा का पूर्वावलोकन देखने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d3721-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="d3721-117">**डेटा स्थानांतरित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d3721-117">Select **Transform data**.</span></span> <span data-ttu-id="d3721-118">इस चरण में, आप अपने डेटा स्रोत में निकायों को जोड़ेंगे.</span><span class="sxs-lookup"><span data-stu-id="d3721-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="d3721-119">निकाय डेटासेट होते हैं.</span><span class="sxs-lookup"><span data-stu-id="d3721-119">Entities are datasets.</span></span> <span data-ttu-id="d3721-120">यदि आपके पास एक डेटाबेस है जिसमें कई डेटासेट शामिल हैं, तो प्रत्येक डेटासेट अपना निकाय है.</span><span class="sxs-lookup"><span data-stu-id="d3721-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="d3721-121">**Power Query - क्वेरी संपादित करें** संवाद आपकी डेटा की समीक्षा करने और उसे परिष्कृत करने में मदद करता है.</span><span class="sxs-lookup"><span data-stu-id="d3721-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="d3721-122">आपके चयनित डेटा स्रोत में सिस्टम द्वारा पहचाने गए निकाय बाएं फलक में दिखाई देते हैं.</span><span class="sxs-lookup"><span data-stu-id="d3721-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3721-123">![क्वेरी संपादित करें संवाद](media/data-manager-configure-edit-queries.png "क्वेरी संपादित करें संवाद")</span><span class="sxs-lookup"><span data-stu-id="d3721-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="d3721-124">आप अपना डेटा बदल भी सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d3721-124">You can also transform your data.</span></span> <span data-ttu-id="d3721-125">संपादित करने या बदलने के लिए एक निकाय का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d3721-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="d3721-126">रूपांतरण को लागू करने के लिए Power Query विंडो में विकल्पों का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="d3721-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="d3721-127">प्रत्येक रूपांतरण **लागू चरण** के तहत सूचीबद्ध हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="d3721-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="d3721-128">Power Query कई पूर्व-निर्मित रूपांतरण विकल्प प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="d3721-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="d3721-129">अधिक जानकारी के लिए, [Power Query रूपांतरण](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations) देखें.</span><span class="sxs-lookup"><span data-stu-id="d3721-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="d3721-130">आप **संपादित करें** संवाद में **डेटा प्राप्त करें** का चयन करके अपने डेटा स्रोत में अतिरिक्त निकाय जोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d3721-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="d3721-131">इन परिवर्तनों की अत्यधिक अनुशंसा की जाती है:</span><span class="sxs-lookup"><span data-stu-id="d3721-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="d3721-132">यदि आप CSV फ़ाइल से डेटा इंजेस्ट कर रहे हैं, तो पहली पंक्ति में अक्सर शीर्षलेख होते हैं.</span><span class="sxs-lookup"><span data-stu-id="d3721-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="d3721-133">**तालिका रूपांतरित करें** पर जाएँ और **पहली पंक्ति के रूप में शीर्षलेख का उपयोग करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d3721-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="d3721-134">सुनिश्चित करें कि डेटा प्रकार उचित रूप से सेट किया गया है.</span><span class="sxs-lookup"><span data-stu-id="d3721-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="d3721-135">रूपांतरणों को सहेजने के लिए Power Query विंडो के निचले भाग पर **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d3721-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="d3721-136">सहेजने के बाद, आप अपने डेटा स्रोत को **डेटा** > **डेटा स्रोत** पर देखेंगे.</span><span class="sxs-lookup"><span data-stu-id="d3721-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="d3721-137">**डेटा स्रोत** पृष्ठ, आप देखेंगे कि नया डेटा स्रोत **रीफ़्रेशिंग** स्थिति में है.</span><span class="sxs-lookup"><span data-stu-id="d3721-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="d3721-138">उपलब्ध Power Query डेटा स्रोत</span><span class="sxs-lookup"><span data-stu-id="d3721-138">Available Power Query data sources</span></span>

<span data-ttu-id="d3721-139">उन कनेक्टर की अप-टू-डेट सूची के लिए, जिन्हें आप Customer Insights को डेटा आयात करने के लिए चुन सकते हैं [Power Query कनेक्टर संदर्भ](https://docs.microsoft.com/power-query/connectors/) देखें.</span><span class="sxs-lookup"><span data-stu-id="d3721-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="d3721-140">**Customer Insights (डेटाप्रवाह)** स्तंभ में चेकमार्क वाले कनेक्टर Power Query पर आधारित नए डेटा स्रोतों को बनाने के लिए उपलब्ध हैं.</span><span class="sxs-lookup"><span data-stu-id="d3721-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="d3721-141">विशिष्ट कनेक्टर की पूर्वावश्यकताओं, सीमाओं और अन्य विवरणों के बारे में अधिक जानने के लिए उसके दस्तावेज़ की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="d3721-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="d3721-142">Power Query डेटा स्रोत संपादित करें</span><span class="sxs-lookup"><span data-stu-id="d3721-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="d3721-143">उन डेटा स्रोतों में परिवर्तन करना संभव नहीं हो सकता है जो वर्तमान में अनुप्रयोगों की प्रक्रियाओं (उदाहरण के लिए *विभाजन*, *मिलान* , या *विलीन*) में से एक में उपयोग किए जा रहे हैं.</span><span class="sxs-lookup"><span data-stu-id="d3721-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="d3721-144">**सेटिंग** पृष्ठ का उपयोग करके, आप सक्रिय प्रक्रियाओं में से प्रत्येक की प्रगति को देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d3721-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="d3721-145">जब कोई प्रक्रिया पूरी हो जाती है, तो आप **डेटा स्रोत** पृष्ठ पर वापस आ सकते हैं और अपने परिवर्तन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d3721-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="d3721-146">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="d3721-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d3721-147">जिस डेटा स्रोत को आप बदलना चाहते हैं, उसके बगल में दिये लंबवत एलिप्सिस का चयन करें और ड्रॉप-डाउन मेनू से **संपादित करें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="d3721-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3721-148">![संपादित करें विकल्प](media/edit-option-data-sources.png "संपादित करें विकल्प")</span><span class="sxs-lookup"><span data-stu-id="d3721-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="d3721-149">[एक नया डेटा स्रोत बनाएँ](#create-a-new-data-source) सेक्शन में वर्णित अनुसार अपने परिवर्तनों और रूपांतरणों को **Power Query - क्वेरी संपादित करें** संवाद में लागू करें.</span><span class="sxs-lookup"><span data-stu-id="d3721-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="d3721-150">अपने परिवर्तनों को सहेजने के लिए अपने संपादन को पूरा करने के बाद Power Query में **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d3721-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
