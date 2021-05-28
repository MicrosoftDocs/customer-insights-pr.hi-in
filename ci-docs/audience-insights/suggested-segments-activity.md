---
title: गतिविधि के आधार पर सुझाए गए अनुभाग.
description: ग्राहक गतिविधि के आधार पर मशीन लर्निंग को नए और दिलचस्प अनुभाग खोजने में आपकी मदद करने दें.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034079"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="9b979-103">गतिविधि डेटा के आधार पर सुझाए गए अनुभाग (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="9b979-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="9b979-104">Customer Insights में शामिल ग्राहक गतिविधि डेटा के आधार पर अपने ग्राहकों के दिलचस्प अनुभाग खोजें.</span><span class="sxs-lookup"><span data-stu-id="9b979-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="9b979-105">गतिविधि डेटा के उदाहरण लेन-देन, समर्थन कॉल अवधि, खरीदारी या प्रतिलाभ हैं.</span><span class="sxs-lookup"><span data-stu-id="9b979-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="9b979-106">अनुभागों का सुझाव देने के लिए, गतिविधि डेटा का विश्लेषण रीसेंसी, फ़्रीक्वेंसी और मौद्रिक मान (या अवधि) के लिए किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="9b979-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="9b979-107">वैकल्पिक रूप से, आप [किसी माप को बेहतर बनाने के लिए या किसी विशेषता को बेहतर ढंग से समझने के लिए सुझाए गए अनुभाग उत्पन्न कर सकते हैं](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="9b979-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="गतिविधि-आधारित और विशेषता-आधारित अनुभाग के लिए अनुभाग सुझाव दिखाने वाला सुझाया गया अनुभाग टैब.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="9b979-109">गतिविधि के आधार पर ग्राहकों को वर्गीकृत करें</span><span class="sxs-lookup"><span data-stu-id="9b979-109">Categorize customers by activity</span></span>

<span data-ttu-id="9b979-110">Customer Insights में उपलब्ध [गतिविधि डेटा](activities.md) के साथ, हम ग्राहक समूहों का प्रतिनिधित्व करने वाले सुझाव उत्पन्न कर सकते हैं:</span><span class="sxs-lookup"><span data-stu-id="9b979-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="9b979-111">सर्वाधिक सक्रिय ग्राहक</span><span class="sxs-lookup"><span data-stu-id="9b979-111">most active customers</span></span> 
- <span data-ttu-id="9b979-112">सर्वाधिक खरीदारी करने वाले ग्राहक</span><span class="sxs-lookup"><span data-stu-id="9b979-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="9b979-113">सर्वाधिक राजस्व उत्पन्न करने वाले ग्राहक</span><span class="sxs-lookup"><span data-stu-id="9b979-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="9b979-114">ग्राहक जो हाल ही में सक्रिय नहीं हुए हैं</span><span class="sxs-lookup"><span data-stu-id="9b979-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="9b979-115">ग्राहक जो अक्सर आपके व्यवसाय के साथ सहभागिता करते हैं</span><span class="sxs-lookup"><span data-stu-id="9b979-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="9b979-116">यदि आपका कोई खुदरा व्यवसाय है, तो आप पता लगा सकते हैं कि कौन से ग्राहक सर्वाधिक राजस्व अर्जित करते हैं और उन्हें कूपन द्वारा पुरस्कृत कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9b979-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="9b979-117">या आप अनियत ग्राहकों की पहचान कर सकते हैं और उन्हें किसी पुरस्कार कार्यक्रम में शामिल होने की पेशकश कर सकते हैं ताकि वे आपके व्यवसाय में अधिक हिस्सेदारी करें.</span><span class="sxs-lookup"><span data-stu-id="9b979-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="9b979-118">यदि आप सार्वजनिक स्वास्थ्य सेवा प्रदान करने वाले स्वास्थ्य सेवा व्यवसाय में हैं और आपका लक्ष्य व्यक्तिगत रोगियों के लिए खर्चों को कम करना है.</span><span class="sxs-lookup"><span data-stu-id="9b979-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="9b979-119">ऐसा करने का एक तरीका यह हो सकता है कि यथासंभव कम से कम विजिट में सर्वोत्तम देखभाल उपलब्ध कराई जाए ताकि बार-बार की विजिट घटाई जा सके.</span><span class="sxs-lookup"><span data-stu-id="9b979-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="9b979-120">इस मामले में, आपका लक्ष्य विज़िट की आवृत्ति कम रखना और रोगियों के लिए आवर्ती लागत को कम करना है.</span><span class="sxs-lookup"><span data-stu-id="9b979-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="9b979-121">या आप उन रोगियों के वर्गों की पहचान कर सकते हैं जो बार-बार एपॉइंटमेंट्स लेते हैं, जिनका बार-बार होने वाला खर्च अधिक है, और व्यक्ति के उपचार में सुधार के लिए इन मामलों का विश्लेषण कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9b979-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="9b979-122">आवश्यक डेटा</span><span class="sxs-lookup"><span data-stu-id="9b979-122">Required data</span></span>

<span data-ttu-id="9b979-123">चयनित इनपुट डेटा के आधार पर सुझाव तैयार किए जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="9b979-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="9b979-124">ग्राहक प्रोफाइल: सभी ग्राहक या एक विशिष्ट अनुभाग के सदस्य.</span><span class="sxs-lookup"><span data-stu-id="9b979-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="9b979-125">समय अवधि: पिछले महीने, पिछले साल, या कोई कस्टम समय सीमा.</span><span class="sxs-lookup"><span data-stu-id="9b979-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="9b979-126">गतिविधि का प्रकार: खरीदारी, खुदरा लेनदेन, ऑनलाइन लेनदेन, ग्राहक सहायता मामले, सदस्यता, आदि.</span><span class="sxs-lookup"><span data-stu-id="9b979-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="9b979-127">Customer Insights में वह निकाय जिसमें गतिविधि डेटा होता है: UnifiedActivity निकाय या किसी विशिष्ट गतिविधि के लिए निकाय.</span><span class="sxs-lookup"><span data-stu-id="9b979-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="9b979-128">सम्मिलित करने के लिए आयाम: आपकी व्यावसायिक आवश्यकताओं के आधार पर रीसेंसी, आवृत्ति, या मौद्रिक आयाम।</span><span class="sxs-lookup"><span data-stu-id="9b979-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="9b979-129">सुझाए गए सेगमेंट जनरेट करें</span><span class="sxs-lookup"><span data-stu-id="9b979-129">Generate suggested segments</span></span>

1. <span data-ttu-id="9b979-130">**सेगमेंट** अनुभाग पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="9b979-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="9b979-131">**सुझाव (पूर्वावलोकन)** टैब चुनें.</span><span class="sxs-lookup"><span data-stu-id="9b979-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="9b979-132">**नए सुझाव ढूंढें** चुनें और **ग्राहक व्यवहार देखें या अनुमान लगाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9b979-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="9b979-133">निर्देशित अनुभव चलाने के लिए **शुरू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9b979-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="गतिविधि के आधार पर सुझाए गए सेगमेंट के लिए कॉन्फ़िगरेशन विज़ार्ड का पहला चरण.":::

1. <span data-ttu-id="9b979-135">आवश्यक इनपुट डेटा प्रदान करें और **अगला** आगे बढ़ें चुनें.</span><span class="sxs-lookup"><span data-stu-id="9b979-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="9b979-136">ग्राहक चुनें: सभी ग्राहकों या एक विशिष्ट अनुभाग को सम्मिलित करें.</span><span class="sxs-lookup"><span data-stu-id="9b979-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="9b979-137">गतिविधि चुनें: गतिविधि प्रकार और गतिविधि का वर्णन करने वाले निकायों को चुनें.</span><span class="sxs-lookup"><span data-stu-id="9b979-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="9b979-138">वरीयताएं: ध्यानार्थ समयावधि, सुझावों के लिए कारक, और विशेषताओं को मैप करें.</span><span class="sxs-lookup"><span data-stu-id="9b979-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="9b979-139">अपने इनपुट की समीक्षा करें और मॉडल चलाने और सुझाव जनरेट करने के लिए **रन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9b979-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="9b979-140">ग्राहक प्रोफाइल और चयनित गतिविधियों की संख्या के आधार पर, इसे पूरा होने में कुछ मिनट लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9b979-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="9b979-141">सुझाव जनरेट करने के बाद, आप उन्हें उस आयाम या मान के आधार पर फ़िल्टर कर सकते हैं जिसमें आप सबसे अधिक रुचि रखते हैं.</span><span class="sxs-lookup"><span data-stu-id="9b979-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="9b979-142">किसी सुझाए गए अनुभाग का विवरण देखें</span><span class="sxs-lookup"><span data-stu-id="9b979-142">View details of a suggested segment</span></span>

<span data-ttu-id="9b979-143">सुझाव जनरेट होने के बाद, आप उन्हें **अनुभाग** > **सुझाव (पूर्वावलोकन)** पर **गतिविधि-आधारित सुझाव** अनुभाग में सूचीबद्ध पाएंगे.</span><span class="sxs-lookup"><span data-stu-id="9b979-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="सुझाए गए अनुभाग का विस्तृत डेटा दिखाते हुए विस्तृत साइड फलक.":::

<span data-ttu-id="9b979-145">सुझाए गए अनुभाग पर **सुझाव देखें** का चयन करके उस अनुभाग का विवरण देखें.</span><span class="sxs-lookup"><span data-stu-id="9b979-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="9b979-146">साइड फलक लक्ष्य समूह की तुलना में प्रत्येक आयाम की सीमा जैसे विवरण प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="9b979-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="9b979-147">यह अनुभाग में संभावित सदस्यों की संख्या और कुल ग्राहकों के संगत प्रतिशत पर भी प्रकाश डालता है.</span><span class="sxs-lookup"><span data-stu-id="9b979-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="9b979-148">यदि आप सुझाव को एक अनुभाग के रूप में रखना चाहते हैं, तो **सेगमेंट बनाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9b979-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="9b979-149">सुझाव को एक अनुभाग के रूप में सेव करें</span><span class="sxs-lookup"><span data-stu-id="9b979-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="9b979-150">**अनुभाग** > **सुझाव (पूर्वावलोकन)** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="9b979-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="9b979-151">वो अनुभाग चुनें जिसे आप सेव करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="9b979-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="9b979-152">साइड फलक में, **सेगमेंट बनाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9b979-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="9b979-153">अनुभाग को सहेजने के बाद, यह **सभी अनुभाग** टैब पर अनुभाग की सूची में दिखाई देगा. इसे अब [किसी भी अन्य अनुभाग की तरह ताज़ा या हटाया जा सकता है](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9b979-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="9b979-154">आप अनुभाग विवरण संपादित नहीं कर सकते.</span><span class="sxs-lookup"><span data-stu-id="9b979-154">You can't edit the segment details.</span></span> <span data-ttu-id="9b979-155">हालाँकि, आप सुझावों के लिए इनपुट मानदंड बदल सकते हैं और विभिन्न सुझाव उत्पन्न कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9b979-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="9b979-156">सुझावों का एक सेट रिफ़्रेश करें या संपादित करें</span><span class="sxs-lookup"><span data-stu-id="9b979-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="9b979-157">**अनुभाग** > **सुझाव (पूर्वावलोकन)** पर जाएं और **गतिविधि-आधारित सुझाव** अनुभाग में अनुभाग देखें.</span><span class="sxs-lookup"><span data-stu-id="9b979-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="9b979-158">कॉन्फ़िगर किए गए एट्रिब्यूट को रखते हुए सुझावों को रिफ़्रेश करने के लिए **सुझावों को रिफ़्रेश करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9b979-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="9b979-159">या कॉन्फ़िगर की गई विशेषताओं को संशोधित करने के लिए **सुझाव संपादित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9b979-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="9b979-160">सिस्टम प्रक्रिया को फिर से चलाएगा, नवीनतम डेटा के आधार पर अनुभाग सुझाव उत्पन्न करेगा, और वर्तमान सुझावों को प्रतिस्थापित करेगा.</span><span class="sxs-lookup"><span data-stu-id="9b979-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
