---
title: डेटा एकीकरण में निकायों को मर्ज करें
description: एकीकृत ग्राहक प्रोफाइल बनाने के लिए निकायों को मर्ज करें.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085578"
---
# <a name="merge-entities"></a><span data-ttu-id="fde60-103">निकायों को विलीन करें</span><span class="sxs-lookup"><span data-stu-id="fde60-103">Merge entities</span></span>

<span data-ttu-id="fde60-104">विलीनीकरण चरण डेटा एकीकरण प्रक्रिया में अंतिम चरण है.</span><span class="sxs-lookup"><span data-stu-id="fde60-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="fde60-105">इसका उद्देश्य परस्पर विरोधी डेटा में सामंजस्य बिठाना है.</span><span class="sxs-lookup"><span data-stu-id="fde60-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="fde60-106">परस्पर विरोधी डेटा के उदाहरणों में एक ग्राहक नाम शामिल हो सकता है जो आपके दो डेटासेट में पाया जाता है, लेकिन प्रत्येक ("ग्रांट मार्शल" बनाम "ग्रांट मार्शल"), या एक फ़ोन नंबर जो प्रारूप में भिन्न होता है (617-803-091X बनाम 617803091X).</span><span class="sxs-lookup"><span data-stu-id="fde60-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="fde60-107">उन परस्पर विरोधी डेटा बिंदुओं का विलीनीकरण विशेषता-दर-विशेषता के आधार पर किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="fde60-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="एकीकृत ग्राहक प्रोफ़ाइल को निर्दिष्ट करने वाले मर्ज किए गए फ़ील्ड वाली तालिका दिखाते हुए डेटा एकीकरण प्रक्रिया में पृष्ठ को मर्ज करें.":::

<span data-ttu-id="fde60-109">[मिलान चरण](match-entities.md) को पूरा करने के बाद, आप **विलीन** टाइल पर **एकीकृत** पेज का चयन करके विलीनीकरण चरण शुरू करते हैं.</span><span class="sxs-lookup"><span data-stu-id="fde60-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="fde60-110">सिस्टम सिफारिशों की समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="fde60-110">Review system recommendations</span></span>

<span data-ttu-id="fde60-111">**डेटा** > **Unify** > **मर्ज** पर, आप अपने एकीकृत ग्राहक प्रोफ़ाइल निकाय में मर्ज करने के लिए विशेषताओं को चुनते हैं और शामिल नहीं करते हैं.</span><span class="sxs-lookup"><span data-stu-id="fde60-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="fde60-112">एकीकृत ग्राहक प्रोफ़ाइल डेटा एकीकरण प्रक्रिया का परिणाम है.</span><span class="sxs-lookup"><span data-stu-id="fde60-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="fde60-113">कुछ विशेषताओं को सिस्टम द्वारा स्वचालित रूप से विलीन किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="fde60-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="fde60-114">आपकी स्वचालित रूप से मर्ज की गई विशेषताओं में से एक में शामिल विशेषताओं को देखने के लिए, तालिका के **ग्राहक फ़ील्ड** टैब में मर्ज की गई विशेषता का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fde60-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="fde60-115">मर्ज की गई विशेषता को बनाने वाली विशेषताएं मर्ज की गई विशेषता के नीचे दो नई पंक्तियों में प्रदर्शित होती हैं.</span><span class="sxs-lookup"><span data-stu-id="fde60-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="fde60-116">मर्ज किए गए फ़ील्ड को अलग करें, नाम बदलें, बाहर करें और संपादित करें</span><span class="sxs-lookup"><span data-stu-id="fde60-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="fde60-117">आप एकीकृत ग्राहक प्रोफ़ाइल जनरेट करने के लिए मर्ज की गई विशेषता को सिस्टम द्वारा संसाधित करने के तरीके को बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fde60-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="fde60-118">**और दिखाएं** चुनें और चयन करें कि आप क्या बदलना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="fde60-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="मर्ज की गई विशेषताओं को प्रबंधित करने के लिए अधिक दिखाएं ड्रॉप-डाउन मेनू में विकल्प.":::

<span data-ttu-id="fde60-120">अधिक जानकारी के लिए, निम्न अनुभाग देखें.</span><span class="sxs-lookup"><span data-stu-id="fde60-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="fde60-121">मर्ज किए गए फ़ील्ड को अलग करें</span><span class="sxs-lookup"><span data-stu-id="fde60-121">Separate merged fields</span></span>

<span data-ttu-id="fde60-122">मर्ज किए गए फ़ील्ड को पृथक करने के लिए, तालिका में विशेषता खोजें.</span><span class="sxs-lookup"><span data-stu-id="fde60-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="fde60-123">पृथक किए गए फ़ील्ड एकीकृत ग्राहक प्रोफ़ाइल पर अलग-अलग डेटा बिंदुओं के रूप में दिखाई देते हैं.</span><span class="sxs-lookup"><span data-stu-id="fde60-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="fde60-124">मर्ज किए गए फ़ील्ड को चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="fde60-125">**और दिखाएं** चुनें और **पृथक फ़ील्ड** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="fde60-126">पृथक्करण की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="fde60-126">Confirm the separation.</span></span>

1. <span data-ttu-id="fde60-127">परिवर्तनों को संसाधित करने के लिए **सहेजें** और **रन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="fde60-128">मर्ज किए गए फ़ील्ड का नाम बदलें</span><span class="sxs-lookup"><span data-stu-id="fde60-128">Rename merged fields</span></span>

<span data-ttu-id="fde60-129">मर्ज की गई विशेषताओं का प्रदर्शन नाम बदलें.</span><span class="sxs-lookup"><span data-stu-id="fde60-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="fde60-130">आप आउटपुट निकाय का नाम बदल नही सकते.</span><span class="sxs-lookup"><span data-stu-id="fde60-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="fde60-131">मर्ज किए गए फ़ील्ड को चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="fde60-132">**और दिखाएं** चुनें और **नाम बदलें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="fde60-133">बदले हुए प्रदर्शन नाम की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="fde60-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="fde60-134">परिवर्तनों को संसाधित करने के लिए **सहेजें** और **रन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="fde60-135">मर्ज किए गए फ़ील्ड बाहर करें</span><span class="sxs-lookup"><span data-stu-id="fde60-135">Exclude merged fields</span></span>

<span data-ttu-id="fde60-136">एकीकृत ग्राहक प्रोफ़ाइल से एक विशेषता बाहर निकालें.</span><span class="sxs-lookup"><span data-stu-id="fde60-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="fde60-137">यदि फ़ील्ड का उपयोग अन्य प्रक्रियाओं में किया जाता है, उदाहरण के लिए किसी सेगमेंट में, तो इसे ग्राहक प्रोफ़ाइल से बाहर करने से पहले इन प्रक्रियाओं से बाहर कर दें.</span><span class="sxs-lookup"><span data-stu-id="fde60-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="fde60-138">मर्ज किए गए फ़ील्ड को चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="fde60-139">**और दिखाएं** चुनें और **बाहर निकालें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="fde60-140">बहिष्करण की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="fde60-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="fde60-141">परिवर्तनों को संसाधित करने के लिए **सहेजें** और **रन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="fde60-142">समस्त बहिष्कृत फ़ील्ड की सूची देखने के लिए **मर्ज** पृष्ठ पर **बहिष्कृत फ़ील्ड** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="fde60-143">यह फलक आपको बहिष्कृत फ़ील्ड्स को पुनः जोड़ने देता है.</span><span class="sxs-lookup"><span data-stu-id="fde60-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="fde60-144">फ़ील्ड को मैन्युअल रूप से संयोजित करें</span><span class="sxs-lookup"><span data-stu-id="fde60-144">Manually combine fields</span></span>

<span data-ttu-id="fde60-145">मर्ज की गई विशेषता को मैन्युअल रूप से निर्दिष्ट करें.</span><span class="sxs-lookup"><span data-stu-id="fde60-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="fde60-146">**मर्ज करें** पृष्ठ पर, **फ़ील्ड संयोजित करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fde60-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="fde60-147">एक **नाम** और एक **आउटपुट फ़ील्ड नाम** उपलब्ध कराएं.</span><span class="sxs-lookup"><span data-stu-id="fde60-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="fde60-148">जोड़ने के लिए कोई फ़ील्ड चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-148">Choose a field to add.</span></span> <span data-ttu-id="fde60-149">और अधिक फ़ील्ड संयोजित करने के लिए **फ़ील्ड जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="fde60-150">बहिष्करण की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="fde60-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="fde60-151">परिवर्तनों को संसाधित करने के लिए **सहेजें** और **रन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="fde60-152">फ़ील्ड का क्रम बदलें</span><span class="sxs-lookup"><span data-stu-id="fde60-152">Change the order of fields</span></span>

<span data-ttu-id="fde60-153">कुछ निकायों में अन्य की तुलना में अधिक विवरण शामिल होते हैं.</span><span class="sxs-lookup"><span data-stu-id="fde60-153">Some entities contain more details than others.</span></span> <span data-ttu-id="fde60-154">यदि किसी निकाय में किसी फ़ील्ड के बारे में नवीनतम डेटा शामिल है, तो आप मानों को मर्ज करते समय अन्य निकायों के मुकाबले इसे प्राथमिकता दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fde60-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="fde60-155">मर्ज किए गए फ़ील्ड को चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="fde60-156">**और दिखाएं** चुनें और **संपादित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="fde60-157">**फ़ील्ड को मिलाएं** फलक में, ऑर्डर सेट करने के लिए **ऊपर/नीचे ले जाएं** चुनें या उन्हें इच्छित स्थिति में खींचें और छोड़ें.</span><span class="sxs-lookup"><span data-stu-id="fde60-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="fde60-158">परिवर्तन की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="fde60-158">Confirm the change.</span></span>

1. <span data-ttu-id="fde60-159">परिवर्तनों को संसाधित करने के लिए **सहेजें** और **रन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="fde60-160">अपना विलीनीकरण चलाएं</span><span class="sxs-lookup"><span data-stu-id="fde60-160">Run your merge</span></span>

<span data-ttu-id="fde60-161">चाहे आप मैन्युअल रूप से विलीन करें या सिस्टम को विलीन करने दें, आप हमेशा अपना विलीन चला सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fde60-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="fde60-162">प्रक्रिया शुरू करने के लिए **विलीन** पृष्ठ पर **रन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fde60-163">![डेटा विलीनीकरण सहेजें और चलाएँ](media/configure-data-merge-save-run.png "डेटा विलीनीकरण सहेजें और चलाएँ")</span><span class="sxs-lookup"><span data-stu-id="fde60-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="fde60-164">यदि आप केवल एकीकृत ग्राहक निकाय में प्रदर्शित आउटपुट देखना चाहते हैं, तो **केवल मर्ज चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="fde60-165">डाउनस्ट्रीम प्रक्रियाओं को [रीफ्रेश शेड्यूल में निर्धारित के रूप में रीफ्रेश किया जाएगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fde60-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="fde60-166">अपने परिवर्तनों के साथ सिस्टम को रीफ्रेश करने के लिए **मर्ज और डाउनस्ट्रीम प्रक्रियाएं चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="fde60-167">संवर्धन, अनुभाग और उपायों सहित सभी प्रक्रियाएं स्वचालित रूप से फिर से चलाई जाएंगी.</span><span class="sxs-lookup"><span data-stu-id="fde60-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="fde60-168">सभी डाउनस्ट्रीम प्रक्रियाएं पूरी होने के बाद, आपके द्वारा किए गए किसी भी परिवर्तन को ग्राहक प्रोफाइल दिखाती है.</span><span class="sxs-lookup"><span data-stu-id="fde60-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="fde60-169">और अधिक परिवर्तन करने और चरण को फिर से चलाने के लिए, आप जारी मर्ज को रद्द कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fde60-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="fde60-170">**रीफ़्रेश हो रहा है...** चुनें और उस साइड फलक में **कार्य रद्द करें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="fde60-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="fde60-171">कार्यों/प्रक्रियाओं के लिए [छह प्रकार की स्थिति](system.md#status-types) हैं .</span><span class="sxs-lookup"><span data-stu-id="fde60-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="fde60-172">इसके अतिरिक्त, अधिकांश प्रक्रियाएं [अन्य डाउनस्ट्रीम प्रक्रियाओं पर निर्भर करती हैं](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="fde60-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="fde60-173">आप पूरे कार्य की प्रगति पर विवरण देखने के लिए प्रक्रिया की स्थिति का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fde60-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="fde60-174">किसी एक जॉब कार्य के लिए **विवरण देखें** को चुनने के बाद, आपको अतिरिक्त जानकारी मिलती है: संसाधन समय, अंतिम संसाधन दिनांक और कार्य से जुड़ी सभी त्रुटियां और चेतावनियाँ.</span><span class="sxs-lookup"><span data-stu-id="fde60-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="fde60-175">अगला चरण</span><span class="sxs-lookup"><span data-stu-id="fde60-175">Next Step</span></span>

<span data-ttu-id="fde60-176">अपने ग्राहकों के बारे में अधिक जानकारी प्राप्त करने के लिए कॉन्फ़िगर करें [गतिविधियाँ](activities.md), [संवर्धन](enrichment-hub.md), या [संबंध](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="fde60-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="fde60-177">यदि आप पहले से ही गतिविधियों, संवर्धन, या खंडों को कॉन्फ़िगर कर चुके हैं, तो उन्हें नवीनतम ग्राहक डेटा का उपयोग करने के लिए स्वचालित रूप से संसाधित किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="fde60-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
