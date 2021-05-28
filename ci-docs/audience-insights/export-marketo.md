---
title: Marketo के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Marketo को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059318"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="603dc-103">Marketo को निर्यात खंड (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="603dc-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="603dc-104">अभियान उत्पन्न करने, ईमेल मार्केटिंग प्रदान करने और Marketo के साथ ग्राहकों के विशिष्ट समूहों का उपयोग करने के लिए एकीकृत ग्राहक प्रोफाइल के निर्यात खंड.</span><span class="sxs-lookup"><span data-stu-id="603dc-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="603dc-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="603dc-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="603dc-106">आपके पास [Marketo खाता](https://login.marketo.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="603dc-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="603dc-107">Marketo और संबंधित ID में मौजूदा सूचियां हैं.</span><span class="sxs-lookup"><span data-stu-id="603dc-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="603dc-108">अधिक जानकारी के लिए, [Marketo सूचियां](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) देखें.</span><span class="sxs-lookup"><span data-stu-id="603dc-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="603dc-109">आपके पास [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="603dc-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="603dc-110">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="603dc-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="603dc-111">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="603dc-111">Known limitations</span></span>

- <span data-ttu-id="603dc-112">Marketo को प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक.</span><span class="sxs-lookup"><span data-stu-id="603dc-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="603dc-113">Marketo को निर्यात करना सेगमेंटों तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="603dc-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="603dc-114">कुल 1 मिलियन प्रोफाइल वाले निर्यात खंडों में 3 घंटे तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="603dc-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="603dc-115">Marketo को निर्यात किए जा रहे प्रोफ़ाइल की संख्या Marketo के साथ आपके अनुबंध पर निर्भर और सीमित है.</span><span class="sxs-lookup"><span data-stu-id="603dc-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="603dc-116">Marketo में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="603dc-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="603dc-117">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="603dc-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="603dc-118">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Marketo** चुनें.</span><span class="sxs-lookup"><span data-stu-id="603dc-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="603dc-119">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="603dc-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="603dc-120">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="603dc-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="603dc-121">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="603dc-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="603dc-122">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="603dc-122">Choose who can use this connection.</span></span> <span data-ttu-id="603dc-123">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="603dc-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="603dc-124">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="603dc-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="603dc-125">अपने **[Marketo क्लाइंट ID, क्लाइंट सीक्रेट और रेस्ट एंडपॉइंट होस्टनेम](https://developers.marketo.com/rest-api/authentication/)** दर्ज करें .</span><span class="sxs-lookup"><span data-stu-id="603dc-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="603dc-126">REST समापन बिंदु होस्टनाम केवल `https://`के बिना, होस्टनाम है.</span><span class="sxs-lookup"><span data-stu-id="603dc-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="603dc-127">उदाहरण: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="603dc-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="603dc-128">मैं **डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **सहमत हूं** चुनें और Marketo से कनेक्शन को शुरू करने के लिए **कनेक्ट** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="603dc-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="603dc-129">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="603dc-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="603dc-130">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="603dc-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="603dc-131">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="603dc-131">Configure an export</span></span>

<span data-ttu-id="603dc-132">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="603dc-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="603dc-133">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="603dc-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="603dc-134">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="603dc-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="603dc-135">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="603dc-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="603dc-136">**निर्यात के लिए कनेक्शन** में, Marketo अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="603dc-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="603dc-137">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="603dc-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="603dc-138">अपना **[Marketo सूची ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="603dc-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="603dc-139">सूची ID विशुद्ध रूप से संख्यात्मक मान है.</span><span class="sxs-lookup"><span data-stu-id="603dc-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="603dc-140">उदाहरणस्वरूप, यदि आपका Marketo सूची ID ST12345A7 है तो अंकों के पहले और बाद के वर्ण को हटा दें और `12345` दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="603dc-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="603dc-141">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="603dc-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="603dc-142">वैकल्पिक रूप से, आप अधिक व्यक्तिगत ईमेल बनाने के लिए **पहला नाम**, **अंतिम नाम**, **शहर**, **राज्य**, और **देश/प्रांत** निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="603dc-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="603dc-143">इन फ़ील्ड को मैप करने के लिए **जोड़ें विशेषता** चुनें.</span><span class="sxs-lookup"><span data-stu-id="603dc-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="603dc-144">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="603dc-144">Select the segments you want to export.</span></span> <span data-ttu-id="603dc-145">आप कुल मिलाकर 1 मिलियन ग्राहक प्रोफ़ाइल को Marketo में निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="603dc-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="603dc-146">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="603dc-146">Select **Save**.</span></span>

<span data-ttu-id="603dc-147">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="603dc-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="603dc-148">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="603dc-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="603dc-149">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="603dc-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="603dc-150">Marketo में, अब आप [Marketo सूचियों](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) के तहत अपने सेगमेंट पा सकते हैं .</span><span class="sxs-lookup"><span data-stu-id="603dc-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="603dc-151">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="603dc-151">Data privacy and compliance</span></span>

<span data-ttu-id="603dc-152">जब आप Dynamics 365 Customer Insights को Marketo पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="603dc-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="603dc-153">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Marketo आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="603dc-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="603dc-154">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="603dc-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="603dc-155">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="603dc-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
