---
title: तीसरे पक्ष के एनरिचमेंट Experian के साथ एनरिचमेंट
description: Experian थर्ड पार्टी एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896375"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="8e339-103">Experian (पूर्वावलोकन) से जनसांख्यिकीय के साथ ग्राहक प्रोफाइल को समृद्ध करें</span><span class="sxs-lookup"><span data-stu-id="8e339-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="8e339-104">Experian उपभोक्ता और बिज़नेस क्रेडिट रिपोर्टिंग और मार्केटिंग सेवाओं में ग्लोबल लीडर है.</span><span class="sxs-lookup"><span data-stu-id="8e339-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="8e339-105">Experian की डेटा संवर्धन सेवाओं के साथ, आप अपने ग्राहक प्रोफ़ाइल को घरेलू आकार, आय इत्यादि जैसे जनसांख्यिकीय डेटा के साथ समृद्ध करके अपने ग्राहकों के बारे में गहराई से समझ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8e339-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8e339-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="8e339-106">Prerequisites</span></span>

<span data-ttu-id="8e339-107">Experian को कॉन्फ़िगर करने के लिए, निम्न पूर्वापेक्षाएँ पूरी होनी चाहिए:</span><span class="sxs-lookup"><span data-stu-id="8e339-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8e339-108">आपके पास एक सक्रिय Experian सदस्यता है.</span><span class="sxs-lookup"><span data-stu-id="8e339-108">You have an active Experian subscription.</span></span> <span data-ttu-id="8e339-109">सदस्यता पाने के लिए, सीधे [Experian से संपर्क करें](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="8e339-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="8e339-110">[Experian डेटा संवर्द्धन के बारे में अधिक जानें](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="8e339-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="8e339-111">एक एक्सपीरियन कनेक्शन पहले से ही एक व्यवस्थापक द्वारा कॉन्फ़िगर किया गया है *या* आपके पास [व्यवस्थापक](permissions.md#administrator) अनुमतियां हैं.</span><span class="sxs-lookup"><span data-stu-id="8e339-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="8e339-112">आपको अपने SSH-सक्षम सुरक्षित ट्रांसपोर्ट (ST) खाते के लिए उपयोगकर्ता ID, पार्टी ID और मॉडल नंबर की भी आवश्यकता है जो आपके लिए बनाया गया था.</span><span class="sxs-lookup"><span data-stu-id="8e339-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="8e339-113">एनरिचमेंट को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="8e339-113">Configure the enrichment</span></span>

1. <span data-ttu-id="8e339-114">**डेटा** > **समृद्ध** पर जाएं और **खोजें** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="8e339-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="8e339-115">Experian टाइल पर **मेरे डेटा को समृद्ध करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="8e339-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e339-116">![Experian टाइल](media/experian-tile.png "Experian टाइल")</span><span class="sxs-lookup"><span data-stu-id="8e339-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="8e339-117">ड्राप-डाउन से एक [कनेक्शन](connections.md) चुनें.</span><span class="sxs-lookup"><span data-stu-id="8e339-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="8e339-118">यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.</span><span class="sxs-lookup"><span data-stu-id="8e339-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="8e339-119">यदि आप एक व्यवस्थापक हैं, तो आप **कनेक्शन जोड़ें** का चयन करके और ड्रॉप-डाउन से एक्सपीरियन चुनकर कनेक्शन बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8e339-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="8e339-120">कनेक्शन के चयन की पुष्टि करने के लिए **एक्सपीरियन से कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8e339-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="8e339-121">**अगला** चुनें और उन **ग्राहक डेटा सेट** का चयन करें जिसे आप एक्सपीरियन के जनसांख्यिकी डेटा के साथ समृद्ध करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="8e339-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="8e339-122">आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए **ग्राहक** निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8e339-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="ग्राहक डेटा सेट चुनते समय का स्क्रीनशॉट.":::

1. <span data-ttu-id="8e339-124">**अगला** चुनें और निर्धारित करें कि एक्सपीरियन से जनसांख्यिकी डेटा का मिलान करने के लिए आपके एकीकृत प्रोफ़ाइल से किस प्रकार के फ़ील्ड का उपयोग किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="8e339-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="8e339-125">कम से कम एक फ़ील्ड **नाम और पता**, **फ़ोन**, या **ईमेल** की ज़रूरत है.</span><span class="sxs-lookup"><span data-stu-id="8e339-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="8e339-126">एक उच्च मैच सटीकता के लिए, दो अन्य क्षेत्रों को जोड़ा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="8e339-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="8e339-127">यह चयन उन मैपिंग फ़ील्ड को प्रभावित करेगा जिनके पास अगले चरण का एक्सेस है.</span><span class="sxs-lookup"><span data-stu-id="8e339-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="8e339-128">Experian को अधिक भेजे गए महत्वपूर्ण पहचानकर्ता एट्रिब्यूट से अधिक उच्च मिलान दर प्राप्त करने की संभावना होती है.</span><span class="sxs-lookup"><span data-stu-id="8e339-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="8e339-129">फील्ड मैपिंग शुरू करने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8e339-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="8e339-130">निर्धारित करें कि आपके एकीकृत प्रोफ़ाइल से किन फ़ील्ड का उपयोग एक्सपीरियन से जनसांख्यिकी डेटा के मिलान के लिए किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="8e339-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="8e339-131">आवश्यक क्षेत्र चिह्नित किए गए हैं.</span><span class="sxs-lookup"><span data-stu-id="8e339-131">Required fields are marked.</span></span>

1. <span data-ttu-id="8e339-132">संवर्धन के लिए एक नाम और आउटपुट निकाय के लिए एक नाम प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="8e339-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="8e339-133">अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8e339-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="8e339-134">एक्सपीरियन के लिए कनेक्शन को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="8e339-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="8e339-135">आपको कनेक्शन को कॉन्फ़िगर करने के लिए एक व्यवस्थापक होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="8e339-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="8e339-136">किसी संवर्धन को कॉन्फ़िगर करते समय **कनेक्शन जोड़ें** का चयन करें *या* **व्यवस्थापक** > **कनेक्शन** पर जाएं और एक्सपीरियन टाइल पर **सेट करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="8e339-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="8e339-137">**आरंभ करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8e339-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="8e339-138">**डिस्प्ले नाम** बॉक्स में कनेक्शन के लिए एक नाम दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="8e339-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="8e339-139">अपने एक्सपीरियन सुरक्षित ट्रांसपोर्ट खाते के लिए वैध उपयोगकर्ता ID, पार्टी ID और मॉडल नंबर डालें.</span><span class="sxs-lookup"><span data-stu-id="8e339-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="8e339-140">समीक्षा करें और **डेटा गोपनीयता और अनुपालन** के लिए **मैं सहमत हूं** चेकबॉक्स का चयन करके अपनी सहमति प्रदान करें</span><span class="sxs-lookup"><span data-stu-id="8e339-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="8e339-141">कॉन्फ़िगरेशन को मान्य करने के लिए **सत्यापित** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8e339-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="8e339-142">सत्यापन पूरा करने के बाद, **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8e339-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="एक्सपीरियन कनेक्शन कॉन्फ़िगरेशन फलक.":::

## <a name="enrichment-results"></a><span data-ttu-id="8e339-144">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="8e339-144">Enrichment results</span></span>

<span data-ttu-id="8e339-145">संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="8e339-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8e339-146">आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8e339-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8e339-147">संसाधन का समय आपके ग्राहक डेटा के आकार और Experian द्वारा आपके खाते के लिए स्थापित संवर्धन प्रक्रियाओं पर निर्भर करेगा.</span><span class="sxs-lookup"><span data-stu-id="8e339-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="8e339-148">संवर्धन प्रक्रिया पूरी होने के बाद, आप **मेरे संवर्धन** के तहत नए समृद्ध ग्राहक प्रोफ़ाइल डेटा की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8e339-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8e339-149">इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="8e339-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8e339-150">आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8e339-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8e339-151">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="8e339-151">Next steps</span></span>

<span data-ttu-id="8e339-152">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="8e339-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8e339-153">अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [सेगमेंट](segments.md), [मापन](measures.md)बनाएं, और यहां तक कि [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8e339-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8e339-154">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="8e339-154">Data privacy and compliance</span></span>

<span data-ttu-id="8e339-155">जब आप Dynamics 365 Customer Insights को Experian को डेटा प्रसारित करने में सक्षम बनाते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="8e339-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8e339-156">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि एक्सपीरियन आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="8e339-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8e339-157">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="8e339-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8e339-158">आपका Dynamics 365 Customer Insights प्रशासक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस एनरिचमेंट को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="8e339-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
