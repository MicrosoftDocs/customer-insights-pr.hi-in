---
title: Microsoft Graph के साथ ग्राहक प्रोफाइल को समृद्ध करें
description: अपने ग्राहक डेटा को ब्रांड और रुचि आत्मीयताओँ से समृद्ध करने के लिए Microsoft Graph से स्वामित्व डेटा का उपयोग करें.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2c95369c778f592bc1460799aca0fa8cff813d68
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269332"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="c51c5-103">ग्राहक प्रोफाइल को ब्रांड और रुचि आत्मीयताओं से समृद्ध करें (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="c51c5-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="c51c5-104">अपने ग्राहक डेटा को ब्रांड और रुचि आत्मीयताओँ से समृद्ध करने के लिए Microsoft Graph से स्वामित्व डेटा का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="c51c5-105">ये एफ़िनिटी आपके ग्राहकों के समान जनसांख्यिकी वाले लोगों के डेटा के आधार पर निर्धारित की जाती हैं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="c51c5-106">यह जानकारी आपको विशिष्ट ब्रांडों और रुचियों के प्रति आपके ग्राहकों की एफ़िनिटी के आधार पर उनको बेहतर ढंग से समझने और सेगमेंट करने में मदद करती है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="c51c5-107">ऑडिएंस इनसाइट्स में, [संवर्धन कॉन्फ़िगर करें और देखें](enrichment-hub.md) के लिए **डेटा** > **संवर्धन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="c51c5-108">ब्रांड संबंध समृद्धि को कॉन्फ़िगर करने के लिए **खोजें** टैब पर जाएं और **ब्रांड** टाइल पर **मेरा डेटा समृद्ध करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="c51c5-109">रुचि संबंध समृद्धि को कॉन्फ़िगर करने के लिए **खोजें** टैब पर जाएं और **रुचियां** टाइल पर **मेरा डेटा समृद्ध करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c51c5-110">![ब्रांड और रुचियां टाइल्स](media/BrandsInterest-tile-Hub.png "ब्रांड और रुचियां टाइल्स")</span><span class="sxs-lookup"><span data-stu-id="c51c5-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="c51c5-111">Microsoft Graph के बारे में</span><span class="sxs-lookup"><span data-stu-id="c51c5-111">About Microsoft Graph</span></span>

<span data-ttu-id="c51c5-112">हम Microsoft Graph से ऑनलाइन खोज डेटा का उपयोग विभिन्न जनसांख्यिकीय खंडों (उम्र, लिंग, या स्थान द्वारा परिभाषित) में ब्रांडों और हितों के लिए आत्मीयताएं खोजने के लिए करते हैं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="c51c5-113">किसी ब्रांड या रुचि के लिए ऑनलाइन खोज मात्रा यह निर्धारित करती है कि उस ब्रांड या रुचि से, अन्य अनुभागों की तुलना में, किसी जनसांख्यिकीय अनुभाग में कितनी रुचि है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="c51c5-114">[Microsoft Graph के बारे में और जानें](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="c51c5-114">[Learn more about Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="c51c5-115">एफ़िनिटी का स्तर और स्कोर</span><span class="sxs-lookup"><span data-stu-id="c51c5-115">Affinity level and score</span></span>

<span data-ttu-id="c51c5-116">हर एक समृद्ध ग्राहक प्रोफ़ाइल पर, हम दो संबंधित मान प्रदान करते हैं – एफ़िनिटी स्तर और एफ़िनिटी स्कोर.</span><span class="sxs-lookup"><span data-stu-id="c51c5-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="c51c5-117">ये मान आपको यह निर्धारित करने में मदद करते हैं कि किसी ब्रांड या दिलचस्पी के लिए, अन्य जनसांख्यिकीय अनुभाग की तुलना में उस प्रोफ़ाइल के जनसांख्यिकीय अनुभाग के लिए एफ़िनिटी कितनी मजबूत है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="c51c5-118">*एफ़िनिटी स्तर* में चार स्तर होते हैं और *एफ़िनिटी स्कोर* की गणना 100 अंकों के पैमाने पर की जाती है, जो एफ़िनिटी के स्तरों पर मैप करता है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="c51c5-119">एफ़िनिटी स्तर</span><span class="sxs-lookup"><span data-stu-id="c51c5-119">Affinity level</span></span> |<span data-ttu-id="c51c5-120">एफ़िनिटी स्कोर</span><span class="sxs-lookup"><span data-stu-id="c51c5-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="c51c5-121">बहुत उच्च</span><span class="sxs-lookup"><span data-stu-id="c51c5-121">Very high</span></span>     | <span data-ttu-id="c51c5-122">85-100</span><span class="sxs-lookup"><span data-stu-id="c51c5-122">85-100</span></span>       |
|<span data-ttu-id="c51c5-123">उच्च</span><span class="sxs-lookup"><span data-stu-id="c51c5-123">High</span></span>     | <span data-ttu-id="c51c5-124">70-84</span><span class="sxs-lookup"><span data-stu-id="c51c5-124">70-84</span></span>        |
|<span data-ttu-id="c51c5-125">मध्यम</span><span class="sxs-lookup"><span data-stu-id="c51c5-125">Medium</span></span>     | <span data-ttu-id="c51c5-126">35-69</span><span class="sxs-lookup"><span data-stu-id="c51c5-126">35-69</span></span>        |
|<span data-ttu-id="c51c5-127">कम</span><span class="sxs-lookup"><span data-stu-id="c51c5-127">Low</span></span>     | <span data-ttu-id="c51c5-128">1-34</span><span class="sxs-lookup"><span data-stu-id="c51c5-128">1-34</span></span>        |

<span data-ttu-id="c51c5-129">एफ़िनिटी को मापने के लिए आप जो ग्रैन्युलैरिटी चाहते हैं, उसके आधार पर आप एफ़िनिटी स्तर या स्कोर का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="c51c5-130">एफ़िनिटी स्कोर आपको ज़्यादा सटीक नियंत्रण देता है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="c51c5-131">समर्थित देश/क्षेत्र</span><span class="sxs-lookup"><span data-stu-id="c51c5-131">Supported countries/regions</span></span>

<span data-ttu-id="c51c5-132">वर्तमान में हम निम्नलिखित देशों/क्षेत्रों में समर्थन करते हैं: ऑस्ट्रेलिया, कनाडा (अंग्रेजी), फ्रांस, जर्मनी, यूनाइटेड किंगडम, या संयुक्त राज्य अमेरिका (अंग्रेजी).</span><span class="sxs-lookup"><span data-stu-id="c51c5-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="c51c5-133">किसी देश का चयन करने के लिए, **ब्रांड संवर्धन** या **रुचि संवर्धन** खोलें और **देश/क्षेत्र** के आगे **बदलें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="c51c5-134">**देश/क्षेत्र सेटिंग** फलक में, विकल्प चुनें और **लागू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="c51c5-135">देश चयन से संबंधित निहितार्थ</span><span class="sxs-lookup"><span data-stu-id="c51c5-135">Implications related to country selection</span></span>

- <span data-ttu-id="c51c5-136">जब [अपना खुद का ब्रांड चुनना हो](#define-your-brands-or-interests), तो सिस्टम चयनित देश या क्षेत्र के आधार पर सुझाव प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="c51c5-137">जब [किसी उद्योग का चयन करना हो](#define-your-brands-or-interests), तो आपको चयनित देश या क्षेत्र के आधार पर सबसे ज़्यादा प्रासंगिक ब्रांड या दिलचस्पियां मिलेंगी.</span><span class="sxs-lookup"><span data-stu-id="c51c5-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="c51c5-138">जब [प्रोफ़ाइल को बेहतर बनाना हो](#refresh-enrichment), तो हम सभी ग्राहक प्रोफ़ाइलों को बेहतर बनाएंगे, जिसके लिए हमें चयनित ब्रांडों और दिलचस्पियों के लिए डेटा मिलता है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="c51c5-139">उन प्रोफ़ाइलों सहित, जो चयनित देश या क्षेत्र में नहीं हैं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="c51c5-140">उदाहरण के लिए, यदि आपने जर्मनी का चयन किया है, तो हम संयुक्त राज्य अमेरिका में स्थित प्रोफाइल को समृद्ध करेंगे यदि हमारे पास अमेरिका में चयनित ब्रांड्स और हितों के लिए Microsoft Graph डेटा उपलब्ध है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="c51c5-141">संवर्धन कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="c51c5-141">Configure Enrichment</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="c51c5-142">अपने ब्रांड या रुचियों को परिभाषित करें</span><span class="sxs-lookup"><span data-stu-id="c51c5-142">Define your brands or interests</span></span>

<span data-ttu-id="c51c5-143">निम्न विकल्पों में से किसी एक का चयन करें:</span><span class="sxs-lookup"><span data-stu-id="c51c5-143">Select one of the following options:</span></span>

- <span data-ttu-id="c51c5-144">**उद्योग**: सिस्टम आपके उद्योग के लिए प्रासंगिक शीर्ष ब्रांड्स या रुचियों की पहचान करता है और आपके ग्राहक डेटा को उनसे समृद्ध करता है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="c51c5-145">**खुद चयन करें**: ब्रांड्स या रुचियों की सूची से वो पांच आइटम चुनें, जो आपके संगठन के लिए सबसे अधिक प्रासंगिक हैं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="c51c5-146">किसी ब्रांड या रुचि को जोड़ने के लिए, मिलने वाले शब्दों के आधार पर सुझाव प्राप्त करने के लिए इसे इनपुट क्षेत्र में दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="c51c5-147">यदि आपके द्वारा खोजे जा रहे ब्रांड या रुचि हमारे द्वारा सूचीबद्ध नहीं हैं, तो **सुझाव दें** लिंक का उपयोग करके हमें प्रतिक्रिया भेजें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="c51c5-148">संवर्धन प्राथमिकताओं की समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="c51c5-148">Review enrichment preferences</span></span>

<span data-ttu-id="c51c5-149">अपनी डिफ़ॉल्ट संवर्धन प्राथमिकताओं की समीक्षा करें और उन्हें आवश्यकतानुसार अपडेट करें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="संवर्धन प्राथमिकता विंडो का स्क्रीनशॉट.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="c51c5-151">बेहतर बनाने के लिए निकाय का चयन करें</span><span class="sxs-lookup"><span data-stu-id="c51c5-151">Select entity to enrich</span></span>

<span data-ttu-id="c51c5-152">**बेहतर किया गया निकाय** चुनें और उस डेटा सेट को चुनें जिसे आप Microsoft ग्राफ़ से कंपनी डेटा के साथ बेहतर बनाना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft Graph.</span></span> <span data-ttu-id="c51c5-153">आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए ग्राहक निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="c51c5-154">अपने फ़ील्ड का मानचित्र बनाएं</span><span class="sxs-lookup"><span data-stu-id="c51c5-154">Map your fields</span></span>

<span data-ttu-id="c51c5-155">अपने एकीकृत ग्राहक निकाय से फ़ील्ड को मैप करें, ताकि उस जनसांख्यिकीय अनुभाग को परिभाषित किया जा सके जिसे आप चाहते हैं कि सिस्टम आपके ग्राहक डेटा को बेहतर करने के लिए उपयोग करे.</span><span class="sxs-lookup"><span data-stu-id="c51c5-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="c51c5-156">देश/क्षेत्र और कम से कम जन्मतिथि या लिंग एट्रिब्यूट मैप करें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="c51c5-157">इसके अलावा, आपको कम से कम एक शहर (और राज्य/प्रांत) या पोस्टल कोड को मैप करना होगा.</span><span class="sxs-lookup"><span data-stu-id="c51c5-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="c51c5-158">फ़ील्ड की मैपिंग को परिभाषित करने के लिए **संपादित करें** चुनें और जब आप पूरा कर चुकें तब **लागू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="c51c5-159">फ़ील्ड मैपिंग को पूरा करने के लिए **सहेजें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="c51c5-160">निम्नलिखित प्रारूप और मान समर्थित हैं, मान केस-संवेदी नहीं हैं:</span><span class="sxs-lookup"><span data-stu-id="c51c5-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="c51c5-161">**जन्म तिथि**: हम अनुशंसा करते हैं कि जन्म की तारीख डेटा अंतर्ग्रहण के दौरान DateTime प्रकार में बदल जाती है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="c51c5-162">वैकल्पिक रूप से, यह [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) प्रारूप "yyyy-MM-dd" या "yyyy-MM-ddTHH:mm:ssZ" में एक स्ट्रिंग हो सकता है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="c51c5-163">**लिंग**: पुरुष, महिला, अज्ञात</span><span class="sxs-lookup"><span data-stu-id="c51c5-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="c51c5-164">**पोस्टल कोड**: US के लिए पांच अंकों का ZIP कोड, अन्यत्र के लिए मानक डाक कोड</span><span class="sxs-lookup"><span data-stu-id="c51c5-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="c51c5-165">**शहर**: शहर का नाम अंग्रेजी में</span><span class="sxs-lookup"><span data-stu-id="c51c5-165">**City**: City name in English</span></span>
- <span data-ttu-id="c51c5-166">**राज्य/प्रांत**: अमेरिका और कनाडा के लिए दो-अक्षर का संक्षिप्त नाम.</span><span class="sxs-lookup"><span data-stu-id="c51c5-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="c51c5-167">ऑस्ट्रेलिया के लिए दो या तीन अक्षरीय संक्षिप्त नाम.</span><span class="sxs-lookup"><span data-stu-id="c51c5-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="c51c5-168">फ्रांस, जर्मनी या यूके के लिए लागू नहीं है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="c51c5-169">**देश/क्षेत्र**:</span><span class="sxs-lookup"><span data-stu-id="c51c5-169">**Country/Region**:</span></span>

  - <span data-ttu-id="c51c5-170">US: यूनाइटेड स्टेट्स ऑफ अमेरिका, यूनाइटेड स्टेट्स, USA, US, अमेरिका</span><span class="sxs-lookup"><span data-stu-id="c51c5-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="c51c5-171">CA: कनाडा, CA</span><span class="sxs-lookup"><span data-stu-id="c51c5-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="c51c5-172">GB: यूनाइटेड किंगडम, UK, ग्रेट ब्रिटेन, GB, ग्रेट ब्रिटेन का यूनाइटेड किंगडम और उत्तरी आयरलैंड, ग्रेट ब्रिटेन का यूनाइटेड किंगडम</span><span class="sxs-lookup"><span data-stu-id="c51c5-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="c51c5-173">AU: ऑस्ट्रेलिया, AU, कॉमन वेल्थ ऑफ ऑस्ट्रेलिया</span><span class="sxs-lookup"><span data-stu-id="c51c5-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="c51c5-174">FR: फ्रांस, FR, फ्रेंच रिपब्लिक</span><span class="sxs-lookup"><span data-stu-id="c51c5-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="c51c5-175">DE: जर्मनी, जर्मन, डॉयच्लान्ट्, अल्लेमाग्ने, DE, संघीय गणराज्य जर्मनी, जर्मनी गणराज्य</span><span class="sxs-lookup"><span data-stu-id="c51c5-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="c51c5-176">संवर्धन को ताज़ा रिफ्रेश करें</span><span class="sxs-lookup"><span data-stu-id="c51c5-176">Refresh enrichment</span></span>

<span data-ttu-id="c51c5-177">ब्रांड, रुचियों और जनसांख्यिकी के लिए फ़ील्ड मैपिंग कॉन्फ़िगर करने के बाद समृद्ध करना चालू करें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-177">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="c51c5-178">प्रक्रिया शुरू करने के लिए, ब्रांड या रुचि कॉन्फ़िगरेशन पृष्ठ पर **चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-178">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="c51c5-179">इसके अतिरिक्त, आप सिस्टम को शेड्यूल किए गए रीफ़्रेश के भाग के रूप में संवर्धन को स्वत: चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-179">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="c51c5-180">आपके ग्राहक डेटा के आकार के आधार पर, समृद्ध रन को पूरा होने में कई मिनट लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-180">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="c51c5-181">कार्यों/प्रक्रियाओं के लिए [छह प्रकार की स्थिति](system.md#status-types) हैं .</span><span class="sxs-lookup"><span data-stu-id="c51c5-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c51c5-182">इसके अतिरिक्त, अधिकांश प्रक्रियाएं [अन्य डाउनस्ट्रीम प्रक्रियाओं पर निर्भर करती हैं](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c51c5-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c51c5-183">आप पूरे कार्य की प्रगति पर विवरण देखने के लिए प्रक्रिया की स्थिति का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c51c5-184">किसी एक जॉब कार्य के लिए **विवरण देखें** को चुनने के बाद, आपको अतिरिक्त जानकारी मिलती है: संसाधन समय, अंतिम संसाधन दिनांक और कार्य से जुड़ी सभी त्रुटियां और चेतावनियाँ.</span><span class="sxs-lookup"><span data-stu-id="c51c5-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="c51c5-185">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="c51c5-185">Enrichment results</span></span>

<span data-ttu-id="c51c5-186">संवर्धन प्रक्रिया चलाने के बाद, समृद्ध ग्राहकों की कुल संख्या और समृद्ध ग्राहक प्रोफाइल में ब्रांड्स या रुचियों के विश्लेषण की समीक्षा करने के लिए **मेरे संवर्धन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-186">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="संवर्धन की प्रक्रिया चलाने के बाद परिणामों का पूर्वावलोकन":::

<span data-ttu-id="c51c5-188">चार्ट में **समृद्ध डेटा देखें** को चुनकर समृद्ध डेटा की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-188">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="c51c5-189">ब्रांड के लिए समृद्ध डेटा **BrandAffinityFromMicrosoft** निकाय में जाता है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-189">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="c51c5-190">रुचियों के लिए डेटा **InterestAffinityFromMicrosoft** निकाय में है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-190">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="c51c5-191">आपको ये निकाय **डेटा** > **निकाय** के **संवर्धन** समूह में भी सूचीबद्ध मिल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-191">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="c51c5-192">ग्राहक कार्ड पर संवर्द्धन डेटा देखें</span><span class="sxs-lookup"><span data-stu-id="c51c5-192">See enrichment data on the customer card</span></span>

<span data-ttu-id="c51c5-193">ब्रांड और रुचियो की एफ़िनिटी को व्यक्तिगत ग्राहक कार्ड पर देखा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-193">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="c51c5-194">**ग्राहकों** पर जाएँ और एक ग्राहक प्रोफ़ाइल का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="c51c5-194">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="c51c5-195">ग्राहक कार्ड में, आपको उन ब्रांड्स या रुचियों के लिए चार्ट मिलेंगे जिनके लिए उस ग्राहक की जनसांख्यिकीय प्रोफ़ाइल में लोगों से समानता है.</span><span class="sxs-lookup"><span data-stu-id="c51c5-195">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="संवर्धन डेटा वाला के साथ ग्राहक कार्ड":::

## <a name="next-steps"></a><span data-ttu-id="c51c5-197">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="c51c5-197">Next steps</span></span>

<span data-ttu-id="c51c5-198">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="c51c5-198">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c51c5-199">अपने ग्राहकों को व्यक्तिगत अनुभव डिलीवर करने के लिए [सेगमेंट](segments.md), [मापन](measures.md)बनाएं, और यहां तक कि [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c51c5-199">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]