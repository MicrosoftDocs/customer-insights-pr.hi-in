---
title: Customer Insights डेटा को AdRoll में निर्यात करें
description: AdRoll में कनेक्शन कॉन्फ़िगर करना सीखें.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697076"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="5cfdb-103">AdRoll के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="5cfdb-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="5cfdb-104">एकीकृत ग्राहक प्रोफ़ाइल के सेगमेंट AdRoll पर निर्यात करें और विज्ञापन के लिए उनका उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5cfdb-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="5cfdb-105">Prerequisites</span></span>

-   <span data-ttu-id="5cfdb-106">आपके पास [AdRoll अकाउंट](https://www.adroll.com/) और संबंधित एडमिनिस्ट्रेटर के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5cfdb-107">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5cfdb-108">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="5cfdb-109">AdRoll से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="5cfdb-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="5cfdb-110">**व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5cfdb-111">**AdRoll** के अंतर्गत, **सेट अप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="5cfdb-112">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll कनेक्शन के लिए कॉन्फ़िगरेशन फलक.":::

1. <span data-ttu-id="5cfdb-114">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5cfdb-115">AdRoll से कनेक्शन को शुरू करने के लिए **जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="5cfdb-116">**AdRoll के साथ प्रमाणीकरण** चुनें और AdRoll के लिए अपने एडमिन क्रेडेंशियल्स प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="5cfdb-117">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="5cfdb-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5cfdb-118">अपनी **AdRoll विज्ञापनदाता ID** दर्ज करें [AdRoll विज्ञापन करने योग्य](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="5cfdb-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="5cfdb-119">निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="5cfdb-120">कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="5cfdb-120">Configure the connector</span></span>

1. <span data-ttu-id="5cfdb-121">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5cfdb-122">सेगमेंट को AdRoll पर निर्यात करना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="5cfdb-123">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-123">Select the segments you want to export.</span></span> <span data-ttu-id="5cfdb-124">कम से कम 100 सदस्यों वाले सेगमेंट का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="5cfdb-125">आप छोटे सेगमेंट को निर्यात नहीं कर सकते.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-125">You can't export smaller segments.</span></span> <span data-ttu-id="5cfdb-126">इसके अतिरिक्त निर्यात किए जाने वाले एक सेगमेंट का अधिकतम आकार 250'000 सदस्य प्रति निर्यात है.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="5cfdb-127">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5cfdb-128">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="5cfdb-128">Export the data</span></span>

<span data-ttu-id="5cfdb-129">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="5cfdb-130">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5cfdb-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5cfdb-131">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="5cfdb-131">Known limitations</span></span>

- <span data-ttu-id="5cfdb-132">आप प्रति निर्यात में 250'000 प्रोफ़ाइल AdRoll पर निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="5cfdb-133">आप 100 से कम प्रोफ़ाइल वाले सेगमेंट AdRoll पर निर्यात नहीं कर सकते.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="5cfdb-134">AdRoll पर निर्यात करना सेगमेंट पर सीमित है.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="5cfdb-135">250'000 प्रोफ़ाइल को AdRoll पर निर्यात करने में 10 मिनट तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="5cfdb-136">आपके द्वारा AdRoll पर निर्यात की जा सकने वाली प्रोफ़ाइल की संख्या AdRoll के साथ आपके अनुबंध पर निर्भर है और सीमित है.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5cfdb-137">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="5cfdb-137">Data privacy and compliance</span></span>

<span data-ttu-id="5cfdb-138">जब आप AdRoll पर डेटा ट्रांसमिट करने के लिए Dynamics 365 Customer Insights सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा ट्रांसफर करने देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे कि व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5cfdb-139">Microsoft आपके निर्देश पर ऐसे डेटा को ट्रांसफर कर देगा, लेकिन आप यह सुनिश्चित करने के लिए ज़िम्मेदार हैं कि AdRoll आपके किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5cfdb-140">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5cfdb-141">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="5cfdb-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
