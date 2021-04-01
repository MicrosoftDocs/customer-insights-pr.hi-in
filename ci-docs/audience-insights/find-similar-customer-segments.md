---
title: AI के साथ समान ग्राहकों का पता लगाएं
description: कृत्रिम इंटेलिजेंस वाले समान ग्राहक वर्ग ढूंढें.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596777"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="9735c-103">समान ग्राहक (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="9735c-103">Similar Customers (preview)</span></span>

<span data-ttu-id="9735c-104">यह सुविधा आपको कृत्रिम इंटेलिजेंस का उपयोग करके अपने ग्राहक आधार में समान ग्राहक ढूंढने देती है.</span><span class="sxs-lookup"><span data-stu-id="9735c-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="9735c-105">इस सुविधा का उपयोग करने के लिए आपको कम से कम एक अनुभाग तैयार करना होगा.</span><span class="sxs-lookup"><span data-stu-id="9735c-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="9735c-106">मौजूदा अनुभाग के मापदंडों का विस्तार करने से उन ग्राहकों को खोजने में मदद मिलती है जो उस अनुभाग के समान होते हैं.</span><span class="sxs-lookup"><span data-stu-id="9735c-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="9735c-107">*समान ग्राहक खोजें*, डेटा का मूल्यांकन करने और उस डेटा के आधार पर पूर्वानुमान करने के लिए स्वचालित साधनों का उपयोग करता है और इसलिए इसे प्रोफ़ाइलिंग की एक विधि के रूप में उपयोग करने की क्षमता है, जैसे कि इस शब्द को सामान्य डेटा सुरक्षा विनियम ("GDPR") द्वारा परिभाषित किया गया है.</span><span class="sxs-lookup"><span data-stu-id="9735c-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="9735c-108">डेटा को संसाधित करने के लिए इस सुविधा का ग्राहक द्वारा उपयोग GDPR या दूसरे कानूनों या विनियमों के अधीन हो सकता है.</span><span class="sxs-lookup"><span data-stu-id="9735c-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="9735c-109">आप यह सुनिश्चित करने के लिए ज़िम्मेदार हैं कि भविष्यवाणियों सहित Dynamics 365 Customer Insights का आपका उपयोग गोपनीयता, व्यक्तिगत डेटा, बायोमेट्रिक डेटा, डेटा संरक्षण और संचार की गोपनीयता से संबंधित कानूनों सहित सभी लागू कानूनों और विनियमों का अनुपालन करता है.</span><span class="sxs-lookup"><span data-stu-id="9735c-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="9735c-110">समान ग्राहक ढूंढना</span><span class="sxs-lookup"><span data-stu-id="9735c-110">Finding similar customers</span></span>

1. <span data-ttu-id="9735c-111">ऑडियंस इनसाइट्स में, **सेगमेंट** पर जाएं और उस सेगमेंट का चयन करें, जिस पर आप अपने नए सेगमेंट को आधार बनाना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="9735c-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="9735c-112">वह आपका *स्रोत अनुभाग* है.</span><span class="sxs-lookup"><span data-stu-id="9735c-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="9735c-113">क्रिया पट्टी में, **समान ग्राहक ढूंढें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9735c-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="9735c-114">अपने नए अनुभाग के लिए सुझाए गए नाम की समीक्षा करें और यदि आवश्यक हो तो इसे बदल दें.</span><span class="sxs-lookup"><span data-stu-id="9735c-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="9735c-115">उन फ़ील्ड्स की समीक्षा करें जो आपके नए अनुभाग को परिभाषित करती हैं.</span><span class="sxs-lookup"><span data-stu-id="9735c-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="9735c-116">ये फ़ील्ड उस आधार को परिभाषित करती हैं जिस पर सिस्टम आपके स्रोत अनुभाग के समान ग्राहकों को खोजने का प्रयास करेगा.</span><span class="sxs-lookup"><span data-stu-id="9735c-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="9735c-117">सिस्टम डिफ़ॉल्ट रूप से अनुशंसित फ़ील्ड का चयन करेगा.</span><span class="sxs-lookup"><span data-stu-id="9735c-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="9735c-118">जो फ़ील्ड मॉडल प्रदर्शन को महत्वपूर्ण रूप से कम कर सकते हैं उन्हें स्वचालित रूप से शामिल नहीं किया जाता है:</span><span class="sxs-lookup"><span data-stu-id="9735c-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="9735c-119">निम्नलिखित डेटा प्रकारों वाले फ़ील्ड: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="9735c-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="9735c-120">2 से कम या 30 से अधिक कार्डिनालिटी (किसी फ़ील्ड में तत्वों की संख्या) वाली फ़ील्ड</span><span class="sxs-lookup"><span data-stu-id="9735c-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="9735c-121">चुनें कि आप अपने नए अनुभाग में **सभी ग्राहक** या केवल किसी **विशिष्ट मौजूदा अनुभाग** में ग्राहकों को शामिल करना चाहते हैं या नहीं.</span><span class="sxs-lookup"><span data-stu-id="9735c-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="9735c-122">**स्रोत अनुभाग से सभी को बाहर निकालें** चेकबॉक्स का चयन करके अपने स्रोत अनुभाग में ग्राहकों को शामिल न करें.</span><span class="sxs-lookup"><span data-stu-id="9735c-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="9735c-123">डिफ़ॉल्ट रूप से, सिस्टम आपके आउटपुट में लक्षित ऑडिएंस आकार का केवल 20% शामिल करने का सुझाव देता है.</span><span class="sxs-lookup"><span data-stu-id="9735c-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="9735c-124">इस थ्रेशहोल्ड का आवश्यकतानुसार संपादन करें.</span><span class="sxs-lookup"><span data-stu-id="9735c-124">Edit this threshold as needed.</span></span> <span data-ttu-id="9735c-125">थ्रेशहोल्ड बढ़ाने से शुद्धता कम हो जाएगी.</span><span class="sxs-lookup"><span data-stu-id="9735c-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="9735c-126">बाइनरी वर्गीकरण कार्य (मशीन लर्निंग की एक विधि) शुरू करने के लिए, पृष्ठ पर सबसे नीचे की ओर **रन** का चयन करें जो डेटासेट का विश्लेषण करता है.</span><span class="sxs-lookup"><span data-stu-id="9735c-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="9735c-127">समान अनुभाग देखें</span><span class="sxs-lookup"><span data-stu-id="9735c-127">View the similar segment</span></span>

<span data-ttu-id="9735c-128">समान अनुभाग को संसाधित करने के बाद, आपको नया अनुभाग **अनुभाग** पृष्ठ पर सूचीबद्ध मिलेगा.</span><span class="sxs-lookup"><span data-stu-id="9735c-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9735c-129">![समान ग्राहक अनुभाग](media/expanded-segment.png "समान ग्राहक अनुभाग")</span><span class="sxs-lookup"><span data-stu-id="9735c-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="9735c-130">अनुभाग का विवरण खोलने के लिए क्रिया पट्टी पर **देखें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9735c-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="9735c-131">इस दृश्य में [समानता स्कोर](#about-similarity-scores) में परिणाम वितरण के बारे में जानकारी शामिल होती है.</span><span class="sxs-lookup"><span data-stu-id="9735c-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="9735c-132">आपको **अनुभाग के सदस्यों का पूर्वावलोकन** में समानता स्कोर मान भी मिलेंगे.</span><span class="sxs-lookup"><span data-stu-id="9735c-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="9735c-133">समान अनुभाग के आउटपुट का उपयोग करें</span><span class="sxs-lookup"><span data-stu-id="9735c-133">Use the output of a similar segment</span></span>

<span data-ttu-id="9735c-134">आप [समान अनुभाग के आउटपुट के साथ काम करें](segments.md), वैसे ही कर सकते हैं जैसा कि आप अन्य अनुभागों के साथ करते हैं.</span><span class="sxs-lookup"><span data-stu-id="9735c-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="9735c-135">उदाहरण के लिए, अनुभाग को निर्यात करें या एक माप बनाएं.</span><span class="sxs-lookup"><span data-stu-id="9735c-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="9735c-136">समान अनुभाग को रीफ़्रेश करें और संपादित करें</span><span class="sxs-lookup"><span data-stu-id="9735c-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="9735c-137">समान अनुभाग को रीफ़्रेश करने के लिए, इसे **अनुभाग** पृष्ठ पर चुनें और क्रिया पट्टी में **रीफ़्रेश करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9735c-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="9735c-138">समान अनुभाग का संपादन करने से आपका डेटा पुन: संसाधित होगा.</span><span class="sxs-lookup"><span data-stu-id="9735c-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="9735c-139">पहले बनाया गया अनुभाग रीफ़्रेश किए गए डेटा के साथ अद्यतित हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="9735c-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="9735c-140">समान अनुभाग को संपादित करने के लिए, इसे **अनुभाग** पृष्ठ पर चुनें और क्रिया पट्टी में **संपादित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9735c-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="9735c-141">अपने परिवर्तन लागू करें और संसाधन चालू करने के लिए **रन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9735c-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="9735c-142">एक समान अनुभाग को हटाएं</span><span class="sxs-lookup"><span data-stu-id="9735c-142">Delete a similar segment</span></span>

<span data-ttu-id="9735c-143">**अनुभाग** पृष्ठ पर अनुभाग चुनें और क्रिया पट्टी में **हटाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9735c-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="9735c-144">इसके बाद, हटाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="9735c-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="9735c-145">समानता स्कोर के बारे में</span><span class="sxs-lookup"><span data-stu-id="9735c-145">About similarity scores</span></span>

<span data-ttu-id="9735c-146">बाइनरी वर्गीकरण मशीन लर्निंग मॉडल, समान अनुभाग में ग्राहकों को एक स्कोर प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="9735c-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="9735c-147">स्कोर, स्रोत अनुभाग में ग्राहकों के साथ समानता पर आधारित होता है.</span><span class="sxs-lookup"><span data-stu-id="9735c-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="9735c-148">0.55 से कम समानता स्कोर वाले ग्राहक वे होते हैं जिन्हें सिस्टम स्रोत अनुभाग में ग्राहकों के साथ *असमान* होने के रूप में वर्गीकृत करता है</span><span class="sxs-lookup"><span data-stu-id="9735c-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="9735c-149">0.55 - 0.7 के बीच के समानता स्कोर को *कुछ समान* के रूप में वर्गीकृत किया जाता है</span><span class="sxs-lookup"><span data-stu-id="9735c-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="9735c-150">0.7 - 0.85 के बीच के समानता स्कोर को *समान* के रूप में वर्गीकृत किया जाता है</span><span class="sxs-lookup"><span data-stu-id="9735c-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="9735c-151">0.85 - 1 के बीच के समानता स्कोर वाले ग्राहकों को सिस्टम *बहुत समान* के रूप में वर्गीकृत करता है</span><span class="sxs-lookup"><span data-stu-id="9735c-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="9735c-152">0.4 से नीचे के स्कोर वाले ग्राहकों को मॉडल आउटपुट में शामिल नहीं किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="9735c-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="9735c-153">सिस्टम उन्हें स्रोत अनुभाग के समान पर्याप्त नहीं मानता है.</span><span class="sxs-lookup"><span data-stu-id="9735c-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]