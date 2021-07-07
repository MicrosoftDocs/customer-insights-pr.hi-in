---
title: Customer Insights से डेटा निर्यात करें
description: डेटा साझा करने के लिए निर्यात का प्रबंधन करें.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305480"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="e12e9-103">निर्यात (पूर्वावलोकन) अवलोकन</span><span class="sxs-lookup"><span data-stu-id="e12e9-103">Exports (preview) overview</span></span>

<span data-ttu-id="e12e9-104">**निर्यात** पृष्ठ आपको सभी कॉन्फ़िगर किए गए निर्यात को दिअकाउंट है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="e12e9-105">निर्यात, विभिन्न अनुप्रयोगों के साथ विशिष्ट डेटा साझा करते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="e12e9-106">वे ग्राहक प्रोफ़ाइल या निकायों, स्कीमा, और मैपिंग के विवरण शामिल कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="e12e9-107">प्रत्येक निर्यात को [प्रमाणीकरण और एक्सेस के प्रबंधन के लिए एक व्यवस्थापक द्वारा सेट की गई एक कनेक्शन](connections.md) की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="e12e9-108">निर्यात पृष्ठ को देखने के लिए **डेटा** > **निर्यात** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="e12e9-109">सभी उपयोगकर्ता भूमिकाएं कॉन्फ़िगर किए गए निर्यात देख सकती हैं।</span><span class="sxs-lookup"><span data-stu-id="e12e9-109">All user roles can view configured exports.</span></span> <span data-ttu-id="e12e9-110">निर्यात को उनके नाम, कनेक्शन नाम, या कनेक्शन प्रकार से खोजने के लिए आदेश पट्टी में खोज फ़ील्ड का उपयोग करें।</span><span class="sxs-lookup"><span data-stu-id="e12e9-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="e12e9-111">एक नया निर्यात सेट करें</span><span class="sxs-lookup"><span data-stu-id="e12e9-111">Set up a new export</span></span>

<span data-ttu-id="e12e9-112">किसी निर्यात को सेट या संपादित करने के लिए, आपके पास कनेक्शन उपलब्ध होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="e12e9-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="e12e9-113">कनेक्शन आपके [उपयोगकर्ता भूमिका](permissions.md) पर निर्भर करते हैं:</span><span class="sxs-lookup"><span data-stu-id="e12e9-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="e12e9-114">व्यवस्थापकों के पास सभी कनेक्शनों तक एक्सेस है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-114">Administrators have access to all connections.</span></span> <span data-ttu-id="e12e9-115">किसी निर्यात को सेट करते वक्त वे नए कनेक्शन भी बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="e12e9-116">योगदानकर्ताओं के पास विशिष्ट कनेक्शन तक एक्सेस हो सकती है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="e12e9-117">वे कनेक्शनों को कॉन्फ़िगर करने और साझा करने के लिए व्यवस्थापकों पर निर्भर करते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="e12e9-118">निर्यात सूची योगदानकर्ताओं को दिखाती है कि क्या वे संपादित कर सकते हैं या केवल **आपकी अनुमतियां** कॉलम में निर्यात देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="e12e9-119">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e12e9-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="e12e9-120">दर्शक केवल मौजूदा निर्यात देख सकते हैं लेकिन उन्हें बना नहीं सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="e12e9-121">एक नया निर्यात परिभाषित करें</span><span class="sxs-lookup"><span data-stu-id="e12e9-121">Define a new export</span></span>

1. <span data-ttu-id="e12e9-122">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="e12e9-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e12e9-123">एक नया निर्यात बनाने के लिए, **निर्यात जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="e12e9-124">**निर्यात सेट अप करें** फलक में, उपयोग में आने वाले कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="e12e9-125">[कनेक्शन](connections.md) व्यवस्थापकों द्वारा प्रबंधित किए गए हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="e12e9-126">आवश्यक विवरण प्रदान करें और निर्यात बनाने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="e12e9-127">मौजूदा निर्यात के आधार पर एक नया निर्यात परिभाषित करें</span><span class="sxs-lookup"><span data-stu-id="e12e9-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="e12e9-128">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="e12e9-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e12e9-129">निर्यातों की सूची में, उस निर्यात को चुनें, जिसे आप डुप्लिकेट करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="e12e9-130">चयनित निर्यात के विवरण के साथ **निर्यात सेट करें** फलक को खोलने के लिए कमांड बार में **डुप्लिकेट बनाएं** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="e12e9-131">निर्यात की समीक्षा करें और उसे अनुकूलित करें और नया निर्यात बनाने के लिए **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="e12e9-132">निर्यात को संपादित करें</span><span class="sxs-lookup"><span data-stu-id="e12e9-132">Edit an export</span></span>

1. <span data-ttu-id="e12e9-133">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="e12e9-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e12e9-134">निर्यातों की सूची में, उस निर्यात को चुनें, जिसे आप संपादित करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="e12e9-135">कमांड बार में **संपादित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="e12e9-136">उन मानों को बदलें जिसे आप अपडेट करना चाहते हैं और **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="e12e9-137">निर्यात और निर्यात के विवरण देखें</span><span class="sxs-lookup"><span data-stu-id="e12e9-137">View exports and export details</span></span>

<span data-ttu-id="e12e9-138">निर्यात डेस्टिनेशन बनाने के बाद, उन्हें **डेटा** > **निर्यात** पर सूचीबद्ध किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="e12e9-139">सभी उपयोगकर्ता साझा किए गए डेटा और इसकी नवीनतम स्थिति को देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="e12e9-140">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="e12e9-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e12e9-141">बिना संपादन अनुमति वाले उपयोगकर्ता, निर्यात विवरण देखने के लिए **संपादित करें** के बजाय **दृश्य** चुनें।</span><span class="sxs-lookup"><span data-stu-id="e12e9-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="e12e9-142">साइड फलक, निर्यात की कॉन्फ़िगरेशन दिखाता है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="e12e9-143">संपादन की अनुमतियों के बिना, आप मानों को नहीं बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="e12e9-144">निर्यात पृष्ठ पर लौटने के लिए **बंद करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="e12e9-145">निर्यातों को शेड्यूल और रन करें</span><span class="sxs-lookup"><span data-stu-id="e12e9-145">Schedule and run exports</span></span>

<span data-ttu-id="e12e9-146">आपके द्वारा कॉन्फ़िगर किए गए प्रत्येक निर्यात का एक रीफ़्रेश शेड्यूल होता है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="e12e9-147">रीफ़्रेश के दौरान, सिस्टम, निर्यात में शामिल करने के लिए नए या अपडेट किए गए डेटा की तलाश करता है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="e12e9-148">डिफ़ॉल्ट रूप से, निर्यात प्रत्येक [शेड्यूल्ड सिस्टम रिफ्रेश](system.md#schedule-tab) के हिस्से के रूप में रन किए जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e12e9-149">मैन्युअल रूप से निर्यातों को रन करने के लिए आप रीफ़्रेश शेड्यूल को कस्टमाइज़ कर सकते हैं या इसे बंद कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="e12e9-150">निर्यात शेड्यूल आपके परिवेश की स्थिति पर निर्भर करते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="e12e9-151">यदि [निर्भरता](system.md#refresh-policies) पर अपडेट जारी हैं जब एक अनुसूचित निर्यात शुरू होना चाहिए, तो सिस्टम पहले अद्यतनों को पूरा करेगा और फिर निर्यात चलाएगा।</span><span class="sxs-lookup"><span data-stu-id="e12e9-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="e12e9-152">आप **रीफ़्रेश किया गया** कॉलम में देख सकते हैं कि निर्यात को आखिरी बार कब रीफ्रेश किया गया था.</span><span class="sxs-lookup"><span data-stu-id="e12e9-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="e12e9-153">निर्यातों को शेड्यूल करें</span><span class="sxs-lookup"><span data-stu-id="e12e9-153">Schedule exports</span></span>

<span data-ttu-id="e12e9-154">आप एक बार में व्यक्तिगत निर्यातों या एक साथ कई निर्यातों के लिए कस्टम रीफ्रेश शेड्यूल परिभाषित कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="e12e9-155">वर्तमान में परिभाषित शेड्यूल निर्यात सूची के **शेड्यूल** कॉलम में सूचीबद्ध है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="e12e9-156">शेड्यूल बदलने की अनुमति [निर्यात को संपादित करना और परिभाषित करना](export-destinations.md#set-up-a-new-export) की अनुमति के समान है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="e12e9-157">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="e12e9-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e12e9-158">वो निर्यात चुनें जिसे आप शेड्यूल करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="e12e9-159">कमांड बार में, **शेड्यूल करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="e12e9-160">**निर्यात शेड्यूल करें** फलक में, निर्यात को स्वतः रन करने के लिए **रन शेड्यूल करें** को **चालू** पर सेट करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="e12e9-161">इसे मैन्युअल रूप से रीफ्रेश करने के लिए **बंद** पर सेट करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="e12e9-162">स्वचालित रूप से रीफ़्रेश किए गए निर्यातों के लिए, **पुनरावृत्ति** मान चुनें और इसके लिए विवरण निर्दिष्ट करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="e12e9-163">परिभाषित समय, पुनरावृत्ति के सभी उदाहरणों पर लागू होता है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="e12e9-164">यह वह समय है जब निर्यात को रीफ़्रेश करना शुरू करना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="e12e9-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="e12e9-165">**सहेजें** चुनकर अपने परिवर्तन लागू करें और सक्रिय करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="e12e9-166">कई निर्यातों के लिए शेड्यूल संपादित करते समय, आपको **शेड्यूल रखें या ओवरराइड करें** के अंतर्गत चयन करने की आवश्यकता होती है:</span><span class="sxs-lookup"><span data-stu-id="e12e9-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="e12e9-167">**अलग-अलग शेड्यूल रखें**: चयनित निर्यातों के लिए पहले से निर्धारित शेड्यूल को बनाए रखें और केवल उन्हें अक्षम या सक्षम करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="e12e9-168">**सभी चयनित निर्यातों के लिए नया शेड्यूल परिभाषित करें**: चयनित निर्यातों के मौजूदा शेड्यूल ओवरराइड करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="e12e9-169">मांग पर निर्यातों को रन करें</span><span class="sxs-lookup"><span data-stu-id="e12e9-169">Run exports on demand</span></span>

<span data-ttu-id="e12e9-170">शेड्यूल किए गए एक रिफ्रेश के लिए इंतजार किए बिना डेटा निर्यात करने के लिए, **डेटा** > **निर्यात** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="e12e9-171">सभी निर्यातों को रन करने के लिए, कमांड बार में **सभी को रन करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="e12e9-172">यह क्रिया केवल उन निर्यातों को रन करेगी जिनका एक सक्रिय शेड्यूल है.</span><span class="sxs-lookup"><span data-stu-id="e12e9-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="e12e9-173">एकल निर्यात रन करने के लिए, इसे सूची में चुनें और कमांड बार में **रन करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="e12e9-174">इस तरह आप बिना सक्रिय शेड्यूल वाले निर्यातों को रन करते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="e12e9-175">एक निर्यात हटाएं</span><span class="sxs-lookup"><span data-stu-id="e12e9-175">Remove an Export</span></span>

1. <span data-ttu-id="e12e9-176">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="e12e9-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e12e9-177">उस निर्यात का चयन करें जिसे आप निकालना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="e12e9-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="e12e9-178">कमांड बार में, **निकालें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="e12e9-179">पुष्टिकरण स्क्रीन पर **हटाएँ** चुनते हुए उसके हटाए जाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="e12e9-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
