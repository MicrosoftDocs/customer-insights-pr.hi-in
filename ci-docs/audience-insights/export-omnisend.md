---
title: Customer Insights डेटा को Omnisend में निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Omnisend में निर्यात करने का तरीका जानें.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124499"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="1de57-103">Omnisend में अनुभाग निर्यात करें (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="1de57-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="1de57-104">Omnisend में एकीकृत ग्राहक प्रोफ़ाइल के अनुभाग निर्यात करें और मार्केटिंग सें जुड़ी गतिविधियों के लिए उनका उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="1de57-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1de57-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="1de57-105">Prerequisites</span></span>

-   <span data-ttu-id="1de57-106">आपके पास एक [Omnisend खाता](https://www.omnisend.com/) और संबंधित व्यवस्थापक क्रेडेंशियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="1de57-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1de57-107">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="1de57-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1de57-108">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="1de57-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1de57-109">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="1de57-109">Known limitations</span></span>

- <span data-ttu-id="1de57-110">आप Omnisend को प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक निर्यात कर सकते हैं और इसे पूरा होने में 4 घंटे तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="1de57-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="1de57-111">Omnisend को निर्यात करना सेगमेंट तक ही सीमित है.</span><span class="sxs-lookup"><span data-stu-id="1de57-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="1de57-112">आप Omnisend को कितने प्रोफ़ाइल निर्यात कर सकते हैं, वह Omnisend के साथ आपके अनुबंध पर निर्भर करता है.</span><span class="sxs-lookup"><span data-stu-id="1de57-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="1de57-113">Omnisend में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="1de57-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="1de57-114">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="1de57-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1de57-115">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Omnisend** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1de57-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="1de57-116">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="1de57-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1de57-117">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="1de57-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1de57-118">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="1de57-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1de57-119">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="1de57-119">Choose who can use this connection.</span></span> <span data-ttu-id="1de57-120">डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं.</span><span class="sxs-lookup"><span data-stu-id="1de57-120">By default it's only administrators.</span></span> <span data-ttu-id="1de57-121">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1de57-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1de57-122">अपनी [Omnisend API कुंजी](https://support.omnisend.com/en/articles/1061890-generating-api-key) दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="1de57-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="1de57-123">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1de57-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1de57-124">Omnisend से कनेक्शन शुरू करने के लिए **कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1de57-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="1de57-125">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="1de57-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1de57-126">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1de57-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1de57-127">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="1de57-127">Configure an export</span></span>

<span data-ttu-id="1de57-128">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1de57-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1de57-129">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1de57-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1de57-130">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="1de57-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1de57-131">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1de57-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1de57-132">**निर्यात के लिए कनेक्शन** फ़ील्ड में, Omnisend सेक्शन से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1de57-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="1de57-133">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="1de57-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1de57-134">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="1de57-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1de57-135">Omnisend करने के लिए अनुभाग का निर्यात करना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="1de57-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="1de57-136">वैकल्पिक रूप से, आप अधिक व्यक्तिगत ईमेल बनाने के लिए प्रथम नाम, अंतिम नाम, पता, देश/प्रांत, शहर, राज्य, और पोस्ट कोड निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1de57-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="1de57-137">इन फ़ील्ड को मैप करने के लिए **जोड़ें विशेषता** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1de57-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1de57-138">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1de57-138">Select **Save**.</span></span>

<span data-ttu-id="1de57-139">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="1de57-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1de57-140">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="1de57-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1de57-141">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1de57-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1de57-142">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="1de57-142">Data privacy and compliance</span></span>

<span data-ttu-id="1de57-143">जब आप Dynamics 365 Customer Insights को Ommisend में डेटा प्रसारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के ट्रांसफ़र की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="1de57-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1de57-144">Microsoft आपके निर्देश पर ऐसे डेटा को ट्रांसफ़र करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि Omnisend आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="1de57-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1de57-145">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="1de57-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1de57-146">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="1de57-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
