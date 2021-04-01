---
title: ग्राहक गतिविधियां
description: ग्राहक गतिविधियों को परिभाषित करें और उन्हें ग्राहक समयरेखा में देखें.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596731"
---
# <a name="customer-activities"></a><span data-ttu-id="41550-103">ग्राहक गतिविधियां</span><span class="sxs-lookup"><span data-stu-id="41550-103">Customer activities</span></span>

<span data-ttu-id="41550-104">Dynamics 365 Customer Insights में [विभिन्न डेटा स्रोत](data-sources.md) से ग्राहक गतिविधियों को मिलाएं, ताकि एक ग्राहक समयरेखा बनाई जा सके जो कालानुक्रमिक क्रम में गतिविधियों को सूचीबद्ध करता है.</span><span class="sxs-lookup"><span data-stu-id="41550-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="41550-105">आप [कस्टमर कार्ड ऐड-इन](customer-card-add-in.md) का उपयोग करके Dynamics 365 में या Power BI डैशबोर्ड में ग्राहक सहभागिता ऐप में टाइमलाइन शामिल कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="41550-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="41550-106">एक गतिविधि को निर्धारित करें</span><span class="sxs-lookup"><span data-stu-id="41550-106">Define an activity</span></span>

<span data-ttu-id="41550-107">आपके डेटा स्रोतों में कई डेटा स्रोतों से लेनदेन और गतिविधि डेटा वाले निकाय शामिल हैं।</span><span class="sxs-lookup"><span data-stu-id="41550-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="41550-108">इन निकायों को पहचानें और उन गतिविधियों का चयन करें जिन्हें आप ग्राहक की टाइमलाइन पर देखना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="41550-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="41550-109">वह निकाय चुनें जिसमें आपकी लक्ष्य गतिविधि या गतिविधियाँ शामिल हों.</span><span class="sxs-lookup"><span data-stu-id="41550-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="41550-110">ऑडियंस इनसाइट्स में, **डेटा** > **गतिविधियां** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="41550-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="41550-111">**गतिविधि जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="41550-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="41550-112">एक निकाय में ग्राहक की टाइमलाइन में शामिल होने के लिए टाइप **दिनांक** की कम से कम एक विशेषता होनी चाहिए और आप **दिनांक** फ़ील्ड के बिना निकायों को जोड़ नहीं सकते.</span><span class="sxs-lookup"><span data-stu-id="41550-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="41550-113">यदि कोई ऐसा निकाय नहीं मिला है, तो **गतिविधि जोड़ें** नियंत्रण अक्षम है.</span><span class="sxs-lookup"><span data-stu-id="41550-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="41550-114">**गतिविधि जोड़ें** फलक में, निम्न फ़ील्ड के लिए मान सेट करें:</span><span class="sxs-lookup"><span data-stu-id="41550-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="41550-115">**निकाय**: एक निकाय का चयन करें जिसमें लेनदेन या गतिविधि डेटा शामिल है.</span><span class="sxs-lookup"><span data-stu-id="41550-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="41550-116">**प्राथमिक कुंजी**: उस क्षेत्र का चयन करें जो विशिष्ट रूप से एक रिकॉर्ड की पहचान करता है.</span><span class="sxs-lookup"><span data-stu-id="41550-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="41550-117">इसमें कोई डुप्लिकेट मान, खाली मान या अनुपलब्ध मान नहीं होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="41550-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="41550-118">**टाइमस्टैम्प**: उस क्षेत्र का चयन करें जो आपकी गतिविधि के आरंभ समय का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="41550-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="41550-119">**इवेंट**: उस क्षेत्र का चयन करें जो गतिविधि के लिए इवेंट है.</span><span class="sxs-lookup"><span data-stu-id="41550-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="41550-120">**वेब पता**: इस गतिविधि के बारे में अतिरिक्त जानकारी प्रदान करने वाले URL का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="41550-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="41550-121">उदाहरण के लिए, संव्यवहार सिस्टम जो इस गतिविधि का स्रोत है.</span><span class="sxs-lookup"><span data-stu-id="41550-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="41550-122">यह URL डेटा स्रोत की कोई भी फ़ील्ड हो सकती है, या इसका निर्माण Power Query रूपांतरण का उपयोग करके नए फ़ील्ड के रूप में किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="41550-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="41550-123">यह URL डेटा यूनिफ़ाइड एक्टिविटी निकाय में संग्रहीत किया जाएगा, जिसे API का उपयोग करके डाउनस्ट्रीम में प्रयुक्त किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="41550-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="41550-124">**विवरण**: वैकल्पिक रूप से, अतिरिक्त विवरण के लिए जोड़ा गया फ़ील्ड चुनें.</span><span class="sxs-lookup"><span data-stu-id="41550-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="41550-125">**आइकन**: वैकल्पिक रूप से, उस आइकन का चयन करें जो इस गतिविधि को दर्शाता है.</span><span class="sxs-lookup"><span data-stu-id="41550-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="41550-126">**गतिविधि प्रकार**: सामान्य डेटा मॉडल के गतिविधि प्रकार के संदर्भ को परिभाषित करें जो गतिविधि की अर्थ-संबंधी परिभाषा का सबसे अच्छा वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="41550-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="41550-127">**संबंध स्थापित करें** अनुभाग में, अपने गतिविधि डेटा को उसके संबंधित ग्राहक से जोड़ने के लिए विवरण कॉन्फ़िगर करें.</span><span class="sxs-lookup"><span data-stu-id="41550-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="41550-128">**गतिविधि निकाय फ़ील्ड**: अपने गतिविधि निकाय में वह फ़ील्ड चुनें जिसका उपयोग किसी अन्य निकाय के साथ संबंध स्थापित करने के लिए किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="41550-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="41550-129">**ग्राहक निकाय**: वह संबंधित स्रोत ग्राहक निकाय चुनें जिसके साथ आपकी गतिविधि निकाय संबंध में होगी.</span><span class="sxs-lookup"><span data-stu-id="41550-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="41550-130">आप केवल उन स्रोत ग्राहक निकायों से संबंधित हो सकते हैं जो डेटा एकीकरण प्रक्रिया में उपयोग किए जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="41550-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="41550-131">**ग्राहक निकाय फ़ील्ड**: यह फ़ील्ड मानचित्र प्रक्रिया में चुने गए अनुसार स्रोत ग्राहक निकाय की प्राथमिक कुंजी दिखाती है.</span><span class="sxs-lookup"><span data-stu-id="41550-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="41550-132">स्रोत ग्राहक निकाय में इस प्राथमिक कुंजी फ़ील्ड का उपयोग गतिविधि निकाय के साथ संबंध स्थापित करने के लिए किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="41550-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="41550-133">**नाम**: यदि इस गतिविधि निकाय और चुने गए स्रोत ग्राहक निकाय के बीच पहले से ही कोई संबंध मौजूद है, तो संबंध नाम रीड- ओन्ली मोड में होगा.</span><span class="sxs-lookup"><span data-stu-id="41550-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="41550-134">यदि ऐसा कोई संबंध नहीं है, तो यहां दिए गए नाम के साथ एक नया संबंध बनाया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="41550-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41550-135">![निकाय संबंध को परिभाषित करें](media/activities-entities-define.png "निकाय संबंध को परिभाषित करें")</span><span class="sxs-lookup"><span data-stu-id="41550-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="41550-136">अपने परिवर्तन लागू करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="41550-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="41550-137">**गतिविधियां** पृष्ठ पर **चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="41550-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="41550-138">कार्यों/प्रक्रियाओं के लिए [छह प्रकार की स्थिति](system.md#status-types) हैं .</span><span class="sxs-lookup"><span data-stu-id="41550-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="41550-139">इसके अतिरिक्त, अधिकांश प्रक्रियाएं [अन्य डाउनस्ट्रीम प्रक्रियाओं पर निर्भर करती हैं](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="41550-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="41550-140">आप पूरे कार्य की प्रगति पर विवरण देखने के लिए प्रक्रिया की स्थिति का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="41550-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="41550-141">किसी एक जॉब कार्य के लिए **विवरण देखें** को चुनने के बाद, आपको अतिरिक्त जानकारी मिलती है: संसाधन समय, अंतिम संसाधन दिनांक और कार्य से जुड़ी सभी त्रुटियां और चेतावनियाँ.</span><span class="sxs-lookup"><span data-stu-id="41550-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="41550-142">गतिविधि संपादित करें</span><span class="sxs-lookup"><span data-stu-id="41550-142">Edit an activity</span></span>

1. <span data-ttu-id="41550-143">ऑडियंस इनसाइट्स में, **डेटा** > **गतिविधियां** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="41550-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="41550-144">वह गतिविधि निकाय चुनें जिसे आप संपादित करना चाहते हैं और **संपादित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="41550-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="41550-145">या, आप निकाय पंक्ति पर होवर कर सकते हैं और **संपादित करें** आइकन को चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="41550-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="41550-146">**संपादित करें** आइकन पर क्लिक करें.</span><span class="sxs-lookup"><span data-stu-id="41550-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="41550-147">**संपादन गतिविधि** फलक में मानों को अपडेट करें और **सहेजे** चुनें.</span><span class="sxs-lookup"><span data-stu-id="41550-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="41550-148">**गतिविधियां** पृष्ठ पर **चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="41550-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="41550-149">गतिविधि हटाएँ</span><span class="sxs-lookup"><span data-stu-id="41550-149">Delete an activity</span></span>

1. <span data-ttu-id="41550-150">ऑडियंस इनसाइट्स में, **डेटा** > **गतिविधियां** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="41550-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="41550-151">वह गतिविधि निकाय चुनें जिसे आप हटाना चाहते हैं और **हटाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="41550-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="41550-152">या, आप निकाय पंक्ति पर होवर कर सकते हैं और **हटाएं** आइकन को चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="41550-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="41550-153">इसके अतिरिक्त, आप एक ही बार में हटाए जाने के लिए कई गतिविधि निकायों को भी चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="41550-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41550-154">![निकाय संबंध संपादित करें या हटाएं](media/activities-entities-edit-delete.png "निकाय संबंध संपादित करें या हटाएं")</span><span class="sxs-lookup"><span data-stu-id="41550-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="41550-155">**हटाएं** आइकन चुनें.</span><span class="sxs-lookup"><span data-stu-id="41550-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="41550-156">हटाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="41550-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]