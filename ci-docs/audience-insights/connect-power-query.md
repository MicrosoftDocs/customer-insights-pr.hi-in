---
title: Power क्वेरी कनेक्टर के माध्यम से डेटा को इन्जेस्ट करें
description: Power Query पर आधारित डेटा स्रोतों के लिए कनेक्टर.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267771"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="6fc91-103">Power Query डेटा स्रोत से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="6fc91-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="6fc91-104">Power Query डेटा इंजेस्ट करने के लिए कनेक्टर का एक व्यापक सेट प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="6fc91-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="6fc91-105">इनमें से अधिकांश कनेक्टर Dynamics 365 Customer Insights द्वारा समर्थित हैं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="6fc91-106">Power Query कनेक्टर पर आधारित डेटा स्रोतों को जोड़ना आम तौर पर अगले भाग में उल्लिखित चरणों का पालन करता है.</span><span class="sxs-lookup"><span data-stu-id="6fc91-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="6fc91-107">हालांकि, आपके द्वारा उपयोग किए जाने वाले कनेक्टर के आधार पर, विभिन्न जानकारी की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="6fc91-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="6fc91-108">अधिक जानकारी के लिए, [Power Query कनेक्टर संदर्भ](https://docs.microsoft.com/power-query/connectors/) में व्यक्तिगत कनेक्टर के बारे में दस्तावेज़ देखें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="6fc91-109">नया डेटा स्रोत बनाएँ</span><span class="sxs-lookup"><span data-stu-id="6fc91-109">Create a new data source</span></span>

1. <span data-ttu-id="6fc91-110">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="6fc91-111">**डेटा स्रोत जोड़ें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="6fc91-112">**डेटा आयात करें** विधि चुनें और **अगला** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="6fc91-113">डेटा स्रोत के लिए एक **नाम** प्रदान करें और डेटा स्रोत बनाने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="6fc91-114">नाम दिशानिर्देश:</span><span class="sxs-lookup"><span data-stu-id="6fc91-114">Name guidelines:</span></span> 
   - <span data-ttu-id="6fc91-115">अक्षर के साथ शुरू करें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-115">Start with a letter.</span></span>
   - <span data-ttu-id="6fc91-116">केवल अक्षर और संख्याओं का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-116">Use letters and numbers only.</span></span> <span data-ttu-id="6fc91-117">विशेष वर्ण और खाली जगह की अनुमति नहीं है.</span><span class="sxs-lookup"><span data-stu-id="6fc91-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="6fc91-118">3 से 64 वर्णों के बीच उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="6fc91-119">[उपलब्ध कनेक्टरों](#available-power-query-data-sources) में से एक चुनें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="6fc91-120">इस उदाहरण के लिए, हमने **पाठ/CSV** कनेक्टर चुना है.</span><span class="sxs-lookup"><span data-stu-id="6fc91-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6fc91-121">चयनित कनेक्टर के लिए **कनेक्शन सेटिंग** में आवश्यक विवरण दर्ज करें और डेटा का पूर्वावलोकन देखने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="6fc91-122">**डेटा स्थानांतरित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-122">Select **Transform data**.</span></span> <span data-ttu-id="6fc91-123">इस चरण में, आप अपने डेटा स्रोत में निकायों को जोड़ेंगे.</span><span class="sxs-lookup"><span data-stu-id="6fc91-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="6fc91-124">निकाय डेटासेट होते हैं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-124">Entities are datasets.</span></span> <span data-ttu-id="6fc91-125">यदि आपके पास एक डेटाबेस है जिसमें कई डेटासेट शामिल हैं, तो प्रत्येक डेटासेट अपना निकाय है.</span><span class="sxs-lookup"><span data-stu-id="6fc91-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="6fc91-126">**Power Query - क्वेरी संपादित करें** संवाद आपकी डेटा की समीक्षा करने और उसे परिष्कृत करने में मदद करता है.</span><span class="sxs-lookup"><span data-stu-id="6fc91-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="6fc91-127">आपके चयनित डेटा स्रोत में सिस्टम द्वारा पहचाने गए निकाय बाएं फलक में दिखाई देते हैं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6fc91-128">![क्वेरी संपादित करें संवाद](media/data-manager-configure-edit-queries.png "क्वेरी संपादित करें संवाद")</span><span class="sxs-lookup"><span data-stu-id="6fc91-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="6fc91-129">आप अपना डेटा बदल भी सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-129">You can also transform your data.</span></span> <span data-ttu-id="6fc91-130">संपादित करने या बदलने के लिए एक निकाय का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="6fc91-131">रूपांतरण को लागू करने के लिए Power Query विंडो में विकल्पों का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="6fc91-132">प्रत्येक रूपांतरण **लागू चरण** के तहत सूचीबद्ध हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="6fc91-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="6fc91-133">Power Query कई पूर्व-निर्मित रूपांतरण विकल्प प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="6fc91-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="6fc91-134">अधिक जानकारी के लिए, [Power Query रूपांतरण](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations) देखें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-134">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="6fc91-135">आप **संपादित करें** संवाद में **डेटा प्राप्त करें** का चयन करके अपने डेटा स्रोत में अतिरिक्त निकाय जोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="6fc91-136">इन परिवर्तनों की अत्यधिक अनुशंसा की जाती है:</span><span class="sxs-lookup"><span data-stu-id="6fc91-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="6fc91-137">यदि आप CSV फ़ाइल से डेटा इंजेस्ट कर रहे हैं, तो पहली पंक्ति में अक्सर शीर्षलेख होते हैं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="6fc91-138">**तालिका रूपांतरित करें** पर जाएँ और **पहली पंक्ति के रूप में शीर्षलेख का उपयोग करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="6fc91-139">सुनिश्चित करें कि डेटा प्रकार उचित रूप से सेट किया गया है.</span><span class="sxs-lookup"><span data-stu-id="6fc91-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="6fc91-140">रूपांतरणों को सहेजने के लिए Power Query विंडो के निचले भाग पर **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="6fc91-141">सहेजने के बाद, आप अपने डेटा स्रोत को **डेटा** > **डेटा स्रोत** पर देखेंगे.</span><span class="sxs-lookup"><span data-stu-id="6fc91-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="6fc91-142">**डेटा स्रोत** पृष्ठ, आप देखेंगे कि नया डेटा स्रोत **रीफ़्रेशिंग** स्थिति में है.</span><span class="sxs-lookup"><span data-stu-id="6fc91-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="6fc91-143">उपलब्ध Power Query डेटा स्रोत</span><span class="sxs-lookup"><span data-stu-id="6fc91-143">Available Power Query data sources</span></span>

<span data-ttu-id="6fc91-144">उन कनेक्टर की अप-टू-डेट सूची के लिए, जिन्हें आप Customer Insights को डेटा आयात करने के लिए चुन सकते हैं [Power Query कनेक्टर संदर्भ](https://docs.microsoft.com/power-query/connectors/) देखें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-144">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="6fc91-145">**Customer Insights (डेटाप्रवाह)** स्तंभ में चेकमार्क वाले कनेक्टर Power Query पर आधारित नए डेटा स्रोतों को बनाने के लिए उपलब्ध हैं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="6fc91-146">विशिष्ट कनेक्टर की पूर्वावश्यकताओं, सीमाओं और अन्य विवरणों के बारे में अधिक जानने के लिए उसके दस्तावेज़ की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="6fc91-147">Power Query डेटा स्रोत संपादित करें</span><span class="sxs-lookup"><span data-stu-id="6fc91-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="6fc91-148">उन डेटा स्रोतों में परिवर्तन करना संभव नहीं हो सकता है जो वर्तमान में अनुप्रयोगों की प्रक्रियाओं (उदाहरण के लिए *विभाजन*, *मिलान* , या *विलीन*) में से एक में उपयोग किए जा रहे हैं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="6fc91-149">**सेटिंग** पृष्ठ का उपयोग करके, आप सक्रिय प्रक्रियाओं में से प्रत्येक की प्रगति को देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="6fc91-150">जब कोई प्रक्रिया पूरी हो जाती है, तो आप **डेटा स्रोत** पृष्ठ पर वापस आ सकते हैं और अपने परिवर्तन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="6fc91-151">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="6fc91-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6fc91-152">जिस डेटा स्रोत को आप बदलना चाहते हैं, उसके बगल में दिये लंबवत एलिप्सिस का चयन करें और ड्रॉप-डाउन मेनू से **संपादित करें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6fc91-153">![संपादित करें विकल्प](media/edit-option-data-sources.png "संपादित करें विकल्प")</span><span class="sxs-lookup"><span data-stu-id="6fc91-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="6fc91-154">[एक नया डेटा स्रोत बनाएँ](#create-a-new-data-source) सेक्शन में वर्णित अनुसार अपने परिवर्तनों और रूपांतरणों को **Power Query - क्वेरी संपादित करें** संवाद में लागू करें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="6fc91-155">अपने परिवर्तनों को सहेजने के लिए अपने संपादन को पूरा करने के बाद Power Query में **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6fc91-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]