---
title: उपाय बनाएं और प्रबंधित करें
description: अपने व्यवसाय के प्रदर्शन का विश्लेषण करने और प्रतिबिंबित करने के उपायों को परिभाषित करें.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654734"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="f3a5a-103">उपाय निर्धारित और प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="f3a5a-103">Define and manage measures</span></span>

<span data-ttu-id="f3a5a-104">उपाय [एकीकृत प्रोफ़ाइल](data-unification.md) से प्रासंगिक मानों को प्राप्त करके ग्राहक व्यवहार और व्यवसाय के प्रदर्शन को बेहतर ढंग से समझने में आपकी सहायता करते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="f3a5a-105">उदाहरण के लिए, एक व्यवसाय व्यक्तिगत ग्राहक की खरीद के इतिहास को समझने के लिए *प्रति ग्राहक कुल खर्च* देखना चाहता है.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="f3a5a-106">या पूरे व्यवसाय में समग्र-स्तर राजस्व को समझने के लिए *कंपनी का कुल विक्रय* को मापें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="f3a5a-107">उपाय बिल्डर, विभिन्न ऑपरेटरों के साथ एक डेटा क्वेरी प्लेटफ़ॉर्म और सरल मैपिंग विकल्पों का उपयोग करके उपाय बनाए जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="f3a5a-108">यह आपको डेटा, समूह परिणामों को फ़िल्टर करने, [निकाय संबंध पथ](relationships.md) का पता लगाने और आउटपुट का पूर्वावलोकन करने देता है.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="f3a5a-109">ग्राहक डेटा की क्वेरी और इनसाइट्स निकालने के द्वारा व्यावसायिक गतिविधियों की योजना बनाने के लिए उपाय बिल्डर का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="f3a5a-110">उदाहरण के लिए, *प्रति ग्राहक कुल खर्च* और *प्रति ग्राहक कुल रिटर्न* का उपाय बनाने से उच्च व्यय के साथ उच्च वापसी वाले ग्राहकों के समूह की पहचान करने में मदद मिलती है.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="f3a5a-111">अगले सर्वोत्तम एक्शन को करने के लिए आप [एक सेगमेंट बना](segments.md) सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="f3a5a-112">एक उपाय बनाएँ</span><span class="sxs-lookup"><span data-stu-id="f3a5a-112">Create a measure</span></span>

<span data-ttu-id="f3a5a-113">यह अनुभाग आपको स्क्रैच से नया उपाय बनाने की जानकारी देता है.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="f3a5a-114">आप डेटा निकायों से डेटा विशेषताओं के साथ एक उपाय का निर्माण कर सकते हैं जो ग्राहक निकाय से जुड़ने के लिए संबंध स्थापित करता है.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="f3a5a-115">ऑडिएंस इनसाइट्स में, **माप** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="f3a5a-116">**नया** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-116">Select **New**.</span></span>

1. <span data-ttu-id="f3a5a-117">**नाम संपादित करें** चुनें और उपाय के लिए एक **नाम** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="f3a5a-118">यदि आपके नए उपाय कॉन्फ़िगरेशन में केवल दो फ़ील्ड हैं, उदाहरण के लिए, CustomerID और एक गणना, तो आउटपुट को सिस्टम द्वारा उत्पन्न किए गए निकाय के एक नए कॉलम के रूप में जोड़ा जाएगा, जिसे Customer_Measure कहा जाता है.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="f3a5a-119">और आप एकीकृत ग्राहक प्रोफ़ाइल में उपाय के मान को देख पाएंगे.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="f3a5a-120">अन्य उपाय उनकी अपने निकाय उत्पन्न करेंगे.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="f3a5a-121">कॉन्फ़िगरेशन क्षेत्र में, **फ़ंक्शन चुनें** ड्रॉप-डाउन मेनू से एकत्रीकरण फ़ंक्शन चुनें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="f3a5a-122">एकत्रीकरण फ़ंक्शन में शामिल हैं:</span><span class="sxs-lookup"><span data-stu-id="f3a5a-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="f3a5a-123">**जोड़ें**</span><span class="sxs-lookup"><span data-stu-id="f3a5a-123">**Sum**</span></span>
   - <span data-ttu-id="f3a5a-124">**औसत**</span><span class="sxs-lookup"><span data-stu-id="f3a5a-124">**Average**</span></span>
   - <span data-ttu-id="f3a5a-125">**गणना करें**</span><span class="sxs-lookup"><span data-stu-id="f3a5a-125">**Count**</span></span>
   - <span data-ttu-id="f3a5a-126">**अनन्य की गणना**</span><span class="sxs-lookup"><span data-stu-id="f3a5a-126">**Count Unique**</span></span>
   - <span data-ttu-id="f3a5a-127">**अधिकतम**</span><span class="sxs-lookup"><span data-stu-id="f3a5a-127">**Max**</span></span>
   - <span data-ttu-id="f3a5a-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="f3a5a-128">**Min**</span></span>
   - <span data-ttu-id="f3a5a-129">**पहला**: डेटा रिकॉर्ड का पहला मान लेता है</span><span class="sxs-lookup"><span data-stu-id="f3a5a-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="f3a5a-130">**अंतिम**: डेटा रिकॉर्ड में जोड़ा गया अंतिम मान लेता है</span><span class="sxs-lookup"><span data-stu-id="f3a5a-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="माप की गणना के लिए ऑपरेटर.":::

1. <span data-ttu-id="f3a5a-132">इस उपाय को बनाने के लिए आवश्यक डेटा का चयन करने के लिए **विशेषता जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="f3a5a-133">**विशेषता** टैब चुनें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="f3a5a-134">डेटा निकाय: वह निकाय चुनें जिसमें वह विशेषता शामिल हो जिसे आप मापना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="f3a5a-135">डेटा विशेषता: माप की गणना के लिए एकत्रीकरण फ़ंक्शन में उपयोग की जाने वाली विशेषता चुनें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="f3a5a-136">आप एक समय में केवल एक विशेषता चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="f3a5a-137">आप **उपाय** टैब का चयन करके मौजूदा उपाय से डेटा विशेषता का चयन कर सकते हैं. या, आप एक निकाय की खोज कर सकते हैं या नाम को माप सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="f3a5a-138">उपाय में चयनित विशेषता जोड़ने के लिए **जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="गणना में उपयोग करने के लिए एक विशेषता चुनें":::

1. <span data-ttu-id="f3a5a-140">अधिक जटिल उपायों का निर्माण करने के लिए, आप अधिक विशेषताओं को जोड़ सकते हैं या अपने माप फ़ंक्शन पर गणित ऑपरेटरों का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="गणित ऑपरेटरों के साथ जटिल माप बनाएं":::

1. <span data-ttu-id="f3a5a-142">फ़िल्टर जोड़ने के लिए, कॉन्फ़िगरेशन क्षेत्र में **फ़िल्टर** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="f3a5a-143">**फ़िल्टर** फलक के **विशेषता जोड़ें** अनुभाग में, फ़िल्टर बनाने के लिए आप जिस विशेषता का उपयोग करना चाहते हैं उसका चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="f3a5a-144">प्रत्येक चयनित विशेषता के लिए फ़िल्टर को परिभाषित करने के लिए फ़िल्टर ऑपरेटर सेट करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="f3a5a-145">माप में फ़िल्टर जोड़ने के लिए **लागू करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="f3a5a-146">आयाम जोड़ने के लिए, कॉन्फ़िगरेशन क्षेत्र में **आयाम** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="f3a5a-147">आयाम माप आउटपुट निकाय में कॉलम के रूप में दिखाई देंगे.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="f3a5a-148">उन डेटा विशेषताओं को जोड़ने के लिए **आयामों को संपादित करें** चुनें, जिनके द्वारा आप माप मानों को समूहित करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="f3a5a-149">उदाहरण के लिए, शहर या लिंग।</span><span class="sxs-lookup"><span data-stu-id="f3a5a-149">For example, city or gender.</span></span> <span data-ttu-id="f3a5a-150">डिफ़ॉल्ट रूप से, *ग्राहक-स्तरीय उपाय* बनाने के लिए *CustomerID* आयाम का चयन किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="f3a5a-151">यदि आप *व्यवसाय-स्तरीय उपाय* बनाना चाहते हैं तो आप डिफ़ॉल्ट आयाम को हटा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="f3a5a-152">उपाय में आयाम जोड़ने के लिए **पूर्ण** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="f3a5a-153">यदि आपके द्वारा मैप किए गए डेटा निकाय और *ग्राहक* निकाय के बीच कई पथ हैं, तो आपको पहचान किए गए [निकाय संबंध पथ](relationships.md) में से एक को चुनना होगा.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="f3a5a-154">उपाय परिणाम चयनित पथ के आधार पर भिन्न हो सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="f3a5a-155">**डेटा वरीयताओं** का चयन करें और अपने पथ की पहचान करने के लिए जिस निकाय पथ का उपयोग किया जाना चाहिए उसे चुनें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="f3a5a-156">यदि *ग्राहक* निकाय के लिए केवल एक ही पथ है, तो यह नियंत्रण नहीं दिखेगा.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="f3a5a-157">अपने चयन को लागू करने के लिए **पूर्ण** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="माप के लिए निकाय पथ का चयन करें.":::

1. <span data-ttu-id="f3a5a-159">माप के लिए अधिक गणना जोड़ने के लिए, **नई गणना** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="f3a5a-160">आप नई गणना के लिए केवल समान निकाय पथ पर निकायों का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="f3a5a-161">अधिक गणना माप आउटपुट निकाय में नए कॉलम के रूप में दिखाई देंगी.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="f3a5a-162">एक माप से गणना को **डुप्लिकेट**, **नाम बदलने**, या **निकालने** के लिए गणना पर **...** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="f3a5a-163">**पूर्वावलोकन** क्षेत्र में, आप माप आउटपुट निकाय का डेटा स्कीमा देखेंगे, जिसमें फ़िल्टर और आयाम शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="f3a5a-164">पूर्वावलोकन कॉन्फ़िगरेशन में बदलाव के लिए गतिशील रूप से प्रतिक्रिया करता है.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="f3a5a-165">कॉन्फ़िगर किए गए माप के परिणामों की गणना करने के लिए **रन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="f3a5a-166">यदि आप वर्तमान कॉन्फ़िगरेशन रखना चाहते हैं और बाद में माप को रन करना चाहते हैं तो **सेव करें और बंद करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="f3a5a-167">सूची में नए बनाए गए माप को देखने के लिए **माप** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="f3a5a-168">अपने उपाय प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="f3a5a-168">Manage your measures</span></span>

<span data-ttu-id="f3a5a-169">[एक माप बनाना](#create-a-measure) के बाद, आप **माप** पृष्ठ पर मापों की एक सूची देखते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="f3a5a-170">आप माप प्रकार, निर्माता, निर्माण तिथि, स्थिति और स्थिति के बारे में जानकारी प्राप्त करेंगे.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="f3a5a-171">जब आप सूची से एक माप का चयन करते हैं, तो आप आउटपुट का पूर्वावलोकन कर सकते हैं और .CSV फ़ाइल डाउनलोड कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="f3a5a-172">एक साथ अपने सभी उपायों को रिफ्रेश करने के लिए, कोई विशिष्ट उपाय चुने बिना **सभी रिफ्रेश करें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f3a5a-173">![एकल उपायों को प्रबंधित करने के लिए कार्रवाई](media/measure-actions.png "एकल उपायों का प्रबंधन करने की क्रिया")</span><span class="sxs-lookup"><span data-stu-id="f3a5a-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="f3a5a-174">निम्नलिखित विकल्पों के लिए सूची से माप का चयन करें:</span><span class="sxs-lookup"><span data-stu-id="f3a5a-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="f3a5a-175">उपाय का विवरण देखने के लिए उसका नाम चुनें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="f3a5a-176">उपाय के कॉन्फ़िगरेशन को **संपादित करें**.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="f3a5a-177">**रीफ्रेश** डेटा के आधार पर माप को रीफ्रेश करें.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="f3a5a-178">उपाय का **नाम बदलें**.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-178">**Rename** the measure.</span></span>
- <span data-ttu-id="f3a5a-179">उपाय **हटाएं**.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-179">**Delete** the measure.</span></span>
- <span data-ttu-id="f3a5a-180">**सक्रिय करें** या **निष्क्रिय करें**.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="f3a5a-181">निष्क्रिय माप [निर्धारित रीफ्रेश](system.md#schedule-tab) के दौरान रीफ्रेश नहीं होंगे.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="f3a5a-182">कार्यों/प्रक्रियाओं के लिए [छह प्रकार की स्थिति](system.md#status-types) हैं .</span><span class="sxs-lookup"><span data-stu-id="f3a5a-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f3a5a-183">इसके अतिरिक्त, अधिकांश प्रक्रियाएं [अन्य डाउनस्ट्रीम प्रक्रियाओं पर निर्भर करती हैं](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f3a5a-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f3a5a-184">आप पूरे कार्य की प्रगति पर विवरण देखने के लिए प्रक्रिया की स्थिति का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f3a5a-185">किसी एक जॉब कार्य के लिए **विवरण देखें** को चुनने के बाद, आपको अतिरिक्त जानकारी मिलती है: संसाधन समय, अंतिम संसाधन दिनांक और कार्य से जुड़ी सभी त्रुटियां और चेतावनियाँ.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="f3a5a-186">अगला चरण</span><span class="sxs-lookup"><span data-stu-id="f3a5a-186">Next step</span></span>

<span data-ttu-id="f3a5a-187">आप [ग्राहक सेगमेंट](segments.md) बनाने के लिए मौजूदा मापों का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f3a5a-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]