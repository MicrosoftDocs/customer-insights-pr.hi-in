---
title: अनुभाग बनाएं और प्रबंधित करें
description: ग्राहकों को विभिन्न विशेषताओं के आधार पर समूहित करने के लिए उनके सेगमेंट बनाएं.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597054"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="d4dbf-103">अनुभाग बनाएं और प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="d4dbf-103">Create and manage segments</span></span>

<span data-ttu-id="d4dbf-104">सेगमेंट्स आपको जनसांख्यिकीय, लेन-देन या व्यवहार संबंधी विशेषताओं के आधार पर अपने ग्राहकों को समूहित करने देते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="d4dbf-105">आप अपने व्यावसायिक लक्ष्यों को प्राप्त करने के लिए प्रचार अभियानों, बिक्री गतिविधियों और ग्राहक सहायता कार्यों को लक्षित करने के लिए अनुभागों का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="d4dbf-106">आप ग्राहक की प्रोफ़ाइल इकाई और उसकी संबंधित इकाइयों के बारे में जटिल फ़िल्टर निर्धारित कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="d4dbf-107">प्रत्येक अनुभाग, संसाधित किए जाने के बाद, ग्राहक रिकॉर्ड का सेट बनाता है जिसे आप निर्यात कर सकते हैं और उस पर कार्रवाई कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="d4dbf-108">कुछ [सेवा सीमा](service-limits.md) लागू होते हैं .</span><span class="sxs-lookup"><span data-stu-id="d4dbf-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="d4dbf-109">जब तक अन्यथा नहीं कहा जाता है, सभी सेगमेंट्स **डायनामिक सेगमेंट्स** हैं, जो एक आवर्ती शेड्यूल पर रीफ़्रेश होते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="d4dbf-110">निम्नलिखित उदाहरण विभाजन की क्षमता को दर्शाता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="d4dbf-111">हमने उन ग्राहकों के लिए एक खंड को परिभाषित किया है जिन्होंने पिछले 90 दिनों में कम से कम $500 का सामान ऑर्डर किया था *और* जो एक ग्राहक सेवा कॉल में शामिल थे जिसे आगे बढ़ाया गया.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4dbf-112">![एकाधिक समूह](media/segmentation-group1-2.png "एकाधिक समूह")</span><span class="sxs-lookup"><span data-stu-id="d4dbf-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="d4dbf-113">कोई नया सेगमेंट बनाना</span><span class="sxs-lookup"><span data-stu-id="d4dbf-113">Create a new segment</span></span>

<span data-ttu-id="d4dbf-114">सेगमेंट्स को **सेगमेंट्स** पृष्ठ पर प्रबंधित किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="d4dbf-115">ऑडिएंस इनसाइट्स में, **सेगमेंट** पृष्ठ पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="d4dbf-116">**नया** > **रिक्त खंड** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="d4dbf-117">**नया सेगमेंट** फ़लक पर, सेगमेंट प्रकार का चयन करें और कोई **नाम** दें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="d4dbf-118">वैकल्पिक रूप से, कोई प्रदर्शन नाम और ऐसा वर्णन प्रदान करें जिससे सेगमेंट को पहचानने में मदद मिले.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="d4dbf-119">**सेगमेंट बिल्डर** पेज पर पहुंचने के लिए **आगे बढ़ें** का चयन करें, जहां आप समूह को परिभाषित कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="d4dbf-120">समूह, ग्राहकों का एक सेट होता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="d4dbf-121">उस इकाई को चुनें, जिसमें वह विशेषता शामिल हो, जिसके अनुसार आप सेगमेंट करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="d4dbf-122">खंड के लिए विशेषता चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="d4dbf-123">इस विशेषता के चार मान प्रकार हो सकते हैं: संख्यात्मक, स्ट्रिंग, तिथि या बूलियन.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="d4dbf-124">कोई ऑपरेटर और चयनित विशेषता के लिए मूल्य चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4dbf-125">![कस्टम समूह फ़िल्टर](media/customer-group-numbers.png "ग्राहक समूह फ़िल्टर")</span><span class="sxs-lookup"><span data-stu-id="d4dbf-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="d4dbf-126">संख्या</span><span class="sxs-lookup"><span data-stu-id="d4dbf-126">Number</span></span> |<span data-ttu-id="d4dbf-127">परिभाषा</span><span class="sxs-lookup"><span data-stu-id="d4dbf-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="d4dbf-128">1</span><span class="sxs-lookup"><span data-stu-id="d4dbf-128">1</span></span>     |<span data-ttu-id="d4dbf-129">Entity</span><span class="sxs-lookup"><span data-stu-id="d4dbf-129">Entity</span></span>          |
   |<span data-ttu-id="d4dbf-130">2</span><span class="sxs-lookup"><span data-stu-id="d4dbf-130">2</span></span>     |<span data-ttu-id="d4dbf-131">विशेषता</span><span class="sxs-lookup"><span data-stu-id="d4dbf-131">Attribute</span></span>          |
   |<span data-ttu-id="d4dbf-132">3</span><span class="sxs-lookup"><span data-stu-id="d4dbf-132">3</span></span>    |<span data-ttu-id="d4dbf-133">ऑपरेटर</span><span class="sxs-lookup"><span data-stu-id="d4dbf-133">Operator</span></span>         |
   |<span data-ttu-id="d4dbf-134">4</span><span class="sxs-lookup"><span data-stu-id="d4dbf-134">4</span></span>    |<span data-ttu-id="d4dbf-135">मान</span><span class="sxs-lookup"><span data-stu-id="d4dbf-135">Value</span></span>         |

8. <span data-ttu-id="d4dbf-136">यदि [संबन्ध](relationships.md) के माध्यम से निकाय एकीकृत ग्राहक निकाय से जुड़ा है, तो आपको वैध खंड बनाने के लिए संबंध पथ को परिभाषित करने की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="d4dbf-137">संबंध पथ से निकायों को तब तक जोड़ें जब तक आप ड्रॉपडाउन से **ग्राहक: CustomerInsights** निकाय का चयन नहीं कर पाते.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="d4dbf-138">फिर, प्रत्येक स्थिति के लिए **सभी रिकॉर्ड्स** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4dbf-139">![खंड निर्माण के दौरान संबंध पथ](media/segments-multiple-relationships.png "अनुभाग बनाने के दौरान संबंध पथ")</span><span class="sxs-lookup"><span data-stu-id="d4dbf-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="d4dbf-140">डिफ़ॉल्ट रूप से, सेगमेंट एक आउटपुट निकाय उत्पन्न करते हैं जिसमें ग्राहक प्रोफ़ाइल की सभी विशेषता होती हैं जो परिभाषित फिल्टर से मेल खाती हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="d4dbf-141">यदि एक सेगमेंट *ग्राहक* निकाय की तुलना में अन्य निकायों पर आधारित है, तो आप इन निकायों से आउटपुट निकाय में अधिक विशेषताएं जोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="d4dbf-142">उन विशेषताओं को चुनने के लिए जिन्हें आउटपुट निकाय में जोड़ा जाएगा के लिए **प्रोजेक्ट विशेषताएं** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="d4dbf-143">उदाहरण: सेगमेंट एक निकाय पर आधारित होता है जिसमें ग्राहक गतिविधि डेटा होता है जो *ग्राहक* निकाय से संबंधित होता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="d4dbf-144">यह सेगमेंट उन सभी ग्राहकों की तलाश करता है जिन्होंने पिछले 60 दिनों में हेल्प डेस्क को कॉल की है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="d4dbf-145">आप आउटपुट निकाय में सभी मिलान वाले ग्राहक रिकॉर्ड में कॉल की अवधि और कॉल की संख्या को जोड़ना चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="d4dbf-146">यह जानकारी उन ग्राहकों को ऑनलाइन मदद वाले आलेख और FAQ के उपयोगी लिंक के साथ एक ईमेल भेजने में उपयोगी हो सकती है जो बार-बार कॉल करते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="d4dbf-147">सेगमेंट को सहेजने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="d4dbf-148">अगर सभी आवश्यकताओं का सत्यापन हो जाता है, तो आपके सेगमेंट सहेज लिए जाएंगे और उन्हें संसाधित कर लिया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="d4dbf-149">अन्यथा, उन्हें प्रारूप के रूप में सहेज लिया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="d4dbf-150">**अनुभाग** पृष्ठ पर वापस जाने के लिए **अनुभाग में वापस जाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="d4dbf-151">मौजूदा सेगमेंट को प्रबंधित करना</span><span class="sxs-lookup"><span data-stu-id="d4dbf-151">Manage existing segments</span></span>

<span data-ttu-id="d4dbf-152">**सेगमेंट** पेज पर, आप अपने सभी सहेजे गए सेगमेंट देख सकते हैं और उन्हें प्रबंधित कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="d4dbf-153">प्रत्येक अनुभाग को पंक्ति द्वारा दर्शाया जाता है जिसमें अनुभाग के बारे में अतिरिक्त जानकारी शामिल होती है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="d4dbf-154">आप कॉलम शीर्षक का चयन करके किसी कॉलम में खंड को सॉर्ट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="d4dbf-155">अनुभाग को फ़िल्टर करने के लिए शीर्ष-दाएं कोने में **खोज** बॉक्स का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4dbf-156">![किसी मौजूदा खंड को प्रबंधित करने के विकल्प](media/segments-selected-segment.png "मौजूदा अनुभाग को प्रबंधित करने के विकल्प")</span><span class="sxs-lookup"><span data-stu-id="d4dbf-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="d4dbf-157">अनुभाग को चुनने पर, निम्न क्रिया उपलब्ध होती हैं:</span><span class="sxs-lookup"><span data-stu-id="d4dbf-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="d4dbf-158">खंड विवरण **देखें**, जिसमें सदस्य गणना प्रवृत्ति खंड सदस्यों का पूर्वावलोकन शामिल है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="d4dbf-159">इसके गुणों को बदलने के लिए खंड को **संपादित करें**.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="d4dbf-160">एक सेगमेंट का **डुप्लीकेट बनाएं**.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="d4dbf-161">आप इसके गुणों को तुरंत संपादित करना चुन सकते हैं या केवल डुप्लीकेट को सेव कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="d4dbf-162">नवीनतम डेटा शामिल करने के लिए खंड को **रीफ़्रेश करें**.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="d4dbf-163">खंड को **सक्रिय** या **निष्क्रिय** करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="d4dbf-164">अनुभागों की दो संभावित स्थिति हैं - सक्रिय या निष्क्रिय.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="d4dbf-165">अनुभाग को संपादित करने के दौरान ये स्थिति आसान हो जाती हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="d4dbf-166">निष्क्रिय अनुभाग के लिए, अनुभाग परिभाषा मौजूद है, लेकिन उसमें अभी तक कोई ग्राहक नहीं है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="d4dbf-167">जब आप किसी अनुभाग को सक्रिय करते हैं, तो उसकी स्थिति 'निष्क्रिय' से 'सक्रिय' में बदल जाती है और वह उन ग्राहकों की तलाश शुरू कर देता है, जो अनुभाग की परिभाषा से मेल खाते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="d4dbf-168">यदि एक [शेड्यूल किया हुआ रीफ़्रेश](system.md#schedule-tab) कॉन्फ़िगर होता है, तो निष्क्रिय अनुभाग की **स्थिति** **छोड़ी गई** के रूप में सूचीबद्ध होती है, जो यह दर्शाता है कि रीफ़्रेश करने का प्रयास भी नहीं किया गया था.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="d4dbf-169">जब एक निष्क्रिय अनुभाग सक्रिय होता है, तो वह रीफ़्रेश हो जाएगा और शेड्यूल किए गए रीफ़्रेश में शामिल किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="d4dbf-170">वैकल्पिक रूप से, आप विशेष अनुभाग को सक्रिय और निष्क्रिय करने के लिए भविष्य के दिनांक और समय निर्दिष्ट करने हेतु, **सक्रिय करें/निष्क्रिय करें** ड्रॉपडाउन में **बाद में शेड्यूल करें** क्षमता का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="d4dbf-171">अनुभाग का **नाम बदलें**.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-171">**Rename** the segment.</span></span>
- <span data-ttu-id="d4dbf-172">सदस्यों की सूची .CSV फ़ाइल के रूप में **डाउनलोड** करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="d4dbf-173">**इसमें जोड़े** विकल्प अनुभाग में ग्राहक ID की सूची भेजता है, ताकि अन्य एप्लिकेशन में उसे संसाधित किया जा सके.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="d4dbf-174">अनुभाग को **हटाना**.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="d4dbf-175">अनुभाग रीफ़्रेश करें</span><span class="sxs-lookup"><span data-stu-id="d4dbf-175">Refresh segments</span></span>

<span data-ttu-id="d4dbf-176">आप **अनुभाग** पृष्ठ पर **सभी रिफ़्रेश करें** को चुन कर एक बार में सभी अनुभागों को रिफ़्रेश कर सकते हैं या जब आप उन्हें चुनते हैं तो एक या कई अनुभागों को रिफ़्रेश कर सकते हैं और विकल्पों में से **रिफ़्रेश करें** चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="d4dbf-177">वैकल्पिक रूप से, आप **व्यवस्थापक** > **सिस्टम** > **शेड्यूल** पर एक आवर्ती रीफ़्रेश कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="d4dbf-178">कार्यों/प्रक्रियाओं के लिए [छह प्रकार की स्थिति](system.md#status-types) हैं .</span><span class="sxs-lookup"><span data-stu-id="d4dbf-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d4dbf-179">इसके अतिरिक्त, अधिकांश प्रक्रियाएं [अन्य डाउनस्ट्रीम प्रक्रियाओं पर निर्भर करती हैं](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d4dbf-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d4dbf-180">आप पूरे कार्य की प्रगति पर विवरण देखने के लिए प्रक्रिया की स्थिति का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d4dbf-181">किसी एक जॉब कार्य के लिए **विवरण देखें** को चुनने के बाद, आपको अतिरिक्त जानकारी मिलती है: संसाधन समय, अंतिम संसाधन दिनांक और कार्य से जुड़ी सभी त्रुटियां और चेतावनियाँ.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="d4dbf-182">खंड को डाउनलोड और निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="d4dbf-182">Download and export segments</span></span>

<span data-ttu-id="d4dbf-183">आप अपने अनुभाग को CSV फ़ाइल में डाउनलोड कर सकते हैं या उन्हें Dynamics 365 Sales में निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="d4dbf-184">अनुभागों को CSV फ़ाइल में डाउनलोड करें</span><span class="sxs-lookup"><span data-stu-id="d4dbf-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="d4dbf-185">ऑडिएंस इनसाइट्स में, **सेगमेंट** पृष्ठ पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="d4dbf-186">विशिष्ट अनुभाग टाइल में एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="d4dbf-187">कार्रवाई ड्रॉप-डाउन सूची से **CSV के रूप में डाउनलोड करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="d4dbf-188">अनुभागों को Dynamics 365 Sales पर निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="d4dbf-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="d4dbf-189">Dynamics 365 Sales में अनुभाग निर्यात करने से पहले, Dynamics 365 Sales के लिए व्यवस्थापक को [निर्यात गंतव्य बनाने](export-destinations.md) की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="d4dbf-190">ऑडिएंस इनसाइट्स में, **सेगमेंट** पृष्ठ पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="d4dbf-191">विशिष्ट अनुभाग टाइल में एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="d4dbf-192">कार्रवाई की ड्रॉप-डाउन सूची से **में जोड़ें** को चुनें और उस निर्यात गंतव्य का चयन करें, जहां आप डेटा भेजना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="d4dbf-193">सेगमेंट के लिए प्रारूप मोड</span><span class="sxs-lookup"><span data-stu-id="d4dbf-193">Draft mode for segments</span></span>

<span data-ttu-id="d4dbf-194">अगर किसी सेगमेंट को संसाधित करने की सभी आवश्यकताओं की पूर्ति नहीं होती है, तो आप सेगमेंट को प्रारूप के रूप में सहेज सकते हैं और उसे **सेगमेंट** पेज से उस पर पहुंच सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="d4dbf-195">इसे एक निष्क्रिय अनुभाग के रूप में सहेजा जाएगा, और इसे तब तक सक्रिय नहीं किया जा सकता जब तक कि यह वैध न हो जाए.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="d4dbf-196">समूह में और शर्तें जोड़ें</span><span class="sxs-lookup"><span data-stu-id="d4dbf-196">Add more conditions to a group</span></span>

<span data-ttu-id="d4dbf-197">किसी समूह में और शर्तें जोड़ने के लिए आप दो लॉजिकल ऑपरेटर का उपयोग कर सकते हैं:</span><span class="sxs-lookup"><span data-stu-id="d4dbf-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="d4dbf-198">**और** ऑपरेटर: सेगमेंटेशन प्रक्रिया के रूप में दोनों शर्तों की पूर्ति होना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="d4dbf-199">जब आप विभिन्न निकायों में शर्तों को परिभाषित करते हैं तो यह विकल्प सबसे उपयोगी होता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="d4dbf-200">**या** ऑपरेटर: सेगमेंटेशन प्रक्रिया के रूप में किसी भी एक शर्त की पूर्ति होना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="d4dbf-201">जब आप समान निकाय के लिए एकाधिक शर्तों को परिभाषित करते हैं तो यह विकल्प सबसे उपयोगी होता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4dbf-202">![OR ऑपरेटर जहाँ या तो शर्त को पूरा करना आवश्यक है](media/segmentation-either-condition.png "OR ऑपरेटर जहाँ या तो शर्त को पूरा करना आवश्यक है")</span><span class="sxs-lookup"><span data-stu-id="d4dbf-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="d4dbf-203">वर्तमान में किसी **या** ऑपरेटर को **और** ऑपरेटर के अंतर्गत नेस्ट करना संभव है, लेकिन इसके विपरीत नहीं किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="d4dbf-204">एक से अधिक समूहों को संयोजित करना</span><span class="sxs-lookup"><span data-stu-id="d4dbf-204">Combine multiple groups</span></span>

<span data-ttu-id="d4dbf-205">प्रत्येक समूह ग्राहकों का एक विशिष्ट सेट तैयार करता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="d4dbf-206">आप अपने व्यावसायिक मामले के लिए आवश्यक ग्राहकों को शामिल करने के लिए इन समूहों को जोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="d4dbf-207">ऑडियंस इनसाइट्स में, **सेगमेंट** पृष्ठ पर जाएं और एक सेगमेंट चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="d4dbf-208">**समूह जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4dbf-209">![ग्राहक समूह में जाकर कोई समूह जोड़ें](media/customer-group-add-group.png "ग्राहक समूह, समूह जोड़ें")</span><span class="sxs-lookup"><span data-stu-id="d4dbf-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="d4dbf-210">निम्नलिखित सेट संचालकों में से किसी एक को चुनें: **यूनियन**, **इंटरसेक्ट**, या **एक्सेप्ट**.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4dbf-211">![ग्राहक समूह समुच्चय जोड़ें](media/customer-group-union.png "ग्राहक समूह, यूनियन जोड़ें")</span><span class="sxs-lookup"><span data-stu-id="d4dbf-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="d4dbf-212">नया समूह परिभाषित करने के लिए सेट ऑपरेटर चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="d4dbf-213">अलग-अलग समूहों को यह निर्धारित करने के लिए सहेजें कि क्या डेटा बरकरार रखा गया है:</span><span class="sxs-lookup"><span data-stu-id="d4dbf-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="d4dbf-214">**यूनियन** दो समूहों को संयोजित करता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="d4dbf-215">**इंटरसेक्ट** दो समूहों को ओवरलैप करता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="d4dbf-216">केवल डेटा जो दोनों समूहों में *सामान्य है* को एकीकृत समूह में बनाए रखा गया है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="d4dbf-217">**सिवाय** दो समूहों को संयोजित करता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-217">**Except** combines the two groups.</span></span> <span data-ttu-id="d4dbf-218">केवल समूह A में डेटा जो समूह B में डेटा के लिए *सामान्य नहीं है* को बनाए रखा गया है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="d4dbf-219">संसाधन इतिहास और सेगमेंट सदस्य देखें</span><span class="sxs-lookup"><span data-stu-id="d4dbf-219">View processing history and segment members</span></span>

<span data-ttu-id="d4dbf-220">आप डेटा के विवरणों की समीक्षा करके किसी सेगमेंट के बारे में समेकित डेटा देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="d4dbf-221">**सेगमेंट** पेज पर, उन सेगमेंट का चयन करें, जिनकी आप समीक्षा करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="d4dbf-222">पेज के ऊपरी भाग में रुझान का ग्राफ़ शामिल होता है जिससे सदस्यों की संख्या में परिवर्तन विज़ुअलाइज़ किए जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="d4dbf-223">किसी विशिष्ट तिथि पर सदस्यों की संख्या देखने के लिए डेटा पॉइंट पर होवर करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="d4dbf-224">आप विज़ुअलाइज़ेशन की समय सीमा अपडेट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4dbf-225">![अनुभाग समय सीमा](media/segment-time-range.png "अनुभाग समय सीमा")</span><span class="sxs-lookup"><span data-stu-id="d4dbf-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="d4dbf-226">निचले भाग में सेगमेंट सदस्यों की सूची शामिल होती है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="d4dbf-227">वे फ़ील्ड, जो इस सूची में दिखाई देते हैं, आपके अनुभाग के एट्रिब्यूट की विशेषताओं पर आधारित होते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="d4dbf-228">सूची, मिलान वाले सेगमेंट सदस्यों का पूर्वावलोकन देती है और आपके सेगमेंट के पहले 100 रिकॉर्ड दिखाती है ताकि आप उसका तुरंत मूल्यांकन कर सकें और आवश्यकता होने पर उसकी परिभाषाओं की समीक्षा कर सकें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="d4dbf-229">मिलान वाले सभी रिकॉर्ड देखने के लिए आपको [सेगमेंट निर्यात करना](export-destinations.md)होगा.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="d4dbf-230">त्वरित अनुभाग</span><span class="sxs-lookup"><span data-stu-id="d4dbf-230">Quick segments</span></span>

<span data-ttu-id="d4dbf-231">सेगमेंट बिल्डर के अलावा, सेगमेंट्स बनाने के लिए एक और पथ है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="d4dbf-232">त्वरित अनुभाग की मदद से आप तत्काल इनसाइट के साथ तुरंत एकल ऑपरेटर वाले सरल अनुभाग बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="d4dbf-233">**अनुभाग** पेज पर, **नया** > **से जल्दी बनाएं** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="d4dbf-234">वह सेगमेंट बनाने के लिए, जो एकीकृत ग्राहक इकाई पर आधारित है, **प्रोफ़ाइल** विकल्प का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="d4dbf-235">**उपाय** विकल्प का चयन, ग्राहक विशेषता प्रकार के ऐसे उपायों में से हर एक के बारे में सेगमेंट बनाने के लिए करें, जिसे आपने पहले **उपाय** पेज पर बनाया है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="d4dbf-236">**पूर्वानुमान** या **कस्टम मॉडल** क्षमताओं का उपयोग करके उत्पन्न आउटपुट संस्थाओं में से एक के आसपास एक अनुभाग बनाने के लिए **इंटेलिजेंस** विकल्प चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="d4dbf-237">**नया त्वरित अनुभाग** संवाद बॉक्स में, **फ़ील्ड** ड्रॉपडाउन से कोई एक एट्रिब्यूट चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="d4dbf-238">सिस्टम कुछ ऐसी अतिरिक्त इनसाइट प्रदान करेगा, जिससे आपको अपने ग्राहक के लिए बेहतर सेगमेंट बनाने में मदद मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="d4dbf-239">श्रेणीगत फ़ील्ड के लिए, हम 10 शीर्ष ग्राहक गणनाएँ दिखाएंगे.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="d4dbf-240">कोई **मान** चुनें और **समीक्षा करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="d4dbf-241">किसी सांख्यिक विशेषता के लिए, सिस्टम यह दिखाएगा कि हर ग्राहक के पर्सेंटाइल के तहत कौन सा विशेषता मूल्य आता है.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="d4dbf-242">कोई **ऑपरेटर** और किसी **मान** का चयन करें और फिर **समीक्षा करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="d4dbf-243">सिस्टम आपको **अनुमानित सेगमेंट आकार** प्रदान करेगा.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="d4dbf-244">आप यह चुन सकते हैं कि आपको आपके द्वारा निर्धारित सेगमेंट जनरेट किए जाएं या कोई दूसरा सेगमेंट आकार प्राप्त करने के लिए पहले उन पर जाया जाए.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d4dbf-245">![त्वरित अनुभाग के लिए नाम और अनुमान](media/quick-segment-name.png "त्वरित सेगमेंट के लिए नाम और पूर्वानुमान")</span><span class="sxs-lookup"><span data-stu-id="d4dbf-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="d4dbf-246">अपने सेगमेंट के लिए **नाम** दें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="d4dbf-247">वैकल्पिक रूप से, **प्रदर्शन नाम** दें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="d4dbf-248">अपना सेगमेंट बनाने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="d4dbf-249">सेगमेंट का संसाधन समाप्त हो जाने के बाद, आप उसे अपने बनाए गए किसी भी दूसरे सेगमेंट की तरह देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="d4dbf-250">नीचे दिए गए परिदृश्यों के लिए हमारा सुझाव है कि आप अनुशंसित सेगमेंट क्षमता के बजाय सेगमेंट बिल्डर का उपयोग करें:</span><span class="sxs-lookup"><span data-stu-id="d4dbf-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="d4dbf-251">उन श्रेणीकृत फ़ील्ड के लिए फ़िल्टर वाले सेगमेंट बनाना, जिनमें ऑपरेटर **Is** ऑपरेटर से अलग हो</span><span class="sxs-lookup"><span data-stu-id="d4dbf-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="d4dbf-252">उन सांख्यिक फ़ील्ड पर फ़िल्टर वाले सेगमेंट बनाना, जिनमें ऑपरेटर **Between**, **Greater than**, और **Less than** ऑपरेटर से अलग हो</span><span class="sxs-lookup"><span data-stu-id="d4dbf-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="d4dbf-253">दिनांक प्रकार फ़ील्ड पर फ़िल्टर के साथ अनुभाग बनाना</span><span class="sxs-lookup"><span data-stu-id="d4dbf-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="d4dbf-254">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="d4dbf-254">Next steps</span></span>

<span data-ttu-id="d4dbf-255">ग्राहक स्तर पर इनसाइट प्राप्त करने के लिए [अनुभाग निर्यात करें](export-destinations.md) और [ग्राहक कार्ड](customer-card-add-in.md) और [कनेक्टर](export-power-bi.md) का अन्वेषण करें.</span><span class="sxs-lookup"><span data-stu-id="d4dbf-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]