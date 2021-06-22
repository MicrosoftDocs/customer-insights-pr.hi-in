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
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095716"
---
# <a name="manage-predictions"></a><span data-ttu-id="52757-103">पूर्वानुमानों को प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="52757-103">Manage predictions</span></span>

<span data-ttu-id="52757-104">यह आलेख कुछ ऐसे कार्यों पर चर्चा करता है जो अधिकांश पूर्वानुमान परिदृश्य साझा करते हैं.</span><span class="sxs-lookup"><span data-stu-id="52757-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="52757-105">एक असफल पूर्वानुमान को ठीक करें</span><span class="sxs-lookup"><span data-stu-id="52757-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="52757-106">**इंटेलिजेंस** > **पूर्वानुमानों** पर जाएं और **मेरे पूर्वानुमान** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="52757-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="52757-107">आप जिस पूर्वानुमान के लिए त्रुटि लॉग देखना चाहते हैं, उसके बगल में लंबवत दीर्घवृत्त चुनें.</span><span class="sxs-lookup"><span data-stu-id="52757-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="52757-108">**लॉग** चुनें.</span><span class="sxs-lookup"><span data-stu-id="52757-108">Select **Logs**.</span></span>

1. <span data-ttu-id="52757-109">सभी त्रुटियों की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="52757-109">Review all the errors.</span></span> <span data-ttu-id="52757-110">कई प्रकार की त्रुटियां हो सकती हैं और वे बताती हैं कि त्रुटि किस कारण से हुई.</span><span class="sxs-lookup"><span data-stu-id="52757-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="52757-111">उदाहरण के लिए, एक त्रुटि जिसके बारे में सटीक पूर्वानुमान करने के लिए पर्याप्त डेटा नहीं है, को आमतौर पर Customer Insights में अतिरिक्त डेटा लोड करके ठीक किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="52757-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="52757-112">इनपुट डेटा प्रयोज्य रिपोर्ट</span><span class="sxs-lookup"><span data-stu-id="52757-112">Input data usability report</span></span>

<span data-ttu-id="52757-113">इनपुट डेटा उपयोगिता रिपोर्ट उन त्रुटियों और चेतावनियों का एक समेकित दृश्य प्रदान करती है जिन्हें आपके आउट-ऑफ-बॉक्स पूर्वानुमान जनरेट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="52757-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="52757-114">यह सुझाव भी देता है कि मॉडल के प्रदर्शन को कैसे बेहतर बनाया जाए.</span><span class="sxs-lookup"><span data-stu-id="52757-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="52757-115">एक मॉडल द्वारा अपनी प्रशिक्षण प्रक्रिया पूरी करने के बाद रिपोर्ट उपलब्ध होती है.</span><span class="sxs-lookup"><span data-stu-id="52757-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="52757-116">यह प्रत्येक मॉडल के लिए अलग से बनाया गया है, भले ही वह सफलतापूर्वक पूरा हुआ हो या नहीं.</span><span class="sxs-lookup"><span data-stu-id="52757-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="52757-117">फिलहाल यह फ़ीचर सिर्फ़ ट्रांज़ैक्शन चर्न मॉडल के लिए काम करता है.</span><span class="sxs-lookup"><span data-stu-id="52757-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="52757-118">इनपुट डेटा प्रयोज्य रिपोर्ट देखें</span><span class="sxs-lookup"><span data-stu-id="52757-118">View the input data usability report</span></span>

<span data-ttu-id="52757-119">किसी आउट-ऑफ़-बॉक्स मॉडल द्वारा अपना प्रशिक्षण चरण पूरा करने के बाद, रिपोर्ट देखें:</span><span class="sxs-lookup"><span data-stu-id="52757-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="52757-120">मॉडल नाम के आगे मौजूद दीर्घवृत्त को चुनें और **इनपुट डेटा उपयोगिता रिपोर्ट** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="52757-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="52757-121">एक मॉडल की स्थिति का चयन करें और बगल के फलक में **इनपुट डेटा उपयोगिता रिपोर्ट देखें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="52757-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="52757-122">सूची में से किसी एक मॉडल का चयन करना और कमांड बार में **इनपुट डेटा उपयोगिता रिपोर्ट** चुनें.</span><span class="sxs-lookup"><span data-stu-id="52757-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="52757-123">सूची में से किसी एक मॉडल को खोलें और कमांड बार में **इनपुट डेटा उपयोगिता रिपोर्ट** चुनें.</span><span class="sxs-lookup"><span data-stu-id="52757-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="52757-124">इनपुट डेटा उपयोगिता रिपोर्ट में जानकारी</span><span class="sxs-lookup"><span data-stu-id="52757-124">Information in the input data usability report</span></span>

<span data-ttu-id="52757-125">मॉडल हेतु डेटा को बेहतर बनाने के लिए रिपोर्ट में निम्नलिखित कॉलम में उपयोगी जानकारी है.</span><span class="sxs-lookup"><span data-stu-id="52757-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="त्रुटियों, चेतावनियों और सलाह वाली तालिका दिखाने वाली इनपुट डेटा प्रयोज्य रिपोर्ट का उदाहरण.":::

- <span data-ttu-id="52757-127">नाम: त्रुटि, चेतावनी या सलाह का वर्णनात्मक नाम.</span><span class="sxs-lookup"><span data-stu-id="52757-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="52757-128">चरण: मॉडल चरण, ट्रेन या स्कोर, जानकारी को संदर्भित करता है.</span><span class="sxs-lookup"><span data-stu-id="52757-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="52757-129">स्थिति: जानकारी की गंभीरता (त्रुटि, चेतावनी, सलाह).</span><span class="sxs-lookup"><span data-stu-id="52757-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="52757-130">कॉलम का नाम: किसी निकाय में कॉलम जिसे मॉडल के प्रदर्शन को बेहतर बनाने के लिए संशोधित करने की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="52757-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="52757-131">निकाय का नाम: निकाय का नाम जिसे मॉडल के प्रदर्शन को बेहतर बनाने के लिए संशोधित करने की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="52757-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="52757-132">विवरण: त्रुटि, चेतावनी या सलाह के बारे में विवरण.</span><span class="sxs-lookup"><span data-stu-id="52757-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="52757-133">एक पूर्वानुमान को रिफ्रेश करें</span><span class="sxs-lookup"><span data-stu-id="52757-133">Refresh a prediction</span></span>

<span data-ttu-id="52757-134">पूर्वानुमानों को सेटिंग्स में कॉन्फ़िगर किए गए के अनुसार उसी [आपके डेटा को रिफ्रेश करने का शेड्यूल](system.md#schedule-tab) पर स्वत: रिफ्रेश किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="52757-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="52757-135">आप मैन्युअल रूप से भी रीफ़्रेश कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="52757-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="52757-136">**इंटेलिजेंस** > **पूर्वानुमानों** पर जाएं और **मेरे पूर्वानुमान** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="52757-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="52757-137">पूर्वानुमान के बगल में उस लंबवत दीर्घवृत्त का चयन करें, जिसे आप रिफ्रेश करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="52757-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="52757-138">**रिफ्रेश** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="52757-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="52757-139">एक पूर्वानुमान हटाएं</span><span class="sxs-lookup"><span data-stu-id="52757-139">Delete a prediction</span></span>

<span data-ttu-id="52757-140">एक पूर्वानुमान को हटाने से इसका आउटपुट निकाय भी मिट जाता है.</span><span class="sxs-lookup"><span data-stu-id="52757-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="52757-141">**इंटेलिजेंस** > **पूर्वानुमानों** पर जाएं और **मेरे पूर्वानुमान** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="52757-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="52757-142">आप जिस पूर्वानुमान को हटाना चाहते हैं, उसके बगल में लंबवत दीर्घवृत्त चुनें.</span><span class="sxs-lookup"><span data-stu-id="52757-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="52757-143">**हटाएँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="52757-143">Select **Delete**.</span></span>
