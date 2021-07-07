---
title: पूर्वानुमान परिदृश्यों के लिए साझा किए गए कार्य
description: पूर्वानुमानों को प्रबंधित करने, उनका निवारण करने और उन्हें परिशोधित करने का तरीका जानें.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315880"
---
# <a name="manage-predictions"></a><span data-ttu-id="88ef4-103">पूर्वानुमानों को प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="88ef4-103">Manage predictions</span></span>

<span data-ttu-id="88ef4-104">यह आलेख कुछ ऐसे कार्यों पर चर्चा करता है जो अधिकांश पूर्वानुमान परिदृश्य साझा करते हैं.</span><span class="sxs-lookup"><span data-stu-id="88ef4-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="88ef4-105">एक असफल पूर्वानुमान को ठीक करें</span><span class="sxs-lookup"><span data-stu-id="88ef4-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="88ef4-106">**इंटेलिजेंस** > **पूर्वानुमानों** पर जाएं और **मेरे पूर्वानुमान** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="88ef4-107">आप जिस पूर्वानुमान के लिए त्रुटि लॉग देखना चाहते हैं, उसके बगल में लंबवत दीर्घवृत्त चुनें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="88ef4-108">**लॉग** चुनें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-108">Select **Logs**.</span></span>

1. <span data-ttu-id="88ef4-109">सभी त्रुटियों की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-109">Review all the errors.</span></span> <span data-ttu-id="88ef4-110">कई प्रकार की त्रुटियां हो सकती हैं और वे बताती हैं कि त्रुटि किस कारण से हुई.</span><span class="sxs-lookup"><span data-stu-id="88ef4-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="88ef4-111">उदाहरण के लिए, एक त्रुटि जिसके बारे में सटीक पूर्वानुमान करने के लिए पर्याप्त डेटा नहीं है, को आमतौर पर Customer Insights में अतिरिक्त डेटा लोड करके ठीक किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="88ef4-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="88ef4-112">इनपुट डेटा प्रयोज्य रिपोर्ट</span><span class="sxs-lookup"><span data-stu-id="88ef4-112">Input data usability report</span></span>

<span data-ttu-id="88ef4-113">इनपुट डेटा उपयोगिता रिपोर्ट उन त्रुटियों और चेतावनियों का एक समेकित दृश्य प्रदान करती है जिन्हें आपके आउट-ऑफ-बॉक्स पूर्वानुमान जनरेट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="88ef4-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="88ef4-114">यह सुझाव भी देता है कि मॉडल के प्रदर्शन को कैसे बेहतर बनाया जाए.</span><span class="sxs-lookup"><span data-stu-id="88ef4-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="88ef4-115">एक मॉडल द्वारा अपनी प्रशिक्षण प्रक्रिया पूरी करने के बाद रिपोर्ट उपलब्ध होती है.</span><span class="sxs-lookup"><span data-stu-id="88ef4-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="88ef4-116">यह प्रत्येक मॉडल के लिए अलग से बनाया गया है, भले ही वह सफलतापूर्वक पूरा हुआ हो या नहीं.</span><span class="sxs-lookup"><span data-stu-id="88ef4-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="88ef4-117">इनपुट डेटा प्रयोज्य रिपोर्ट देखें</span><span class="sxs-lookup"><span data-stu-id="88ef4-117">View the input data usability report</span></span>

<span data-ttu-id="88ef4-118">किसी आउट-ऑफ़-बॉक्स मॉडल द्वारा अपना प्रशिक्षण चरण पूरा करने के बाद, रिपोर्ट देखें:</span><span class="sxs-lookup"><span data-stu-id="88ef4-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="88ef4-119">मॉडल नाम के आगे मौजूद दीर्घवृत्त को चुनें और **इनपुट डेटा उपयोगिता रिपोर्ट** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="88ef4-120">एक मॉडल की स्थिति का चयन करें और बगल के फलक में **इनपुट डेटा उपयोगिता रिपोर्ट देखें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="88ef4-121">सूची में से किसी एक मॉडल का चयन करना और कमांड बार में **इनपुट डेटा उपयोगिता रिपोर्ट** चुनें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="88ef4-122">सूची में से किसी एक मॉडल को खोलें और कमांड बार में **इनपुट डेटा उपयोगिता रिपोर्ट** चुनें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="88ef4-123">इनपुट डेटा उपयोगिता रिपोर्ट में जानकारी</span><span class="sxs-lookup"><span data-stu-id="88ef4-123">Information in the input data usability report</span></span>

<span data-ttu-id="88ef4-124">मॉडल हेतु डेटा को बेहतर बनाने के लिए रिपोर्ट में निम्नलिखित कॉलम में उपयोगी जानकारी है.</span><span class="sxs-lookup"><span data-stu-id="88ef4-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="त्रुटियों, चेतावनियों और सलाह वाली तालिका दिखाने वाली इनपुट डेटा प्रयोज्य रिपोर्ट का उदाहरण.":::

- <span data-ttu-id="88ef4-126">नाम: त्रुटि, चेतावनी या सलाह का वर्णनात्मक नाम.</span><span class="sxs-lookup"><span data-stu-id="88ef4-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="88ef4-127">चरण: मॉडल चरण, ट्रेन या स्कोर, जानकारी को संदर्भित करता है.</span><span class="sxs-lookup"><span data-stu-id="88ef4-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="88ef4-128">स्थिति: जानकारी की गंभीरता (त्रुटि, चेतावनी, सलाह).</span><span class="sxs-lookup"><span data-stu-id="88ef4-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="88ef4-129">कॉलम का नाम: किसी निकाय में कॉलम जिसे मॉडल के प्रदर्शन को बेहतर बनाने के लिए संशोधित करने की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="88ef4-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="88ef4-130">निकाय का नाम: निकाय का नाम जिसे मॉडल के प्रदर्शन को बेहतर बनाने के लिए संशोधित करने की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="88ef4-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="88ef4-131">विवरण: त्रुटि, चेतावनी या सलाह के बारे में विवरण.</span><span class="sxs-lookup"><span data-stu-id="88ef4-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="88ef4-132">एक पूर्वानुमान को रिफ्रेश करें</span><span class="sxs-lookup"><span data-stu-id="88ef4-132">Refresh a prediction</span></span>

<span data-ttu-id="88ef4-133">पूर्वानुमानों को सेटिंग्स में कॉन्फ़िगर किए गए के अनुसार उसी [आपके डेटा को रिफ्रेश करने का शेड्यूल](system.md#schedule-tab) पर स्वत: रिफ्रेश किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="88ef4-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="88ef4-134">आप मैन्युअल रूप से भी रीफ़्रेश कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="88ef4-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="88ef4-135">**इंटेलिजेंस** > **पूर्वानुमानों** पर जाएं और **मेरे पूर्वानुमान** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="88ef4-136">पूर्वानुमान के बगल में उस लंबवत दीर्घवृत्त का चयन करें, जिसे आप रिफ्रेश करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="88ef4-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="88ef4-137">**रिफ्रेश** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="88ef4-138">एक पूर्वानुमान हटाएं</span><span class="sxs-lookup"><span data-stu-id="88ef4-138">Delete a prediction</span></span>

<span data-ttu-id="88ef4-139">एक पूर्वानुमान को हटाने से इसका आउटपुट निकाय भी मिट जाता है.</span><span class="sxs-lookup"><span data-stu-id="88ef4-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="88ef4-140">**इंटेलिजेंस** > **पूर्वानुमानों** पर जाएं और **मेरे पूर्वानुमान** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="88ef4-141">आप जिस पूर्वानुमान को हटाना चाहते हैं, उसके बगल में लंबवत दीर्घवृत्त चुनें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="88ef4-142">**हटाएँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="88ef4-142">Select **Delete**.</span></span>
