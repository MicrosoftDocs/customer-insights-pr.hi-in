---
title: अनुभाग बनाएं और प्रबंधित करें
description: ग्राहकों को विभिन्न विशेषताओं के आधार पर समूहित करने के लिए उनके सेगमेंट बनाएं.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064939"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="ab41c-103">अनुभाग बनाएं और प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="ab41c-103">Create and manage segments</span></span>

<span data-ttu-id="ab41c-104">एकीकृत ग्राहक निकाय और उससे संबंधित निकायों के आसपास जटिल फ़िल्टर निर्धारित करें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="ab41c-105">प्रत्येक अनुभाग, संसाधित किए जाने के बाद, ग्राहक रिकॉर्ड का सेट बनाता है जिसे आप निर्यात कर सकते हैं और उस पर कार्रवाई कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="ab41c-106">सेगमेंट्स को **सेगमेंट्स** पृष्ठ पर प्रबंधित किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="ab41c-107">निम्नलिखित उदाहरण विभाजन की क्षमता को दर्शाता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="ab41c-108">हमने उन ग्राहकों के लिए एक खंड को परिभाषित किया है जिन्होंने पिछले 90 दिनों में कम से कम $500 का सामान ऑर्डर किया था *और* जो एक ग्राहक सेवा कॉल में शामिल थे जिसे आगे बढ़ाया गया.</span><span class="sxs-lookup"><span data-stu-id="ab41c-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="ग्राहक अनुभाग को निर्दिष्ट करने वाले दो समूहों के साथ अनुभाग निर्माता UI का स्क्रीनशॉट.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="ab41c-110">कोई नया सेगमेंट बनाना</span><span class="sxs-lookup"><span data-stu-id="ab41c-110">Create a new segment</span></span>

<span data-ttu-id="ab41c-111">एक नया अनुभाग बनाने के अनेक तरीके हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="ab41c-112">यह अनुभाग बताता है कि शुरुआत से एक *रिक्त अनुभाग* कैसे बनाया जाता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="ab41c-113">आप वर्तमान निकायों के आधार पर एक *त्वरित अनुभाग* भी बना सकते हैं या *सुझाए गए अनुभाग* प्राप्त करने के लिए मशीन लर्निंग मॉडल का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="ab41c-114">और अधिक जानकारीः [अनुभाग अवलोकन](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ab41c-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="ab41c-115">अनुभाग बनाते समय, आप एक ड्राफ़्ट सहेज सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="ab41c-116">इसे एक निष्क्रिय अनुभाग के रूप में सहेजा जाएगा, और इसे सक्रिय नहीं किया जा सकता, इसे एक मान्य कॉन्फ़िगरेशन के साथ समाप्त किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="ab41c-117">**अनुभाग** पृष्ठ पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="ab41c-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="ab41c-118">**नया** > **रिक्त खंड** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="ab41c-119">**नया अनुभाग** फलक में, एक अनुभाग प्रकार चुनें:</span><span class="sxs-lookup"><span data-stu-id="ab41c-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="ab41c-120">**डायनामिक अनुभाग** [रीफ्रेश करें](segments.md#refresh-segments) पुनरावर्ती शेड्यूल पर.</span><span class="sxs-lookup"><span data-stu-id="ab41c-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="ab41c-121">**स्थिर अनुभाग** जब आप बनाते हैं तो वे एक बार चलते हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="ab41c-122">अनुभाग के लिए **आउटपुट निकाय नाम** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="ab41c-123">वैकल्पिक रूप से, कोई प्रदर्शन नाम और ऐसा वर्णन प्रदान करें जिससे सेगमेंट को पहचानने में मदद मिले.</span><span class="sxs-lookup"><span data-stu-id="ab41c-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="ab41c-124">**सेगमेंट बिल्डर** पेज पर पहुंचने के लिए **आगे बढ़ें** का चयन करें, जहां आप समूह को परिभाषित कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="ab41c-125">समूह, ग्राहकों का एक सेट होता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="ab41c-126">उस इकाई को चुनें, जिसमें वह विशेषता शामिल हो, जिसके अनुसार आप सेगमेंट करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="ab41c-127">खंड के लिए विशेषता चुनें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="ab41c-128">इस विशेषता के चार मान प्रकार हो सकते हैं: संख्यात्मक, स्ट्रिंग, तिथि या बूलियन.</span><span class="sxs-lookup"><span data-stu-id="ab41c-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="ab41c-129">कोई ऑपरेटर और चयनित विशेषता के लिए मूल्य चुनें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ab41c-130">![कस्टम समूह फ़िल्टर](media/customer-group-numbers.png "ग्राहक समूह फ़िल्टर")</span><span class="sxs-lookup"><span data-stu-id="ab41c-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="ab41c-131">नंबर</span><span class="sxs-lookup"><span data-stu-id="ab41c-131">Number</span></span> |<span data-ttu-id="ab41c-132">परिभाषा</span><span class="sxs-lookup"><span data-stu-id="ab41c-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="ab41c-133">1</span><span class="sxs-lookup"><span data-stu-id="ab41c-133">1</span></span>     |<span data-ttu-id="ab41c-134">Entity</span><span class="sxs-lookup"><span data-stu-id="ab41c-134">Entity</span></span>          |
   |<span data-ttu-id="ab41c-135">2</span><span class="sxs-lookup"><span data-stu-id="ab41c-135">2</span></span>     |<span data-ttu-id="ab41c-136">विशेषता</span><span class="sxs-lookup"><span data-stu-id="ab41c-136">Attribute</span></span>          |
   |<span data-ttu-id="ab41c-137">3</span><span class="sxs-lookup"><span data-stu-id="ab41c-137">3</span></span>    |<span data-ttu-id="ab41c-138">ऑपरेटर</span><span class="sxs-lookup"><span data-stu-id="ab41c-138">Operator</span></span>         |
   |<span data-ttu-id="ab41c-139">4</span><span class="sxs-lookup"><span data-stu-id="ab41c-139">4</span></span>    |<span data-ttu-id="ab41c-140">मान</span><span class="sxs-lookup"><span data-stu-id="ab41c-140">Value</span></span>         |

   1. <span data-ttu-id="ab41c-141">किसी समूह में और शर्तें जोड़ने के लिए आप दो लॉजिकल ऑपरेटर का उपयोग कर सकते हैं:</span><span class="sxs-lookup"><span data-stu-id="ab41c-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="ab41c-142">**और** ऑपरेटर: सेगमेंटेशन प्रक्रिया के रूप में दोनों शर्तों की पूर्ति होना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="ab41c-143">जब आप विभिन्न निकायों में शर्तों को परिभाषित करते हैं तो यह विकल्प सबसे उपयोगी होता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="ab41c-144">**या** ऑपरेटर: सेगमेंटेशन प्रक्रिया के रूप में किसी भी एक शर्त की पूर्ति होना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="ab41c-145">जब आप समान निकाय के लिए एकाधिक शर्तों को परिभाषित करते हैं तो यह विकल्प सबसे उपयोगी होता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="ab41c-146">![OR ऑपरेटर जहाँ या तो शर्त को पूरा करना आवश्यक है](media/segmentation-either-condition.png "OR ऑपरेटर जहाँ या तो शर्त को पूरा करना आवश्यक है")</span><span class="sxs-lookup"><span data-stu-id="ab41c-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="ab41c-147">वर्तमान में किसी **या** ऑपरेटर को **और** ऑपरेटर के अंतर्गत नेस्ट करना संभव है, लेकिन इसके विपरीत नहीं किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="ab41c-148">प्रत्येक समूह ग्राहकों के समूह से मेल खाता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-148">Each group matches set of customers.</span></span> <span data-ttu-id="ab41c-149">आप अपने व्यावसायिक मामले के लिए इच्छित ग्राहकों को शामिल करने के लिए समूहों को जोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="ab41c-150">**समूह जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="ab41c-151">![ग्राहक समूह में जाकर कोई समूह जोड़ें](media/customer-group-add-group.png "ग्राहक समूह, समूह जोड़ें")</span><span class="sxs-lookup"><span data-stu-id="ab41c-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="ab41c-152">सेट ऑपरेटरों में से एक का चयन करें: **संघ**, **व्यंजक**, या **एक्सेप्ट**.</span><span class="sxs-lookup"><span data-stu-id="ab41c-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ab41c-153">![ग्राहक समूह समुच्चय जोड़ें](media/customer-group-union.png "ग्राहक समूह, यूनियन जोड़ें")</span><span class="sxs-lookup"><span data-stu-id="ab41c-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="ab41c-154">**यूनियन** दो समूहों को संयोजित करता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="ab41c-155">**इंटरसेक्ट** दो समूहों को ओवरलैप करता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="ab41c-156">केवल डेटा जो दोनों समूहों में *सामान्य है* को एकीकृत समूह में बनाए रखा गया है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="ab41c-157">**सिवाय** दो समूहों को संयोजित करता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-157">**Except** combines the two groups.</span></span> <span data-ttu-id="ab41c-158">केवल समूह A में डेटा जो समूह B में डेटा के लिए *सामान्य नहीं है* को बनाए रखा गया है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="ab41c-159">यदि [संबन्ध](relationships.md) के माध्यम से निकाय एकीकृत ग्राहक निकाय से जुड़ा है, तो आपको वैध खंड बनाने के लिए संबंध पथ को परिभाषित करने की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="ab41c-160">संबंध पथ से निकायों को तब तक जोड़ें जब तक आप ड्रॉपडाउन से **ग्राहक: CustomerInsights** निकाय का चयन नहीं कर पाते.</span><span class="sxs-lookup"><span data-stu-id="ab41c-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="ab41c-161">फिर, प्रत्येक चरण के लिए **सभी रिकॉर्ड** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ab41c-162">![खंड निर्माण के दौरान संबंध पथ](media/segments-multiple-relationships.png "अनुभाग बनाने के दौरान संबंध पथ")</span><span class="sxs-lookup"><span data-stu-id="ab41c-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="ab41c-163">डिफ़ॉल्ट रूप से, सेगमेंट एक आउटपुट निकाय उत्पन्न करते हैं जिसमें ग्राहक प्रोफ़ाइल की सभी विशेषता होती हैं जो परिभाषित फिल्टर से मेल खाती हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="ab41c-164">यदि एक सेगमेंट *ग्राहक* निकाय की तुलना में अन्य निकायों पर आधारित है, तो आप इन निकायों से आउटपुट निकाय में अधिक विशेषताएं जोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="ab41c-165">उन विशेषताओं को चुनने के लिए जिन्हें आउटपुट निकाय में जोड़ा जाएगा के लिए **प्रोजेक्ट विशेषताएं** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="ab41c-166">उदाहरण: सेगमेंट एक निकाय पर आधारित होता है जिसमें ग्राहक गतिविधि डेटा होता है जो *ग्राहक* निकाय से संबंधित होता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="ab41c-167">यह सेगमेंट उन सभी ग्राहकों की तलाश करता है जिन्होंने पिछले 60 दिनों में हेल्प डेस्क को कॉल की है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="ab41c-168">आप आउटपुट निकाय में सभी मिलान वाले ग्राहक रिकॉर्ड में कॉल की अवधि और कॉल की संख्या को जोड़ना चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="ab41c-169">यह जानकारी उन ग्राहकों को ऑनलाइन मदद वाले आलेख और FAQ के उपयोगी लिंक के साथ एक ईमेल भेजने में उपयोगी हो सकती है जो बार-बार कॉल करते हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="ab41c-170">प्रस्तुत विशेषताएँ केवल उन निकायों के लिए कार्य करती हैं जिनका ग्राहक निकाय के साथ एक-से-अनेक संबंध होता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="ab41c-171">उदाहरण के लिए, एक ग्राहक के पास एकाधिक सदस्यताएँ हो सकती हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="ab41c-172">आप केवल उस निकाय से विशेषताएं प्रस्तुत कर सकते हैं जिसका उपयोग आपके द्वारा बनाए जा रहे सेगमेंट क्वेरी के प्रत्येक समूह में किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="ab41c-173">प्रस्तुत विशेषताओं को सेट ऑपरेटरों का उपयोग करते समय शामिल किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="ab41c-174">सेगमेंट को सहेजने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="ab41c-175">अगर सभी आवश्यकताओं का सत्यापन हो जाता है, तो आपके सेगमेंट सहेज लिए जाएंगे और उन्हें संसाधित कर लिया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="ab41c-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="ab41c-176">अन्यथा, उन्हें प्रारूप के रूप में सहेज लिया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="ab41c-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="ab41c-177">**अनुभाग** पृष्ठ पर वापस जाने के लिए **अनुभाग में वापस जाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="ab41c-178">त्वरित अनुभाग</span><span class="sxs-lookup"><span data-stu-id="ab41c-178">Quick segments</span></span>

<span data-ttu-id="ab41c-179">त्वरित अनुभाग आपको त्वरित इनसाइट के लिए सिंसल ऑपरेटर के साथ सरल अनुभाग बनाने देता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="ab41c-180">**अनुभाग** पेज पर, **नया** > **इससे बनाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="ab41c-181">*एकीकृत ग्राहक* निकाय पर आधारित अनुभाग बनाने के लिए **प्रोफाइल** विकल्प चुनें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="ab41c-182">आपके द्वारा पहले बनाए गए माप के आसपास एक अनुभाग बनाने के लिए **माप** विकल्प चुनें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="ab41c-183">**पूर्वानुमान** या **कस्टम मॉडल** क्षमताओं का उपयोग करके उत्पन्न आउटपुट संस्थाओं में से एक के आसपास एक अनुभाग बनाने के लिए **इंटेलिजेंस** विकल्प चुनें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="ab41c-184">**नया त्वरित अनुभाग** संवाद बॉक्स में, **फ़ील्ड** ड्रॉपडाउन से कोई एक एट्रिब्यूट चुनें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="ab41c-185">सिस्टम कुछ ऐसी अतिरिक्त इनसाइट प्रदान करेगा, जिससे आपको अपने ग्राहक के लिए बेहतर सेगमेंट बनाने में मदद मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="ab41c-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="ab41c-186">श्रेणीगत फ़ील्ड के लिए, हम 10 शीर्ष ग्राहक गणनाएँ दिखाएंगे.</span><span class="sxs-lookup"><span data-stu-id="ab41c-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="ab41c-187">कोई **मान** चुनें और **समीक्षा करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="ab41c-188">किसी सांख्यिक विशेषता के लिए, सिस्टम यह दिखाएगा कि हर ग्राहक के पर्सेंटाइल के तहत कौन सा विशेषता मूल्य आता है.</span><span class="sxs-lookup"><span data-stu-id="ab41c-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="ab41c-189">कोई **ऑपरेटर** और किसी **मान** का चयन करें और फिर **समीक्षा करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="ab41c-190">सिस्टम आपको **अनुमानित सेगमेंट आकार** प्रदान करेगा.</span><span class="sxs-lookup"><span data-stu-id="ab41c-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="ab41c-191">आप यह चुन सकते हैं कि आपको आपके द्वारा निर्धारित सेगमेंट जनरेट किए जाएं या कोई दूसरा सेगमेंट आकार प्राप्त करने के लिए पहले उन पर जाया जाए.</span><span class="sxs-lookup"><span data-stu-id="ab41c-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ab41c-192">![त्वरित अनुभाग के लिए नाम और अनुमान](media/quick-segment-name.png "त्वरित सेगमेंट के लिए नाम और पूर्वानुमान")</span><span class="sxs-lookup"><span data-stu-id="ab41c-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="ab41c-193">अपने सेगमेंट के लिए **नाम** दें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="ab41c-194">वैकल्पिक रूप से, **प्रदर्शन नाम** दें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="ab41c-195">अपना सेगमेंट बनाने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="ab41c-196">सेगमेंट का संसाधन समाप्त हो जाने के बाद, आप उसे अपने बनाए गए किसी भी दूसरे सेगमेंट की तरह देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ab41c-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ab41c-197">अगले कदम</span><span class="sxs-lookup"><span data-stu-id="ab41c-197">Next steps</span></span>

<span data-ttu-id="ab41c-198">ग्राहक स्तर पर इनसाइट प्राप्त करने के लिए [अनुभाग निर्यात करें](export-destinations.md) और [ग्राहक कार्ड](customer-card-add-in.md) और [कनेक्टर](export-power-bi.md) का अन्वेषण करें.</span><span class="sxs-lookup"><span data-stu-id="ab41c-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
