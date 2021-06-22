---
title: Customer Insights डेटा को RollWorks में निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और RollWorks को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124091"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="29fa9-103">अनुभागों को RollWorks (पूर्वावलोकन) में निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="29fa9-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="29fa9-104">RollWorks को एकीकृत ग्राहक प्रोफ़ाइल के निर्यात सेगमेंट और विज्ञापन के लिए उनका उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="29fa9-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="29fa9-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="29fa9-106">आपके पास एक [RollWorks खाता](https://www.rollworks.com/) और संबंधित व्यवस्थापक क्रेडेंशियल्स.</span><span class="sxs-lookup"><span data-stu-id="29fa9-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="29fa9-107">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="29fa9-108">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="29fa9-109">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="29fa9-109">Known limitations</span></span>

- <span data-ttu-id="29fa9-110">आप RollWorks को प्रति निर्यात में 250'000 प्रोफ़ाइल तक निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="29fa9-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="29fa9-111">आप RollWorks के लिए 100 से कम प्रोफ़ाइल वाले सेगमेंट का निर्यात नहीं कर सकते.</span><span class="sxs-lookup"><span data-stu-id="29fa9-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="29fa9-112">RollWorks को निर्यात करना सेगमेंट तक ही सीमित है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="29fa9-113">RollWorks को 250'000 प्रोफ़ाइल तक निर्यात पूरा करनें में 10 मिनट तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="29fa9-114">प्रोफ़ाइल की संख्या है कि आप RollWorks करने के लिए निर्यात कर सकते है निर्भर है और RollWorks के साथ अपने अनुबंध पर सीमित है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="29fa9-115">RollWorks में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="29fa9-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="29fa9-116">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="29fa9-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="29fa9-117">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **RollWorks** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="29fa9-118">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="29fa9-119">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="29fa9-120">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="29fa9-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="29fa9-121">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-121">Choose who can use this connection.</span></span> <span data-ttu-id="29fa9-122">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="29fa9-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="29fa9-123">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="29fa9-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="29fa9-124">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="29fa9-125">RollWorks से कनेक्शन शुरू करने के लिए **कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="29fa9-126">**RollWorks के साथ प्रमाणित** चुनें और RollWorks के लिए अपने व्यवस्थापक क्रेडेंशियल्स प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="29fa9-127">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="29fa9-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="29fa9-128">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="29fa9-129">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="29fa9-129">Configure an export</span></span>

<span data-ttu-id="29fa9-130">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="29fa9-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="29fa9-131">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="29fa9-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="29fa9-132">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="29fa9-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="29fa9-133">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="29fa9-134">**निर्यात के लिए कनेक्शन** में, RollWorks अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="29fa9-135">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="29fa9-136">अपने **RollWorks विज्ञापनदाता ID** [RollWorks विज्ञापन](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles) को दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="29fa9-137">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="29fa9-138">RollWorks करने के लिए सेगमेंट का निर्यात करना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="29fa9-139">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="29fa9-139">Select the segments you want to export.</span></span> <span data-ttu-id="29fa9-140">कम से कम 100 सदस्यों वाले सेगमेंट का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="29fa9-141">आप छोटे सेगमेंट को निर्यात नहीं कर सकते.</span><span class="sxs-lookup"><span data-stu-id="29fa9-141">You can't export smaller segments.</span></span> <span data-ttu-id="29fa9-142">इसके अतिरिक्त निर्यात किए जाने वाले एक सेगमेंट का अधिकतम आकार 250'000 सदस्य प्रति निर्यात है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="29fa9-143">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-143">Select **Save**.</span></span>

<span data-ttu-id="29fa9-144">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="29fa9-145">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="29fa9-146">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="29fa9-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="29fa9-147">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="29fa9-147">Data privacy and compliance</span></span>

<span data-ttu-id="29fa9-148">जब आप Dynamics 365 Customer Insights को RollWorks में डेटा प्रसारित करने में सक्षम बनाते हैं, तो आप गतिशीलता Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="29fa9-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="29fa9-149">Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि RollWorks आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="29fa9-150">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="29fa9-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="29fa9-151">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="29fa9-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
