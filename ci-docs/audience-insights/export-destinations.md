---
title: Customer Insights से डेटा निर्यात करें
description: डेटा साझा करने के लिए निर्यात का प्रबंधन करें.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896145"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="eb91a-103">निर्यात (पूर्वावलोकन) अवलोकन</span><span class="sxs-lookup"><span data-stu-id="eb91a-103">Exports (preview) overview</span></span>

<span data-ttu-id="eb91a-104">**निर्यात** पृष्ठ आपको सभी कॉन्फ़िगर किए गए निर्यात को दिअकाउंट है.</span><span class="sxs-lookup"><span data-stu-id="eb91a-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="eb91a-105">निर्यात, विभिन्न अनुप्रयोगों के साथ विशिष्ट डेटा साझा करते हैं.</span><span class="sxs-lookup"><span data-stu-id="eb91a-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="eb91a-106">वे ग्राहक प्रोफ़ाइल या निकायों, स्कीमा, और मैपिंग के विवरण शामिल कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="eb91a-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="eb91a-107">प्रत्येक निर्यात को [प्रमाणीकरण और एक्सेस के प्रबंधन के लिए एक व्यवस्थापक द्वारा सेट की गई एक कनेक्शन](connections.md) की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="eb91a-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="eb91a-108">मार्च 2021 तक, निर्यात ने संबंधित सेवा के लिए स्वचालित रूप से एक कनेक्शन बनाया.</span><span class="sxs-lookup"><span data-stu-id="eb91a-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="eb91a-109">निर्यात को अब आपके द्वारा बना सकने से पहले [एक व्यवस्थापक द्वारा बनाए और साझा किए गए कनेक्शन](connections.md) की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="eb91a-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="eb91a-110">निर्यात पृष्ठ को देखने के लिए **डेटा** > **निर्यात** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="eb91a-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="eb91a-111">सभी उपयोगकर्ता भूमिकाओं के पास कॉन्फ़िगर किए गए निर्यात को देखने की एक्सेस होती है.</span><span class="sxs-lookup"><span data-stu-id="eb91a-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="eb91a-112">कमांड बार में निर्यात को उनके नाम, कनेक्शन नाम या कनेक्शन के प्रकार से खोजने के लिए सर्च फ़ील्ड का उपयोग.</span><span class="sxs-lookup"><span data-stu-id="eb91a-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="eb91a-113">एक नया निर्यात सेट करें</span><span class="sxs-lookup"><span data-stu-id="eb91a-113">Set up a new export</span></span>

<span data-ttu-id="eb91a-114">किसी निर्यात को सेट या संपादित करने के लिए, आपके पास कनेक्शन उपलब्ध होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="eb91a-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="eb91a-115">कनेक्शन आपके [उपयोगकर्ता भूमिका](permissions.md) पर निर्भर करते हैं:</span><span class="sxs-lookup"><span data-stu-id="eb91a-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="eb91a-116">व्यवस्थापकों के पास सभी कनेक्शनों तक एक्सेस है.</span><span class="sxs-lookup"><span data-stu-id="eb91a-116">Administrators have access to all connections.</span></span> <span data-ttu-id="eb91a-117">किसी निर्यात को सेट करते वक्त वे नए कनेक्शन भी बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="eb91a-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="eb91a-118">योगदानकर्ताओं के पास विशिष्ट कनेक्शन तक एक्सेस हो सकती है.</span><span class="sxs-lookup"><span data-stu-id="eb91a-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="eb91a-119">वे कनेक्शनों को कॉन्फ़िगर करने और साझा करने के लिए व्यवस्थापकों पर निर्भर करते हैं.</span><span class="sxs-lookup"><span data-stu-id="eb91a-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="eb91a-120">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="eb91a-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="eb91a-121">दर्शक केवल मौजूदा निर्यात देख सकते हैं लेकिन उन्हें बना नहीं सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="eb91a-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="eb91a-122">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="eb91a-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="eb91a-123">निर्यात के लिए एक नया डेस्टिनेशन बनाने के लिए **निर्यात जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="eb91a-124">**निर्यात सेट अप करें** फलक में, उपयोग में आने वाले कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="eb91a-125">[कनेक्शन](connections.md) व्यवस्थापकों द्वारा प्रबंधित किए गए हैं.</span><span class="sxs-lookup"><span data-stu-id="eb91a-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="eb91a-126">आवश्यक विवरण प्रदान करें और निर्यात बनाने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="eb91a-127">निर्यात को संपादित करें</span><span class="sxs-lookup"><span data-stu-id="eb91a-127">Edit an export</span></span>

1. <span data-ttu-id="eb91a-128">आप जिस निर्यात डेस्टिनेशन को संपादित करना चाहते हैं, उसके लिए वर्टिकल एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="eb91a-129">ड्राप-डाउन मेनू से एक **संपादित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="eb91a-130">उन मानों को बदलें जिसे आप अपडेट करना चाहते हैं और **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="eb91a-131">निर्यात और निर्यात विवरण देखें</span><span class="sxs-lookup"><span data-stu-id="eb91a-131">View Exports and export details</span></span>

<span data-ttu-id="eb91a-132">निर्यात डेस्टिनेशन बनाने के बाद, उन्हें **डेटा** > **निर्यात** पर सूचीबद्ध किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="eb91a-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="eb91a-133">सभी उपयोगकर्ता साझा किए गए डेटा और इसकी नवीनतम स्थिति को देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="eb91a-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="eb91a-134">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="eb91a-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="eb91a-135">संपादन की अनुमतियों के बिना उपयोगकर्ता निर्यात के विवरण को देखने के लिए **संपादित करें** के बजाय **देखें** का चयन करते हैं.</span><span class="sxs-lookup"><span data-stu-id="eb91a-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="eb91a-136">बगल का यह फलक इस निर्यात के सेट अप को दर्शाता है.</span><span class="sxs-lookup"><span data-stu-id="eb91a-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="eb91a-137">संपादन की अनुमतियों के बिना, आप मानों को नहीं बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="eb91a-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="eb91a-138">निर्यात पृष्ठ पर लौटने के लिए **बंद करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="eb91a-139">मांग पर निर्यातों को रन करें</span><span class="sxs-lookup"><span data-stu-id="eb91a-139">Run exports on demand</span></span>

<span data-ttu-id="eb91a-140">एक निर्यात को कॉन्फ़िगर करने के बाद, यह हर [शेड्यूल किए गए रिफ्रेश](system.md#schedule-tab) के साथ तब तक रन करेगा जब तक इसमें काम करने वाला कनेक्शन है.</span><span class="sxs-lookup"><span data-stu-id="eb91a-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="eb91a-141">शेड्यूल किए गए एक रिफ्रेश के लिए इंतजार किए बिना डेटा निर्यात करने के लिए, **डेटा** > **निर्यात** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="eb91a-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="eb91a-142">आपके पास दो विकल्‍प हैं :</span><span class="sxs-lookup"><span data-stu-id="eb91a-142">You have two options:</span></span>

- <span data-ttu-id="eb91a-143">सभी निर्यातों को रन करने के लिए, कमांड बार में **सभी को रन करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="eb91a-144">केवल एक निर्यात को रन करने के लिए, सूची के एक आइटम पर एलिप्सिस (...) का चयन करें और फिर **रन करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="eb91a-145">एक निर्यात हटाएं</span><span class="sxs-lookup"><span data-stu-id="eb91a-145">Remove an Export</span></span>

1. <span data-ttu-id="eb91a-146">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="eb91a-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="eb91a-147">आप जिस निर्यात को हटाना चाहते हैं उसके लिए वर्टिकल एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="eb91a-148">ड्रॉपडाउन मेनू से **हटाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="eb91a-149">पुष्टिकरण स्क्रीन पर **हटाएँ** चुनते हुए उसके हटाए जाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="eb91a-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
