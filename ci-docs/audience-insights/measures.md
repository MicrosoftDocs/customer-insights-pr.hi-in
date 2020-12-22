---
title: साधन बनाएं और संपादित करें
description: कुछ व्यावसायिक क्षेत्रों के प्रदर्शन का विश्लेषण और प्रतिबिंबित करने के लिए ग्राहक से संबंधित उपायों को निर्दिष्ट करें.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405964"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="d4eee-103">उपाय निर्धारित और प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="d4eee-103">Define and manage measures</span></span>

<span data-ttu-id="d4eee-104">**उपाय** मुख्य प्रदर्शन संकेतक (KPI) का प्रतिनिधित्व करते हैं जो विशिष्ट व्यावसायिक क्षेत्रों के प्रदर्शन और स्थिति को दर्शाते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="d4eee-105">ऑडियंस इनसाइट्स विभिन्न प्रकार के साधनों के निर्माण के लिए एक सहज अनुभव प्रदान करता है, एक क्वेरी बिल्डर का उपयोग करके, जिसके लिए आपको अपने साधनों को मैन्युअल रूप से कोड या मान्य करने की आवश्यकता नहीं होती है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="d4eee-106">आप अपने व्यवसाय के उपायों को **होम** पेज पर जांच कर सकते हैं, **कस्टमर कार्ड** पर विशिष्ट ग्राहकों के लिए उपाय देख सकते हैं, और **सेगमेंट** पेज पर ग्राहक सेगमेंट को निर्दिष्ट करने के उपायों का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="d4eee-107">एक उपाय बनाएँ</span><span class="sxs-lookup"><span data-stu-id="d4eee-107">Create a measure</span></span>

<span data-ttu-id="d4eee-108">यह खंड आपको शून्य से एक उपाय बनाने के साथ चलाता है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="d4eee-109">आप ग्राहक निकाय के माध्यम से जुड़े हुए कई डेटा स्रोतों के डेटा के साथ उपाय बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="d4eee-110">कुछ [सेवा सीमा](service-limits.md) लागू होते हैं .</span><span class="sxs-lookup"><span data-stu-id="d4eee-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="d4eee-111">ऑडिएंस इनसाइट्स में, **माप** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="d4eee-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="d4eee-112">**नए माप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-112">Select **New measure**.</span></span>

3. <span data-ttu-id="d4eee-113">उपाय **प्रकार** चुनें:</span><span class="sxs-lookup"><span data-stu-id="d4eee-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="d4eee-114">**ग्राहक विशेषता**: प्रति ग्राहक एक क्षेत्र जो ग्राहक के लिए स्कोर, मूल्य या स्थिति को दर्शाता है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="d4eee-115">ग्राहक विशेषताओं को **ग्राहक_उपाय** नामक एक नए प्रणाली-जनित निकाय में विशेषता के रूप में बनाया गया है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="d4eee-116">**ग्राहक उपाय**: चयनित आयामों के विश्लेषण के साथ ग्राहक व्यवहार पर इनसाइट.</span><span class="sxs-lookup"><span data-stu-id="d4eee-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="d4eee-117">प्रत्येक उपाय के लिए एक नया निकाय संभावित रूप से प्रति ग्राहक कई रिकॉर्ड के साथ उत्पन्न किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="d4eee-118">**व्यापार उपाय**: आपके व्यवसाय के प्रदर्शन और व्यवसाय के स्वास्थ्य की जांच करता है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="d4eee-119">व्यावसायिक उपायों में दो अलग-अलग आउटपुट हो सकते हैं: एक संख्यात्मक आउटपुट जो **होम** पेज पर दिखाता है या एक नया निकाय जो आपको **निकाय** पेज पर मिलता है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="d4eee-120">एक **नाम** और एक वैकल्पिक **प्रदर्शन नाम** प्रदान करें, फिर **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="d4eee-121">**निकाय** अनुभाग में, ड्रॉप-डाउन सूची से पहला निकाय चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="d4eee-122">इस बिंदु पर आपको यह तय करना चाहिए कि आपके उपाय परिभाषा के हिस्से के रूप में अतिरिक्त निकायों की आवश्यकता है या नहीं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4eee-123">![माप की परिभाषा](media/measure-definition.png "माप की परिभाषा")</span><span class="sxs-lookup"><span data-stu-id="d4eee-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="d4eee-124">अधिक निकाय जोड़ने के लिए, **निकाय जोड़ें** चुनें और उन निकायों का चयन करें जिन्हें आप उपाय के लिए उपयोग करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d4eee-125">आप केवल उन्हीं निकायों का चयन कर सकते हैं, जिनका आपके प्रारंभिक निकाय से संबंध है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="d4eee-126">रिश्तों को निर्दिष्ट करने के बारे में अधिक जानकारी के लिए, देखें [रिश्ते](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d4eee-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="d4eee-127">वैकल्पिक रूप से, आप वैरिएबल्स को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="d4eee-128">**वैरिएबल्स** अनुभाग में, **नया वैरिएबल** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="d4eee-129">वैरिएबल्स वे गणनाएं हैं जो आपके प्रत्येक चयनित रिकॉर्ड पर की जाती हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="d4eee-130">उदाहरण के लिए, अपने प्रत्येक ग्राहक के रिकॉर्ड के लिए पॉइंट-ऑफ-सेल (POS) और ऑनलाइन बिक्री को जोड़ना.</span><span class="sxs-lookup"><span data-stu-id="d4eee-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="d4eee-131">वैरिएबल के लिए **नाम** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="d4eee-132">**अभिव्यक्ति** क्षेत्र में, अपनी गणना शुरू करने के लिए एक क्षेत्र चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="d4eee-133">अपनी गणना में शामिल करने के लिए अधिक फ़ील्ड चुनते समय **अभिव्यक्ति** क्षेत्र में एक अभिव्यक्ति टाइप करें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d4eee-134">वर्तमान में, केवल अंकगणितीय भावों का समर्थन किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="d4eee-135">इसके अतिरिक्त, विभिन्न [निकाय पथ](relationships.md) से संस्थाओं के लिए वैरिएबल्स गणना समर्थित नहीं है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="d4eee-136">**पूर्ण** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-136">Select **Done**.</span></span>

11. <span data-ttu-id="d4eee-137">**उपाय परिभाषा** अनुभाग में, आप स्पष्ट करेंगे कि कैसे आपके चुने हुए निकाय और गणना किए गए वैरिएबल्स एक नए उपाय निकाय या विशेषता में एकत्रित होते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="d4eee-138">**नया आयाम** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-138">Select **New dimension**.</span></span> <span data-ttu-id="d4eee-139">आप एक कार्य को *समूह द्वारा* कार्य के रूप में सोच सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="d4eee-140">आपका उपाय निकाय या विशेषता का डेटा आउटपुट आपके सभी निर्धारित आयामों द्वारा समूहीकृत किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="d4eee-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d4eee-141">![सामूहिक चक्र चुनें](media/measures-businessreport-measure-definition2.png "सामूहिक चक्र चुनें")</span><span class="sxs-lookup"><span data-stu-id="d4eee-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="d4eee-142">निम्न जानकारी को अपने आयाम की परिभाषा के भाग के रूप में चुनें या दर्ज करें:</span><span class="sxs-lookup"><span data-stu-id="d4eee-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="d4eee-143">**निकाय**: यदि आप उपाय निकाय को निर्दिष्ट करते हैं, तो इसमें कम से कम एक विशेषता शामिल होनी चाहिए.</span><span class="sxs-lookup"><span data-stu-id="d4eee-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="d4eee-144">यदि आप एक उपाय विशेषता निर्दिष्ट करते हैं, तो इसमें डिफ़ॉल्ट रूप से केवल एक विशेषता शामिल होगी.</span><span class="sxs-lookup"><span data-stu-id="d4eee-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="d4eee-145">यह चयन उस निकाय को चुनने के बारे में है जिसमें वह विशेषता शामिल है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="d4eee-146">**फ़ील्ड**: अपने उपाय निकाय या विशेषता में शामिल होने के लिए खास विशेषता चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="d4eee-147">**बके**: चुनें कि क्या आप दैनिक, मासिक या वार्षिक आधार पर डेटा एकत्र करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="d4eee-148">यह एक आवश्यक चयन है केवल यदि आपने दिनांक प्रकार एट्रिब्यूट चुना है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="d4eee-149">**के रूप में**: अपने नए क्षेत्र का नाम निर्दिष्ट करता है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="d4eee-150">**प्रदर्शन नाम**: आपके क्षेत्र के प्रदर्शन नाम को निर्दिष्ट करता है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4eee-151">जब तक आप अपने उपाय में अधिक आयाम नहीं जोड़ते हैं, तब तक आपका व्यवसाय उपाय एकल नंबर निकाय के रूप में सहेजा जाएगा और **होम** पेज पर दिखाई देगा.</span><span class="sxs-lookup"><span data-stu-id="d4eee-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="d4eee-152">अधिक आयाम जोड़ने के बाद, उपाय **होम** पेज पर *नहीं* दिखाई देगा.</span><span class="sxs-lookup"><span data-stu-id="d4eee-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="d4eee-153">वैकल्पिक रूप से, एकत्रीकरण कार्य जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="d4eee-154">कोई भी एकत्रीकरण जो आप बनाते हैं, उनसे आपके उपाय निकाय या विशेषता के भीतर एक नया मूल्य प्राप्त होता है.</span><span class="sxs-lookup"><span data-stu-id="d4eee-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="d4eee-155">समर्थित एकत्रीकरण कार्य हैं: **न्यूनतम**, **अधिकतम**, **औसत**, **मेडियन**, **सम**, **विशेष गिनती**, **पहला** (आयाम मान का पहला रिकॉर्ड लेता है) और **अंतिम** (आयाम मान में जोड़ा गया अंतिम रिकॉर्ड लेता है).</span><span class="sxs-lookup"><span data-stu-id="d4eee-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="d4eee-156">उपाय में अपने परिवर्तन लागू करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="d4eee-157">अपने उपाय प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="d4eee-157">Manage your measures</span></span>

<span data-ttu-id="d4eee-158">कम से कम एक साधन बनाने के बाद, आपको **साधन** पृष्ठ पर साधनों की एक सूची दिखाई देगा.</span><span class="sxs-lookup"><span data-stu-id="d4eee-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="d4eee-159">आपको उपाय प्रकार, निर्माता, निर्माण तिथि और समय, अंतिम संपादन तिथि और समय, स्थिति (क्या उपाय सक्रिय, निष्क्रिय या विफल है), और अंतिम ताज़ा दिनांक और समय के बारे में जानकारी मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="d4eee-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="d4eee-160">जब आप सूची से एक उपाय चुनते हैं, तो आप इसके आउटपुट का पूर्वावलोकन देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="d4eee-161">एक साथ अपने सभी उपायों को रिफ्रेश करने के लिए, कोई विशिष्ट उपाय चुने बिना **सभी रिफ्रेश करें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4eee-162">![एकल उपायों को प्रबंधित करने के लिए कार्रवाई](media/measure-actions.png "एकल उपायों का प्रबंधन करने की क्रिया")</span><span class="sxs-lookup"><span data-stu-id="d4eee-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="d4eee-163">वैकल्पिक रूप से, सूची में से कोई एक उपाय चुनें और निम्नलिखित कार्रवाइयों में से एक करें:</span><span class="sxs-lookup"><span data-stu-id="d4eee-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="d4eee-164">उपाय का विवरण देखने के लिए उसका नाम चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="d4eee-165">उपाय के कॉन्फ़िगरेशन को **संपादित करें**.</span><span class="sxs-lookup"><span data-stu-id="d4eee-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="d4eee-166">उपाय का **नाम बदलें**.</span><span class="sxs-lookup"><span data-stu-id="d4eee-166">**Rename** the measure.</span></span>
- <span data-ttu-id="d4eee-167">उपाय **हटाएं**.</span><span class="sxs-lookup"><span data-stu-id="d4eee-167">**Delete** the measure.</span></span>
- <span data-ttu-id="d4eee-168">उपाय की रिफ्रेश प्रक्रिया शुरू करने के लिए दीर्घवृत्त (...) को चुनें और उसके बाद **रिफ्रेश करें**.</span><span class="sxs-lookup"><span data-stu-id="d4eee-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="d4eee-169">एलिप्सिस (...) को चुनें और उसके बाद उपाय की .CSV फ़ाइल प्राप्त करने के लिए **डाउनलोड करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="d4eee-170">कार्यों/प्रक्रियाओं के लिए [छह प्रकार की स्थिति](system.md#status-types) हैं .</span><span class="sxs-lookup"><span data-stu-id="d4eee-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d4eee-171">इसके अतिरिक्त, अधिकांश प्रक्रियाएं [अन्य डाउनस्ट्रीम प्रक्रियाओं पर निर्भर करती हैं](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d4eee-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d4eee-172">आप पूरे कार्य की प्रगति पर विवरण देखने के लिए प्रक्रिया की स्थिति का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d4eee-173">किसी एक जॉब कार्य के लिए **विवरण देखें** को चुनने के बाद, आपको अतिरिक्त जानकारी मिलती है: संसाधन समय, अंतिम संसाधन दिनांक और कार्य से जुड़ी सभी त्रुटियां और चेतावनियाँ.</span><span class="sxs-lookup"><span data-stu-id="d4eee-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d4eee-174">अगला चरण</span><span class="sxs-lookup"><span data-stu-id="d4eee-174">Next step</span></span>

<span data-ttu-id="d4eee-175">आप **सेगमेंट** पृष्ठ पर अपना पहला ग्राहक खंड बनाने के लिए मौजूदा उपायों का उपयोग करते हैं.</span><span class="sxs-lookup"><span data-stu-id="d4eee-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="d4eee-176">अधिक जानकारी के लिए, [खंड](segments.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="d4eee-176">For more information, see [Segments](segments.md).</span></span>
