---
title: थर्ड पार्टी के एनरिचमेंट के साथ HERE Technologies का एनरिचमेंट
description: HERE Technologies थर्ड पार्टी के एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597743"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="1736c-103">HERE Technologies (पूर्वावलोकन) के साथ ग्राहक प्रोफाइल का एनरिचमेंट</span><span class="sxs-lookup"><span data-stu-id="1736c-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="1736c-104">HERE Technologies एक लोकेशन प्लेटफ़ॉर्म कंपनी है जो स्थान-केंद्रित डेटा और सेवाएं प्रदान करती है.</span><span class="sxs-lookup"><span data-stu-id="1736c-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="1736c-105">HERE टेक्नोलॉजीज की डेटा संवर्धन सेवाओं के साथ, आप अपने ग्राहकों के पते के सामान्यीकरण, अक्षांश और देशांतर निष्कर्षण आदि के साथ अधिक सटीक स्थान समझ बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1736c-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1736c-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="1736c-106">Prerequisites</span></span>

<span data-ttu-id="1736c-107">HERE Technologies के एनरिचमेंट को कॉन्फ़िगर करने के लिए, निम्नलिखित आवश्यकताओं को पूरा किया जाना चाहिए:</span><span class="sxs-lookup"><span data-stu-id="1736c-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="1736c-108">आपके पास एक सक्रिय HERE Technologies सदस्यता है.</span><span class="sxs-lookup"><span data-stu-id="1736c-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="1736c-109">सदस्यता प्राप्त करने के लिए, आप [यहां साइन-अप कर सकते हैं](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) या सीधे [HERE Technologies से संपर्क करें](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="1736c-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="1736c-110">HERE Technologies लोकेशन एनरिचमेंट के बारे में अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="1736c-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="1736c-111">आपके पास HERE Technologies API कुंजी है.</span><span class="sxs-lookup"><span data-stu-id="1736c-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="1736c-112">आपके पास [प्रशासक](permissions.md#administrator) की अनुमतियाँ है.</span><span class="sxs-lookup"><span data-stu-id="1736c-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="1736c-113">कॉन्फ़िगरेशन</span><span class="sxs-lookup"><span data-stu-id="1736c-113">Configuration</span></span>

1. <span data-ttu-id="1736c-114">**डेटा** > **संवर्धन** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="1736c-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="1736c-115">HERE Technologies टाइल पर **मेरे डेटा को समृद्ध करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1736c-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1736c-116">![HERE Technologies टाइल](media/HERE-tile.png "HERE Technologies टाइल")</span><span class="sxs-lookup"><span data-stu-id="1736c-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="1736c-117">एक सक्रिय **HERE Technologies API कुंजी** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="1736c-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="1736c-118">समीक्षा करें और **डेटा गोपनीयता और अनुपालन** के लिए **मैं सहमत हूं** चेकबॉक्स का चयन करके अपनी सहमति प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="1736c-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="1736c-119">**HERE से कनेक्ट करें** चुनकर दोनों इनपुट्स की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="1736c-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="1736c-120">**डेटा जोड़ें** का चयन करें और **ग्राहक डेटा सेट चुनें** जिनको आप HERE Technologies से स्थान डेटा के साथ समृद्ध करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="1736c-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="1736c-121">आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए **ग्राहक** निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1736c-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="ग्राहक डेटा सेट चुनते समय का स्क्रीनशॉट.":::

1. <span data-ttu-id="1736c-123">चुनें कि क्या आप फ़ील्ड को प्राथमिक और/या द्वितीयक पते पर मैप करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="1736c-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="1736c-124">आप दोनों पतों (उदाहरण के लिए, एक घर और एक व्यवसाय पता) के लिए एक फ़ील्ड मैपिंग निर्दिष्ट कर सकते हैं और दोनों पतों के लिए प्रोफाइल को अलग-अलग समृद्ध कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1736c-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="1736c-125">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1736c-125">Select **Next**.</span></span>

1. <span data-ttu-id="1736c-126">यह परिभाषित करें कि आपके एकीकृत प्रोफाइल से किन फ़ील्ड का उपयोग HERE Technologies से स्थान डेटा का मिलान करने के लिए किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="1736c-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="1736c-127">चयनित प्राइमरी और/या सेकेंडरी पते के लिए **स्ट्रीट 1** और **ज़िप/पोस्टल कोड** फ़ील्डों की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="1736c-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="1736c-128">एक उच्च मिलान सटीकता के लिए, अधिक फ़ील्डों को जोड़ा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="1736c-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1736c-129">![HERE Technologies एनरिचमेंट कॉन्फ़िगरेशन पेज](media/enrichment-HERE-configuration.png "HERE Technologies एनरिचमेंट कॉन्फिगरेशन पेज")</span><span class="sxs-lookup"><span data-stu-id="1736c-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="1736c-130">फ़ील्ड मैपिंग को पूरा करने के लिए **लागू** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1736c-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="1736c-131">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="1736c-131">Enrichment results</span></span>

<span data-ttu-id="1736c-132">संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1736c-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="1736c-133">आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1736c-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1736c-134">प्रोसेस करने का समय आपके ग्राहक डेटा के आकार और HERE Technologies से API प्रतिक्रिया समय पर निर्भर करेगा.</span><span class="sxs-lookup"><span data-stu-id="1736c-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="1736c-135">संवर्धन प्रक्रिया पूरी होने के बाद, आप **मेरे संवर्धन** के तहत नए समृद्ध ग्राहक प्रोफ़ाइल डेटा की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1736c-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="1736c-136">इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="1736c-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="1736c-137">आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1736c-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1736c-138">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="1736c-138">Next steps</span></span>

<span data-ttu-id="1736c-139">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="1736c-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="1736c-140">अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [सेगमेंट](segments.md), [मापन](measures.md)बनाएं, और यहां तक कि [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1736c-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1736c-141">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="1736c-141">Data privacy and compliance</span></span>

<span data-ttu-id="1736c-142">जब आप Dynamics 365 Customer Insights को HERE Technologies पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="1736c-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1736c-143">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि HERE Technologies आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="1736c-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1736c-144">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="1736c-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1736c-145">आपका Dynamics 365 Customer Insights प्रशासक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस एनरिचमेंट को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="1736c-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]