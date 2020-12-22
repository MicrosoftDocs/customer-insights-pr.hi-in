---
title: DotDigital को Customer Insights डेटा निर्यात करें
description: DotDigital के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644450"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="b8e28-103">DotDigital के लिए संबंधक (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="b8e28-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="b8e28-104">एकीकृत ग्राहक प्रोफाइल के निर्यात सेगमेंट DotDigital पता पुस्तकों के लिए और उन्हें अभियानों, ईमेल विपणन के लिए उपयोग करते हैं, और DotDigital के साथ ग्राहक वाले सेगमेंटों का निर्माण करने के लिए.</span><span class="sxs-lookup"><span data-stu-id="b8e28-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b8e28-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="b8e28-105">Prerequisites</span></span>

-   <span data-ttu-id="b8e28-106">आपके पास [DotDigital खाता](https://dotdigital.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="b8e28-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b8e28-107">DotDigital और संबंधित AD में मौजूदा पते की किताबें हैं.</span><span class="sxs-lookup"><span data-stu-id="b8e28-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="b8e28-108">पता बुक सिलने और खोलने पर ID यूआरएल में मिल सकती है.</span><span class="sxs-lookup"><span data-stu-id="b8e28-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="b8e28-109">अधिक जानकारी के लिए देखें [DotDigital पता किताबें](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="b8e28-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="b8e28-110">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="b8e28-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b8e28-111">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="b8e28-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="b8e28-112">DotDigital से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="b8e28-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="b8e28-113">**व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="b8e28-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b8e28-114">**DotDigital** के तहत, **सेट अप** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b8e28-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="b8e28-115">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="b8e28-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital निर्यात के लिए कॉन्फ़िगरेशन फलक.":::

1. <span data-ttu-id="b8e28-117">अपना **DotDigital उपयोगकर्ता नाम और पासवर्ड** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="b8e28-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="b8e28-118">अपने **[DotDigital पता पुस्तक ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** दर्ज करें .</span><span class="sxs-lookup"><span data-stu-id="b8e28-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="b8e28-119">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b8e28-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b8e28-120">DotDigital के लिए कनेक्शन शुरू करने के लिए **कनेक्ट** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b8e28-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="b8e28-121">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="b8e28-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b8e28-122">निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b8e28-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b8e28-123">कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="b8e28-123">Configure the connector</span></span>

1. <span data-ttu-id="b8e28-124">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="b8e28-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b8e28-125">अन्य वैकल्पिक फ़ील्ड जैसे **फर्स्ट नाम**, **अंतिम नाम**, **पूरा नाम**, **लिंग**, और **पोस्ट कोड** के लिए भी यही कदम दोहराएं.</span><span class="sxs-lookup"><span data-stu-id="b8e28-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="b8e28-126">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="b8e28-126">Select the segments you want to export.</span></span> <span data-ttu-id="b8e28-127">आप कुल मिलाकर 1 मिलियन ग्राहक प्रोफाइल को DotDigital में निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b8e28-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="b8e28-128">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b8e28-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b8e28-129">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="b8e28-129">Export the data</span></span>

<span data-ttu-id="b8e28-130">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b8e28-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b8e28-131">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b8e28-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b8e28-132">DotDigital में, अब आप [DotDigital पता किताबें](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) में अपने खंडों पा सकते हैं .</span><span class="sxs-lookup"><span data-stu-id="b8e28-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b8e28-133">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="b8e28-133">Known limitations</span></span>

- <span data-ttu-id="b8e28-134">DotDigital को प्रति निर्यात 1 मिलियन प्रोफाइल तक.</span><span class="sxs-lookup"><span data-stu-id="b8e28-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="b8e28-135">DotDigital को निर्यात करना खंडों तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="b8e28-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="b8e28-136">प्रदाता पक्ष पर सीमाओं के कारण कुल 1 मिलियन प्रोफाइल वाले निर्यात खंडों में 3 घंटे तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="b8e28-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="b8e28-137">DotDigital को निर्यात किए जा रहे प्रोफाइल की संख्या DotDigital के साथ आपके अनुबंध पर निर्भर और सीमित है.</span><span class="sxs-lookup"><span data-stu-id="b8e28-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b8e28-138">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="b8e28-138">Data privacy and compliance</span></span>

<span data-ttu-id="b8e28-139">जब आप Dynamics 365 Customer Insights को DotDigital में डेटा संचारित करने में सक्षम बनाते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="b8e28-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b8e28-140">Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि DotDigital आपके किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करे.</span><span class="sxs-lookup"><span data-stu-id="b8e28-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b8e28-141">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="b8e28-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b8e28-142">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="b8e28-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
