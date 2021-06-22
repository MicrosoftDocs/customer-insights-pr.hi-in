---
title: Customer Insights डेटा को Snapchat में निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Snapchat को निर्यात करने का तरीका जानें.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124045"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="21970-103">अनुभागों को Snapchat (पूर्वावलोकन) में निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="21970-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="21970-104">अभियान की निगरानी के लिए एकीकृत ग्राहक प्रोफ़ाइल के निर्यात के अनुभाग और मार्केटिंग सें जुड़ी गतिविधियों के लिए उनका उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="21970-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="21970-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="21970-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="21970-106">आपके पास एक [Snapchat व्यावसायिक अकाउंट](https://business.snapchat.com/) और [Snapchat Ads अकाउंट](https://ads.snapchat.com/) संबंधित व्यवस्थापक क्रेडेंशियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="21970-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="21970-107">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="21970-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="21970-108">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="21970-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="21970-109">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="21970-109">Known limitations</span></span>

- <span data-ttu-id="21970-110">Snapchat को निर्यात करना सेगमेंट तक ही सीमित है.</span><span class="sxs-lookup"><span data-stu-id="21970-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="21970-111">Snapchat को 1 मिलियन प्रोफ़ाइल तक निर्यात पूरा करनें में 15 मिनट तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="21970-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="21970-112">Snapchat में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="21970-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="21970-113">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="21970-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="21970-114">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Snapchat** चुनें.</span><span class="sxs-lookup"><span data-stu-id="21970-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="21970-115">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="21970-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="21970-116">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="21970-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="21970-117">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="21970-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="21970-118">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="21970-118">Choose who can use this connection.</span></span> <span data-ttu-id="21970-119">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="21970-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="21970-120">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="21970-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="21970-121">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="21970-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="21970-122">Snapchat से कनेक्शन शुरू करने के लिए **कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="21970-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="21970-123">**Snapchat के साथ प्रमाणित** चुनें और Snapchat के लिए अपने व्यवस्थापक क्रेडेंशियल्स प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="21970-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="21970-124">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="21970-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="21970-125">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="21970-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="21970-126">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="21970-126">Configure an export</span></span>

<span data-ttu-id="21970-127">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="21970-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="21970-128">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="21970-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="21970-129">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="21970-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="21970-130">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="21970-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="21970-131">**निर्यात के लिए कनेक्शन** में, Snapchat अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="21970-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="21970-132">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="21970-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="21970-133">[**Snapchat ऑडियंस ID**](https://businesshelp.snapchat.com/s/article/custom-audiences) दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="21970-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="21970-134">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="21970-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="21970-135">Snapchat करने के लिए सेगमेंट का निर्यात करना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="21970-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="21970-136">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="21970-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="21970-137">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="21970-137">Select **Save**.</span></span>

<span data-ttu-id="21970-138">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="21970-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="21970-139">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="21970-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="21970-140">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="21970-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="21970-141">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="21970-141">Data privacy and compliance</span></span>

<span data-ttu-id="21970-142">जब आप Dynamics 365 Customer Insights को अभियान मॉनिटर में डेटा प्रसारित करने में सक्षम बनाते हैं, तो आप गतिशीलता Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="21970-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="21970-143">Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि Snapchat आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="21970-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="21970-144">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="21970-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="21970-145">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="21970-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
