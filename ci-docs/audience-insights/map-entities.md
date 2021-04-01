---
title: डेटा एकीकरण के लिए मानचित्र निकायएं
description: एकीकृत ग्राहक प्रोफाइल बनाने के लिए डेटा मैप करें.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595995"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="28597-103">मानचित्र निकाय और विशेषताएँ</span><span class="sxs-lookup"><span data-stu-id="28597-103">Map entities and attributes</span></span>

<span data-ttu-id="28597-104">**मानचित्र** ऑडियंस इनसाइट्स के डेटा एकीकरण प्रक्रिया में पहला चरण है.</span><span class="sxs-lookup"><span data-stu-id="28597-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="28597-105">मैपिंग में तीन चरण होते हैं:</span><span class="sxs-lookup"><span data-stu-id="28597-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="28597-106">*निकाय चयन*: उन संयोज्य निकायों की पहचान करें, जो आपके ग्राहकों के बारे में अधिक संपूर्ण जानकारी के साथ एक डेटासेट दिखाती हैं.</span><span class="sxs-lookup"><span data-stu-id="28597-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="28597-107">*विशेषता चयन*: प्रत्येक निकाय के लिए उन कॉलमों की पहचान करें जिन्हें आप *मिलान* और *मर्ज* चरणों में मिलाना और पुनर्स्थापित करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="28597-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="28597-108">इन स्तंभों को *गुण* कहा जाता है.</span><span class="sxs-lookup"><span data-stu-id="28597-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="28597-109">*प्राथमिक कुंजी और सिमैंटिक टाइप चयन*: प्रत्येक निकाय के लिए, एक विशेषता की पहचान करें जिसे आप उस निकाय के लिए प्राथमिक कुंजी के रूप में परिभाषित करना चाहते हैं, और प्रत्येक विशेषता के लिए, एक सिमैंटिक टाइप की पहचान करें जो उस विशेषता का सबसे अच्छा वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="28597-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="28597-110">डेटा एकीकरण के सामान्य प्रवाह के बारे में अधिक जानकारी के लिए, [एकीकृत](data-unification.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="28597-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="28597-111">प्रथम निकाय का चयन करें</span><span class="sxs-lookup"><span data-stu-id="28597-111">Select the first entities</span></span>

1. <span data-ttu-id="28597-112">ऑडिएंस इनसाइट्स में, **डेटा** > **एकीकृत** > **मैप** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="28597-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="28597-113">**निकाय चुनें** का चयन करते हुए मैप चरण शुरू करें.</span><span class="sxs-lookup"><span data-stu-id="28597-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="28597-114">उन निकायों और एट्रिब्यूट का चयन करें जिन्हें आप *मिलान* और *विलय* चरणों में उपयोग करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="28597-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="28597-115">आप किसी निकाय से व्यक्तिगत रूप से आवश्यक विशेषताओं का चयन कर सकते हैं या निकाय स्तर पर **सभी फ़ील्ड शामिल करें** चेकबॉक्स का चयन करके किसी निकाय से सभी विशेषताओं को शामिल कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="28597-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="28597-116">हम सलाह देते हैं कि डेटा एकीकरण प्रक्रिया का लाभ के लिए कम दो निकायों का चयन किया जाए.</span><span class="sxs-lookup"><span data-stu-id="28597-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="28597-117">![निकाय उदाहरण जोड़ें](media/data-manager-configure-map-add-entities-example.png "निकाय उदाहरण जोड़ें")</span><span class="sxs-lookup"><span data-stu-id="28597-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="28597-118">इस उदाहरण में, **eCommerceContacts** और **loyCustomers** निकायों को हम जोड़ रहे हैं.</span><span class="sxs-lookup"><span data-stu-id="28597-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="28597-119">इन निकायों को चुनकर, आप इनसाइट्स प्राप्त कर सकते हैं कि किस ऑनलाइन व्यवसाय पर ग्राहक विश्वसनीय कार्यक्रम के सदस्य हैं.</span><span class="sxs-lookup"><span data-stu-id="28597-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="28597-120">आप उन आवश्यक विशेषताओं का चयन करने के लिए सभी विशेषताओं और निकायों में मुख्य शब्द खोज सकते हैं जिन्हें आप मैप करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="28597-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="28597-121">![फ़ील्ड उदाहरण खोजें](media/data-manager-configure-map-search-fields-example.png "फ़ील्ड उदाहरण खोजें")</span><span class="sxs-lookup"><span data-stu-id="28597-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="28597-122">अपने चयन की पुष्टि करने के लिए **लागू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="28597-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="28597-123">विशेषताओं के लिए प्राथमिक कुंजी और सिमैंटिक टाइप का चयन करें</span><span class="sxs-lookup"><span data-stu-id="28597-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="28597-124">अपनी निकायों का चयन करने के बाद, **मैप** पृष्ठ आपकी समीक्षा के लिए चयनित निकायों को सूचीबद्ध करता है.</span><span class="sxs-lookup"><span data-stu-id="28597-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="28597-125">किसी निकाय के लिए प्राथमिक कुंजी को परिभाषित करें और निकाय में किसी विशेषता के लिए सिमैंटिक टाइप की पहचान करें.</span><span class="sxs-lookup"><span data-stu-id="28597-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="28597-126">**प्राथमिक कुंजी**: अपने प्रत्येक निकाय के लिए प्राथमिक कुंजी के रूप में एक एट्रिब्यूट का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="28597-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="28597-127">एक मान्य प्राथमिक कुंजी होने के लिए, इसमें डुप्लिकेट मान, गुम हुए मान या शून्य मान शामिल नहीं होने चाहिए.</span><span class="sxs-lookup"><span data-stu-id="28597-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="28597-128">स्ट्रिंग, पूर्णांक और GUID डेटा प्रकार एट्रिब्यूट को प्राथमिक कुंजी के रूप में समर्थित किया जाता है और आपको चुनने के लिए एक फ़ील्ड में प्रदर्शित किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="28597-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="28597-129">**एट्रिब्यूट सिमेंटिक प्रकार**: आपके एट्रिब्यूट की श्रेणियां, जैसे ई-मेल पता या नाम.</span><span class="sxs-lookup"><span data-stu-id="28597-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="28597-130">शब्दार्थों के स्मार्ट पूर्वानुमान के लिए AI मॉडल का उपयोग करने के लिए, समय की बचत करें और सटीकता में सुधार करें,  **इंटेलिजेंट मैपिंग** को **चालू** पर सेट करें.</span><span class="sxs-lookup"><span data-stu-id="28597-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="28597-131">इंटेलिजेंट मैपिंग **प्रकार** फ़ील्ड में AI-आधारित शब्दार्थ के लिए अनुशंसाओं को हाइलाइट करता है.</span><span class="sxs-lookup"><span data-stu-id="28597-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="28597-132">यदि आप इसे **बंद करें** पर सेट कर देते हैं, तो आप हमारे नियमित मैपिंग सुझाव देखेंगे.</span><span class="sxs-lookup"><span data-stu-id="28597-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="28597-133">आप विकल्पों की उपलब्ध सूची से किसी भी शब्दार्थ प्रकार का चयन कर सकते हैं और सुझाए गए चयन को ओवरराइड कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="28597-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="28597-134">![एट्रिब्यूट प्रकार और शब्दार्थ पूर्वानुमान](media/data-manager-configure-map-add-attributes-semantic-prediction.png "एट्रिब्यूट प्रकार और शब्दार्थ पूर्वानुमान")</span><span class="sxs-lookup"><span data-stu-id="28597-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="28597-135">कस्टम सिमेंटिक प्रकार जोड़ना भी संभव है.</span><span class="sxs-lookup"><span data-stu-id="28597-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="28597-136">एक एट्रिब्यूट के लिए प्रकार फ़ील्ड चुनें, और अपने कस्टम सिमेंटिक-प्रकार नाम लिखें.</span><span class="sxs-lookup"><span data-stu-id="28597-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="28597-137">इस तरह, आप सिस्टम द्वारा पहचाने गए एट्रिब्यूट प्रकारों को भी बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="28597-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="28597-138">जिन विशेषताओं के लिए एक सिमेंटिक टाइप की स्वचालित रूप से पहचान की जाती है, उन्हें **मैप किए गए फ़ील्ड की समीक्षा करें** अनुभाग में समूहित किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="28597-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="28597-139">इन विशेषताओं और उनके सिमैंटिक टाइप की समीक्षा करें क्योंकि उनका उपयोग डेटा एकीकरण के विलय चरण में आपकी निकायों को संयोजित करने के लिए किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="28597-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="28597-140">जिन विशेषताओं को स्वचालित रूप से सिमैंटिक टाइप में मैप नहीं किया जाता है, उन्हें **बिना मैप किए गए फ़ील्ड में परिभाषित डेटा** अनुभाग में समूहीकृत किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="28597-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="28597-141">बिना मैप किए गए गुणों के लिए सिमैंटिक टाइप फ़ील्ड चुनें, या अपना कस्टम विशेषता-प्रकार का नाम दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="28597-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="28597-142">![प्राथमिक कुंजी और एट्रिब्यूट प्रकार](media/data-manager-configure-map-add-attributes.png "प्राथमिक कुंजी और एट्रिब्यूट प्रकार")</span><span class="sxs-lookup"><span data-stu-id="28597-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="28597-143">ग्राहक कार्ड में ग्राहक के नाम को बढ़ाने के लिए एक फ़ील्ड सिमैंटिक टाइप Person.FullName को मैप करना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="28597-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="28597-144">अन्यथा, ग्राहक कार्ड बिना नाम के दिखाई देंगे.</span><span class="sxs-lookup"><span data-stu-id="28597-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="28597-145">विशेषताओं और निकायों को जोड़ें और हटाएं</span><span class="sxs-lookup"><span data-stu-id="28597-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="28597-146">**एकीकृत** > **मैप** पर, **फ़ील्ड संपादित करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="28597-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="28597-147">**फ़ील्ड संपादित करें** फलक में, विशेषताओं और निकायों को जोड़ें या हटाएं.</span><span class="sxs-lookup"><span data-stu-id="28597-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="28597-148">खोज या स्क्रॉल का उपयोग अपनी विशेषताओं और रुचि की निकायों को खोजने और चुनने के लिए करें.</span><span class="sxs-lookup"><span data-stu-id="28597-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="28597-149">आप किसी विशेषता या निकाय को नहीं निकाल सकते यदि वो पहले से मिलान हो चुके हैं.</span><span class="sxs-lookup"><span data-stu-id="28597-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="28597-150">![विशेषताएँ जोड़ें या निकालें](media/configure-data-map-edit.png "एट्रिब्यूट जोड़ें या निकालें")</span><span class="sxs-lookup"><span data-stu-id="28597-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="28597-151">**लागू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="28597-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="28597-152">प्रोफाइल में चित्र जोड़ें</span><span class="sxs-lookup"><span data-stu-id="28597-152">Add images to profiles</span></span>

<span data-ttu-id="28597-153">यदि किसी निकाय में सार्वजनिक रूप से उपलब्ध प्रोफ़ाइल छवियाँ या लोगो के URL हैं, तो आप उन्हें एकीकृत ग्राहक प्रोफ़ाइल में जोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="28597-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="28597-154">निकाय का चयन करें और वह फ़ील्ड खोजें जिसमें प्रोफ़ाइल छवियों के URL है.</span><span class="sxs-lookup"><span data-stu-id="28597-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="28597-155">**प्रकार** इनपुट फ़ील्ड में मैन्युअल रूप से निम्नलिखित मान दर्ज करें:</span><span class="sxs-lookup"><span data-stu-id="28597-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="28597-156">एक व्यक्ति के लिए: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="28597-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="28597-157">एक संगठन के लिए: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="28597-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="28597-158">एकीकरण चरणों को जारी रखें और यह सुनिश्चित करें कि छवि URL वाली विशेषता [विलय](merge-entities.md) चरण में भी जोड़ा गया है.</span><span class="sxs-lookup"><span data-stu-id="28597-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="28597-159">संगठनों के लिए एट्रिब्यूट स्थापित करें</span><span class="sxs-lookup"><span data-stu-id="28597-159">Set attributes for organizations</span></span>

<span data-ttu-id="28597-160">संगठन (पूर्वावलोकन) के लिए, विशेषता प्रकार को "Organization.Name" में मैप किया जाना चाहिए</span><span class="sxs-lookup"><span data-stu-id="28597-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="28597-161">![प्राथमिक कुंजी और B2B एट्रिब्यूट प्रकार](media/configure-data-map-edit-b2b.png "प्राथमिक कुंजी और B2B एट्रिब्यूट प्रकार")</span><span class="sxs-lookup"><span data-stu-id="28597-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="28597-162">अगला स्टेप</span><span class="sxs-lookup"><span data-stu-id="28597-162">Next step</span></span>

<span data-ttu-id="28597-163">डेटा एकीकरण प्रक्रिया के हिस्से के रूप में, **मिलान** पृष्ठ पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="28597-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="28597-164">इस चरण के बारे में जानने के लिए [**मैच**](match-entities.md) पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="28597-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="28597-165">निम्नलिखित वीडियो देखें: [प्रारंभ करना: एकीकृत कस्टमर प्रोफ़ाइल बनाना](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="28597-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]