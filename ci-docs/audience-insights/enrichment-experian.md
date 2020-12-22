---
title: तीसरे पक्ष के एनरिचमेंट Experian के साथ एनरिचमेंट
description: Experian थर्ड पार्टी एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668814"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="892fc-103">Experian (पूर्वावलोकन) से जनसांख्यिकीय के साथ ग्राहक प्रोफाइल को समृद्ध करें</span><span class="sxs-lookup"><span data-stu-id="892fc-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="892fc-104">Experian उपभोक्ता और बिज़नेस क्रेडिट रिपोर्टिंग और मार्केटिंग सेवाओं में ग्लोबल लीडर है.</span><span class="sxs-lookup"><span data-stu-id="892fc-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="892fc-105">Experian की डेटा संवर्धन सेवाओं के साथ, आप अपने ग्राहक प्रोफ़ाइल को घरेलू आकार, आय इत्यादि जैसे जनसांख्यिकीय डेटा के साथ समृद्ध करके अपने ग्राहकों के बारे में गहराई से समझ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="892fc-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="892fc-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="892fc-106">Prerequisites</span></span>

<span data-ttu-id="892fc-107">Experian को कॉन्फ़िगर करने के लिए, निम्न पूर्वापेक्षाएँ पूरी होनी चाहिए:</span><span class="sxs-lookup"><span data-stu-id="892fc-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="892fc-108">आपके पास एक सक्रिय Experian सदस्यता है.</span><span class="sxs-lookup"><span data-stu-id="892fc-108">You have an active Experian subscription.</span></span> <span data-ttu-id="892fc-109">सदस्यता पाने के लिए, सीधे [Experian से संपर्क करें](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="892fc-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="892fc-110">[Experian डेटा संवर्द्धन के बारे में अधिक जानें](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="892fc-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="892fc-111">आपके पास अपने SSH-सक्षम सुरक्षित ट्रांसपोर्ट (ST) खाते के लिए उपयोगकर्ता ID, पार्टी ID और मॉडल नंबर है जो Experian द्वारा आपके लिए बनाया गया है.</span><span class="sxs-lookup"><span data-stu-id="892fc-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="892fc-112">आपके पास ऑडियंस इनसाइट्स में [प्रशासक](permissions.md#administrator) अनुमतियां हैं.</span><span class="sxs-lookup"><span data-stu-id="892fc-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="892fc-113">कॉन्फ़िगरेशन</span><span class="sxs-lookup"><span data-stu-id="892fc-113">Configuration</span></span>

1. <span data-ttu-id="892fc-114">**डेटा** > **समृद्ध** पर जाएं और **खोजें** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="892fc-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="892fc-115">Experian टाइल पर **मेरे डेटा को समृद्ध करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="892fc-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="892fc-116">![Experian टाइल](media/experian-tile.png "Experian टाइल")</span><span class="sxs-lookup"><span data-stu-id="892fc-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="892fc-117">**शुरू करें** का चयन करें और अपने Experian सुरक्षा ट्रांस्पोर्ट खाते के लिए उपयोगकर्ता ID, पार्टी ID और मॉडल नंबर दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="892fc-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="892fc-118">समीक्षा करें और **डेटा गोपनीयता और अनुपालन** के लिए **मैं सहमत हूं** चेकबॉक्स का चयन करके अपनी सहमति प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="892fc-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="892fc-119">**लागू करें** का चयन करके सभी इनपुट की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="892fc-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="892fc-120">अपने फ़ील्ड का मानचित्र बनाएं</span><span class="sxs-lookup"><span data-stu-id="892fc-120">Map your fields</span></span>

1. <span data-ttu-id="892fc-121">**डेटा जोड़ें** का चयन करें और पहचान समाधान के लिए Experian को भेजने के लिए **नाम और पता**, **ईमेल**, या **फ़ोन** से अपने प्रमुख पहचानकर्ताओं को चुनें.</span><span class="sxs-lookup"><span data-stu-id="892fc-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="892fc-122">Experian को अधिक भेजे गए महत्वपूर्ण पहचानकर्ता एट्रिब्यूट से अधिक उच्च मिलान दर प्राप्त करने की संभावना होती है.</span><span class="sxs-lookup"><span data-stu-id="892fc-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="892fc-123">**अगला** चुनें और चयनित प्रमुख पहचानकर्ता फ़ील्ड के लिए अपने एकीकृत ग्राहक निकाय से संबंधित एट्रिब्यूट को मैप करें.</span><span class="sxs-lookup"><span data-stu-id="892fc-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="892fc-124">जो अतिरिक्त एट्रिब्यूट आप Experian पर भेजना चाहते हैं, उन्हें मैप करने के लिए **एट्रिब्यूट जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="892fc-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="892fc-125">फ़ील्ड मैपिंग को पूरा करने के लिए **सहेजें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="892fc-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="892fc-126">![Experian फ़ील्ड मैपिंग](media/experian-field-mapping.png "Experian फ़ील्ड मैपिंग")</span><span class="sxs-lookup"><span data-stu-id="892fc-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="892fc-127">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="892fc-127">Enrichment results</span></span>

<span data-ttu-id="892fc-128">संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="892fc-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="892fc-129">आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="892fc-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="892fc-130">संसाधन का समय आपके ग्राहक डेटा के आकार और Experian द्वारा आपके खाते के लिए स्थापित संवर्धन प्रक्रियाओं पर निर्भर करेगा.</span><span class="sxs-lookup"><span data-stu-id="892fc-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="892fc-131">संवर्धन प्रक्रिया पूरी होने के बाद, आप **मेरे संवर्धन** के तहत नए समृद्ध ग्राहक प्रोफ़ाइल डेटा की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="892fc-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="892fc-132">इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="892fc-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="892fc-133">आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="892fc-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="892fc-134">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="892fc-134">Next steps</span></span>

<span data-ttu-id="892fc-135">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="892fc-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="892fc-136">अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [सेगमेंट](segments.md), [मापन](measures.md)बनाएं, और यहां तक कि [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="892fc-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="892fc-137">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="892fc-137">Data privacy and compliance</span></span>

<span data-ttu-id="892fc-138">जब आप Dynamics 365 Customer Insights को Experian को डेटा प्रसारित करने में सक्षम बनाते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="892fc-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="892fc-139">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि एक्सपीरियन आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="892fc-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="892fc-140">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="892fc-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="892fc-141">आपका Dynamics 365 Customer Insights प्रशासक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस एनरिचमेंट को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="892fc-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
