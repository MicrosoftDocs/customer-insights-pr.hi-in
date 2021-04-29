---
title: ग्राहक गतिविधियां
description: ग्राहक गतिविधियों को परिभाषित करें और उन्हें ग्राहक समयरेखा में देखें.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866409"
---
# <a name="customer-activities"></a><span data-ttu-id="547df-103">ग्राहक गतिविधियां</span><span class="sxs-lookup"><span data-stu-id="547df-103">Customer activities</span></span>

<span data-ttu-id="547df-104">Dynamics 365 Customer Insights में [विभिन्न डेटा स्रोतों](data-sources.md) से ग्राहक गतिविधियों को मिलाएं ताकि एक टाइमलाइन बनाई जा सके जो गतिविधियों को कालानुक्रमिक सूचीबद्ध करती है.</span><span class="sxs-lookup"><span data-stu-id="547df-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="547df-105">Dynamics 365 अनुप्रयोगों में टाइमलाइन को [कस्टमर कार्ड ऐड-इन](customer-card-add-in.md) सॉल्यूशन के साथ या Power BI डैशबोर्ड में शामिल करें.</span><span class="sxs-lookup"><span data-stu-id="547df-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="547df-106">एक गतिविधि को निर्धारित करें</span><span class="sxs-lookup"><span data-stu-id="547df-106">Define an activity</span></span>

<span data-ttu-id="547df-107">आपके डेटा स्रोतों में कई डेटा स्रोतों से लेनदेन और गतिविधि डेटा वाले निकाय शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="547df-108">इन निकायों को पहचानें और उन गतिविधियों का चयन करें जिन्हें आप ग्राहक की टाइमलाइन पर देखना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="547df-109">वह निकाय चुनें जिसमें आपकी लक्ष्य गतिविधि या गतिविधियाँ शामिल हों.</span><span class="sxs-lookup"><span data-stu-id="547df-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="547df-110">एक निकाय में ग्राहक की टाइमलाइन में शामिल होने के लिए टाइप **दिनांक** की कम से कम एक विशेषता होनी चाहिए और आप **दिनांक** फ़ील्ड के बिना निकायों को जोड़ नहीं सकते.</span><span class="sxs-lookup"><span data-stu-id="547df-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="547df-111">यदि कोई ऐसा निकाय नहीं मिला है, तो **गतिविधि जोड़ें** नियंत्रण अक्षम है.</span><span class="sxs-lookup"><span data-stu-id="547df-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="547df-112">ऑडियंस इनसाइट्स में, **डेटा** > **गतिविधियां** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="547df-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="547df-113">गतिविधि सेटअप प्रक्रिया के लिए निर्देशित अनुभव शुरू करने के लिए **गतिविधि जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="547df-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="547df-114">**गतिविधि डेटा** चरण में, निम्नलिखित फ़ील्ड के लिए मान निर्धारित करें:</span><span class="sxs-lookup"><span data-stu-id="547df-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="547df-115">**गतिविधि का नाम**: अपनी गतिविधि के लिए एक नाम चुनें.</span><span class="sxs-lookup"><span data-stu-id="547df-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="547df-116">**निकाय**: एक निकाय का चयन करें जिसमें लेनदेन या गतिविधि डेटा शामिल है.</span><span class="sxs-lookup"><span data-stu-id="547df-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="547df-117">**प्राथमिक कुंजी**: उस क्षेत्र का चयन करें जो विशिष्ट रूप से एक रिकॉर्ड की पहचान करता है.</span><span class="sxs-lookup"><span data-stu-id="547df-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="547df-118">इसमें कोई डुप्लिकेट मान, खाली मान या अनुपलब्ध मान नहीं होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="547df-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="नाम, निकाय और प्राथमिक कुंजी के साथ गतिविधि डेटा सेट करें.":::

1. <span data-ttu-id="547df-120">अगले चरण पर जाने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="547df-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="547df-121">**संबंध** चरण में, अपने गतिविधि डेटा को अपने संबंधित ग्राहक से जोड़ने के लिए विवरण को कॉन्फ़िगर करें.</span><span class="sxs-lookup"><span data-stu-id="547df-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="547df-122">यह कदम निकायों के बीच संबंध की कल्पना करता है.</span><span class="sxs-lookup"><span data-stu-id="547df-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="547df-123">**पहला**: आपकी गतिविधि निकाय में विदेशी फ़ील्ड जिसका उपयोग किसी अन्य निकाय के साथ संबंध स्थापित करने के लिए किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="547df-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="547df-124">**दूसरा**: संबंधित स्रोत ग्राहक निकाय जिसके साथ आपकी गतिविधि निकाय का संबंध होगा.</span><span class="sxs-lookup"><span data-stu-id="547df-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="547df-125">आप केवल डेटा एकीकरण प्रक्रिया में उपयोग की जाने वाली स्रोत ग्राहक निकायों से संबंधित हो सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="547df-126">**तीसरा**: यदि इस गतिविधि निकाय और चयनित स्रोत ग्राहक निकाय के बीच कोई संबंध पहले से मौजूद है, तो रिश्ते का नाम रीड-ओनली मोड में होगा.</span><span class="sxs-lookup"><span data-stu-id="547df-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="547df-127">यदि ऐसा कोई संबंध मौजूद नहीं है, तो इस बॉक्स में आपके द्वारा प्रदान किए जाने वाले नाम के साथ एक नया संबंध बनाया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="547df-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="निकाय संबंध को परिभाषित करें.":::

1. <span data-ttu-id="547df-129">अगले चरण पर जाने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="547df-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="547df-130">**गतिविधि एकीकरण** चरण में, गतिविधि की घटना और अपनी गतिविधि के शुरुआती समय का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="547df-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="547df-131">**आवश्यक फ़ील्ड्स**</span><span class="sxs-lookup"><span data-stu-id="547df-131">**Required fields**</span></span>
      1. <span data-ttu-id="547df-132">**ईवेंट गतिविधि**: वैसा फ़ील्ड जो इस गतिविधि के लिए ईवेंट है</span><span class="sxs-lookup"><span data-stu-id="547df-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="547df-133">**टाइमस्टैम्प**: वैसा फ़ील्ड जो आपकी गतिविधि के शुरुआती समय का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="547df-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="547df-134">**वैकल्पिक फ़ील्ड**</span><span class="sxs-lookup"><span data-stu-id="547df-134">**Optional fields**</span></span>
      1. <span data-ttu-id="547df-135">**अतिरिक्त विवरण**: इस गतिविधि के लिए प्रासंगिक जानकारी के साथ वाला फ़ील्ड.</span><span class="sxs-lookup"><span data-stu-id="547df-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="547df-136">**आइकन**: वैसा आइकन जो इस गतिविधि प्रकार का सबसे अच्छा प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="547df-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="547df-137">**वेब पता**: इस गतिविधि के बारे में जानकारी के साथ एक URL युक्त फ़ील्ड.</span><span class="sxs-lookup"><span data-stu-id="547df-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="547df-138">उदाहरण के लिए, संव्यवहार सिस्टम जो इस गतिविधि का स्रोत है.</span><span class="sxs-lookup"><span data-stu-id="547df-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="547df-139">यह URL डेटा स्रोत की कोई भी फ़ील्ड हो सकती है, या इसका निर्माण Power Query रूपांतरण का उपयोग करके नए फ़ील्ड के रूप में किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="547df-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="547df-140">URL डेटा *एकीकृत गतिविधि* निकाय में स्टोर किया जाएगा, जिसे [APIs](apis.md) माल करते हुए डाउनस्ट्रीम उपभोग कंज़्यूम किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="547df-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="एक एकीकृत गतिविधि निकाय में ग्राहक गतिविधि डेटा निर्दिष्ट करें.":::

1. <span data-ttu-id="547df-142">अगली सलाह पर जाने के लिए **अगले** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="547df-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="547df-143">आप अब गतिविधि के प्रकार को **अन्य** में सेट कर के गतिविधि को सहेजने के लिए **समाप्त और समीक्षा** का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="547df-144">**गतिविधि के प्रकार** चरण में, गतिविधि के प्रकार को चुनें और वैकल्पिक रूप से चुनें यदि आप Customer Insights के अन्य क्षेत्रों में उपयोग के लिए कुछ गतिविधि के प्रकारों को अर्थपूर्ण रूप से मैप करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="547df-145">वर्तमान में, *सदस्यता* & *SalesOrderLine* जैसे गतिविधि के प्रकारों को क्षेत्रों को मैप करने के लिए सहमत होने के बाद अर्थपूर्ण रूप से मैप किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="547df-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="547df-146">अगर कोई गतिविधि का प्रकार नई गतिविधि के लिए प्रासंगिक नहीं है, तो आप कस्टम गतिविधि के प्रकार के लिए *अन्य* या *नया बनाएं* चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="547df-147">अगली सलाह पर जाने के लिए **अगले** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="547df-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="547df-148">**समीक्षा** चरण में, अपने चयनों को सत्यापित करें.</span><span class="sxs-lookup"><span data-stu-id="547df-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="547df-149">आप पिछले किसी भी चरण में वापस जाएं और यदि आवश्यक हो तो जानकारी अपडेट करें.</span><span class="sxs-lookup"><span data-stu-id="547df-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="एक गतिविधि के लिए निर्दिष्ट फ़ील्ड की समीक्षा करें.":::
   
1. <span data-ttu-id="547df-151">अपने परिवर्तनों को लागू करने के लिए **गतिविधि सहेजें** चुनें और **डेटा** > **गतिविधि** पर वापस जाने के लिए **हो गया** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="547df-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="547df-152">यहां आप देखते हैं कि कौन सी गतिविधियां टाइमलाइन में दिखाने के लिए सेट की गई हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="547df-153">**गतिविधि** पृष्ठ पर, गतिविधि को संसाधित करने के लिए **रन करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="547df-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="547df-154">कार्यों/प्रक्रियाओं के लिए [छह प्रकार की स्थिति](system.md#status-types) हैं .</span><span class="sxs-lookup"><span data-stu-id="547df-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="547df-155">इसके अतिरिक्त, अधिकांश प्रक्रियाएं [अन्य डाउनस्ट्रीम प्रक्रियाओं पर निर्भर करती हैं](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="547df-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="547df-156">आप पूरे कार्य की प्रगति पर विवरण देखने के लिए प्रक्रिया की स्थिति का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="547df-157">किसी एक जॉब कार्य के लिए **विवरण देखें** को चुनने के बाद, आपको अतिरिक्त जानकारी मिलती है: संसाधन समय, अंतिम संसाधन दिनांक और कार्य से जुड़ी सभी त्रुटियां और चेतावनियाँ.</span><span class="sxs-lookup"><span data-stu-id="547df-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="547df-158">मौजूदा गतिविधि प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="547df-158">Manage existing activities</span></span>

<span data-ttu-id="547df-159">**डेटा** > **गतिविधि** पर, आप अपनी सभी सहेजी गई गतिविधियों को देख सकते हैं, और उन्हें प्रबंधित कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="547df-160">प्रत्येक गतिविधि का प्रतिनिधित्व एक पंक्ति द्वारा किया जाता है जिसमें स्रोत, निकाय और गतिविधि प्रकार के बारे में विवरण भी शामिल होते हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="547df-161">जब आप किसी गतिविधि का चयन करते हैं तो निम्नलिखित कार्रवाइयां उपलब्ध होती हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="547df-162">**संपादित करें**: समीक्षा चरण पर गतिविधि सेटअप खोलता है.</span><span class="sxs-lookup"><span data-stu-id="547df-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="547df-163">आप इस चरण से किसी भी या सभी वर्तमान कॉन्फ़िगरेशन को बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="547df-164">कॉन्फ़िगरेशन बदलने के बाद, **गतिविधि सहेजें** चुनें और फिर बदलावों की प्रक्रिया करने के लिए **रन करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="547df-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="547df-165">**नाम बदलें**: एक डायलॉग खोलता है जहां चयनित गतिविधि के लिए एक अलग नाम दर्ज करना है.</span><span class="sxs-lookup"><span data-stu-id="547df-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="547df-166">अपने परिवर्तन लागू करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="547df-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="547df-167">**मिटाएं**: चयनित गतिविधि को मिटाने की पुष्टि करने के लिए एक डायलॉग खोलता है.</span><span class="sxs-lookup"><span data-stu-id="547df-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="547df-168">आप गतिविधियों का चयन करके और फिर डिलीट आइकन का चयन करके एक बार में एक से अधिक गतिविधि को मिटा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="547df-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="547df-169">हटाने की पुष्टि करें, **हटाएँ** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="547df-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
