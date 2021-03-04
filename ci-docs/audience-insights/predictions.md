---
title: भविष्यवाणियों का उपयोग करके आंशिक डेटा पूरा करें
description: अधूरा ग्राहक डेटा भरने के लिए भविष्यवाणियों का उपयोग करें.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268274"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="fca46-103">प्रिडिक्शन्स के साथ अपना आंशिक डेटा पूरा करें</span><span class="sxs-lookup"><span data-stu-id="fca46-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="fca46-104">पूर्वानुमानों से आप आसानी से ऐसे पूर्वानुमानित मान बना सकते हैं, जो ग्राहक के बारे में आपकी समझ को बेहतर बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fca46-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="fca46-105">**इंटेलिजेंस** > **भविष्यवाणियों** पृष्ठ पर, आप उन भविष्यवाणियों को देखने के लिए **मेरी भविष्यवाणियों** का चयन कर सकते हैं जिन्हें आपने ऑडियंस इनसाइट्स के अन्य हिस्सों में कॉन्फ़िगर किया है, और आपको उन्हें और अनुकूलित करने की अनुमति देते हैं.</span><span class="sxs-lookup"><span data-stu-id="fca46-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="fca46-106">आप इस सुविधा का उपयोग नहीं कर सकते हैं, अगर आपके परिवेश में Azure Data Lake Gen 2 संग्रहण का उपयोग किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="fca46-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="fca46-107">पूर्वानुमान सुविधा, डेटा का मूल्यांकन करने के लिए स्वचालित साधनों का उपयोग करती है और उस डेटा के आधार पर पूर्वानुमान लगाती है और इसलिए इसमें प्रोफ़ाइलिंग के तौर पर उपयोग किए जाने की क्षमता होती है, जैसा कि इस शब्द को जनरल डेटा प्रोटेक्शन रेग्यूलेशन (“GDPR”) द्वारा निर्धारित किया गया है.</span><span class="sxs-lookup"><span data-stu-id="fca46-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="fca46-108">डेटा को संसाधित करने के लिए इस सुविधा का ग्राहक द्वारा उपयोग GDPR या दूसरे कानूनों या विनियमों के अधीन हो सकता है.</span><span class="sxs-lookup"><span data-stu-id="fca46-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="fca46-109">आप यह सुनिश्चित करने के लिए ज़िम्मेदार हैं कि भविष्यवाणियों सहित Dynamics 365 Customer Insights का आपका उपयोग गोपनीयता, व्यक्तिगत डेटा, बायोमेट्रिक डेटा, डेटा संरक्षण और संचार की गोपनीयता से संबंधित कानूनों सहित सभी लागू कानूनों और विनियमों का अनुपालन करता है.</span><span class="sxs-lookup"><span data-stu-id="fca46-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fca46-110">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="fca46-110">Prerequisites</span></span>

<span data-ttu-id="fca46-111">आपके संगठन द्वारा इस अनुमान सुविधा उपयोग करने से पहले, निम्नलिखित पूर्व-आवश्यकताएँ पूरी करनी होंगी:</span><span class="sxs-lookup"><span data-stu-id="fca46-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="fca46-112">आपके संगठन का एक उदाहरण है [Common Data Service में स्थापित](https://docs.microsoft.com/ai-builder/build-model#prerequisites) और यह Customer Insights के रूप में एक ही संगठन में है.</span><span class="sxs-lookup"><span data-stu-id="fca46-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="fca46-113">आपका परिवेश आपके Common Data Service उदाहरण से जुड़ा हुआ है.</span><span class="sxs-lookup"><span data-stu-id="fca46-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="fca46-114">यदि आप [नया परिवेश बनाते हैं](manage-environments.md), तो उसे **परिवेश बनाएँ** संवाद में बनाएँ और **उन्नत** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="fca46-115">यदि आपने पहले से कोई परिवेश बनाया है तो उसकी सेटिंग में जाएँ और **उन्नत** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="fca46-116">किसी भी तरीके से, **पूर्वानुमान उपयोग करें** अनुभाग में, Common Data Service उदाहरण URL दर्ज करें, जिसमें आप अपने परिवेश को जोड़ना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="fca46-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="fca46-117">ग्राहक निकाय में पूर्वानुमान बनाएं</span><span class="sxs-lookup"><span data-stu-id="fca46-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="fca46-118">ऑडियंस इनसाइट्स में, **डेटा** > **एंटिटी** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="fca46-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="fca46-119">**ग्राहक** निकाय चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="fca46-120">**ग्राहक: CustomerInsights** निकाय में, **फ़ील्ड्स** टैब पर चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="fca46-121">वह एट्रिब्यूट नाम खोजें, जिसके लिए आप मूल्यों का पूर्वानुमान करना चाहते हैं, फिर **सारांश** स्तंभ में **ओवरव्यू** स्तंभ का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fca46-122">![ओवरव्यू चिह्न](media/intelligence-overviewicon.png "ओवरव्यू चिह्न")</span><span class="sxs-lookup"><span data-stu-id="fca46-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="fca46-123">अगर आपकी विशेषता के लिए अनुपलब्ध मूल्यों की दर बहुत अधिक है, तो अपने पूर्वानुमानों के साथ आगे बढ़ने के लिए **अनुपलब्ध मानों का पूर्वानुमान करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fca46-124">![अनुपलब्ध मानों का पूर्वानुमान बटन के साथ ओवरव्यू स्थिति](media/intelligence-overviewpredictmissingvalues.png "अनुपलब्ध मानों का पूर्वानुमान बटन के साथ ओवरव्यू स्थिति")</span><span class="sxs-lookup"><span data-stu-id="fca46-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="fca46-125">पूर्वानुमान के परिणामों के लिए कोई **प्रदर्शन नाम** और **आउटपुट निकाय नाम** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="fca46-126">आपको विकल्पों की पहले से भरी हुई सूची दिखाई देगी, जिसमें आप मूल्यों को पूर्वानुमानित श्रेणी पर मैप कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fca46-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="fca46-127">इस मामले में, आपके केवल वर्ग विकल्प 0 या 1 होंगे क्योंकि वे अनुमान के सच/गलत या दोहरी प्रकृति की माप करते हैं.</span><span class="sxs-lookup"><span data-stu-id="fca46-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="fca46-128">श्रेणी कॉलम में, अपनी इच्छानुसार “0” के अंतिम पूर्वानुमान में फील्ड मान को “0” के रूप में वर्गीकृत करें और वह मद जिसे आप अंतिम अनुमान में "1" के रूप में वर्गीकृत करना चाहते हैं उसे "1" वर्गीकृत करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fca46-129">![श्रेणी में मैप किए गए फ़ील्ड मानों को दर्शाता उदाहरण](media/intelligence-categorymapping.png "श्रेणी में मैप किए गए फ़ील्ड मानों को दर्शाता उदाहरण")</span><span class="sxs-lookup"><span data-stu-id="fca46-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="fca46-130">**पूर्ण** का चयन करें और पूर्वानुमानों को संसाधित किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="fca46-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="fca46-131">डेटा के आकार और उसकी जटिलता पर निर्भर करते हुए संसाधन में कुछ समय लगेगा.</span><span class="sxs-lookup"><span data-stu-id="fca46-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="fca46-132">आपके द्वारा बनाए गए अनुमान के **आउटपुट निकाय नाम** आधार पर परिणाम नए निकाय में उपलब्ध होंगे.</span><span class="sxs-lookup"><span data-stu-id="fca46-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="fca46-133">खंड बनाने के दौरान कोई पूर्वानुमान बनाना</span><span class="sxs-lookup"><span data-stu-id="fca46-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="fca46-134">खंड बनाते समय अपनी पसंद की किसी विशिष्ट एट्रिब्यूट के लिए अनुपलब्ध नामों का पूर्वानुमान लगाना भी संभव है.</span><span class="sxs-lookup"><span data-stu-id="fca46-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="fca46-135">ख़ासतौर से, जब आप अपनी एकीकृत ग्राहक निकाय या Customer_Measure इकाई के आधार पर तुरंत कोई सेगमेंट बनाते हैं.</span><span class="sxs-lookup"><span data-stu-id="fca46-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="fca46-136">इस प्रवाह के भाग के रूप में, आप अपने खंड का आधार तय करने के लिए एक विशेष गुण चुनेंगे जैसे ग्राहक संतुष्टि या खरीद की राशि.</span><span class="sxs-lookup"><span data-stu-id="fca46-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="fca46-137">खंड बनने पर, सिस्टम इस गुण के लिए यदि कोई अनुपलब्ध वैल्यू हो, तो उसका अनुमान लगाने की विधि बताएगा.</span><span class="sxs-lookup"><span data-stu-id="fca46-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="fca46-138">ऑडियंस इनसाइट्स में, **सेगमेंट्स** पर जाएं और **प्रोफ़ाइल** टाइल चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="fca46-139">कोई सेगमेंट बनाने के लिए कोई **फ़ील्ड** चुनें और किसी **ऑपरेटर** ऑपरेटर का चयन करें, इसके बाद **समीक्षा करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="fca46-140">खंड के लिए कोई **नाम** और **प्रदर्शन नाम** दें.</span><span class="sxs-lookup"><span data-stu-id="fca46-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="fca46-141">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-141">Select **Save**.</span></span>

5. <span data-ttu-id="fca46-142">यदि आपके द्वारा बनाए गए खंड में स्रोत फील्ड में अपूर्ण डेटा है तो आप अनुपलब्ध वैल्यू का अनुमान करने का विकल्प चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fca46-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fca46-143">![पूर्वानुमान बटन](media/segments-predictoption.png "पूर्वानुमान बटन")</span><span class="sxs-lookup"><span data-stu-id="fca46-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="fca46-144">पूर्वानुमान के परिणामों के लिए कोई **प्रदर्शन नाम** और **आउटपुट निकाय नाम** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="fca46-145">**पूर्ण** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-145">Select **Done**.</span></span> <span data-ttu-id="fca46-146">आपका अनुमान जल्द ही एक नया निकाय बनाएगा जो आपके द्वारा **आउटपुट निकाय नाम** के लिए दिए गए नाम से होगा.</span><span class="sxs-lookup"><span data-stu-id="fca46-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="fca46-147">कोई पूर्वानुमान देखें</span><span class="sxs-lookup"><span data-stu-id="fca46-147">View a prediction</span></span>

1. <span data-ttu-id="fca46-148">ऑडियंस इनसाइट्स में, **इंटेलिजेंस** > **पूर्वानुमान** > **मेरी पूर्वानुमान** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="fca46-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="fca46-149">जिसकी आप समीक्षा करना चाहते हैं वह पूर्वानुमान चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="fca46-150">**कार्रवाई** स्तंभ में एलिप्सिस का चयन करें और **देखें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="fca46-151">आपको अपने पूर्वानुमान के दृश्य में बहुत से डेटा पॉइंट दिखाई देंगे.</span><span class="sxs-lookup"><span data-stu-id="fca46-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fca46-152">![पूर्वानुमान पृष्ठ](media/intelligence-predictionsviewpage.png "पूर्वानुमान पृष्ठ")</span><span class="sxs-lookup"><span data-stu-id="fca46-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="fca46-153">**पूर्वानुमानित मान** आपको वह मैपिंग दिखाते हैं, जिन्हें आपने फ़ील्ड मान से श्रेणी मैपिंग चरण के दौरान बनाया था.</span><span class="sxs-lookup"><span data-stu-id="fca46-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="fca46-154">आपके डेटासेट में ये वही वैल्यू हैं जिन्हें विशेष वर्ग माना गया है.</span><span class="sxs-lookup"><span data-stu-id="fca46-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="fca46-155">-**शीर्ष प्रभावित करने वाले**, आपके डेटासेट के अंतर्गत वे कारक हैं, जिनके, किसी विशिष्ट श्रेणी में मैप किए गए आपके फ़ील्ड मानों के पूर्वानुमानों की विश्वसनीयता को प्रभावित करने की सबसे ज़्यादा संभावना है.</span><span class="sxs-lookup"><span data-stu-id="fca46-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="fca46-156">**प्रदर्शन** यह इंगित करता है कि पूर्वानुमान कैसा काम कर रहे हैं.</span><span class="sxs-lookup"><span data-stu-id="fca46-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="fca46-157">अधिक जानने के लिए लिंक का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="fca46-158">**पूर्वावलोकन** आपके पूर्वानुमान और उसकी संभावना से आउटपुट डेटासेट के नमूने दिखाता है या पूर्वानुमानित मान का हमारा विश्वास दर्शाता है, जहां का मतलब 0 अनिश्चित और 1 का मतलब निश्चित है.</span><span class="sxs-lookup"><span data-stu-id="fca46-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="fca46-159">कोई पूर्वानुमान अद्यतन करें</span><span class="sxs-lookup"><span data-stu-id="fca46-159">Update a prediction</span></span>

1. <span data-ttu-id="fca46-160">ऑडियंस इनसाइट्स में, **इंटेलिजेंस** > **पूर्वानुमान** > **मेरी पूर्वानुमान** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="fca46-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="fca46-161">जिस पूर्वानुमान का आप अद्यतन करना चाहते हैं उसे चुनें और **अद्यतन करें** चिह्न का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="fca46-162">पूर्वानुमान को संसाधन के लिए शेड्यूल किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="fca46-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="fca46-163">आप **पूर्वानुमान** पेज पर **अपडेट किया गया** स्तंभ में वह समय देख सकते हैं, जब उसे पिछली बार अपडेट किया गया था.</span><span class="sxs-lookup"><span data-stu-id="fca46-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="fca46-164">कोई पूर्वानुमान संपादित करें</span><span class="sxs-lookup"><span data-stu-id="fca46-164">Edit a prediction</span></span>

<span data-ttu-id="fca46-165">आपके द्वारा अनुमान बनाने के बाद, अपने मॉडल की प्रभावशीलता बढ़ाने के लिए आप AI Builder में मॉडल को अपने अनुकूल बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fca46-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="fca46-166">ऑडियंस इनसाइट्स में, **इंटेलिजेंस** > **पूर्वानुमान** > **मेरी पूर्वानुमान** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="fca46-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="fca46-167">जिस पूर्वानुमान को आप संपादित करना चाहते हैं, उसका चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="fca46-168">**कार्रवाई** स्तंभ में एलिप्सिस का चयन करें और **देखें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="fca46-169">**AI Builder में अनुकूलित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="fca46-170">अपने मॉडल को AI Builder में अपडेट करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="fca46-171">[ AI builder में मॉडल के प्रबंधन के बारे में और अधिक जानें ](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="fca46-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="fca46-172">आपके पूर्वानुमान को अगली बार चलाने पर आपके द्वारा बनाए गए अपडेट मॉडल का इस्तेमाल किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="fca46-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="fca46-173">AI Builder में बनाए गए नए मॉडल को तब तक ऑडियंस इनसाइट्स में नहीं दिखाया जाएगा जब तक कि मॉडल ऊपर सूचीबद्ध अनुभवों से नहीं बनाया गया हो.</span><span class="sxs-lookup"><span data-stu-id="fca46-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="fca46-174">किसी पूर्वानुमान को हटाएँ</span><span class="sxs-lookup"><span data-stu-id="fca46-174">Remove a prediction</span></span>

1. <span data-ttu-id="fca46-175">ऑडियंस इनसाइट्स में, **इंटेलिजेंस** > **पूर्वानुमान** > **मेरी पूर्वानुमान** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="fca46-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="fca46-176">जिसको आप हटाना चाहते हैं वह पूर्वानुमान चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="fca46-177">**कार्रवाई** स्तंभ में एलिप्सिस का चयन करें और **हटाएँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="fca46-178">हटाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="fca46-179">समस्‍या निवारण</span><span class="sxs-lookup"><span data-stu-id="fca46-179">Troubleshooting</span></span>

<span data-ttu-id="fca46-180">यदि आप किसी त्रुटि के कारण अनुलग्नक Common Data Service प्रक्रिया को पूरा नहीं कर सकते हैं, तो आप मैन्युअल रूप से प्रक्रिया को पूरा करने का प्रयास कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fca46-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="fca46-181">दो ज्ञात समस्याएँ हैं जो अनुलग्नक प्रक्रिया में हो सकती हैं:</span><span class="sxs-lookup"><span data-stu-id="fca46-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="fca46-182">ग्राहक कार्ड एड-इन समाधान स्थापित नहीं है.</span><span class="sxs-lookup"><span data-stu-id="fca46-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="fca46-183">[समाधान स्थापित करने और कॉन्फ़िगर करने के लिए](customer-card-add-in.md) के निर्देशों को पूरा करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="fca46-184">अनुप्रयोग की अनुमतियाँ नहीं दी गई है.</span><span class="sxs-lookup"><span data-stu-id="fca46-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="fca46-185">[https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com) पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="fca46-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="fca46-186">**परिवेश** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="fca46-187">उस परिवेश के आगे स्थित एलिप्सिस का चयन करें जिससे आप अनुमति जोड़ना चाहते हैं और **सेटिंग्स** का चयन चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="fca46-188">**उपयोगकर्ता + अनुमतियां** का विस्तार करें और **उपयोगकर्ता** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="fca46-189">**नया** चुनें और फिर **उपयोगकर्ता** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="fca46-190">**अनुप्रयोग उपयोगकर्ता का चयन करें** यदि यह पहले से ही चयनित नहीं है और निम्नलिखित जानकारी दर्ज करें:</span><span class="sxs-lookup"><span data-stu-id="fca46-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="fca46-191">**उपयोगकर्ता नाम:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fca46-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="fca46-192">**अनुप्रयोग ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="fca46-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="fca46-193">**प्रथम नाम:** ग्राहक</span><span class="sxs-lookup"><span data-stu-id="fca46-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="fca46-194">**अंतिम नाम:** इनसाइट</span><span class="sxs-lookup"><span data-stu-id="fca46-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="fca46-195">**प्राथमिक ईमेल:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fca46-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="fca46-196">**सहेजें और बंद करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="fca46-197">आपने जो उपयोगकर्ता बनाई है, उसका चयन अभी करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="fca46-198">शीर्ष मेनू बार में **भूमिका प्रबंधित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fca46-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="fca46-199">**सिस्टम व्यवस्थापक** का चयन करें, फिर **ओके** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fca46-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]