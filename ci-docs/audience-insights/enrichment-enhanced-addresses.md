---
title: पता वृद्धि संवर्धन
description: Microsoft के मॉडल के साथ ग्राहक प्रोफ़ाइल की पता जानकारी को समृद्ध और सामान्य करें.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305434"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="a203f-103">उन्नत पतों के साथ ग्राहक प्रोफाइल का संवर्धन</span><span class="sxs-lookup"><span data-stu-id="a203f-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="a203f-104">आपके डेटा में पते असंरचित, अपूर्ण या गलत हो सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a203f-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="a203f-105">बेहतर सटीकता और इनसाइट के लिए अपने पते को [सामान्य डेटा मॉडल प्रारूप](/common-data-model/schema/core/applicationcommon/address) में सामान्य और समृद्ध करने के लिए Microsoft के मॉडल का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="a203f-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="a203f-106">हम पतों को कैसे संवर्धित करते हैं</span><span class="sxs-lookup"><span data-stu-id="a203f-106">How we enhance addresses</span></span>

<span data-ttu-id="a203f-107">हमारा मॉडल एक पते के संवर्धन के लिए दो-चरणीय प्रक्रिया से गुजरता है.</span><span class="sxs-lookup"><span data-stu-id="a203f-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="a203f-108">सर्वप्रथम, यह अपने घटकों की पहचान करने के लिए पते को पार्स करता है और उन्हें एक संरचित प्रारूप में रखता है.</span><span class="sxs-lookup"><span data-stu-id="a203f-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="a203f-109">फिर, हम पते में मानों को सही, पूर्ण और मानकीकृत करने के लिए AI का उपयोग करते हैं.</span><span class="sxs-lookup"><span data-stu-id="a203f-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="a203f-110">उदाहरण</span><span class="sxs-lookup"><span data-stu-id="a203f-110">Example</span></span>

<span data-ttu-id="a203f-111">पता जानकारी गैर-मानक प्रारूप में हो सकती है और इसमें वर्तनी की त्रुटियां शामिल हो सकती हैं।</span><span class="sxs-lookup"><span data-stu-id="a203f-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="a203f-112">मॉडल इन समस्याओं को ठीक कर सकता है और एकीकृत ग्राहक प्रोफाइल में सुसंगत पते बना सकता है.</span><span class="sxs-lookup"><span data-stu-id="a203f-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="a203f-113">सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="a203f-113">Limitations</span></span>

<span data-ttu-id="a203f-114">उन्नत पते केवल उन मानों के साथ काम करते हैं जो आपके अंतर्ग्रहीत पता डेटा में पहले से मौजूद हैं.</span><span class="sxs-lookup"><span data-stu-id="a203f-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="a203f-115">मॉडल नहीं करता है:</span><span class="sxs-lookup"><span data-stu-id="a203f-115">The model doesn't:</span></span> 

1. <span data-ttu-id="a203f-116">मान्य पते का सत्यापन.</span><span class="sxs-lookup"><span data-stu-id="a203f-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="a203f-117">ज़िप कोड या सड़क के नाम जैसे मान मान्य हैं यह सत्यापित करें.</span><span class="sxs-lookup"><span data-stu-id="a203f-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="a203f-118">उन मानों को बदलें जिन्हें वह नहीं पहचानता.</span><span class="sxs-lookup"><span data-stu-id="a203f-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="a203f-119">मॉडल पतों के संवर्धन के लिए मशीन लर्निंग-आधारित तकनीकों का उपयोग करता है.</span><span class="sxs-lookup"><span data-stu-id="a203f-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="a203f-120">किसी भी मशीन लर्निंग-आधारित मॉडल के साथ जब मॉडल इनपुट मान बदलता है, तो उसके लिए हम एक उच्च विश्वास सीमा लागू करते हैं, 100 प्रतिशत सटीकता की गारंटी नहीं होती है.</span><span class="sxs-lookup"><span data-stu-id="a203f-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="a203f-121">समर्थित देश या क्षेत्र</span><span class="sxs-lookup"><span data-stu-id="a203f-121">Supported countries or regions</span></span>

<span data-ttu-id="a203f-122">वर्तमान में हम इन देशों या क्षेत्रों में समृद्ध पतों का समर्थन करते हैं:</span><span class="sxs-lookup"><span data-stu-id="a203f-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="a203f-123">ऑस्ट्रेलिया</span><span class="sxs-lookup"><span data-stu-id="a203f-123">Australia</span></span>
- <span data-ttu-id="a203f-124">कनाडा</span><span class="sxs-lookup"><span data-stu-id="a203f-124">Canada</span></span>
- <span data-ttu-id="a203f-125">युनाइटेड किंगडम</span><span class="sxs-lookup"><span data-stu-id="a203f-125">United Kingdom</span></span>
- <span data-ttu-id="a203f-126">संयुक्त राज्य</span><span class="sxs-lookup"><span data-stu-id="a203f-126">United States</span></span>

<span data-ttu-id="a203f-127">पतों में एक देश/क्षेत्र मान होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="a203f-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="a203f-128">हम उन देशों या क्षेत्रों के पतों को प्रोसेस नहीं करते हैं जो समर्थित नहीं हैं और जिन पते पर कोई देश या क्षेत्र प्रदान नहीं किया गया है.</span><span class="sxs-lookup"><span data-stu-id="a203f-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="a203f-129">एनरिचमेंट को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="a203f-129">Configure the enrichment</span></span>

1. <span data-ttu-id="a203f-130">**डेटा** > **संवर्धन** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="a203f-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="a203f-131">**उन्नत पते** टाइल पर **मेरा डेटा समृद्ध करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="a203f-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="उन्नत पता टाइल का स्क्रीनशॉट.":::

1. <span data-ttu-id="a203f-133">**ग्राहक डेटा सेट** का चयन करें और वह निकाय चुनें जिसमें वे पते हों जिन्हें आप समृद्ध करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="a203f-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="a203f-134">आप अपने सभी ग्राहक प्रोफाइल में पतों को समृद्ध करने के लिए *ग्राहक* निकाय का चयन कर सकते हैं या केवल उस अनुभाग में निहित ग्राहक प्रोफाइल में पतों को समृद्ध करने के लिए एक अनुभाग निकाय को चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a203f-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="a203f-135">आपके डेटा सेट में पतों को कैसे स्वरूपित किया जाता है, उसे चुनें.</span><span class="sxs-lookup"><span data-stu-id="a203f-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="a203f-136">यदि आपके डेटा के पते एकल फ़ील्ड का उपयोग करते हैं, तो **एकल-विशेषता पता** चुनें.</span><span class="sxs-lookup"><span data-stu-id="a203f-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="a203f-137">यदि आपके डेटा में पते एक से अधिक डेटा फ़ील्ड का उपयोग करते हैं, तो **एकाधिक-विशेषता पता** चुनें.</span><span class="sxs-lookup"><span data-stu-id="a203f-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a203f-138">देश/क्षेत्र एकल-एट्रिब्यूट और एकाधिक-एट्रिब्यूट दोनों पतों में अनिवार्य है।</span><span class="sxs-lookup"><span data-stu-id="a203f-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="a203f-139">जिन पतों में मान्य या समर्थित देश/क्षेत्र मान शामिल नहीं हैं, उन्हें संवर्धित नहीं किया जाएगा।</span><span class="sxs-lookup"><span data-stu-id="a203f-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="a203f-140">अपने एकीकृत ग्राहक निकाय से पता फ़ील्ड को मैप करें.</span><span class="sxs-lookup"><span data-stu-id="a203f-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="उन्नत पता फ़ील्ड-मानचित्रण पृष्ठ.":::

1. <span data-ttu-id="a203f-142">फील्ड मैपिंग को पूरा करने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="a203f-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="a203f-143">उन्नत और आउटपुट निकाय के लिए एक नाम प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="a203f-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="a203f-144">अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="a203f-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a203f-145">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="a203f-145">Enrichment results</span></span>

<span data-ttu-id="a203f-146">संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="a203f-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a203f-147">आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a203f-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a203f-148">प्रोसेसिंग समय आपके ग्राहक डेटा के आकार पर निर्भर करता है.</span><span class="sxs-lookup"><span data-stu-id="a203f-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="a203f-149">संवर्धन प्रक्रिया पूरी होने के बाद, आप **मेरे संवर्धन** के तहत नए समृद्ध ग्राहक प्रोफ़ाइल डेटा की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a203f-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a203f-150">इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="a203f-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a203f-151">आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a203f-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a203f-152">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="a203f-152">Next steps</span></span>

<span data-ttu-id="a203f-153">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="a203f-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a203f-154">[खंडों](segments.md) को बनाएं और [साधानों](measures.md) और यहां तक कि अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a203f-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
