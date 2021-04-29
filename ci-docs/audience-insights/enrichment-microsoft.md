---
title: Microsoft से डेटा के साथ ग्राहक प्रोफाइल को बेहतर करें
description: ब्रांड और दिलचस्पी के लिए झुकाव के साथ अपने ग्राहक डेटा को समृद्ध करने के लिए Microsoft से मालिकाना डेटा का उपयोग करें.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896604"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="7db8a-103">ग्राहक प्रोफाइल को ब्रांड और रुचि आत्मीयताओं से समृद्ध करें (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="7db8a-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="7db8a-104">ब्रांड और दिलचस्पी के लिए झुकाव के साथ अपने ग्राहक डेटा को समृद्ध करने के लिए Microsoft के मालिकाना डेटा का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="7db8a-105">ये एफ़िनिटी आपके ग्राहकों के समान जनसांख्यिकी वाले लोगों के डेटा के आधार पर निर्धारित की जाती हैं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="7db8a-106">यह जानकारी आपको विशिष्ट ब्रांडों और रुचियों के प्रति आपके ग्राहकों की एफ़िनिटी के आधार पर उनको बेहतर ढंग से समझने और सेगमेंट करने में मदद करती है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="7db8a-107">ऑडिएंस इनसाइट्स में, [संवर्धन कॉन्फ़िगर करें और देखें](enrichment-hub.md) के लिए **डेटा** > **संवर्धन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="7db8a-108">ब्रांड संबंध समृद्धि को कॉन्फ़िगर करने के लिए **खोजें** टैब पर जाएं और **ब्रांड** टाइल पर **मेरा डेटा समृद्ध करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="7db8a-109">रुचि संबंध समृद्धि को कॉन्फ़िगर करने के लिए **खोजें** टैब पर जाएं और **रुचियां** टाइल पर **मेरा डेटा समृद्ध करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7db8a-110">![ब्रांड और रुचियां टाइल्स](media/BrandsInterest-tile-Hub.png "ब्रांड और रुचियां टाइल्स")</span><span class="sxs-lookup"><span data-stu-id="7db8a-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="7db8a-111">हम झुकाव कैसे निर्धारित करते हैं</span><span class="sxs-lookup"><span data-stu-id="7db8a-111">How we determine affinities</span></span>

<span data-ttu-id="7db8a-112">हम विभिन्न जनसांख्यिकीय सेगमेंटों (उम्र, लिंग या स्थान के अनुसार परिभाषित) में ब्रांडों और हितों के लिए समानताएं खोजने के लिए Microsoft के ऑनलाइन खोज डेटा का उपयोग करते हैं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="7db8a-113">किसी ब्रांड या रुचि के लिए ऑनलाइन खोज मात्रा यह निर्धारित करती है कि उस ब्रांड या रुचि से, अन्य अनुभागों की तुलना में, किसी जनसांख्यिकीय अनुभाग में कितनी रुचि है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="7db8a-114">ब्रांड या रुचि.</span><span class="sxs-lookup"><span data-stu-id="7db8a-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="7db8a-115">एफ़िनिटी का स्तर और स्कोर</span><span class="sxs-lookup"><span data-stu-id="7db8a-115">Affinity level and score</span></span>

<span data-ttu-id="7db8a-116">हर एक समृद्ध ग्राहक प्रोफ़ाइल पर, हम दो संबंधित मान प्रदान करते हैं – एफ़िनिटी स्तर और एफ़िनिटी स्कोर.</span><span class="sxs-lookup"><span data-stu-id="7db8a-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="7db8a-117">ये मान आपको यह निर्धारित करने में मदद करते हैं कि किसी ब्रांड या दिलचस्पी के लिए, अन्य जनसांख्यिकीय अनुभाग की तुलना में उस प्रोफ़ाइल के जनसांख्यिकीय अनुभाग के लिए एफ़िनिटी कितनी मजबूत है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="7db8a-118">*एफ़िनिटी स्तर* में चार स्तर होते हैं और *एफ़िनिटी स्कोर* की गणना 100 अंकों के पैमाने पर की जाती है, जो एफ़िनिटी के स्तरों पर मैप करता है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="7db8a-119">एफ़िनिटी स्तर</span><span class="sxs-lookup"><span data-stu-id="7db8a-119">Affinity level</span></span> |<span data-ttu-id="7db8a-120">एफ़िनिटी स्कोर</span><span class="sxs-lookup"><span data-stu-id="7db8a-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="7db8a-121">बहुत उच्च</span><span class="sxs-lookup"><span data-stu-id="7db8a-121">Very high</span></span>     | <span data-ttu-id="7db8a-122">85-100</span><span class="sxs-lookup"><span data-stu-id="7db8a-122">85-100</span></span>       |
|<span data-ttu-id="7db8a-123">उच्च</span><span class="sxs-lookup"><span data-stu-id="7db8a-123">High</span></span>     | <span data-ttu-id="7db8a-124">70-84</span><span class="sxs-lookup"><span data-stu-id="7db8a-124">70-84</span></span>        |
|<span data-ttu-id="7db8a-125">मध्यम</span><span class="sxs-lookup"><span data-stu-id="7db8a-125">Medium</span></span>     | <span data-ttu-id="7db8a-126">35-69</span><span class="sxs-lookup"><span data-stu-id="7db8a-126">35-69</span></span>        |
|<span data-ttu-id="7db8a-127">कम</span><span class="sxs-lookup"><span data-stu-id="7db8a-127">Low</span></span>     | <span data-ttu-id="7db8a-128">1-34</span><span class="sxs-lookup"><span data-stu-id="7db8a-128">1-34</span></span>        |

<span data-ttu-id="7db8a-129">एफ़िनिटी को मापने के लिए आप जो ग्रैन्युलैरिटी चाहते हैं, उसके आधार पर आप एफ़िनिटी स्तर या स्कोर का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="7db8a-130">एफ़िनिटी स्कोर आपको ज़्यादा सटीक नियंत्रण देता है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="7db8a-131">समर्थित देश/क्षेत्र</span><span class="sxs-lookup"><span data-stu-id="7db8a-131">Supported countries/regions</span></span>

<span data-ttu-id="7db8a-132">वर्तमान में हम निम्नलिखित देशों/क्षेत्रों में समर्थन करते हैं: ऑस्ट्रेलिया, कनाडा (अंग्रेजी), फ्रांस, जर्मनी, यूनाइटेड किंगडम, या संयुक्त राज्य अमेरिका (अंग्रेजी).</span><span class="sxs-lookup"><span data-stu-id="7db8a-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="7db8a-133">किसी देश का चयन करने के लिए, **ब्रांड संवर्धन** या **रुचि संवर्धन** खोलें और **देश/क्षेत्र** के आगे **बदलें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="7db8a-134">**देश/क्षेत्र सेटिंग** फलक में, विकल्प चुनें और **लागू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="7db8a-135">देश चयन से संबंधित निहितार्थ</span><span class="sxs-lookup"><span data-stu-id="7db8a-135">Implications related to country selection</span></span>

- <span data-ttu-id="7db8a-136">जब [अपना खुद का ब्रांड चुनना हो](#define-your-brands-or-interests), तो सिस्टम चयनित देश या क्षेत्र के आधार पर सुझाव प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="7db8a-137">जब [किसी उद्योग का चयन करना हो](#define-your-brands-or-interests), तो आपको चयनित देश या क्षेत्र के आधार पर सबसे ज़्यादा प्रासंगिक ब्रांड या दिलचस्पियां मिलेंगी.</span><span class="sxs-lookup"><span data-stu-id="7db8a-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="7db8a-138">जब [प्रोफ़ाइल को बेहतर बनाना हो](#refresh-enrichment), तो हम सभी ग्राहक प्रोफ़ाइलों को बेहतर बनाएंगे, जिसके लिए हमें चयनित ब्रांडों और दिलचस्पियों के लिए डेटा मिलता है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="7db8a-139">उन प्रोफ़ाइलों सहित, जो चयनित देश या क्षेत्र में नहीं हैं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="7db8a-140">उदाहरण के लिए, अगर आपने जर्मनी का चयन किया है, तो हम संयुक्त राज्य अमेरिका में स्थित प्रोफ़ाइल को समृद्ध करेंगे, अगर हमारे पास अमेरिका में चयनित ब्रांडों और दिलचस्पी के लिए डेटा उपलब्ध है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="7db8a-141">संवर्धन कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="7db8a-141">Configure Enrichment</span></span>

<span data-ttu-id="7db8a-142">एक निर्देशित अनुभव आपको संवर्धन के कॉन्फ़िगरेशन के माध्यम से मदद करता है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="7db8a-143">अपने ब्रांड या रुचियों को परिभाषित करें</span><span class="sxs-lookup"><span data-stu-id="7db8a-143">Define your brands or interests</span></span>

<span data-ttu-id="7db8a-144">निम्न विकल्पों में से किसी एक का चयन करें:</span><span class="sxs-lookup"><span data-stu-id="7db8a-144">Select one of the following options:</span></span>

- <span data-ttu-id="7db8a-145">**उद्योग**: सिस्टम आपके उद्योग के लिए प्रासंगिक शीर्ष ब्रांड्स या रुचियों की पहचान करता है और आपके ग्राहक डेटा को उनसे समृद्ध करता है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="7db8a-146">**खुद चयन करें**: ब्रांड्स या रुचियों की सूची से वो पांच आइटम चुनें, जो आपके संगठन के लिए सबसे अधिक प्रासंगिक हैं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="7db8a-147">किसी ब्रांड या रुचि को जोड़ने के लिए, मिलने वाले शब्दों के आधार पर सुझाव प्राप्त करने के लिए इसे इनपुट क्षेत्र में दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="7db8a-148">यदि आपके द्वारा खोजे जा रहे ब्रांड या रुचि हमारे द्वारा सूचीबद्ध नहीं हैं, तो **सुझाव दें** लिंक का उपयोग करके हमें प्रतिक्रिया भेजें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="7db8a-149">संवर्धन प्राथमिकताओं की समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="7db8a-149">Review enrichment preferences</span></span>

<span data-ttu-id="7db8a-150">अपनी डिफ़ॉल्ट संवर्धन प्राथमिकताओं की समीक्षा करें और उन्हें आवश्यकतानुसार अपडेट करें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="संवर्धन प्राथमिकता विंडो का स्क्रीनशॉट.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="7db8a-152">बेहतर बनाने के लिए निकाय का चयन करें</span><span class="sxs-lookup"><span data-stu-id="7db8a-152">Select entity to enrich</span></span>

<span data-ttu-id="7db8a-153">**समृद्ध निकाय** चुनें और उस डेटा सेट को चुनें जिसे आप Microsoft के कंपनी डेटा के साथ समृद्ध करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="7db8a-154">आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए ग्राहक निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="7db8a-155">अपने फ़ील्ड का मानचित्र बनाएं</span><span class="sxs-lookup"><span data-stu-id="7db8a-155">Map your fields</span></span>

<span data-ttu-id="7db8a-156">अपने एकीकृत ग्राहक निकाय से फ़ील्ड को मैप करें, ताकि उस जनसांख्यिकीय अनुभाग को परिभाषित किया जा सके जिसे आप चाहते हैं कि सिस्टम आपके ग्राहक डेटा को बेहतर करने के लिए उपयोग करे.</span><span class="sxs-lookup"><span data-stu-id="7db8a-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="7db8a-157">देश/क्षेत्र और कम से कम जन्मतिथि या लिंग एट्रिब्यूट मैप करें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="7db8a-158">इसके अलावा, आपको कम से कम एक शहर (और राज्य/प्रांत) या पोस्टल कोड को मैप करना होगा.</span><span class="sxs-lookup"><span data-stu-id="7db8a-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="7db8a-159">फ़ील्ड की मैपिंग को परिभाषित करने के लिए **संपादित करें** चुनें और जब आप पूरा कर चुकें तब **लागू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="7db8a-160">फ़ील्ड मैपिंग को पूरा करने के लिए **सहेजें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="7db8a-161">निम्नलिखित प्रारूप और मान समर्थित हैं, मान केस-संवेदी नहीं हैं:</span><span class="sxs-lookup"><span data-stu-id="7db8a-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="7db8a-162">**जन्म तिथि**: हम अनुशंसा करते हैं कि जन्म की तारीख डेटा अंतर्ग्रहण के दौरान DateTime प्रकार में बदल जाती है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="7db8a-163">वैकल्पिक रूप से, यह [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) प्रारूप "yyyy-MM-dd" या "yyyy-MM-ddTHH:mm:ssZ" में एक स्ट्रिंग हो सकता है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="7db8a-164">**लिंग**: पुरुष, महिला, अज्ञात</span><span class="sxs-lookup"><span data-stu-id="7db8a-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="7db8a-165">**पोस्टल कोड**: US के लिए पांच अंकों का ZIP कोड, अन्यत्र के लिए मानक डाक कोड</span><span class="sxs-lookup"><span data-stu-id="7db8a-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="7db8a-166">**शहर**: शहर का नाम अंग्रेजी में</span><span class="sxs-lookup"><span data-stu-id="7db8a-166">**City**: City name in English</span></span>
- <span data-ttu-id="7db8a-167">**राज्य/प्रांत**: अमेरिका और कनाडा के लिए दो-अक्षर का संक्षिप्त नाम.</span><span class="sxs-lookup"><span data-stu-id="7db8a-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="7db8a-168">ऑस्ट्रेलिया के लिए दो या तीन अक्षरीय संक्षिप्त नाम.</span><span class="sxs-lookup"><span data-stu-id="7db8a-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="7db8a-169">फ्रांस, जर्मनी या यूके के लिए लागू नहीं है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="7db8a-170">**देश/क्षेत्र**:</span><span class="sxs-lookup"><span data-stu-id="7db8a-170">**Country/Region**:</span></span>

  - <span data-ttu-id="7db8a-171">US: यूनाइटेड स्टेट्स ऑफ अमेरिका, यूनाइटेड स्टेट्स, USA, US, अमेरिका</span><span class="sxs-lookup"><span data-stu-id="7db8a-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="7db8a-172">CA: कनाडा, CA</span><span class="sxs-lookup"><span data-stu-id="7db8a-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="7db8a-173">GB: यूनाइटेड किंगडम, UK, ग्रेट ब्रिटेन, GB, ग्रेट ब्रिटेन का यूनाइटेड किंगडम और उत्तरी आयरलैंड, ग्रेट ब्रिटेन का यूनाइटेड किंगडम</span><span class="sxs-lookup"><span data-stu-id="7db8a-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="7db8a-174">AU: ऑस्ट्रेलिया, AU, कॉमन वेल्थ ऑफ ऑस्ट्रेलिया</span><span class="sxs-lookup"><span data-stu-id="7db8a-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="7db8a-175">FR: फ्रांस, FR, फ्रेंच रिपब्लिक</span><span class="sxs-lookup"><span data-stu-id="7db8a-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="7db8a-176">DE: जर्मनी, जर्मन, डॉयच्लान्ट्, अल्लेमाग्ने, DE, संघीय गणराज्य जर्मनी, जर्मनी गणराज्य</span><span class="sxs-lookup"><span data-stu-id="7db8a-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="7db8a-177">समीक्षा और संवर्धन को नाम दें</span><span class="sxs-lookup"><span data-stu-id="7db8a-177">Review and name the enrichment</span></span>

<span data-ttu-id="7db8a-178">अंत में, आपको जानकारी की समीक्षा करने और संवर्धन के लिए एक नाम प्रदान करने के लिए मिलता है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="दिलचस्पी की समीक्षा और पृष्ठ का नामकरण.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="7db8a-180">संवर्धन को ताज़ा रिफ्रेश करें</span><span class="sxs-lookup"><span data-stu-id="7db8a-180">Refresh enrichment</span></span>

<span data-ttu-id="7db8a-181">ब्रांड, रुचियों और जनसांख्यिकी के लिए फ़ील्ड मैपिंग कॉन्फ़िगर करने के बाद समृद्ध करना चालू करें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="7db8a-182">प्रक्रिया शुरू करने के लिए, ब्रांड या रुचि कॉन्फ़िगरेशन पृष्ठ पर **चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="7db8a-183">इसके अतिरिक्त, आप सिस्टम को शेड्यूल किए गए रीफ़्रेश के भाग के रूप में संवर्धन को स्वत: चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="7db8a-184">आपके ग्राहक डेटा के आकार के आधार पर, समृद्ध रन को पूरा होने में कई मिनट लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="7db8a-185">कार्यों/प्रक्रियाओं के लिए [छह प्रकार की स्थिति](system.md#status-types) हैं .</span><span class="sxs-lookup"><span data-stu-id="7db8a-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="7db8a-186">इसके अतिरिक्त, अधिकांश प्रक्रियाएं [अन्य डाउनस्ट्रीम प्रक्रियाओं पर निर्भर करती हैं](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="7db8a-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="7db8a-187">आप पूरे कार्य की प्रगति पर विवरण देखने के लिए प्रक्रिया की स्थिति का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="7db8a-188">किसी एक जॉब कार्य के लिए **विवरण देखें** को चुनने के बाद, आपको अतिरिक्त जानकारी मिलती है: संसाधन समय, अंतिम संसाधन दिनांक और कार्य से जुड़ी सभी त्रुटियां और चेतावनियाँ.</span><span class="sxs-lookup"><span data-stu-id="7db8a-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="7db8a-189">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="7db8a-189">Enrichment results</span></span>

<span data-ttu-id="7db8a-190">संवर्धन प्रक्रिया चलाने के बाद, समृद्ध ग्राहकों की कुल संख्या और समृद्ध ग्राहक प्रोफाइल में ब्रांड्स या रुचियों के विश्लेषण की समीक्षा करने के लिए **मेरे संवर्धन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="संवर्धन की प्रक्रिया चलाने के बाद परिणामों का पूर्वावलोकन":::

<span data-ttu-id="7db8a-192">चार्ट में **समृद्ध डेटा देखें** को चुनकर समृद्ध डेटा की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="7db8a-193">ब्रांड के लिए समृद्ध डेटा **BrandAffinityFromMicrosoft** निकाय में जाता है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="7db8a-194">रुचियों के लिए डेटा **InterestAffinityFromMicrosoft** निकाय में है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="7db8a-195">आपको ये निकाय **डेटा** > **निकाय** के **संवर्धन** समूह में भी सूचीबद्ध मिल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="7db8a-196">ग्राहक कार्ड पर संवर्द्धन डेटा देखें</span><span class="sxs-lookup"><span data-stu-id="7db8a-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="7db8a-197">ब्रांड और रुचियो की एफ़िनिटी को व्यक्तिगत ग्राहक कार्ड पर देखा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="7db8a-198">**ग्राहकों** पर जाएँ और एक ग्राहक प्रोफ़ाइल का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="7db8a-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="7db8a-199">ग्राहक कार्ड में, आपको उन ब्रांड्स या रुचियों के लिए चार्ट मिलेंगे जिनके लिए उस ग्राहक की जनसांख्यिकीय प्रोफ़ाइल में लोगों से समानता है.</span><span class="sxs-lookup"><span data-stu-id="7db8a-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="संवर्धन डेटा वाला के साथ ग्राहक कार्ड":::

## <a name="next-steps"></a><span data-ttu-id="7db8a-201">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="7db8a-201">Next steps</span></span>

<span data-ttu-id="7db8a-202">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="7db8a-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="7db8a-203">अपने ग्राहकों को व्यक्तिगत अनुभव डिलीवर करने के लिए [सेगमेंट](segments.md), [मापन](measures.md)बनाएं, और यहां तक कि [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7db8a-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
