---
title: Customer Insights से डेटा निर्यात करें
description: डेटा साझा करने के लिए निर्यात का प्रबंधन करें.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016616"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="7985e-103">निर्यात (पूर्वावलोकन) अवलोकन</span><span class="sxs-lookup"><span data-stu-id="7985e-103">Exports (preview) overview</span></span>

<span data-ttu-id="7985e-104">**निर्यात** पृष्ठ आपको सभी कॉन्फ़िगर किए गए निर्यात को दिअकाउंट है.</span><span class="sxs-lookup"><span data-stu-id="7985e-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="7985e-105">निर्यात, विभिन्न अनुप्रयोगों के साथ विशिष्ट डेटा साझा करते हैं.</span><span class="sxs-lookup"><span data-stu-id="7985e-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="7985e-106">वे ग्राहक प्रोफ़ाइल या निकायों, स्कीमा, और मैपिंग के विवरण शामिल कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7985e-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="7985e-107">प्रत्येक निर्यात को [प्रमाणीकरण और एक्सेस के प्रबंधन के लिए एक व्यवस्थापक द्वारा सेट की गई एक कनेक्शन](connections.md) की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="7985e-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="7985e-108">निर्यात पृष्ठ को देखने के लिए **डेटा** > **निर्यात** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="7985e-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="7985e-109">सभी उपयोगकर्ता भूमिकाओं के पास कॉन्फ़िगर किए गए निर्यात को देखने की एक्सेस होती है.</span><span class="sxs-lookup"><span data-stu-id="7985e-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="7985e-110">कमांड बार में निर्यात को उनके नाम, कनेक्शन नाम या कनेक्शन के प्रकार से खोजने के लिए सर्च फ़ील्ड का उपयोग.</span><span class="sxs-lookup"><span data-stu-id="7985e-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="7985e-111">एक नया निर्यात सेट करें</span><span class="sxs-lookup"><span data-stu-id="7985e-111">Set up a new export</span></span>

<span data-ttu-id="7985e-112">किसी निर्यात को सेट या संपादित करने के लिए, आपके पास कनेक्शन उपलब्ध होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="7985e-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="7985e-113">कनेक्शन आपके [उपयोगकर्ता भूमिका](permissions.md) पर निर्भर करते हैं:</span><span class="sxs-lookup"><span data-stu-id="7985e-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="7985e-114">व्यवस्थापकों के पास सभी कनेक्शनों तक एक्सेस है.</span><span class="sxs-lookup"><span data-stu-id="7985e-114">Administrators have access to all connections.</span></span> <span data-ttu-id="7985e-115">किसी निर्यात को सेट करते वक्त वे नए कनेक्शन भी बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7985e-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="7985e-116">योगदानकर्ताओं के पास विशिष्ट कनेक्शन तक एक्सेस हो सकती है.</span><span class="sxs-lookup"><span data-stu-id="7985e-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="7985e-117">वे कनेक्शनों को कॉन्फ़िगर करने और साझा करने के लिए व्यवस्थापकों पर निर्भर करते हैं.</span><span class="sxs-lookup"><span data-stu-id="7985e-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="7985e-118">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7985e-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="7985e-119">दर्शक केवल मौजूदा निर्यात देख सकते हैं लेकिन उन्हें बना नहीं सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7985e-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="7985e-120">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="7985e-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7985e-121">निर्यात के लिए एक नया डेस्टिनेशन बनाने के लिए **निर्यात जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7985e-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="7985e-122">**निर्यात सेट अप करें** फलक में, उपयोग में आने वाले कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7985e-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="7985e-123">[कनेक्शन](connections.md) व्यवस्थापकों द्वारा प्रबंधित किए गए हैं.</span><span class="sxs-lookup"><span data-stu-id="7985e-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="7985e-124">आवश्यक विवरण प्रदान करें और निर्यात बनाने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7985e-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="7985e-125">निर्यात को संपादित करें</span><span class="sxs-lookup"><span data-stu-id="7985e-125">Edit an export</span></span>

1. <span data-ttu-id="7985e-126">आप जिस निर्यात डेस्टिनेशन को संपादित करना चाहते हैं, उसके लिए वर्टिकल एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7985e-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="7985e-127">ड्राप-डाउन मेनू से एक **संपादित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="7985e-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="7985e-128">उन मानों को बदलें जिसे आप अपडेट करना चाहते हैं और **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7985e-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="7985e-129">निर्यात और निर्यात विवरण देखें</span><span class="sxs-lookup"><span data-stu-id="7985e-129">View Exports and export details</span></span>

<span data-ttu-id="7985e-130">निर्यात डेस्टिनेशन बनाने के बाद, उन्हें **डेटा** > **निर्यात** पर सूचीबद्ध किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="7985e-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="7985e-131">सभी उपयोगकर्ता साझा किए गए डेटा और इसकी नवीनतम स्थिति को देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7985e-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="7985e-132">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="7985e-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7985e-133">संपादन की अनुमतियों के बिना उपयोगकर्ता निर्यात के विवरण को देखने के लिए **संपादित करें** के बजाय **देखें** का चयन करते हैं.</span><span class="sxs-lookup"><span data-stu-id="7985e-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="7985e-134">बगल का यह फलक इस निर्यात के सेट अप को दर्शाता है.</span><span class="sxs-lookup"><span data-stu-id="7985e-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="7985e-135">संपादन की अनुमतियों के बिना, आप मानों को नहीं बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7985e-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="7985e-136">निर्यात पृष्ठ पर लौटने के लिए **बंद करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="7985e-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="7985e-137">मांग पर निर्यातों को रन करें</span><span class="sxs-lookup"><span data-stu-id="7985e-137">Run exports on demand</span></span>

<span data-ttu-id="7985e-138">एक निर्यात को कॉन्फ़िगर करने के बाद, यह हर [शेड्यूल किए गए रिफ्रेश](system.md#schedule-tab) के साथ तब तक रन करेगा जब तक इसमें काम करने वाला कनेक्शन है.</span><span class="sxs-lookup"><span data-stu-id="7985e-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="7985e-139">शेड्यूल किए गए एक रिफ्रेश के लिए इंतजार किए बिना डेटा निर्यात करने के लिए, **डेटा** > **निर्यात** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="7985e-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="7985e-140">आपके पास दो विकल्‍प हैं :</span><span class="sxs-lookup"><span data-stu-id="7985e-140">You have two options:</span></span>

- <span data-ttu-id="7985e-141">सभी निर्यातों को रन करने के लिए, कमांड बार में **सभी को रन करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7985e-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="7985e-142">केवल एक निर्यात को रन करने के लिए, सूची के एक आइटम पर एलिप्सिस (...) का चयन करें और फिर **रन करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="7985e-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="7985e-143">एक निर्यात हटाएं</span><span class="sxs-lookup"><span data-stu-id="7985e-143">Remove an Export</span></span>

1. <span data-ttu-id="7985e-144">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="7985e-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7985e-145">आप जिस निर्यात को हटाना चाहते हैं उसके लिए वर्टिकल एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7985e-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="7985e-146">ड्रॉपडाउन मेनू से **हटाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="7985e-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="7985e-147">पुष्टिकरण स्क्रीन पर **हटाएँ** चुनते हुए उसके हटाए जाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="7985e-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
