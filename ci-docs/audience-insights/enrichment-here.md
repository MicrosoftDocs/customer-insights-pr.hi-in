---
title: तृतीय-पक्ष संवर्धन HERE Technologies के साथ संवर्धन
description: HERE Technologies थर्ड पार्टी के एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305296"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="8d87f-103">HERE Technologies (पूर्वावलोकन) के साथ ग्राहक प्रोफाइल का एनरिचमेंट</span><span class="sxs-lookup"><span data-stu-id="8d87f-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="8d87f-104">HERE Technologies एक लोकेशन प्लेटफ़ॉर्म कंपनी है जो स्थान-केंद्रित डेटा और सेवाएं प्रदान करती है.</span><span class="sxs-lookup"><span data-stu-id="8d87f-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="8d87f-105">HERE टेक्नोलॉजीज की डेटा संवर्धन सेवाओं के साथ, आप अपने ग्राहकों के पते के सामान्यीकरण, अक्षांश और देशांतर निष्कर्षण आदि के साथ अधिक सटीक स्थान समझ बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8d87f-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d87f-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="8d87f-106">Prerequisites</span></span>

<span data-ttu-id="8d87f-107">HERE Technologies के एनरिचमेंट को कॉन्फ़िगर करने के लिए, निम्नलिखित आवश्यकताओं को पूरा किया जाना चाहिए:</span><span class="sxs-lookup"><span data-stu-id="8d87f-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8d87f-108">आपके पास एक सक्रिय HERE Technologies सदस्यता है.</span><span class="sxs-lookup"><span data-stu-id="8d87f-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="8d87f-109">सदस्यता प्राप्त करने के लिए, आप [यहां साइन-अप](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) या सीधे [HERE Technologies से संपर्क](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) कर सकते हैं।</span><span class="sxs-lookup"><span data-stu-id="8d87f-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="8d87f-110">HERE Technologies लोकेशन एनरिचमेंट के बारे में अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="8d87f-111">HERE [कनेक्शन](connections.md) उपलब्ध है *या* आपके पास [व्यवस्थापक](permissions.md#administrator) अनुमतियाँ और HERE Technologies API कुंजी हैं।</span><span class="sxs-lookup"><span data-stu-id="8d87f-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="8d87f-112">एनरिचमेंट को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="8d87f-112">Configure the enrichment</span></span>

1. <span data-ttu-id="8d87f-113">**डेटा** > **संवर्धन** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="8d87f-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="8d87f-114">HERE Technologies टाइल पर **मेरे डेटा को समृद्ध करें** और **शुरू करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d87f-115">![HERE Technologies टाइल](media/HERE-tile.png "HERE Technologies टाइल")</span><span class="sxs-lookup"><span data-stu-id="8d87f-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="8d87f-116">ड्राप-डाउन सूची से [कनेक्शन](connections.md) चुनें।</span><span class="sxs-lookup"><span data-stu-id="8d87f-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="8d87f-117">यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="8d87f-118">यदि आप एक व्यवस्थापक हैं, तो आप **कनेक्शन जोड़ें** का चयन करके एक कनेक्शन बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8d87f-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="8d87f-119">ड्रॉपडाउन सूची से **HERE Technologies** चुनें।</span><span class="sxs-lookup"><span data-stu-id="8d87f-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="8d87f-120">चयन की पुष्टि करने के लिए **HERE Technologies से कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="8d87f-121">**अगला** चुनें और उन **ग्राहक डेटा सेट** का चयन करें जिसे आप HERE Technologies के लोकेशन डेटा के साथ समृद्ध करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="8d87f-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="8d87f-122">आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए **ग्राहक** निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8d87f-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="ग्राहक डेटा सेट चुनते समय का स्क्रीनशॉट.":::

1. <span data-ttu-id="8d87f-124">चुनें कि क्या आप फ़ील्ड को प्राथमिक और/या द्वितीयक पते पर मैप करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="8d87f-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="8d87f-125">आप दोनों पतों के लिए एक फ़ील्ड मैपिंग निर्दिष्ट कर सकते हैं और दोनों पतों के लिए प्रोफ़ाइल को अलग-अलग समृद्ध कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8d87f-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="8d87f-126">उदाहरण के लिए, यदि कोई घर और व्यवसाय का पता हो.</span><span class="sxs-lookup"><span data-stu-id="8d87f-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="8d87f-127">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-127">Select **Next**.</span></span>

1. <span data-ttu-id="8d87f-128">यह परिभाषित करें कि आपके एकीकृत प्रोफाइल से किन फ़ील्ड का उपयोग HERE Technologies से स्थान डेटा का मिलान करने के लिए किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="8d87f-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="8d87f-129">चयनित प्राइमरी और/या सेकेंडरी पते के लिए **स्ट्रीट 1** और **ज़िप/पोस्टल कोड** फ़ील्डों की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="8d87f-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="8d87f-130">एक उच्च मिलान सटीकता के लिए, अधिक फ़ील्डों को जोड़ा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="8d87f-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d87f-131">![HERE Technologies एनरिचमेंट कॉन्फ़िगरेशन पेज](media/enrichment-HERE-configuration.png "HERE Technologies एनरिचमेंट कॉन्फिगरेशन पेज")</span><span class="sxs-lookup"><span data-stu-id="8d87f-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="8d87f-132">फील्ड मैपिंग को पूरा करने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="8d87f-133">संवर्धन के लिए एक नाम प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="8d87f-134">अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="8d87f-135">HERE Technologies के लिए कनेक्शन कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="8d87f-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="8d87f-136">आपको कनेक्शन को कॉन्फ़िगर करने के लिए एक व्यवस्थापक होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="8d87f-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="8d87f-137">किसी संवर्धन को कॉन्फ़िगर करते समय **कनेक्शन जोड़ें** का चयन करें *या* **व्यवस्थापक** > **कनेक्शन** पर जाएं और HERE Technologies टाइल पर **सेट करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="8d87f-138">**डिस्प्ले नाम** बॉक्स में कनेक्शन के लिए एक नाम दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="8d87f-139">एक वैध HERE Technologies API कुंजी प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="8d87f-140">**मैं सहमत हूं** चयन करके **डेटा गोपनीयता और अनुपालन** की समीक्षा करें और इसके लिए अपनी सहमति प्रदान करें।</span><span class="sxs-lookup"><span data-stu-id="8d87f-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="8d87f-141">कॉन्फ़िगरेशन को मान्य करने के लिए **सत्यापित** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="8d87f-142">सत्यापन पूरा करने के बाद, **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d87f-143">![HERE Technologies कनेक्शन कॉन्फ़िगरेशन पेज](media/enrichment-HERE-connection.png "HERE Technologies कनेक्शन कॉन्फ़िगरेशन पेज")</span><span class="sxs-lookup"><span data-stu-id="8d87f-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="8d87f-144">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="8d87f-144">Enrichment results</span></span>

<span data-ttu-id="8d87f-145">संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8d87f-146">आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8d87f-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8d87f-147">प्रोसेस करने का समय आपके ग्राहक डेटा के आकार और HERE Technologies से API प्रतिक्रिया समय पर निर्भर करेगा.</span><span class="sxs-lookup"><span data-stu-id="8d87f-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="8d87f-148">संवर्धन प्रक्रिया पूरी होने के बाद, आप **मेरे संवर्धन** के तहत नए समृद्ध ग्राहक प्रोफ़ाइल डेटा की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8d87f-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8d87f-149">इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="8d87f-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8d87f-150">आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8d87f-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8d87f-151">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="8d87f-151">Next steps</span></span>

<span data-ttu-id="8d87f-152">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="8d87f-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8d87f-153">[खंडों](segments.md) को बनाएं और [साधानों](measures.md) और यहां तक कि अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8d87f-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8d87f-154">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="8d87f-154">Data privacy and compliance</span></span>

<span data-ttu-id="8d87f-155">जब आप Dynamics 365 Customer Insights को HERE Technologies पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="8d87f-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8d87f-156">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि HERE Technologies आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="8d87f-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8d87f-157">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="8d87f-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8d87f-158">आपका Dynamics 365 Customer Insights व्यवस्थापक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस संवर्धन को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="8d87f-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
