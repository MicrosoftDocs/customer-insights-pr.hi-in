---
title: तृतीय-पक्ष संवर्धन Experian के साथ संवर्धन
description: Experian तीसरे पक्ष का संवर्धन के बारे में सामान्य जानकारी।
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309822"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="b706e-103">Experian से जनसांख्यिकी के साथ ग्राहक प्रोफाइल को बेहतर बनाएँ (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="b706e-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="b706e-104">Experian, उपभोक्ता और व्यापार क्रेडिट रिपोर्टिंग और विपणन सेवाओं में एक वैश्विक लीडर है।</span><span class="sxs-lookup"><span data-stu-id="b706e-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="b706e-105">Experian की डेटा संवर्धन सेवाओं के साथ, आप अपने ग्राहक प्रोफाइल को जनसांख्यिकीय डेटा जैसे घरेलू आकार, आय, और बहुत कुछ के साथ समृद्ध करके अपने ग्राहकों की गहरी समझ बना सकते हैं।</span><span class="sxs-lookup"><span data-stu-id="b706e-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b706e-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="b706e-106">Prerequisites</span></span>

<span data-ttu-id="b706e-107">Experian कॉन्फ़िगर करने के लिए, निम्न पूर्वापेक्षाएँ पूरी होनी चाहिए:</span><span class="sxs-lookup"><span data-stu-id="b706e-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b706e-108">आपके पास सक्रिय Experian सदस्यता है।</span><span class="sxs-lookup"><span data-stu-id="b706e-108">You have an active Experian subscription.</span></span> <span data-ttu-id="b706e-109">सदस्यता प्राप्त करने के लिए, सीधे [Experian](https://www.experian.com/marketing-services/contact) से संपर्क करें।</span><span class="sxs-lookup"><span data-stu-id="b706e-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="b706e-110">[Experian डेटा संवर्द्धन के बारे में अधिक जानें](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)।</span><span class="sxs-lookup"><span data-stu-id="b706e-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="b706e-111">एक Experian कनेक्शन पहले से ही एक व्यवस्थापक द्वारा कॉन्फ़िगर किया गया है *या* आपके पास [व्यवस्थापक](permissions.md#administrator) अनुमतियाँ हैं।</span><span class="sxs-lookup"><span data-stu-id="b706e-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="b706e-112">आपको अपने SSH-सक्षम सुरक्षित परिवहन (ST) खाते के लिए उपयोगकर्ता ID, पार्टी ID और मॉडल नंबर की भी आवश्यकता है जो कि Experian ने आपके लिए बनाया है।</span><span class="sxs-lookup"><span data-stu-id="b706e-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="b706e-113">समर्थित देश/क्षेत्र</span><span class="sxs-lookup"><span data-stu-id="b706e-113">Supported countries/regions</span></span>

<span data-ttu-id="b706e-114">वर्तमान में हम केवल युनाइटेड स्टेट्स में ग्राहक प्रोफाइल को समृद्ध करने का समर्थन करते हैं।</span><span class="sxs-lookup"><span data-stu-id="b706e-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="b706e-115">एनरिचमेंट को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="b706e-115">Configure the enrichment</span></span>

1. <span data-ttu-id="b706e-116">**डेटा** > **समृद्ध** पर जाएं और **खोजें** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b706e-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="b706e-117">Experian टाइल पर **मेरा डेटा बेहतर बनाएँ** चुनें।</span><span class="sxs-lookup"><span data-stu-id="b706e-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b706e-118">![Experian टाइल](media/experian-tile.png "Experian टाइल")</span><span class="sxs-lookup"><span data-stu-id="b706e-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="b706e-119">ड्राप-डाउन सूची से [कनेक्शन](connections.md) चुनें।</span><span class="sxs-lookup"><span data-stu-id="b706e-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="b706e-120">यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.</span><span class="sxs-lookup"><span data-stu-id="b706e-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="b706e-121">यदि आप एक व्यवस्थापक हैं, तो आप ड्रॉपडाउन सूची से **कनेक्शन जोड़ें** का चयन करके और Experian चुनकर एक कनेक्शन बना सकते हैं ।</span><span class="sxs-lookup"><span data-stu-id="b706e-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="b706e-122">कनेक्शन चयन की पुष्टि करने के लिए **Experian से कनेक्ट करें** का चयन करें।</span><span class="sxs-lookup"><span data-stu-id="b706e-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="b706e-123">**अगला** का चयन करें और उस **ग्राहक डेटा सेट** को चुनें जिसे आप Experian से जनसांख्यिकी डेटा के साथ समृद्ध करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="b706e-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="b706e-124">आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए **ग्राहक** निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b706e-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="ग्राहक डेटा सेट चुनते समय का स्क्रीनशॉट.":::

1. <span data-ttu-id="b706e-126">**अगला** चुनें और परिभाषित करें कि आपकी एकीकृत प्रोफ़ाइल से किस प्रकार के फ़ील्ड का उपयोग Experian से जनसांख्यिकीय डेटा से मेल खाने के लिए किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="b706e-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="b706e-127">कम से कम एक फ़ील्ड **नाम और पता**, **फ़ोन**, या **ईमेल** की ज़रूरत है.</span><span class="sxs-lookup"><span data-stu-id="b706e-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="b706e-128">एक उच्च मैच सटीकता के लिए, दो अन्य क्षेत्रों को जोड़ा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="b706e-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="b706e-129">यह चयन उन मैपिंग फ़ील्ड को प्रभावित करेगा जिनके पास अगले चरण का एक्सेस है.</span><span class="sxs-lookup"><span data-stu-id="b706e-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="b706e-130">Experian पर भेजी गईं अधिक प्रमुख पहचानकर्ता एट्रिब्यूट एक उच्च मिलान दर की संभावना है.</span><span class="sxs-lookup"><span data-stu-id="b706e-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="b706e-131">फील्ड मैपिंग शुरू करने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b706e-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="b706e-132">परिभाषित करें कि आपकी एकीकृत प्रोफ़ाइल से किन फ़ील्ड का उपयोग Experian से जनसांख्यिकीय डेटा से मेल खाने के लिए किया जाना चाहिए।</span><span class="sxs-lookup"><span data-stu-id="b706e-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="b706e-133">आवश्यक क्षेत्र चिह्नित किए गए हैं.</span><span class="sxs-lookup"><span data-stu-id="b706e-133">Required fields are marked.</span></span>

1. <span data-ttu-id="b706e-134">संवर्धन के लिए एक नाम और आउटपुट निकाय के लिए एक नाम प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="b706e-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="b706e-135">अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b706e-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="b706e-136">Experian के लिए कनेक्शन कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="b706e-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="b706e-137">आपको कनेक्शन को कॉन्फ़िगर करने के लिए एक व्यवस्थापक होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="b706e-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="b706e-138">एक संवर्धन को कॉन्फ़िगर करते समय **कनेक्शन जोड़ें** चुनें *या* **व्यवस्थापक** > **कनेक्शन** पर जाएँ और Experian टाइल पर **सेट अप** चुनें।</span><span class="sxs-lookup"><span data-stu-id="b706e-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="b706e-139">**आरंभ करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b706e-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="b706e-140">**डिस्प्ले नाम** बॉक्स में कनेक्शन के लिए एक नाम दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="b706e-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="b706e-141">अपने Experian सुरक्षित परिवहन खाता के लिए मान्य उपयोगकर्ता ID, पार्टी ID और मॉडल नंबर दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="b706e-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="b706e-142">**मैं सहमत हूं** चयन करके **डेटा गोपनीयता और अनुपालन** की समीक्षा करें और इसके लिए अपनी सहमति प्रदान करें।</span><span class="sxs-lookup"><span data-stu-id="b706e-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="b706e-143">कॉन्फ़िगरेशन को मान्य करने के लिए **सत्यापित** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b706e-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="b706e-144">सत्यापन पूरा करने के बाद, **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b706e-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experianकनेक्शन कॉन्फिगरेशन फलक.":::

## <a name="enrichment-results"></a><span data-ttu-id="b706e-146">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="b706e-146">Enrichment results</span></span>

<span data-ttu-id="b706e-147">संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b706e-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b706e-148">आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b706e-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b706e-149">प्रसंस्करण समय आपके ग्राहक डेटा के आकार और Experian द्वारा आपके खाते के लिए स्थापित की गई संवर्धन प्रक्रियाओं पर निर्भर करेगा।</span><span class="sxs-lookup"><span data-stu-id="b706e-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="b706e-150">संवर्धन प्रक्रिया पूरी होने के बाद, आप **मेरे संवर्धन** के तहत नए समृद्ध ग्राहक प्रोफ़ाइल डेटा की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b706e-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="b706e-151">इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="b706e-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b706e-152">आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b706e-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b706e-153">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="b706e-153">Next steps</span></span>

<span data-ttu-id="b706e-154">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="b706e-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b706e-155">[खंडों](segments.md) को बनाएं और [साधानों](measures.md) और यहां तक कि अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b706e-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b706e-156">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="b706e-156">Data privacy and compliance</span></span>

<span data-ttu-id="b706e-157">जब आप Experian पर डेटा संचारित करने के लिए Dynamics 365 Customer Insights सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं।</span><span class="sxs-lookup"><span data-stu-id="b706e-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b706e-158">Microsoft आपके निर्देश पर ऐसा डेटा स्थानांतरित करेगा, लेकिन यह सुनिश्चित करने के लिए आप ज़िम्मेदार हैं कि Experian किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है।</span><span class="sxs-lookup"><span data-stu-id="b706e-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b706e-159">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="b706e-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b706e-160">आपका Dynamics 365 Customer Insights व्यवस्थापक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस संवर्धन को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="b706e-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
