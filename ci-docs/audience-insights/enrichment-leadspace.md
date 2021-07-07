---
title: थर्ड पार्टी एनरिचमेंट Leadspace के साथ कंपनी प्रोफाइल का एनरिचमेंट
description: Leadspace थर्ड पार्टी एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305204"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="86b4e-103">Leadspace के साथ कंपनी प्रोफाइल का समृद्धि (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="86b4e-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="86b4e-104">Leadspace एक डेटा विज्ञान कंपनी है जो B2B ग्राहक डेटा प्लेटफ़ॉर्म प्रदान करती है।</span><span class="sxs-lookup"><span data-stu-id="86b4e-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="86b4e-105">यह कंपनियों के लिए एकीकृत ग्राहक प्रोफाइल के साथ ग्राहकों को उनके डेटा को समृद्ध करने में सक्षम बनाता है.</span><span class="sxs-lookup"><span data-stu-id="86b4e-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="86b4e-106">संवर्धन में कंपनी के आकार, स्थान, उद्योग और बहुत कुछ जैसे अधिक विशेषताएं शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="86b4e-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86b4e-107">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="86b4e-107">Prerequisites</span></span>

<span data-ttu-id="86b4e-108">Leadspace को कॉन्फ़िगर करने के लिए, निम्नलिखित आवश्यक शर्तें पूरी की जानी चाहिए:</span><span class="sxs-lookup"><span data-stu-id="86b4e-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="86b4e-109">आपके पास एक सक्रिय लीडस्पेस लाइसेंस है.</span><span class="sxs-lookup"><span data-stu-id="86b4e-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="86b4e-110">आपके पास कंपनियों के लिए [एकीकृत ग्राहक प्रोफ़ाइलों](customer-profiles.md) है.</span><span class="sxs-lookup"><span data-stu-id="86b4e-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="86b4e-111">एक लीडस्पेस कनेक्शन को पहले ही किसी व्यवस्थापक द्वारा कॉन्फ़िगर किया जा चुका है या आपके पास [व्यवस्थापक](permissions.md#administrator) अनुमतियां और "सतत कुंजी" (जिसे **लीडस्पेस टोकन**) कहा जाता है है.</span><span class="sxs-lookup"><span data-stu-id="86b4e-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="86b4e-112">अपने प्रोडक्ट के बारे में विवरण के लिए [लीडस्पेस](https://www.leadspace.com/products/leadspace-on-demand/) से सीधे संपर्क करें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="86b4e-113">एनरिचमेंट को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="86b4e-113">Configure the enrichment</span></span>

1. <span data-ttu-id="86b4e-114">ऑडियंस इनसाइट्स में, **डेटा** > **संवर्द्धन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="86b4e-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="86b4e-115">लीडस्पेस टाइल पर **मेरे डेटा को समृद्ध करें** को चुनें और **शुरू करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace टाइल का स्क्रीनशॉट.":::

1. <span data-ttu-id="86b4e-117">ड्राप-डाउन सूची से [कनेक्शन](connections.md) चुनें।</span><span class="sxs-lookup"><span data-stu-id="86b4e-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="86b4e-118">यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="86b4e-119">यदि आप एक व्यवस्थापक हैं, तो आप **कनेक्शन जोड़ें** का चयन करके और **लीडस्पेस** का चयन करके एक कनेक्शन बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="86b4e-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="86b4e-120">कनेक्शन की पुष्टि करने के लिए **लीडस्पेस से कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="86b4e-121">**अगला** चुनें और उस **ग्राहक डेटा सेट** को चुनें जिसे आप लीडस्पेस से कंपनी डेटा के साथ समृद्ध करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="86b4e-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="86b4e-122">आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए **ग्राहक** निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="86b4e-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="ग्राहक डेटा सेट चुनते समय का स्क्रीनशॉट.":::

1. <span data-ttu-id="86b4e-124">**अगला** चुनें और परिभाषित करें कि आपके एकीकृत प्रोफ़ाइल से किन फ़ील्ड का उपयोग लीडस्पेस से कंपनी डेटा का मिलान करने के लिए किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="86b4e-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="86b4e-125">**कंपनी का नाम** फ़ील्ड की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="86b4e-125">The **Name of company** field is required.</span></span> <span data-ttu-id="86b4e-126">एक उच्च मिलान सटीकता के लिए, दो अन्य फ़ील्डों तक, **कंपनी की वेबसाइट** और **कंपनी का स्थान**, जोड़ा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="86b4e-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace फील्ड मैपिंग फलक.":::

1. <span data-ttu-id="86b4e-128">फील्ड मैपिंग को पूरा करने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="86b4e-129">संवर्धन के लिए एक नाम प्रदान करें और अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="86b4e-130">Leadspace के लिए कनेक्शन को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="86b4e-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="86b4e-131">आपको कनेक्शन को कॉन्फ़िगर करने के लिए एक व्यवस्थापक होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="86b4e-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="86b4e-132">किसी संवर्धन को कॉन्फ़िगर करते समय **कनेक्शन जोड़ें** का चयन करें *या* **व्यवस्थापक** > **कनेक्शन** पर जाएं और Leadspace टाइल पर **सेट करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="86b4e-133">**आरंभ करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="86b4e-134">**डिस्प्ले नाम** बॉक्स में कनेक्शन के लिए एक नाम दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="86b4e-135">अपना Leadspace टोकन प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="86b4e-136">**मैं सहमत हूं** चयन करके **डेटा गोपनीयता और अनुपालन** की समीक्षा करें और इसके लिए अपनी सहमति प्रदान करें।</span><span class="sxs-lookup"><span data-stu-id="86b4e-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="86b4e-137">कॉन्फ़िगरेशन को मान्य करने के लिए **सत्यापित** चुनें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="86b4e-138">सत्यापन पूरा करने के बाद, **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace कनेक्शन कॉन्फ़िगरेशन पृष्ठ.":::

## <a name="enrichment-results"></a><span data-ttu-id="86b4e-140">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="86b4e-140">Enrichment results</span></span>

<span data-ttu-id="86b4e-141">संवर्धन को रिफ्रेश करने के बाद, आप [मेरे संवर्धन](enrichment-hub.md) के तहत नया संवर्धित कंपनी डेटा की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="86b4e-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="86b4e-142">आप अंतिम अपडेट का समय और समृद्ध प्रोफाइल की संख्या पा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="86b4e-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="86b4e-143">आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="86b4e-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="86b4e-144">अधिक जानकारी के लिए, [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API) देखें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="86b4e-145">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="86b4e-145">Next steps</span></span>

<span data-ttu-id="86b4e-146">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="86b4e-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="86b4e-147">[खंडों](segments.md) को बनाएं और [साधानों](measures.md) और यहां तक कि अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="86b4e-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="86b4e-148">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="86b4e-148">Data privacy and compliance</span></span>

<span data-ttu-id="86b4e-149">जब आप Dynamics 365 Customer Insights को Leadspace पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="86b4e-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="86b4e-150">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Leadspace आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="86b4e-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="86b4e-151">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="86b4e-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="86b4e-152">आपका Dynamics 365 Customer Insights व्यवस्थापक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस संवर्धन को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="86b4e-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
