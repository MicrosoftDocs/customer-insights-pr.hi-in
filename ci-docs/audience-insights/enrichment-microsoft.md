---
title: Microsoft से डेटा के साथ ग्राहक प्रोफाइल को बेहतर करें
description: ब्रांड और दिलचस्पी के लिए झुकाव के साथ अपने ग्राहक डेटा को समृद्ध करने के लिए Microsoft से मालिकाना डेटा का उपयोग करें.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305158"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="d634c-103">ग्राहक प्रोफाइल को ब्रांड और रुचि आत्मीयताओं से समृद्ध करें (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="d634c-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="d634c-104">ब्रांड और दिलचस्पी के लिए झुकाव के साथ अपने ग्राहक डेटा को समृद्ध करने के लिए Microsoft के मालिकाना डेटा का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="d634c-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="d634c-105">ये समानताएँ आपके ग्राहकों की एक समान जनसांख्यिकीय के साथ लोगों के डेटा पर आधारित होते हैं।</span><span class="sxs-lookup"><span data-stu-id="d634c-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="d634c-106">यह जानकारी आपको विशिष्ट ब्रांडों और रुचियों के प्रति आपके ग्राहकों की एफ़िनिटी के आधार पर उनको बेहतर ढंग से समझने और सेगमेंट करने में मदद करती है.</span><span class="sxs-lookup"><span data-stu-id="d634c-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="d634c-107">ऑडिएंस इनसाइट्स में, [संवर्धन कॉन्फ़िगर करें और देखें](enrichment-hub.md) के लिए **डेटा** > **संवर्धन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="d634c-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="d634c-108">ब्रांड संबंध समृद्धि को कॉन्फ़िगर करने के लिए **खोजें** टैब पर जाएं और **ब्रांड** टाइल पर **मेरा डेटा समृद्ध करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d634c-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="d634c-109">रुचि संबंध समृद्धि को कॉन्फ़िगर करने के लिए **खोजें** टैब पर जाएं और **रुचियां** टाइल पर **मेरा डेटा समृद्ध करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d634c-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d634c-110">![ब्रांड और रुचि टाइलें](media/BrandsInterest-tile-Hub.png "ब्रांड और रुचि टाइलें")</span><span class="sxs-lookup"><span data-stu-id="d634c-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="d634c-111">हम झुकाव कैसे निर्धारित करते हैं</span><span class="sxs-lookup"><span data-stu-id="d634c-111">How we determine affinities</span></span>

<span data-ttu-id="d634c-112">हम विभिन्न जनसांख्यिकीय सेगमेंटों (उम्र, लिंग या स्थान के अनुसार परिभाषित) में ब्रांडों और हितों के लिए समानताएं खोजने के लिए Microsoft के ऑनलाइन खोज डेटा का उपयोग करते हैं.</span><span class="sxs-lookup"><span data-stu-id="d634c-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="d634c-113">किसी ब्रांड या रुचि के लिए ऑनलाइन खोज मात्रा यह निर्धारित करती है कि उस ब्रांड या रुचि से, अन्य अनुभागों की तुलना में, किसी जनसांख्यिकीय अनुभाग में कितनी रुचि है.</span><span class="sxs-lookup"><span data-stu-id="d634c-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="d634c-114">एफ़िनिटी का स्तर और स्कोर</span><span class="sxs-lookup"><span data-stu-id="d634c-114">Affinity level and score</span></span>

<span data-ttu-id="d634c-115">हर एक समृद्ध ग्राहक प्रोफ़ाइल पर, हम दो संबंधित मान प्रदान करते हैं: समानता स्तर और समानता स्कोर।</span><span class="sxs-lookup"><span data-stu-id="d634c-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="d634c-116">ये मान आपको यह निर्धारित करने में मदद करते हैं कि किसी ब्रांड या दिलचस्पी के लिए, अन्य जनसांख्यिकीय अनुभाग की तुलना में उस प्रोफ़ाइल के जनसांख्यिकीय अनुभाग के लिए एफ़िनिटी कितनी मजबूत है.</span><span class="sxs-lookup"><span data-stu-id="d634c-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="d634c-117">*एफ़िनिटी स्तर* में चार स्तर होते हैं और *एफ़िनिटी स्कोर* की गणना 100 अंकों के पैमाने पर की जाती है, जो एफ़िनिटी के स्तरों पर मैप करता है.</span><span class="sxs-lookup"><span data-stu-id="d634c-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="d634c-118">एफ़िनिटी स्तर</span><span class="sxs-lookup"><span data-stu-id="d634c-118">Affinity level</span></span> |<span data-ttu-id="d634c-119">एफ़िनिटी स्कोर</span><span class="sxs-lookup"><span data-stu-id="d634c-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="d634c-120">बहुत उच्च</span><span class="sxs-lookup"><span data-stu-id="d634c-120">Very high</span></span>     | <span data-ttu-id="d634c-121">85-100</span><span class="sxs-lookup"><span data-stu-id="d634c-121">85-100</span></span>       |
|<span data-ttu-id="d634c-122">उच्च</span><span class="sxs-lookup"><span data-stu-id="d634c-122">High</span></span>     | <span data-ttu-id="d634c-123">70-84</span><span class="sxs-lookup"><span data-stu-id="d634c-123">70-84</span></span>        |
|<span data-ttu-id="d634c-124">मध्यम</span><span class="sxs-lookup"><span data-stu-id="d634c-124">Medium</span></span>     | <span data-ttu-id="d634c-125">35-69</span><span class="sxs-lookup"><span data-stu-id="d634c-125">35-69</span></span>        |
|<span data-ttu-id="d634c-126">कम</span><span class="sxs-lookup"><span data-stu-id="d634c-126">Low</span></span>     | <span data-ttu-id="d634c-127">1-34</span><span class="sxs-lookup"><span data-stu-id="d634c-127">1-34</span></span>        |

<span data-ttu-id="d634c-128">एफ़िनिटी को मापने के लिए आप जो ग्रैन्युलैरिटी चाहते हैं, उसके आधार पर आप एफ़िनिटी स्तर या स्कोर का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d634c-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="d634c-129">एफ़िनिटी स्कोर आपको ज़्यादा सटीक नियंत्रण देता है.</span><span class="sxs-lookup"><span data-stu-id="d634c-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="d634c-130">समर्थित देश/क्षेत्र</span><span class="sxs-lookup"><span data-stu-id="d634c-130">Supported countries/regions</span></span>

<span data-ttu-id="d634c-131">वर्तमान में हम निम्नलिखित देशों/क्षेत्रों में समर्थन करते हैं: ऑस्ट्रेलिया, कनाडा (अंग्रेजी), फ्रांस, जर्मनी, यूनाइटेड किंगडम, या संयुक्त राज्य अमेरिका (अंग्रेजी).</span><span class="sxs-lookup"><span data-stu-id="d634c-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="d634c-132">किसी देश या क्षेत्र का चयन करने के लिए, **ब्रांड संवर्धन** या **रूचि संवर्धन** खोलें और **देश/क्षेत्र** के बगल में **बदलें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d634c-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="d634c-133">**देश/क्षेत्र सेटिंग** फलक में, विकल्प चुनें और **लागू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d634c-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="d634c-134">देश चयन से संबंधित निहितार्थ</span><span class="sxs-lookup"><span data-stu-id="d634c-134">Implications related to country selection</span></span>

- <span data-ttu-id="d634c-135">जब [अपना खुद का ब्रांड चुनना हो](#define-your-brands-or-interests), तो सिस्टम चयनित देश या क्षेत्र के आधार पर सुझाव प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="d634c-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="d634c-136">जब [किसी उद्योग का चयन करना हो](#define-your-brands-or-interests), तो आपको चयनित देश या क्षेत्र के आधार पर सबसे ज़्यादा प्रासंगिक ब्रांड या दिलचस्पियां मिलेंगी.</span><span class="sxs-lookup"><span data-stu-id="d634c-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="d634c-137">[प्रोफाइल को समृद्ध करते](#refresh-enrichment) समय, हम उन सभी ग्राहक प्रोफ़ाइलों को समृद्ध करेंगे जिनके लिए हमें चयनित ब्रांड और रुचियों के लिए डेटा प्राप्त होता है, जिसमें वे प्रोफ़ाइल भी शामिल हैं जो चयनित देश या क्षेत्र में नहीं हैं।</span><span class="sxs-lookup"><span data-stu-id="d634c-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="d634c-138">उदाहरण के लिए, अगर आपने जर्मनी का चयन किया है, तो हम संयुक्त राज्य अमेरिका में स्थित प्रोफ़ाइल को समृद्ध करेंगे, अगर हमारे पास अमेरिका में चयनित ब्रांडों और दिलचस्पी के लिए डेटा उपलब्ध है.</span><span class="sxs-lookup"><span data-stu-id="d634c-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="d634c-139">संवर्धन कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="d634c-139">Configure enrichment</span></span>

<span data-ttu-id="d634c-140">एक निर्देशित अनुभव आपको संवर्धन के कॉन्फ़िगरेशन के माध्यम से मदद करता है.</span><span class="sxs-lookup"><span data-stu-id="d634c-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="d634c-141">अपने ब्रांड या रुचियों को परिभाषित करें</span><span class="sxs-lookup"><span data-stu-id="d634c-141">Define your brands or interests</span></span>

<span data-ttu-id="d634c-142">इनमें से एक या दोनों विकल्पों का उपयोग करके अधिकतम पांच ब्रांड या दिलचस्पियां चुनें:</span><span class="sxs-lookup"><span data-stu-id="d634c-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="d634c-143">**उद्योग**: ड्रॉपडाउन सूची से अपने उद्योग का चयन करें और फिर उस उद्योग के लिए शीर्ष ब्रांडों या रुचियों में से चुनें।</span><span class="sxs-lookup"><span data-stu-id="d634c-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="d634c-144">**स्वयं का चुनें**: कोई ऐसा ब्रांड या रुचि दर्ज करें जो आपके संगठन के लिए प्रासंगिक हो और फिर मिलना करने वाले सुझावों में से चुनें.</span><span class="sxs-lookup"><span data-stu-id="d634c-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="d634c-145">यदि आपके द्वारा खोजे जा रहे ब्रांड या रुचि हमारे द्वारा सूचीबद्ध नहीं हैं, तो **सुझाव दें** लिंक का उपयोग करके हमें प्रतिक्रिया भेजें.</span><span class="sxs-lookup"><span data-stu-id="d634c-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="d634c-146">संवर्धन प्राथमिकताओं की समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="d634c-146">Review enrichment preferences</span></span>

<span data-ttu-id="d634c-147">अपनी डिफ़ॉल्ट संवर्धन प्राथमिकताओं की समीक्षा करें और उन्हें आवश्यकतानुसार अपडेट करें.</span><span class="sxs-lookup"><span data-stu-id="d634c-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="संवर्धन प्राथमिकता विंडो का स्क्रीनशॉट.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="d634c-149">बेहतर बनाने के लिए निकाय का चयन करें</span><span class="sxs-lookup"><span data-stu-id="d634c-149">Select entity to enrich</span></span>

<span data-ttu-id="d634c-150">**समृद्ध निकाय** चुनें और उस डेटा सेट को चुनें जिसे आप Microsoft के कंपनी डेटा के साथ समृद्ध करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="d634c-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="d634c-151">आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए ग्राहक निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d634c-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="d634c-152">अपने फ़ील्ड का मानचित्र बनाएं</span><span class="sxs-lookup"><span data-stu-id="d634c-152">Map your fields</span></span>

<span data-ttu-id="d634c-153">अपने एकीकृत ग्राहक निकाय से फ़ील्ड को मैप करें, ताकि उस जनसांख्यिकीय अनुभाग को परिभाषित किया जा सके जिसे आप चाहते हैं कि सिस्टम आपके ग्राहक डेटा को बेहतर करने के लिए उपयोग करे.</span><span class="sxs-lookup"><span data-stu-id="d634c-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="d634c-154">देश/क्षेत्र और कम से कम जन्मतिथि या लिंग एट्रिब्यूट मैप करें.</span><span class="sxs-lookup"><span data-stu-id="d634c-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="d634c-155">इसके अलावा, आपको कम से कम एक शहर (और राज्य/प्रांत) या पोस्टल कोड को मैप करना होगा.</span><span class="sxs-lookup"><span data-stu-id="d634c-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="d634c-156">फ़ील्ड की मैपिंग को परिभाषित करने के लिए **संपादित करें** चुनें और जब आप पूरा कर चुकें तब **लागू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d634c-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="d634c-157">फ़ील्ड मैपिंग को पूरा करने के लिए **सहेजें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="d634c-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="d634c-158">निम्नलिखित प्रारूप और मान समर्थित हैं, (मान केस-सेंसिटिव नहीं हैं):</span><span class="sxs-lookup"><span data-stu-id="d634c-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="d634c-159">**जन्म तिथि**: हम अनुशंसा करते हैं कि जन्म की तारीख डेटा अंतर्ग्रहण के दौरान DateTime प्रकार में बदल जाती है.</span><span class="sxs-lookup"><span data-stu-id="d634c-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="d634c-160">वैकल्पिक रूप से, [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" या "yyyy-MM-ddTHH:mm:ss" प्रारूप में यह एक स्ट्रिंग हो सकता है।</span><span class="sxs-lookup"><span data-stu-id="d634c-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="d634c-161">**लिंग**: पुरुष, महिला, अज्ञात।</span><span class="sxs-lookup"><span data-stu-id="d634c-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="d634c-162">**डाक कोड** : संयुक्त राज्य के लिए पांच अंकों का ज़िप कोड, इसके अलावा हर जगह मानक डाक कोड।</span><span class="sxs-lookup"><span data-stu-id="d634c-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="d634c-163">**शहर**: शहर का नाम अंग्रेजी में।</span><span class="sxs-lookup"><span data-stu-id="d634c-163">**City**: City name in English.</span></span>
- <span data-ttu-id="d634c-164">**राज्य/प्रांत**: अमेरिका और कनाडा के लिए दो-अक्षर का संक्षिप्त नाम.</span><span class="sxs-lookup"><span data-stu-id="d634c-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="d634c-165">ऑस्ट्रेलिया के लिए दो- या तीन- अक्षरीय संक्षिप्त नाम।</span><span class="sxs-lookup"><span data-stu-id="d634c-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="d634c-166">फ्रांस, जर्मनी या यूके के लिए लागू नहीं है.</span><span class="sxs-lookup"><span data-stu-id="d634c-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="d634c-167">**देश/क्षेत्र**:</span><span class="sxs-lookup"><span data-stu-id="d634c-167">**Country/Region**:</span></span>

  - <span data-ttu-id="d634c-168">US: यूनाइटेड स्टेट्स ऑफ अमेरिका, यूनाइटेड स्टेट्स, USA, US, अमेरिका</span><span class="sxs-lookup"><span data-stu-id="d634c-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="d634c-169">CA: कनाडा, CA</span><span class="sxs-lookup"><span data-stu-id="d634c-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="d634c-170">GB: यूनाइटेड किंगडम, UK, ग्रेट ब्रिटेन, GB, ग्रेट ब्रिटेन का यूनाइटेड किंगडम और उत्तरी आयरलैंड, ग्रेट ब्रिटेन का यूनाइटेड किंगडम</span><span class="sxs-lookup"><span data-stu-id="d634c-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="d634c-171">AU: ऑस्ट्रेलिया, AU, ऑस्ट्रेलिया का राष्ट्रमंडल</span><span class="sxs-lookup"><span data-stu-id="d634c-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="d634c-172">FR: फ्रांस, FR, फ्रेंच रिपब्लिक</span><span class="sxs-lookup"><span data-stu-id="d634c-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="d634c-173">DE: जर्मनी, जर्मन, डॉयच्लान्ट्, अल्लेमाग्ने, DE, संघीय गणराज्य जर्मनी, जर्मनी गणराज्य</span><span class="sxs-lookup"><span data-stu-id="d634c-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="d634c-174">समीक्षा और संवर्धन को नाम दें</span><span class="sxs-lookup"><span data-stu-id="d634c-174">Review and name the enrichment</span></span>

<span data-ttu-id="d634c-175">अंत में, आपको जानकारी की समीक्षा करने और संवर्धन के लिए एक नाम प्रदान करने के लिए मिलता है.</span><span class="sxs-lookup"><span data-stu-id="d634c-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="दिलचस्पी की समीक्षा और पृष्ठ का नामकरण.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="d634c-177">संवर्धन को ताज़ा रिफ्रेश करें</span><span class="sxs-lookup"><span data-stu-id="d634c-177">Refresh enrichment</span></span>

<span data-ttu-id="d634c-178">ब्रांड, रुचियों और जनसांख्यिकी के लिए फ़ील्ड मैपिंग कॉन्फ़िगर करने के बाद समृद्ध करना चालू करें.</span><span class="sxs-lookup"><span data-stu-id="d634c-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="d634c-179">प्रक्रिया शुरू करने के लिए, ब्रांड या रुचि कॉन्फ़िगरेशन पृष्ठ पर **चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d634c-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="d634c-180">इसके अतिरिक्त, आप सिस्टम को शेड्यूल किए गए रीफ़्रेश के भाग के रूप में संवर्धन को स्वत: चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d634c-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="d634c-181">आपके ग्राहक डेटा के आकार के आधार पर, समृद्ध रन को पूरा होने में कई मिनट लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d634c-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="d634c-182">कार्यों/प्रक्रियाओं के लिए [छह प्रकार की स्थिति](system.md#status-types) हैं .</span><span class="sxs-lookup"><span data-stu-id="d634c-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d634c-183">इसके अतिरिक्त, अधिकांश प्रक्रियाएं [अन्य डाउनस्ट्रीम प्रक्रियाओं पर निर्भर करती हैं](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d634c-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d634c-184">आप पूरे कार्य की प्रगति पर विवरण देखने के लिए प्रक्रिया की स्थिति का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d634c-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d634c-185">**विवरण देखें** चयन करने के बाद कार्य के किसी एक कार्य के लिए, आपको अतिरिक्त जानकारी मिलेगी: संसाधन समय, अंतिम संसाधन तिथि, और कार्य से जुड़ी सभी त्रुटियां और चेतावनियां.</span><span class="sxs-lookup"><span data-stu-id="d634c-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="d634c-186">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="d634c-186">Enrichment results</span></span>

<span data-ttu-id="d634c-187">संवर्धन प्रक्रिया चलाने के बाद, समृद्ध ग्राहकों की कुल संख्या और समृद्ध ग्राहक प्रोफाइल में ब्रांड्स या रुचियों के विश्लेषण की समीक्षा करने के लिए **मेरे संवर्धन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="d634c-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="संवर्धन की प्रक्रिया चलाने के बाद परिणामों का पूर्वावलोकन":::

<span data-ttu-id="d634c-189">चार्ट में **समृद्ध डेटा देखें** को चुनकर समृद्ध डेटा की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="d634c-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="d634c-190">ब्रांड के लिए समृद्ध डेटा **BrandAffinityFromMicrosoft** निकाय में जाता है.</span><span class="sxs-lookup"><span data-stu-id="d634c-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="d634c-191">रुचियों के लिए डेटा **InterestAffinityFromMicrosoft** निकाय में है.</span><span class="sxs-lookup"><span data-stu-id="d634c-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="d634c-192">आपको ये निकाय **डेटा** > **निकाय** के **संवर्धन** समूह में भी सूचीबद्ध मिल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d634c-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="d634c-193">ग्राहक कार्ड पर संवर्द्धन डेटा देखें</span><span class="sxs-lookup"><span data-stu-id="d634c-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="d634c-194">ब्रांड और रुचियो की एफ़िनिटी को व्यक्तिगत ग्राहक कार्ड पर देखा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="d634c-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="d634c-195">**ग्राहकों** पर जाएँ और एक ग्राहक प्रोफ़ाइल का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d634c-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="d634c-196">ग्राहक कार्ड में, आपको उन ब्रांड्स या रुचियों के लिए चार्ट मिलेंगे जिनके लिए उस ग्राहक की जनसांख्यिकीय प्रोफ़ाइल में लोगों से समानता है.</span><span class="sxs-lookup"><span data-stu-id="d634c-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="संवर्धन डेटा वाला के साथ ग्राहक कार्ड":::

## <a name="next-steps"></a><span data-ttu-id="d634c-198">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="d634c-198">Next steps</span></span>

<span data-ttu-id="d634c-199">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="d634c-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d634c-200">[खंडों](segments.md) को बनाएं और [साधानों](measures.md) और यहां तक कि अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d634c-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
