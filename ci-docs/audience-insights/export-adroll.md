---
title: Customer Insights डेटा को AdRoll में निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और AdRoll को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895961"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="bb32f-103">सेगमेंट सूचियां को AdRoll (पूर्वावलोकन) में निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="bb32f-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="bb32f-104">एकीकृत ग्राहक प्रोफ़ाइल के सेगमेंट AdRoll पर निर्यात करें और विज्ञापन के लिए उनका उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="bb32f-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="bb32f-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="bb32f-106">आपके पास [AdRoll अकाउंट](https://www.adroll.com/) और संबंधित एडमिनिस्ट्रेटर के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="bb32f-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bb32f-107">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bb32f-108">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bb32f-109">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="bb32f-109">Known limitations</span></span>

- <span data-ttu-id="bb32f-110">आप प्रति निर्यात में 250'000 प्रोफ़ाइल AdRoll पर निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="bb32f-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="bb32f-111">आप 100 से कम प्रोफ़ाइल वाले सेगमेंट AdRoll पर निर्यात नहीं कर सकते.</span><span class="sxs-lookup"><span data-stu-id="bb32f-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="bb32f-112">AdRoll पर निर्यात करना सेगमेंट पर सीमित है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="bb32f-113">250'000 प्रोफ़ाइल को AdRoll पर निर्यात करने में 10 मिनट तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="bb32f-114">आपके द्वारा AdRoll पर निर्यात की जा सकने वाली प्रोफ़ाइल की संख्या AdRoll के साथ आपके अनुबंध पर निर्भर है और सीमित है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="bb32f-115">AdRoll में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="bb32f-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="bb32f-116">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="bb32f-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bb32f-117">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **AdRoll** चुनें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="bb32f-118">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bb32f-119">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bb32f-120">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="bb32f-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bb32f-121">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-121">Choose who can use this connection.</span></span> <span data-ttu-id="bb32f-122">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="bb32f-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bb32f-123">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bb32f-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bb32f-124">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bb32f-125">AdRoll से कनेक्शन को शुरू करने के लिए **जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="bb32f-126">**AdRoll के साथ प्रमाणीकरण** चुनें और AdRoll के लिए अपने एडमिन क्रेडेंशियल्स प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="bb32f-127">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="bb32f-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bb32f-128">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bb32f-129">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="bb32f-129">Configure an export</span></span>

<span data-ttu-id="bb32f-130">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="bb32f-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bb32f-131">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bb32f-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bb32f-132">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="bb32f-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bb32f-133">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bb32f-134">**निर्यात के लिए कनेक्शन** में, AdRoll अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="bb32f-135">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bb32f-136">अधिक जानकारी के लिए अपनी **AdRoll विज्ञापनदाता ID** दर्ज करें, देखें [AdRoll विज्ञापनदाता प्रोफ़ाइल](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="bb32f-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="bb32f-137">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="bb32f-138">सेगमेंट को AdRoll पर निर्यात करना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="bb32f-139">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="bb32f-139">Select the segments you want to export.</span></span> <span data-ttu-id="bb32f-140">कम से कम 100 सदस्यों वाले सेगमेंट का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="bb32f-141">आप छोटे सेगमेंट को निर्यात नहीं कर सकते.</span><span class="sxs-lookup"><span data-stu-id="bb32f-141">You can't export smaller segments.</span></span> <span data-ttu-id="bb32f-142">इसके अतिरिक्त निर्यात किए जाने वाले एक सेगमेंट का अधिकतम आकार 250'000 सदस्य प्रति निर्यात है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="bb32f-143">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-143">Select **Save**.</span></span>

<span data-ttu-id="bb32f-144">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bb32f-145">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bb32f-146">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="bb32f-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bb32f-147">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="bb32f-147">Data privacy and compliance</span></span>

<span data-ttu-id="bb32f-148">जब आप AdRoll पर डेटा ट्रांसमिट करने के लिए Dynamics 365 Customer Insights सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा ट्रांसफर करने देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे कि व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="bb32f-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bb32f-149">Microsoft आपके निर्देश पर ऐसे डेटा को ट्रांसफर कर देगा, लेकिन आप यह सुनिश्चित करने के लिए ज़िम्मेदार हैं कि AdRoll आपके किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bb32f-150">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="bb32f-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="bb32f-151">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="bb32f-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
