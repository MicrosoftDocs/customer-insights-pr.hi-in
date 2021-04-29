---
title: Autopilot के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Autopilot को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760145"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="21e77-103">Autopilot को निर्यात खंड (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="21e77-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="21e77-104">एकीकृत ग्राहक प्रोफ़ाइल के सेगमेंट Autopilot में निर्यात करें और उन्हें Autopilot में ईमेल मार्केटिंग के लिए उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="21e77-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="21e77-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="21e77-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="21e77-106">आपके पास [Autopilot खाता](https://www.autopilothq.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="21e77-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="21e77-107">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="21e77-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="21e77-108">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="21e77-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="21e77-109">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="21e77-109">Known limitations</span></span>

- <span data-ttu-id="21e77-110">आप Autopilot में कुल 100'000 प्रोफ़ाइल तक निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="21e77-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="21e77-111">Autopilot को निर्यात करना सेगमेंटों तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="21e77-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="21e77-112">Autopilot को 100'000 प्रोफ़ाइल तक निर्यात करने में कुछ घंटे लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="21e77-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="21e77-113">Autopilot को निर्यात किए जा रहे प्रोफ़ाइल की संख्या Autopilot के साथ आपके अनुबंध पर निर्भर और सीमित है.</span><span class="sxs-lookup"><span data-stu-id="21e77-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="21e77-114">Autopilot में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="21e77-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="21e77-115">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="21e77-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="21e77-116">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Autopilot** चुनें.</span><span class="sxs-lookup"><span data-stu-id="21e77-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="21e77-117">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="21e77-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="21e77-118">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="21e77-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="21e77-119">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="21e77-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="21e77-120">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="21e77-120">Choose who can use this connection.</span></span> <span data-ttu-id="21e77-121">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="21e77-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="21e77-122">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="21e77-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="21e77-123">अपनी [ऑटोपायलट API कुंजी](https://autopilot.docs.apiary.io/#) दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="21e77-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="21e77-124">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="21e77-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="21e77-125">Autopilot से कनेक्शन को शुरू करने के लिए **जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="21e77-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="21e77-126">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="21e77-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="21e77-127">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="21e77-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="21e77-128">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="21e77-128">Configure an export</span></span>

<span data-ttu-id="21e77-129">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="21e77-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="21e77-130">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="21e77-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="21e77-131">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="21e77-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="21e77-132">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="21e77-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="21e77-133">**निर्यात के लिए कनेक्शन** में, Autopilot अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="21e77-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="21e77-134">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="21e77-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="21e77-135">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="21e77-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="21e77-136">अन्य वैकल्पिक फ़ील्ड जैसे **प्रथम नाम**, **अंतिम नाम** के लिए इन्हीं चरणों को दोहराएं.</span><span class="sxs-lookup"><span data-stu-id="21e77-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="21e77-137">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="21e77-137">Select the segments you want to export.</span></span> <span data-ttu-id="21e77-138">हम दृढ़ता से Autopilot में **कुल 100'000 से अधिक ग्राहक प्रोफ़ाइल निर्यात नहीं करने की सलाह देते हैं**.</span><span class="sxs-lookup"><span data-stu-id="21e77-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="21e77-139">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="21e77-139">Select **Save**.</span></span>

<span data-ttu-id="21e77-140">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="21e77-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="21e77-141">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="21e77-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="21e77-142">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="21e77-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="21e77-143">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="21e77-143">Data privacy and compliance</span></span>

<span data-ttu-id="21e77-144">जब आप Dynamics 365 Customer Insights को Autopilot पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="21e77-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="21e77-145">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Autopilot आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="21e77-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="21e77-146">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="21e77-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="21e77-147">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="21e77-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
