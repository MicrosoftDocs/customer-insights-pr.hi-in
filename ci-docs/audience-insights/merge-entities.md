---
title: डेटा एकीकरण में निकायों को मर्ज करें
description: एकीकृत ग्राहक प्रोफाइल बनाने के लिए निकायों को मर्ज करें.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405961"
---
# <a name="merge-entities"></a><span data-ttu-id="172f6-103">निकायों को विलीन करें</span><span class="sxs-lookup"><span data-stu-id="172f6-103">Merge entities</span></span>

<span data-ttu-id="172f6-104">विलीनीकरण चरण डेटा एकीकरण प्रक्रिया में अंतिम चरण है.</span><span class="sxs-lookup"><span data-stu-id="172f6-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="172f6-105">इसका उद्देश्य परस्पर विरोधी डेटा में सामंजस्य बिठाना है.</span><span class="sxs-lookup"><span data-stu-id="172f6-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="172f6-106">परस्पर विरोधी डेटा के उदाहरणों में एक ग्राहक नाम शामिल हो सकता है जो आपके दो डेटासेट में पाया जाता है, लेकिन प्रत्येक ("ग्रांट मार्शल" बनाम "ग्रांट मार्शल"), या एक फ़ोन नंबर जो प्रारूप में भिन्न होता है (617-803-091X बनाम 617803091X).</span><span class="sxs-lookup"><span data-stu-id="172f6-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="172f6-107">उन परस्पर विरोधी डेटा बिंदुओं का विलीनीकरण विशेषता-दर-विशेषता के आधार पर किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="172f6-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="172f6-108">[मिलान चरण](match-entities.md) को पूरा करने के बाद, आप **विलीन** टाइल पर **एकीकृत** पेज का चयन करके विलीनीकरण चरण शुरू करते हैं.</span><span class="sxs-lookup"><span data-stu-id="172f6-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="172f6-109">सिस्टम सिफारिशों की समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="172f6-109">Review system recommendations</span></span>

<span data-ttu-id="172f6-110">**विलीन** पृष्ठ पर, आप अपने एकीकृत ग्राहक प्रोफ़ाइल निकाय (कॉन्फ़िगरेशन प्रक्रिया का परिणाम) के भीतर विलय की जाने वाली विशेषताओं का चयन करते हैं और निकालते हैं.</span><span class="sxs-lookup"><span data-stu-id="172f6-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="172f6-111">कुछ विशेषताओं को सिस्टम द्वारा स्वचालित रूप से विलीन किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="172f6-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="172f6-112">मर्ज किया गया एट्रिब्यूट देखें</span><span class="sxs-lookup"><span data-stu-id="172f6-112">View merged attributes</span></span>

<span data-ttu-id="172f6-113">स्वचालित रूप से विलीन की गई विशेषताओं में शामिल विशेषताओं को देखने के लिए, उस विलीन की गई विशेषता का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="172f6-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="172f6-114">विलीन की गयी विशेषता को बनाने वाली दो विशेषताएँ विलीन की गयी विशेषता के नीचे दो नई पंक्तियों में प्रदर्शित होंगी.</span><span class="sxs-lookup"><span data-stu-id="172f6-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="172f6-115">![विलीन की गयी विशेषता का चयन करें](media/configure-data-merge-profile-attributes.png "विलीन की गयी विशेषता का चयन करें")</span><span class="sxs-lookup"><span data-stu-id="172f6-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="172f6-116">मर्ज किया गया एट्रिब्यूट अलग करें</span><span class="sxs-lookup"><span data-stu-id="172f6-116">Separate merged attributes</span></span>

<span data-ttu-id="172f6-117">स्वचालित रूप से विलय की गई विशेषताओं में से किसी को अलग या अविलीन करने के लिए, **प्रोफ़ाइल विशेषताएँ** तालिका में विशेषता ढूंढें.</span><span class="sxs-lookup"><span data-stu-id="172f6-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="172f6-118">एलिप्सिस (...) बटन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="172f6-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="172f6-119">ड्रॉपडाउन सूची में, **अलग फ़ील्ड** चुनें.</span><span class="sxs-lookup"><span data-stu-id="172f6-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="172f6-120">विलीन की गई विशेषताएँ हटाएं</span><span class="sxs-lookup"><span data-stu-id="172f6-120">Remove merged attributes</span></span>

<span data-ttu-id="172f6-121">अंतिम ग्राहक प्रोफ़ाइल निकाय से एक विशेषता को बाहर करने के लिए, इसे **प्रोफ़ाइल विशेषताएं** तालिका में ढूंढें.</span><span class="sxs-lookup"><span data-stu-id="172f6-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="172f6-122">एलिप्सिस (...) बटन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="172f6-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="172f6-123">ड्रॉपडाउन सूची में, **विलीन न करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="172f6-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="172f6-124">विशेषता को **ग्राहक रिकॉर्ड** अनुभाग से हटा दिया गया है.</span><span class="sxs-lookup"><span data-stu-id="172f6-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="172f6-125">विलीन की गयी विशेषता को मैन्युअल रूप से जोड़ें</span><span class="sxs-lookup"><span data-stu-id="172f6-125">Manually add a merged attribute</span></span>

<span data-ttu-id="172f6-126">विलीन की गयी विशेषता को जोड़ने के लिए, **विलीन** पृष्ठ पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="172f6-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="172f6-127">**विलीनीकृत विशेषता जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="172f6-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="172f6-128">बाद में **विलीन** पेज पर इसे पहचानने के लिए **नाम** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="172f6-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="172f6-129">वैकल्पिक रूप से, एकीकृत ग्राहक प्रोफ़ाइल निकाय में प्रदर्शित होने के लिए **प्रदर्शन नाम** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="172f6-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="172f6-130">उन विशेषताओं का चयन करने के लिए **प्रतिकृति विशेषताओं का चयन करें** कॉन्फ़िगर करें जिन्हें आप मिलान वाली संस्थाओं में विलीन करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="172f6-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="172f6-131">आप विशेषताओं को भी खोज सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="172f6-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="172f6-132">अन्य के ऊपर एक विशेषता को प्राथमिकता देने के लिए सेट करें **महत्व के अनुसार श्रेणीबद्ध करें**.</span><span class="sxs-lookup"><span data-stu-id="172f6-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="172f6-133">उदाहरण के लिए, यदि *WebAccountCSV* निकाय में *पूर्ण नाम* विशेषता के बारे में सबसे सटीक डेटा शामिल हैं, तो आप इस निकाय को *ContactCSV* को के मुकाबले *WebAccountCSV* का चयन करके इसे प्राथमिकता दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="172f6-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="172f6-134">परिणामस्वरूप, *पूर्ण नाम* विशेषता के लिए महत्व देते समय *WebAccountCSV* पहली प्राथमिकता पर जाता है, जबकि *ContactCSV* दूसरे स्थान पर रहता है.</span><span class="sxs-lookup"><span data-stu-id="172f6-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="172f6-135">अपना विलीनीकरण चलाएं</span><span class="sxs-lookup"><span data-stu-id="172f6-135">Run your merge</span></span>

<span data-ttu-id="172f6-136">चाहे आप मैन्युअल रूप से विलीन करें या सिस्टम को विलीन करने दें, आप हमेशा अपना विलीन चला सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="172f6-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="172f6-137">प्रक्रिया शुरू करने के लिए **विलीन** पृष्ठ पर **रन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="172f6-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="172f6-138">![डेटा विलीनीकरण सहेजें और चलाएँ](media/configure-data-merge-save-run.png "डेटा विलीनीकरण सहेजें और चलाएँ")</span><span class="sxs-lookup"><span data-stu-id="172f6-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="172f6-139">अतिरिक्त बदलाव करने और चरण को पुन: करने के लिए, आप चल रही मर्ज होने की प्रक्रिया को रद्द कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="172f6-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="172f6-140">**रीफ़्रेश हो रहा है...** चुनें और उस साइड फलक में **कार्य रद्द करें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="172f6-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="172f6-141">**रिफ्रेश हो रहा है ...** टेक्स्ट **सफल रहा** में बदलने के बाद, मर्ज पूरा हो गया है और आपके द्वारा निर्धारित नीतियों के अनुसार आपके डेटा में अंतर्विरोधों को हल कर चुका है.</span><span class="sxs-lookup"><span data-stu-id="172f6-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="172f6-142">एकीकृत प्रोफ़ाइल निकाय में विलय किए गए और पृथक किए गए गुण शामिल किए जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="172f6-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="172f6-143">छोड़ दिये गए गुणों को एकीकृत प्रोफ़ाइल निकाय में शामिल नहीं किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="172f6-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="172f6-144">यदि यह पहली बार नहीं था जब आपने सफलतापूर्वक कोई विलय किया था, तो सभी डाउनस्ट्रीम प्रक्रियाएं, जिनमें संवर्धन, विभाजन और उपाय शामिल हैं, स्वचालित रूप से फिर से चलाएं जाएंगी.</span><span class="sxs-lookup"><span data-stu-id="172f6-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="172f6-145">सभी डाउनस्ट्रीम प्रक्रियाओं को फिर से चलाए जाने के बाद, ग्राहक प्रोफ़ाइल आपके द्वारा किए गए किसी भी बदलाव को दर्शाती है.</span><span class="sxs-lookup"><span data-stu-id="172f6-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="172f6-146">कार्यों/प्रक्रियाओं के लिए [छह प्रकार की स्थिति](system.md#status-types) हैं .</span><span class="sxs-lookup"><span data-stu-id="172f6-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="172f6-147">इसके अतिरिक्त, अधिकांश प्रक्रियाएं [अन्य डाउनस्ट्रीम प्रक्रियाओं पर निर्भर करती हैं](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="172f6-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="172f6-148">आप पूरे कार्य की प्रगति पर विवरण देखने के लिए प्रक्रिया की स्थिति का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="172f6-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="172f6-149">किसी एक जॉब कार्य के लिए **विवरण देखें** को चुनने के बाद, आपको अतिरिक्त जानकारी मिलती है: संसाधन समय, अंतिम संसाधन दिनांक और कार्य से जुड़ी सभी त्रुटियां और चेतावनियाँ.</span><span class="sxs-lookup"><span data-stu-id="172f6-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="172f6-150">अगला चरण</span><span class="sxs-lookup"><span data-stu-id="172f6-150">Next Step</span></span>

<span data-ttu-id="172f6-151">अपने ग्राहकों के बारे में अधिक जानकारी प्राप्त करने के लिए कॉन्फ़िगर करें [गतिविधियाँ](activities.md), [संवर्धन](enrichment-microsoft-graph.md), या [संबंध](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="172f6-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="172f6-152">यदि आपने कार्यकलापों, एनरिचमेंट या संबंधों को पहले से विन्यासित कर दिया है या यदि आपने खंडों को परिभाषित किया है तो ग्राहक के नवीनतम डेटा का उपयोग करने के लिए उनकी प्रक्रिया स्वचालित रूप से की जाएगी.</span><span class="sxs-lookup"><span data-stu-id="172f6-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


