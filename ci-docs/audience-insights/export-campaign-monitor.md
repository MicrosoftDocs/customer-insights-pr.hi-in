---
title: एक Campaign Monitor के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Campaign Monitor विज्ञापन प्रबंधक को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124183"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="e9604-103">सेगमेंट को Campaign Monitor (पूर्वावलोकन) में निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="e9604-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="e9604-104">Campaign Monitor के लिए एकीकृत ग्राहक प्रोफ़ाइल के निर्यात के अनुभाग और मार्केटिंग सें जुड़ी गतिविधियों के लिए उनका उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="e9604-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9604-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="e9604-105">Prerequisites</span></span>

-   <span data-ttu-id="e9604-106">आपके पास एक [Campaign Monitor खाता](https://www.campaignmonitor.com/) और संबंधित व्यवस्थापक क्रेडेंशियल्स.</span><span class="sxs-lookup"><span data-stu-id="e9604-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e9604-107">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="e9604-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e9604-108">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="e9604-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e9604-109">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="e9604-109">Known limitations</span></span>

- <span data-ttu-id="e9604-110">आप Campaign Monitor करने के लिए प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e9604-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="e9604-111">Campaign Monitor को निर्यात करना सेगमेंट तक ही सीमित है.</span><span class="sxs-lookup"><span data-stu-id="e9604-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="e9604-112">Campaign Monitor को 1 मिलियन प्रोफ़ाइल तक निर्यात पूरा करनें में 20 मिनट तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="e9604-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="e9604-113">प्रोफ़ाइल की संख्या है कि आप Campaign Monitor करने के लिए निर्यात कर सकते है निर्भर है और Campaign Monitor के साथ अपने अनुबंध पर सीमित है.</span><span class="sxs-lookup"><span data-stu-id="e9604-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="e9604-114">Campaign Monitor से कनेक्शन सेट करें</span><span class="sxs-lookup"><span data-stu-id="e9604-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="e9604-115">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="e9604-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e9604-116">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Campaign Monitor** चुनें.</span><span class="sxs-lookup"><span data-stu-id="e9604-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="e9604-117">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="e9604-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e9604-118">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="e9604-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e9604-119">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="e9604-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e9604-120">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="e9604-120">Choose who can use this connection.</span></span> <span data-ttu-id="e9604-121">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="e9604-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e9604-122">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e9604-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e9604-123">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="e9604-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e9604-124">Campaign Monitor से कनेक्शन शुरू करने के लिए **कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="e9604-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="e9604-125">**Campaign Monitor के साथ प्रमाणित** चुनें और Campaign Monitor के लिए अपने व्यवस्थापक क्रेडेंशियल्स प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="e9604-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="e9604-126">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="e9604-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e9604-127">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e9604-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e9604-128">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="e9604-128">Configure an export</span></span>

<span data-ttu-id="e9604-129">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e9604-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e9604-130">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e9604-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e9604-131">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="e9604-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e9604-132">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e9604-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e9604-133">**निर्यात के लिए कनेक्शन** में, Adobe Campaign Monitor से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e9604-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="e9604-134">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="e9604-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e9604-135">[**Campaign Monitor सूची ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="e9604-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="e9604-136">Campaign Monitor में **खाता सेटिंग** से पहले API सूची ID देखने के लिए [API कुंजी जेनरेट करें](https://www.campaignmonitor.com/api/getting-started/).</span><span class="sxs-lookup"><span data-stu-id="e9604-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="e9604-137">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="e9604-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e9604-138">Campaign Monitor करने के लिए सेगमेंट का निर्यात करना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="e9604-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="e9604-139">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="e9604-139">Select **Save**.</span></span>

<span data-ttu-id="e9604-140">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="e9604-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e9604-141">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="e9604-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e9604-142">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e9604-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e9604-143">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="e9604-143">Data privacy and compliance</span></span>

<span data-ttu-id="e9604-144">जब आप Dynamics 365 Customer Insights को Campaign Monitor में डेटा प्रसारित करने में सक्षम बनाते हैं, तो आप गतिशीलता Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="e9604-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e9604-145">Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि Campaign Monitor आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="e9604-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e9604-146">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="e9604-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e9604-147">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="e9604-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
