---
title: उपाय बनाएं और प्रबंधित करें
description: अपने व्यवसाय के प्रदर्शन का विश्लेषण करने और प्रतिबिंबित करने के उपायों को परिभाषित करें.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304797"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="560be-103">उपाय निर्धारित और प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="560be-103">Define and manage measures</span></span>

<span data-ttu-id="560be-104">उपाय आपको ग्राहक व्यवहार और व्यावसायिक प्रदर्शन को बेहतर ढंग से समझने में मदद करते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="560be-105">वे [एकीकृत प्रोफ़ाइल](data-unification.md) से प्रासंगिक मानों को देखते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="560be-106">उदाहरण के लिए, कोई व्यवसाय किसी व्यक्तिगत ग्राहक के खरीद इतिहास या माप को समझने के लिए *प्रति ग्राहक कुल खर्च* देखना चाहता है या संपूर्ण व्यवसाय में कुल-स्तर के राजस्व को समझने के लिए *कंपनी की कुल बिक्री* मापना चाहता है।</span><span class="sxs-lookup"><span data-stu-id="560be-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="560be-107">उपाय बिल्डर, विभिन्न ऑपरेटरों के साथ एक डेटा क्वेरी प्लेटफ़ॉर्म और सरल मैपिंग विकल्पों का उपयोग करके उपाय बनाए जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="560be-108">यह आपको डेटा, समूह परिणामों को फ़िल्टर करने, [निकाय संबंध पथ](relationships.md) का पता लगाने और आउटपुट का पूर्वावलोकन करने देता है.</span><span class="sxs-lookup"><span data-stu-id="560be-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="560be-109">ग्राहक डेटा की क्वेरी और इनसाइट्स निकालने के द्वारा व्यावसायिक गतिविधियों की योजना बनाने के लिए उपाय बिल्डर का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="560be-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="560be-110">उदाहरण के लिए, *प्रति ग्राहक कुल खर्च* और *प्रति ग्राहक कुल रिटर्न* का उपाय बनाने से उच्च व्यय के साथ उच्च वापसी वाले ग्राहकों के समूह की पहचान करने में मदद मिलती है.</span><span class="sxs-lookup"><span data-stu-id="560be-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="560be-111">अगले सर्वोत्तम एक्शन को करने के लिए आप [एक सेगमेंट बना](segments.md) सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="560be-112">शुरूआत से अपना खुद का उपाय बनाएं</span><span class="sxs-lookup"><span data-stu-id="560be-112">Build your own measure from scratch</span></span>

<span data-ttu-id="560be-113">यह अनुभाग आपको स्क्रैच से नया उपाय बनाने की जानकारी देता है.</span><span class="sxs-lookup"><span data-stu-id="560be-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="560be-114">आप डेटा निकायों से डेटा विशेषताओं के साथ एक उपाय का निर्माण कर सकते हैं जो ग्राहक निकाय से जुड़ने के लिए संबंध स्थापित करता है.</span><span class="sxs-lookup"><span data-stu-id="560be-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="560be-115">ऑडिएंस इनसाइट्स में, **माप** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="560be-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="560be-116">**नया** चुनें और **अपना खुद का निर्माण करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="560be-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="560be-117">**नाम संपादित करें** चुनें और उपाय के लिए एक **नाम** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="560be-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="560be-118">यदि आपके नए माप कॉन्फ़िगरेशन में केवल दो फ़ील्ड हैं—उदाहरण के लिए, CustomerID और एक गणना हैं—तो आउटपुट को Customer_Measure नाम के सिस्टम द्वारा जनरेट किए गए निकाय में एक नए कॉलम के रूप में जोड़ा जाएगा।</span><span class="sxs-lookup"><span data-stu-id="560be-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="560be-119">और आप एकीकृत ग्राहक प्रोफ़ाइल में उपाय के मान को देख पाएंगे.</span><span class="sxs-lookup"><span data-stu-id="560be-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="560be-120">अन्य उपाय उनकी अपने निकाय उत्पन्न करेंगे.</span><span class="sxs-lookup"><span data-stu-id="560be-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="560be-121">कॉन्फ़िगरेशन क्षेत्र में, **फ़ंक्शन का चयन करें** ड्रॉपडाउन मेनू से से एकत्रीकरण फ़ंक्शन चुनें।</span><span class="sxs-lookup"><span data-stu-id="560be-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="560be-122">एकत्रीकरण फ़ंक्शन में शामिल हैं:</span><span class="sxs-lookup"><span data-stu-id="560be-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="560be-123">**जोड़ें**</span><span class="sxs-lookup"><span data-stu-id="560be-123">**Sum**</span></span>
   - <span data-ttu-id="560be-124">**औसत**</span><span class="sxs-lookup"><span data-stu-id="560be-124">**Average**</span></span>
   - <span data-ttu-id="560be-125">**गिनती**</span><span class="sxs-lookup"><span data-stu-id="560be-125">**Count**</span></span>
   - <span data-ttu-id="560be-126">**अनन्य की गणना**</span><span class="sxs-lookup"><span data-stu-id="560be-126">**Count Unique**</span></span>
   - <span data-ttu-id="560be-127">**अधिकतम**</span><span class="sxs-lookup"><span data-stu-id="560be-127">**Max**</span></span>
   - <span data-ttu-id="560be-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="560be-128">**Min**</span></span>
   - <span data-ttu-id="560be-129">**पहला**: डेटा रिकॉर्ड का पहला मान लेता है</span><span class="sxs-lookup"><span data-stu-id="560be-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="560be-130">**अंतिम**: डेटा रिकॉर्ड में जोड़ा गया अंतिम मान लेता है</span><span class="sxs-lookup"><span data-stu-id="560be-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="माप की गणना के लिए ऑपरेटर.":::

1. <span data-ttu-id="560be-132">इस उपाय को बनाने के लिए आवश्यक डेटा का चयन करने के लिए **विशेषता जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="560be-133">**विशेषता** टैब चुनें.</span><span class="sxs-lookup"><span data-stu-id="560be-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="560be-134">डेटा निकाय: वह निकाय चुनें जिसमें वह विशेषता शामिल हो जिसे आप मापना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="560be-135">डेटा विशेषता: माप की गणना के लिए एकत्रीकरण फ़ंक्शन में उपयोग की जाने वाली विशेषता चुनें.</span><span class="sxs-lookup"><span data-stu-id="560be-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="560be-136">आप एक समय में केवल एक विशेषता चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="560be-137">आप **उपाय** टैब का चयन करके मौजूदा उपाय से डेटा विशेषता का चयन कर सकते हैं. या, आप एक निकाय की खोज कर सकते हैं या नाम को माप सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="560be-138">उपाय में चयनित विशेषता जोड़ने के लिए **जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="गणना में उपयोग करने के लिए एक विशेषता चुनें":::

1. <span data-ttu-id="560be-140">अधिक जटिल उपायों का निर्माण करने के लिए, आप अधिक विशेषताओं को जोड़ सकते हैं या अपने माप फ़ंक्शन पर गणित ऑपरेटरों का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="गणित ऑपरेटरों के साथ जटिल माप बनाएं":::

1. <span data-ttu-id="560be-142">फ़िल्टर जोड़ने के लिए, कॉन्फ़िगरेशन क्षेत्र में **फ़िल्टर** चुनें.</span><span class="sxs-lookup"><span data-stu-id="560be-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="560be-143">**फिल्टर** फलक के **विशेषता जोड़ें** सेक्शन में, उस विशेषता का चयन करें जिसका उपयोग आप फ़िल्टर बनाने के लिए करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="560be-144">प्रत्येक चयनित विशेषता के लिए फ़िल्टर को परिभाषित करने के लिए फ़िल्टर ऑपरेटर सेट करें.</span><span class="sxs-lookup"><span data-stu-id="560be-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="560be-145">माप में फ़िल्टर जोड़ने के लिए **लागू करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="560be-146">आयाम जोड़ने के लिए, कॉन्फ़िगरेशन क्षेत्र में **आयाम** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="560be-147">आयाम माप आउटपुट निकाय में कॉलम के रूप में दिखाई देंगे.</span><span class="sxs-lookup"><span data-stu-id="560be-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="560be-148">उन डेटा विशेषताओं को जोड़ने के लिए **आयामों को संपादित करें** चुनें, जिनके द्वारा आप माप मानों को समूहित करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="560be-149">उदाहरण के लिए, शहर या लिंग।</span><span class="sxs-lookup"><span data-stu-id="560be-149">For example, city or gender.</span></span> <span data-ttu-id="560be-150">डिफ़ॉल्ट रूप से, *ग्राहक-स्तरीय उपाय* बनाने के लिए *CustomerID* आयाम का चयन किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="560be-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="560be-151">यदि आप *व्यवसाय-स्तरीय उपाय* बनाना चाहते हैं तो आप डिफ़ॉल्ट आयाम को हटा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="560be-152">उपाय में आयाम जोड़ने के लिए **पूर्ण** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="560be-153">यदि आपके डेटा में ऐसे मान हैं जिन्हें आपको पूर्णांक से बदलने की आवश्यकता है—उदाहरण के लिए, *शून्य* को *0* के साथ बदलना है, तो—**नियम** चुनें.</span><span class="sxs-lookup"><span data-stu-id="560be-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="560be-154">नियम को कॉन्फ़िगर करें और सुनिश्चित करें कि आप केवल पूर्णांकों को प्रतिस्थापन के रूप में चुनते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="560be-155">यदि आपके द्वारा मैप किए गए डेटा निकाय और *ग्राहक* निकाय के बीच कई पथ हैं, तो आपको पहचान किए गए [निकाय संबंध पथ](relationships.md) में से एक को चुनना होगा.</span><span class="sxs-lookup"><span data-stu-id="560be-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="560be-156">उपाय परिणाम चयनित पथ के आधार पर भिन्न हो सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="560be-157">**डेटा वरीयताओं** का चयन करें और अपने पथ की पहचान करने के लिए जिस निकाय पथ का उपयोग किया जाना चाहिए उसे चुनें.</span><span class="sxs-lookup"><span data-stu-id="560be-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="560be-158">यदि *ग्राहक* निकाय के लिए केवल एक ही पथ है, तो यह नियंत्रण नहीं दिखेगा.</span><span class="sxs-lookup"><span data-stu-id="560be-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="560be-159">अपने चयन को लागू करने के लिए **पूर्ण** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="माप के लिए निकाय पथ का चयन करें.":::

1. <span data-ttu-id="560be-161">माप के लिए अधिक गणना जोड़ने के लिए, **नई गणना** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="560be-162">आप नई गणना के लिए केवल समान निकाय पथ पर निकायों का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="560be-163">अधिक गणना माप आउटपुट निकाय में नए कॉलम के रूप में दिखाई देंगी.</span><span class="sxs-lookup"><span data-stu-id="560be-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="560be-164">एक माप से गणना को **डुप्लिकेट**, **नाम बदलने**, या **निकालने** के लिए गणना पर **...** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="560be-165">**पूर्वावलोकन** क्षेत्र में, आप माप आउटपुट निकाय का डेटा स्कीमा देखेंगे, जिसमें फ़िल्टर और आयाम शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="560be-166">पूर्वावलोकन कॉन्फ़िगरेशन में बदलाव के लिए गतिशील रूप से प्रतिक्रिया करता है.</span><span class="sxs-lookup"><span data-stu-id="560be-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="560be-167">कॉन्फ़िगर किए गए माप के परिणामों की गणना करने के लिए **रन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="560be-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="560be-168">यदि आप वर्तमान कॉन्फ़िगरेशन रखना चाहते हैं और बाद में माप को रन करना चाहते हैं तो **सेव करें और बंद करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="560be-169">सूची में नए बनाए गए माप को देखने के लिए **माप** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="560be-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="560be-170">एक उपाय बनाने के लिए एक टेम्पलेट का उपयोग करें</span><span class="sxs-lookup"><span data-stu-id="560be-170">Use a template to build a measure</span></span>

<span data-ttu-id="560be-171">आप उन्हें बनाने के लिए आमतौर पर उपयोग किए जाने वाले उपायों के पूर्वनिर्धारित टेम्पलेट्स का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="560be-172">टेम्पलेट्स का विस्तृत विवरण और एक निर्देशित अनुभव आपको कुशल उपाय बनाने में मदद करता है.</span><span class="sxs-lookup"><span data-stu-id="560be-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="560be-173">टेम्पलेट्स *एकीकृत गतिविधि* निकाय से मैप किए गए डेटा पर बनाए जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="560be-174">इसलिए सुनिश्चित करें कि आपने टेम्पलेट से उपाय बनाने से पहले [ग्राहक गतिविधियों](activities.md) को कॉन्फ़िगर किया है.</span><span class="sxs-lookup"><span data-stu-id="560be-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="560be-175">माप टेम्पलेट उपलब्ध है:</span><span class="sxs-lookup"><span data-stu-id="560be-175">Available measure templates:</span></span> 
- <span data-ttu-id="560be-176">औसत लेनदेन मूल्य (ATV)</span><span class="sxs-lookup"><span data-stu-id="560be-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="560be-177">कुल लेन-देन मूल्य</span><span class="sxs-lookup"><span data-stu-id="560be-177">Total transaction value</span></span>
- <span data-ttu-id="560be-178">औसत दैनिक राजस्व</span><span class="sxs-lookup"><span data-stu-id="560be-178">Average daily revenue</span></span>
- <span data-ttu-id="560be-179">औसत वर्षिक राजस्व</span><span class="sxs-lookup"><span data-stu-id="560be-179">Average yearly revenue</span></span>
- <span data-ttu-id="560be-180">लेन-देन की गिनती</span><span class="sxs-lookup"><span data-stu-id="560be-180">Transaction count</span></span>
- <span data-ttu-id="560be-181">लॉयल्टी अंक अर्जित</span><span class="sxs-lookup"><span data-stu-id="560be-181">Loyalty points earned</span></span>
- <span data-ttu-id="560be-182">लॉयल्टी पॉइंट्स रिडीम किए गए</span><span class="sxs-lookup"><span data-stu-id="560be-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="560be-183">वफादारी अंक संतुलन</span><span class="sxs-lookup"><span data-stu-id="560be-183">Loyalty points balance</span></span>
- <span data-ttu-id="560be-184">सक्रिय ग्राहक जीवनकाल</span><span class="sxs-lookup"><span data-stu-id="560be-184">Active customer lifespan</span></span>
- <span data-ttu-id="560be-185">लॉयल्टी सदस्यता अवधि</span><span class="sxs-lookup"><span data-stu-id="560be-185">Loyalty membership duration</span></span>
- <span data-ttu-id="560be-186">पिछली खरीद के बाद से समय</span><span class="sxs-lookup"><span data-stu-id="560be-186">Time since last purchase</span></span>

<span data-ttu-id="560be-187">निम्नलिखित प्रक्रिया टेम्पलेट का उपयोग करके एक नया उपाय बनाने के चरणों को रेखांकित करती है.</span><span class="sxs-lookup"><span data-stu-id="560be-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="560be-188">ऑडिएंस इनसाइट्स में, **माप** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="560be-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="560be-189">**नया** चुनें और **एक टेम्पलेट चुनें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="टेम्पलेट पर हाइलाइट के साथ एक नया माप बनाते समय ड्रॉपडाउन मेनू का स्क्रीनशॉट.":::

1. <span data-ttu-id="560be-191">उस टेम्पलेट का पता लगाएं जो आपकी आवश्यकता पर फिट बैठता हो और **टेम्पलेट चुनें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="560be-192">आवश्यक डेटा की समीक्षा करें और यदि आपके पास सभी डेटा मौजूद हैं तो **शुरू करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="560be-193">**संपादित नाम** फलक में, अपने उपाय और आउटपुट निकाय के लिए नाम सेट करें.</span><span class="sxs-lookup"><span data-stu-id="560be-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="560be-194">**पूर्ण** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-194">Select **Done**.</span></span>

1. <span data-ttu-id="560be-195">**समयावधि सेट करें** अनुभाग में, उपयोग करने के लिए डेटा की समय सीमा को परिभाषित करें.</span><span class="sxs-lookup"><span data-stu-id="560be-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="560be-196">**पूरे समय** का चयन करके चुनें कि क्या आप पूरे डेटासेट को कवर करने के लिए नया उपाय चाहते हैं, या आप **विशिष्ट समय अवधि** पर ध्यान केंद्रित करने का उपाय चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="किसी टेम्पलेट से एक उपाय कॉन्फ़िगर करते हुए समयावधि के अनुभाग को दिअकाउंट स्क्रीनशॉट.":::

1. <span data-ttu-id="560be-198">अगले अनुभाग में, गतिविधियों का चयन करने और अपनी *एकीकृत गतिविधि* निकाय से संबंधित डेटा को मैप करने के लिए **डेटा जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="560be-199">2 का चरण 1: **गतिविधि प्रकार** के तहत, उस निकाय का प्रकार चुनें जिसका आप उपयोग करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="560be-200">**गतिविधि** के लिए, उन निकायों का चयन करें जिनको आप मैप करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="560be-201">2 का चरण 2: फॉर्मूले के लिए आवश्यक घटक के लिए *एकीकृत गतिविधि* निकाय से विशेषता चुनें.</span><span class="sxs-lookup"><span data-stu-id="560be-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="560be-202">उदाहरण के लिए, औसत लेनदेन के मान के लिए, यह लेनदेन के मान का प्रतिनिधित्व करने वाली विशेषता है.</span><span class="sxs-lookup"><span data-stu-id="560be-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="560be-203">**गतिविधि टाइमस्टैंप** के लिए, एकीकृत गतिविधि निकाय से वैसी विशेषता चुनें जो गतिविधि की तारीख और समय का प्रतिनिधित्व करती है.</span><span class="sxs-lookup"><span data-stu-id="560be-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="560be-204">एक बार डेटा मैपिंग सफल होने के बाद, आप स्थिति को **पूरा** के रूप में देख सकते हैं और मैप की गई गतिविधियों और विशेषताओं को नाम दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="पूरा हुए किसी उपाय टेम्पलेट के कॉन्फ़िगरेशन का स्क्रीनशॉट.":::

1. <span data-ttu-id="560be-206">अब आप उपाय के परिणामों की गणना करने के लिए **रन** करें का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="560be-207">बाद में इसे परिष्कृत करने के लिए, **ड्राफ्ट सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="560be-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="560be-208">अपने उपाय प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="560be-208">Manage your measures</span></span>

<span data-ttu-id="560be-209">आप **उपाय** पृष्ठ पर उपायों की सूची पा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="560be-210">आप माप प्रकार, निर्माता, निर्माण तिथि, स्थिति और स्थिति के बारे में जानकारी प्राप्त करेंगे.</span><span class="sxs-lookup"><span data-stu-id="560be-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="560be-211">जब आप सूची से कोई माप चुनते हैं, तो आप आउटपुट का पूर्वावलोकन कर सकते हैं और एक CSV फ़ाइल डाउनलोड कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="560be-212">एक साथ अपने सभी उपायों को रिफ्रेश करने के लिए, कोई विशिष्ट उपाय चुने बिना **सभी रिफ्रेश करें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="560be-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="560be-213">![एकल उपायों को प्रबंधित करने के लिए कार्रवाई.](media/measure-actions.png "एकल उपायों को प्रबंधित करने के लिए कार्रवाई.")</span><span class="sxs-lookup"><span data-stu-id="560be-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="560be-214">निम्नलिखित विकल्पों के लिए सूची से माप का चयन करें:</span><span class="sxs-lookup"><span data-stu-id="560be-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="560be-215">उपाय का विवरण देखने के लिए उसका नाम चुनें.</span><span class="sxs-lookup"><span data-stu-id="560be-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="560be-216">उपाय के कॉन्फ़िगरेशन को **संपादित करें**.</span><span class="sxs-lookup"><span data-stu-id="560be-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="560be-217">**रीफ्रेश** डेटा के आधार पर माप को रीफ्रेश करें.</span><span class="sxs-lookup"><span data-stu-id="560be-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="560be-218">उपाय का **नाम बदलें**.</span><span class="sxs-lookup"><span data-stu-id="560be-218">**Rename** the measure.</span></span>
- <span data-ttu-id="560be-219">उपाय **हटाएं**.</span><span class="sxs-lookup"><span data-stu-id="560be-219">**Delete** the measure.</span></span>
- <span data-ttu-id="560be-220">**सक्रिय करें** या **निष्क्रिय करें**.</span><span class="sxs-lookup"><span data-stu-id="560be-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="560be-221">निष्क्रिय माप [निर्धारित रीफ्रेश](system.md#schedule-tab) के दौरान रीफ्रेश नहीं होंगे.</span><span class="sxs-lookup"><span data-stu-id="560be-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="560be-222">कार्यों/प्रक्रियाओं के लिए [छह प्रकार की स्थिति](system.md#status-types) हैं .</span><span class="sxs-lookup"><span data-stu-id="560be-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="560be-223">इसके अतिरिक्त, अधिकांश प्रक्रियाएं [अन्य डाउनस्ट्रीम प्रक्रियाओं पर निर्भर करती हैं](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="560be-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="560be-224">आप पूरे कार्य की प्रगति पर विवरण देखने के लिए प्रक्रिया की स्थिति का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="560be-225">**विवरण देखें** चयन करने के बाद कार्य के किसी एक कार्य के लिए, आपको अतिरिक्त जानकारी मिलेगी: संसाधन समय, अंतिम संसाधन तिथि, और कार्य से जुड़ी सभी त्रुटियां और चेतावनियां.</span><span class="sxs-lookup"><span data-stu-id="560be-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="560be-226">अगला चरण</span><span class="sxs-lookup"><span data-stu-id="560be-226">Next step</span></span>

<span data-ttu-id="560be-227">[एक ग्राहक अनुभाग](segments.md) बनाने के लिए आप मौजूदा उपायों का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="560be-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
