---
title: ActiveCampaign में Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और ActiveCampaign को निर्यात करने का तरीका जानें।
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314623"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="979a9-103">ActiveCampaign में अनुभाग निर्यात करें (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="979a9-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="979a9-104">एकीकृत ग्राहक प्रोफाइल के अनुभाग को ActiveCampaign में निर्यात करें और मार्केटिंग गतिविधियों के लिए उनका उपयोग करें।</span><span class="sxs-lookup"><span data-stu-id="979a9-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="979a9-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="979a9-105">Prerequisites</span></span>

-   <span data-ttu-id="979a9-106">आपके पास [ActiveCampaign खाता](https://www.activecampaign.com/) है और संबंधित व्यवस्थापक क्रेडेंशियल है।</span><span class="sxs-lookup"><span data-stu-id="979a9-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="979a9-107">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="979a9-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="979a9-108">निर्यात किए गए सेगमेंट में एकीकृत ग्राहक प्रोफ़ाइल में ईमेल पते वाली एक फ़ील्ड होती है.</span><span class="sxs-lookup"><span data-stu-id="979a9-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="979a9-109">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="979a9-109">Known limitations</span></span>

- <span data-ttu-id="979a9-110">आप ActiveCampaign को प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक निर्यात कर सकते हैं और इसे पूरा होने में 90 मिनट तक का समय लग सकता है।</span><span class="sxs-lookup"><span data-stu-id="979a9-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="979a9-111">ActiveCampaign में निर्यात करना अनुभागों तक सीमित है।</span><span class="sxs-lookup"><span data-stu-id="979a9-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="979a9-112">आपके द्वारा ActiveCampaign में निर्यात की जा सकने वाली प्रोफ़ाइलों की संख्या ActiveCampaign के साथ आपके अनुबंध पर निर्भर करती है।</span><span class="sxs-lookup"><span data-stu-id="979a9-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="979a9-113">ActiveCampaign में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="979a9-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="979a9-114">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="979a9-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="979a9-115">कनेक्शन को कॉन्फ़िगर करने के लिए **कनेक्शन जोड़ें** चुनें और **ActiveCampaign** चुनें.</span><span class="sxs-lookup"><span data-stu-id="979a9-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="979a9-116">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="979a9-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="979a9-117">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="979a9-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="979a9-118">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="979a9-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="979a9-119">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="979a9-119">Choose who can use this connection.</span></span> <span data-ttu-id="979a9-120">डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं.</span><span class="sxs-lookup"><span data-stu-id="979a9-120">By default, it's only administrators.</span></span> <span data-ttu-id="979a9-121">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="979a9-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="979a9-122">अपना [ActiveCampaign API कुंजी और REST समाप्ति बिंदु होस्टनेम](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) डालें.</span><span class="sxs-lookup"><span data-stu-id="979a9-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="979a9-123">REST समापन बिंदु होस्टनाम केवल https://के बिना, होस्टनाम है.</span><span class="sxs-lookup"><span data-stu-id="979a9-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="979a9-124">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="979a9-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="979a9-125">कनेक्शन को ActiveCampaign पर शुरु करने के लिए **कनेक्ट करें** का चयन करें।</span><span class="sxs-lookup"><span data-stu-id="979a9-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="979a9-126">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="979a9-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="979a9-127">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="979a9-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="979a9-128">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="979a9-128">Configure an export</span></span>

<span data-ttu-id="979a9-129">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप किसी निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="979a9-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="979a9-130">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="979a9-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="979a9-131">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="979a9-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="979a9-132">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="979a9-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="979a9-133">**निर्यात के लिए कनेक्शन** फ़ील्ड में, ActiveCampaign सेक्शन से एक कनेक्शन चुनें।</span><span class="sxs-lookup"><span data-stu-id="979a9-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="979a9-134">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="979a9-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="979a9-135">अपना [**ActiveCampaign सूची ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign) दर्ज करें।</span><span class="sxs-lookup"><span data-stu-id="979a9-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="979a9-136">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="979a9-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="979a9-137">ActiveCampaign में अनुभाग को निर्यात करने के लिए इसकी आवश्यकता है।</span><span class="sxs-lookup"><span data-stu-id="979a9-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="979a9-138">वैकल्पिक रूप से, आप अधिक वैयक्तिकृत ईमेल बनाने के लिए प्रथम नाम, अंतिम नाम, और फ़ोन निर्यात कर सकते हैं।</span><span class="sxs-lookup"><span data-stu-id="979a9-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="979a9-139">इन फ़ील्ड को मैप करने के लिए जोड़ें विशेषता चुनें.</span><span class="sxs-lookup"><span data-stu-id="979a9-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="979a9-140">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="979a9-140">Select **Save**.</span></span>

<span data-ttu-id="979a9-141">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="979a9-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="979a9-142">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="979a9-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="979a9-143">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="979a9-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="979a9-144">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="979a9-144">Data privacy and compliance</span></span>

<span data-ttu-id="979a9-145">जब आप ActiveCampaign पर डेटा संचारित करने के लिए Dynamics 365 Customer Insights सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं।</span><span class="sxs-lookup"><span data-stu-id="979a9-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="979a9-146">Microsoft आपके निर्देश पर ऐसा डेटा स्थानांतरित करेगा, लेकिन यह सुनिश्चित करने के लिए आप ज़िम्मेदार हैं कि ActiveCampaign किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है।</span><span class="sxs-lookup"><span data-stu-id="979a9-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="979a9-147">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="979a9-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="979a9-148">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="979a9-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
