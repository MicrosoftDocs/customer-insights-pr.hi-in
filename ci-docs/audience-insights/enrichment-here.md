---
title: थर्ड पार्टी के एनरिचमेंट के साथ HERE Technologies का एनरिचमेंट
description: HERE Technologies थर्ड पार्टी के एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896053"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="ea5ec-103">HERE Technologies (पूर्वावलोकन) के साथ ग्राहक प्रोफाइल का एनरिचमेंट</span><span class="sxs-lookup"><span data-stu-id="ea5ec-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="ea5ec-104">HERE Technologies एक लोकेशन प्लेटफ़ॉर्म कंपनी है जो स्थान-केंद्रित डेटा और सेवाएं प्रदान करती है.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="ea5ec-105">HERE टेक्नोलॉजीज की डेटा संवर्धन सेवाओं के साथ, आप अपने ग्राहकों के पते के सामान्यीकरण, अक्षांश और देशांतर निष्कर्षण आदि के साथ अधिक सटीक स्थान समझ बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ea5ec-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="ea5ec-106">Prerequisites</span></span>

<span data-ttu-id="ea5ec-107">HERE Technologies के एनरिचमेंट को कॉन्फ़िगर करने के लिए, निम्नलिखित आवश्यकताओं को पूरा किया जाना चाहिए:</span><span class="sxs-lookup"><span data-stu-id="ea5ec-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ea5ec-108">आपके पास एक सक्रिय HERE Technologies सदस्यता है.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="ea5ec-109">सदस्यता प्राप्त करने के लिए, आप [यहां साइन-अप कर सकते हैं](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) या सीधे [HERE Technologies से संपर्क करें](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="ea5ec-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="ea5ec-110">HERE Technologies लोकेशन एनरिचमेंट के बारे में अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="ea5ec-111">यहां HERE [कनेक्शन](connections.md) उपलब्ध है *या* आपके पास [व्यवस्थापक](permissions.md#administrator) की अनुमतियां और HERE Technologies की API कुंजी है.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="ea5ec-112">एनरिचमेंट को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="ea5ec-112">Configure the enrichment</span></span>

1. <span data-ttu-id="ea5ec-113">**डेटा** > **संवर्धन** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="ea5ec-114">HERE Technologies टाइल पर **मेरे डेटा को समृद्ध करें** और **शुरू करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ea5ec-115">![HERE Technologies टाइल](media/HERE-tile.png "HERE Technologies टाइल")</span><span class="sxs-lookup"><span data-stu-id="ea5ec-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="ea5ec-116">ड्राप-डाउन से एक [कनेक्शन](connections.md) चुनें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="ea5ec-117">यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="ea5ec-118">यदि आप एक व्यवस्थापक हैं, तो आप **कनेक्शन जोड़ें** का चयन करके एक कनेक्शन बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="ea5ec-119">ड्रॉप-डाउन से **HERE Technologies** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="ea5ec-120">चयन की पुष्टि करने के लिए **HERE Technologies से कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="ea5ec-121">**अगला** चुनें और उन **ग्राहक डेटा सेट** का चयन करें जिसे आप HERE Technologies के लोकेशन डेटा के साथ समृद्ध करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="ea5ec-122">आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए **ग्राहक** निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="ग्राहक डेटा सेट चुनते समय का स्क्रीनशॉट.":::

1. <span data-ttu-id="ea5ec-124">चुनें कि क्या आप फ़ील्ड को प्राथमिक और/या द्वितीयक पते पर मैप करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="ea5ec-125">आप दोनों पतों के लिए एक फ़ील्ड मैपिंग निर्दिष्ट कर सकते हैं और दोनों पतों के लिए प्रोफ़ाइल को अलग-अलग समृद्ध कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="ea5ec-126">उदाहरण के लिए, यदि कोई घर और व्यवसाय का पता हो.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="ea5ec-127">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-127">Select **Next**.</span></span>

1. <span data-ttu-id="ea5ec-128">यह परिभाषित करें कि आपके एकीकृत प्रोफाइल से किन फ़ील्ड का उपयोग HERE Technologies से स्थान डेटा का मिलान करने के लिए किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="ea5ec-129">चयनित प्राइमरी और/या सेकेंडरी पते के लिए **स्ट्रीट 1** और **ज़िप/पोस्टल कोड** फ़ील्डों की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="ea5ec-130">एक उच्च मिलान सटीकता के लिए, अधिक फ़ील्डों को जोड़ा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ea5ec-131">![HERE Technologies एनरिचमेंट कॉन्फ़िगरेशन पेज](media/enrichment-HERE-configuration.png "HERE Technologies एनरिचमेंट कॉन्फिगरेशन पेज")</span><span class="sxs-lookup"><span data-stu-id="ea5ec-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="ea5ec-132">फील्ड मैपिंग को पूरा करने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="ea5ec-133">संवर्धन के लिए एक नाम प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="ea5ec-134">1.अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="ea5ec-135">HERE Technologies के लिए कनेक्शन कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="ea5ec-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="ea5ec-136">आपको कनेक्शन को कॉन्फ़िगर करने के लिए एक व्यवस्थापक होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="ea5ec-137">किसी संवर्धन को कॉन्फ़िगर करते समय **कनेक्शन जोड़ें** का चयन करें *या* **व्यवस्थापक** > **कनेक्शन** पर जाएं और HERE Technologies टाइल पर **सेट करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="ea5ec-138">**डिस्प्ले नाम** बॉक्स में कनेक्शन के लिए एक नाम दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="ea5ec-139">एक वैध HERE Technologies API कुंजी प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="ea5ec-140">समीक्षा करें और **डेटा गोपनीयता और अनुपालन** के लिए **मैं सहमत हूं** चेकबॉक्स का चयन करके अपनी सहमति प्रदान करें</span><span class="sxs-lookup"><span data-stu-id="ea5ec-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="ea5ec-141">कॉन्फ़िगरेशन को मान्य करने के लिए **सत्यापित** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="ea5ec-142">सत्यापन पूरा करने के बाद, **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="ea5ec-143">![HERE Technologies कनेक्शन कॉन्फ़िगरेशन पेज](media/enrichment-HERE-connection.png "HERE Technologies कनेक्शन कॉन्फ़िगरेशन पेज")</span><span class="sxs-lookup"><span data-stu-id="ea5ec-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ea5ec-144">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="ea5ec-144">Enrichment results</span></span>

<span data-ttu-id="ea5ec-145">संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ea5ec-146">आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ea5ec-147">प्रोसेस करने का समय आपके ग्राहक डेटा के आकार और HERE Technologies से API प्रतिक्रिया समय पर निर्भर करेगा.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="ea5ec-148">संवर्धन प्रक्रिया पूरी होने के बाद, आप **मेरे संवर्धन** के तहत नए समृद्ध ग्राहक प्रोफ़ाइल डेटा की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ea5ec-149">इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ea5ec-150">आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ea5ec-151">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="ea5ec-151">Next steps</span></span>

<span data-ttu-id="ea5ec-152">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ea5ec-153">अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [सेगमेंट](segments.md), [मापन](measures.md)बनाएं, और यहां तक कि [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ea5ec-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ea5ec-154">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="ea5ec-154">Data privacy and compliance</span></span>

<span data-ttu-id="ea5ec-155">जब आप Dynamics 365 Customer Insights को HERE Technologies पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ea5ec-156">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि HERE Technologies आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ea5ec-157">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ea5ec-158">आपका Dynamics 365 Customer Insights प्रशासक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस एनरिचमेंट को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="ea5ec-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
