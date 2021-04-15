---
title: थर्ड पार्टी एनरिचमेंट Leadspace के साथ कंपनी प्रोफाइल का एनरिचमेंट
description: Leadspace थर्ड पार्टी एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597651"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="3c0e1-103">Leadspace के साथ कंपनी प्रोफाइल का समृद्धि (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="3c0e1-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="3c0e1-104">Leadspace एक डेटा विज्ञान कंपनी है जो B2B ग्राहक डेटा प्लेटफ़ॉर्म प्रदान करती है।</span><span class="sxs-lookup"><span data-stu-id="3c0e1-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="3c0e1-105">यह कंपनियों के लिए एकीकृत ग्राहक प्रोफाइल के साथ ग्राहकों को उनके डेटा को समृद्ध करने में सक्षम बनाता है.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="3c0e1-106">एनरिचमेंट में कंपनी के आकार, स्थान, उद्योग आदि जैसे अतिरिक्त विशेषताएं शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3c0e1-107">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="3c0e1-107">Prerequisites</span></span>

<span data-ttu-id="3c0e1-108">Leadspace को कॉन्फ़िगर करने के लिए, निम्नलिखित आवश्यक शर्तें पूरी की जानी चाहिए:</span><span class="sxs-lookup"><span data-stu-id="3c0e1-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3c0e1-109">आपके पास एक सक्रिय Leadspace लाइसेंस और "परपेचुअल कुंजी" (**Leadspace टोकन** के रूप में संदर्भित) है.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="3c0e1-110">[Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) के उत्पाद के बारे में जानकारी के लिए, सीधे उनसे संपर्क करें.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="3c0e1-111">आपके पास [प्रशासक](permissions.md#administrator) की अनुमतियाँ है.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="3c0e1-112">आपके पास कंपनियों के लिए [एकीकृत ग्राहक प्रोफ़ाइलों](customer-profiles.md) है.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="3c0e1-113">कॉन्फ़िगरेशन</span><span class="sxs-lookup"><span data-stu-id="3c0e1-113">Configuration</span></span>

1. <span data-ttu-id="3c0e1-114">ऑडियंस इनसाइट्स में, **डेटा** > **संवर्द्धन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="3c0e1-115">Leadspace टाइल पर **मेरे डेटा बेहतर बनाएँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace टाइल का स्क्रीनशॉट.":::

1. <span data-ttu-id="3c0e1-117">**शुरू करें** चुनें और फिर एक सक्रिय **Leadspace टोकन** (परपेचुअल कुंजी) दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="3c0e1-118">समीक्षा करें और **डेटा गोपनीयता और अनुपालन** के लिए **मैं सहमत हूं** चेकबॉक्स का चयन करके अपनी सहमति प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="3c0e1-119">**Leadspace से कनेक्ट करें** चुनकर दोनों इनपुट्स की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="3c0e1-120">**डेटा मैप करें** चुनें और उस डेटा सेट का चयन करें जिसे आप Leadspace से कंपनी के डेटा के साथ बेहतर बनाना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="3c0e1-121">आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए *ग्राहक* निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="ग्राहक प्रोफ़ाइल और अनुभाग संवर्धन के बीच चयन करें.":::

1. <span data-ttu-id="3c0e1-123">**अगला** पर क्लिक करें और परिभाषित करें कि आपके एकीकृत प्रोफ़ाइल से कौन से फ़ील्ड का उपयोग Leadspace से कंपनी डेटा मिलान के लिए किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="3c0e1-124">**कंपनी का नाम** फ़ील्ड की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-124">The **Name of company** field is required.</span></span> <span data-ttu-id="3c0e1-125">एक उच्च मिलान सटीकता के लिए, दो अन्य फ़ील्डों तक, **कंपनी की वेबसाइट** और **कंपनी का स्थान**, जोड़ा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace फील्ड मैपिंग फलक.":::
   
1. <span data-ttu-id="3c0e1-127">फ़ील्ड मैपिंग को पूरा करने के लिए **लागू** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="3c0e1-128">कंपनी प्रोफाइल को समृद्ध करने के लिए **रन** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="3c0e1-129">एक एनरिचमेंट कितना समय लेता है एकीकृत ग्राहक प्रोफाइल की संख्या पर निर्भर करता है.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="3c0e1-130">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="3c0e1-130">Enrichment results</span></span>

<span data-ttu-id="3c0e1-131">संवर्धन को रिफ्रेश करने के बाद, आप [मेरे संवर्धन](enrichment-hub.md) के तहत नया संवर्धित कंपनी डेटा की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="3c0e1-132">आप अंतिम अपडेट का समय और समृद्ध प्रोफाइल की संख्या पा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3c0e1-133">आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="3c0e1-134">अधिक जानकारी के लिए, [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API) देखें.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3c0e1-135">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="3c0e1-135">Next steps</span></span>

<span data-ttu-id="3c0e1-136">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3c0e1-137">अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [सेगमेंट](segments.md), [मापन](measures.md)बनाएं, और यहां तक कि [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3c0e1-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3c0e1-138">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="3c0e1-138">Data privacy and compliance</span></span>

<span data-ttu-id="3c0e1-139">जब आप Dynamics 365 Customer Insights को Leadspace पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3c0e1-140">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Leadspace आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3c0e1-141">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3c0e1-142">आपका Dynamics 365 Customer Insights प्रशासक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस एनरिचमेंट को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]