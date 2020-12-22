---
title: निकायों और निकाय पथों के बीच संबंध
description: कई डेटा स्रोतों से निकायों के बीच संबंध बनाएं और प्रबंधित करें.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405967"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="7f475-103">निकाय के बीच संबंध</span><span class="sxs-lookup"><span data-stu-id="7f475-103">Relationships between entities</span></span>

<span data-ttu-id="7f475-104">संबंध से आपको इकाइयों को कनेक्ट करने और अपने डेटा का ग्राफ़ जनरेट करने में मदद मिलती है, जबकि दोनों इकाइयों में ऐसा सामान्य आइडेंटिफ़ायर (फ़ॉरेन की) मौजूद हो, जिसे एक इकाई से दूसरी इकाई में संदर्भित किया जा सकता हो.</span><span class="sxs-lookup"><span data-stu-id="7f475-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="7f475-105">कनेक्ट की गई इकाइयों से आप एक से अधिक डेटा स्रोतों के आधार पर सेगमेंट और उपाय परिभाषित कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7f475-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="7f475-106">दो प्रकार के संबंध होते हैं.</span><span class="sxs-lookup"><span data-stu-id="7f475-106">There are two types of relationships.</span></span> <span data-ttu-id="7f475-107">संपादन नहीं करने योग्य सिस्टम संबंध, जो अपने आप बनाए जाते हैं, और कस्टम संबंध जिन्हें उपयोगकर्ता द्वारा बनाया और कॉन्फ़िगर किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="7f475-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="7f475-108">मिलान करने और मर्ज करने की प्रक्रिया के दौरान सिस्टम संबंध, इंटेलिजेंट मिलान प्रक्रिया के आधार पर पृष्ठभूमि में बनाए जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="7f475-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="7f475-109">इन संबंधों से दूसरी संगत इकाइयों के रिकॉर्ड को ग्राहक प्रोफ़ाइल रिकॉर्ड से तुलना करने में मदद मिलती है.</span><span class="sxs-lookup"><span data-stu-id="7f475-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="7f475-110">नीचे दिए गए आरेख से तीन सिस्टम संबंधों को बनाने का तरीका चित्रित होता है, जबकि अंतिम ग्राहक प्रोफ़ाइल इकाई बनाने के लिए ग्राहक इकाई का मिलान अतिरिक्त इकाइयों से किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="7f475-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7f475-111">![संबंध बनाना](media/relationships-entities-merge.png "संबंध बनाना")</span><span class="sxs-lookup"><span data-stu-id="7f475-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="7f475-112">ग्राहक इकाई और संपर्क इकाई के बीच ***CustomerToContact* संबंध** बनाया गया.</span><span class="sxs-lookup"><span data-stu-id="7f475-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="7f475-113">संपर्क इकाई मुख्य फ़ील्ड **contactId** से तुलना करने के लिए ग्राहक इकाई को मुख्य फ़ील्ड **Contact_contactId** प्राप्त होता है.</span><span class="sxs-lookup"><span data-stu-id="7f475-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="7f475-114">ग्राहक निकाय और संपर्क खाता के बीच **_CustomerToContact_ संबंध** बनाया गया.</span><span class="sxs-lookup"><span data-stu-id="7f475-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="7f475-115">संपर्क इकाई मुख्य फ़ील्ड **contactId** से तुलना करने के लिए ग्राहक इकाई को मुख्य फ़ील्ड **Contact_contactId** प्राप्त होता है.</span><span class="sxs-lookup"><span data-stu-id="7f475-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="7f475-116">ग्राहक निकाय और WebAccount निकाय के बीच **_CustomerToWebAccount_ संबंध** बनाया गया.</span><span class="sxs-lookup"><span data-stu-id="7f475-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="7f475-117">WebAccount निकाय मुख्य फ़ील्ड **webaccountId** से तुलना करने के लिए ग्राहक निकाय को मुख्य फ़ील्ड **WebAccount_webaccountId** प्राप्त होता है.</span><span class="sxs-lookup"><span data-stu-id="7f475-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="7f475-118">संबंध बनाएँ</span><span class="sxs-lookup"><span data-stu-id="7f475-118">Create a relationship</span></span>

<span data-ttu-id="7f475-119">**संबंध** पेज पर ग्राहक संबंध परिभाषित करें.</span><span class="sxs-lookup"><span data-stu-id="7f475-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="7f475-120">हर एक संबंध में एक स्रोत इकाई (वह इकाई, जो फ़ॉरेन कुंजी रखती है) और लक्ष्य इकाई (वह इकाई, जिसे स्रोत इकाई की फ़ॉरेन-कुंजी इंगित करती है) होती है.</span><span class="sxs-lookup"><span data-stu-id="7f475-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="7f475-121">ऑडियंस इनसाइट में, **डेटा** > **संबंध** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="7f475-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="7f475-122">**नया संबंध** चुनें.</span><span class="sxs-lookup"><span data-stu-id="7f475-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="7f475-123">**संबंध जोड़ें** फलक में, नीचे दी गई जानकारी प्रदान करें:</span><span class="sxs-lookup"><span data-stu-id="7f475-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7f475-124">![संबंध के विवरण दर्ज करें](media/relationships-add.png "संबंध के विवरण दर्ज करें")</span><span class="sxs-lookup"><span data-stu-id="7f475-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="7f475-125">**संबंध का नाम**: वह नाम, जो संबंध के उद्देश्य को प्रदर्शित करता है, (उदाहरण के लिए, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="7f475-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="7f475-126">**वर्णन**: संबंध का विवरण.</span><span class="sxs-lookup"><span data-stu-id="7f475-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="7f475-127">**स्रोत इकाई**: उस इकाई का चयन करें, जिसका उपयोग, संबंध में स्रोत के रूप में किया जाता है (उदाहरण के लिए, WebLog).</span><span class="sxs-lookup"><span data-stu-id="7f475-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="7f475-128">**कार्डिनेलिटी**: स्रोत इकाई रिकॉर्ड की कार्डिनेलिटी का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7f475-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="7f475-129">उदाहरण के लिए, “कई” का मतलब यह है कि एक से अधिक Weblog रिकॉर्ड, एक WebAccount से संबंधित हैं.</span><span class="sxs-lookup"><span data-stu-id="7f475-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="7f475-130">**स्रोत कुंजी फ़ील्ड**: यह स्रोत इकाई में फ़ॉरेन कुंजी फ़ील्ड प्रदर्शित करता है.</span><span class="sxs-lookup"><span data-stu-id="7f475-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="7f475-131">उदाहरण के लिए, WebLog में **accountId** फ़ॉरेन कुंजी फ़ील्ड होता है.</span><span class="sxs-lookup"><span data-stu-id="7f475-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="7f475-132">**लक्ष्य इकाई**: उस इकाई का चयन करें, जिसका उपयोग, संबंध में (उदाहरण के लिए, WebAccount) के लक्ष्य के रूप में किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="7f475-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="7f475-133">**लक्ष्य की कार्डिनेलिटी**: लक्ष्य इकाई रिकोर्ड की कार्डिनेलिटी का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7f475-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="7f475-134">उदाहरण के लिए, “एक” का मतलब यह है कि एक से अधिक Weblog रिकॉर्ड, एक WebAccount से संबंधित हैं.</span><span class="sxs-lookup"><span data-stu-id="7f475-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="7f475-135">**लक्ष्य कुंजी फ़ील्ड**: यह फ़ील्ड, लक्ष्य इकाई का मुख्य फ़ील्ड प्रदर्शित करता है.</span><span class="sxs-lookup"><span data-stu-id="7f475-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="7f475-136">उदाहरण के लिए, WebAccount में **accountId** कुंजी फ़ील्ड होता है.</span><span class="sxs-lookup"><span data-stu-id="7f475-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="7f475-137">केवल अनेक से एक और एक से एक संबंध ही समर्थित हैं.</span><span class="sxs-lookup"><span data-stu-id="7f475-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="7f475-138">कई से कई संबंध, दो कई से एक संबंधों और लिंक इकाई को बनाकर किया जाता है (इकाई जिसका उपयोग स्रोत इकाई और लक्षित इकाई को कनेक्ट करने के लिए किया जाता है).</span><span class="sxs-lookup"><span data-stu-id="7f475-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="7f475-139">किसी संबंध को हटाना</span><span class="sxs-lookup"><span data-stu-id="7f475-139">Delete a relationship</span></span>

1. <span data-ttu-id="7f475-140">ऑडियंस इनसाइट में, **डेटा** > **संबंध** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="7f475-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="7f475-141">आप जिस संबंध को हटाना चाहते हैं, उसके लिए चेक बॉक्स का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7f475-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="7f475-142">**संबंध** तालिका के ऊपरी भाग में **Delete** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7f475-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="7f475-143">हटाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="7f475-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="7f475-144">अगला स्टेप</span><span class="sxs-lookup"><span data-stu-id="7f475-144">Next step</span></span>

<span data-ttu-id="7f475-145">सिस्टम और कस्टम संबंध का उपयोग, एक से अधिक ऐसे डेटा स्रोतों पर आधारित सेगमेंट बनाने के लिए किया जाता है जो अब सिलो नहीं हैं.</span><span class="sxs-lookup"><span data-stu-id="7f475-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="7f475-146">अधिक जानकारी के लिए, [खंड](segments.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="7f475-146">For more information, see [Segments](segments.md).</span></span>
