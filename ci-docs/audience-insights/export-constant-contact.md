---
title: Customer Insights डेटा को Constant Contact में निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Constant Contact विज्ञापन प्रबंधक को निर्यात करने का तरीका जानें.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124275"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="dd025-103">सेगमेंट को Constant Contact (पूर्वावलोकन) में निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="dd025-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="dd025-104">Constant Contact के लिए एकीकृत ग्राहक प्रोफ़ाइल के निर्यात के अनुभाग और मार्केटिंग सें जुड़ी गतिविधियों के लिए उनका उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="dd025-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="dd025-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="dd025-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="dd025-106">आपके पास एक [Constant Contact खाता](https://www.constantcontact.com/account-home) और संबंधित व्यवस्थापक क्रेडेंशियल्स.</span><span class="sxs-lookup"><span data-stu-id="dd025-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="dd025-107">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="dd025-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="dd025-108">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="dd025-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dd025-109">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="dd025-109">Known limitations</span></span>

- <span data-ttu-id="dd025-110">आप Constant Contact करने के लिए प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="dd025-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="dd025-111">Constant Contact को निर्यात करना सेगमेंट तक ही सीमित है.</span><span class="sxs-lookup"><span data-stu-id="dd025-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="dd025-112">Constant Contact को 1 मिलियन प्रोफ़ाइल तक निर्यात पूरा करनें में 1 घंटा तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="dd025-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="dd025-113">प्रोफ़ाइल की संख्या है कि आप Constant Contact करने के लिए निर्यात कर सकते है निर्भर है और Constant Contact के साथ अपने अनुबंध पर सीमित है.</span><span class="sxs-lookup"><span data-stu-id="dd025-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="dd025-114">Constant Contact से कनेक्शन सेट करें</span><span class="sxs-lookup"><span data-stu-id="dd025-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="dd025-115">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="dd025-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dd025-116">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Constant Contact** चुनें.</span><span class="sxs-lookup"><span data-stu-id="dd025-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="dd025-117">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="dd025-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dd025-118">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="dd025-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dd025-119">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="dd025-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dd025-120">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="dd025-120">Choose who can use this connection.</span></span> <span data-ttu-id="dd025-121">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="dd025-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dd025-122">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dd025-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dd025-123">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="dd025-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dd025-124">Constant Contact से कनेक्शन शुरू करने के लिए **कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="dd025-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="dd025-125">**AdRoll के साथ प्रमाणित** चुनें और Constant Contact के लिए अपने व्यवस्थापक क्रेडेंशियल्स प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="dd025-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="dd025-126">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="dd025-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="dd025-127">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="dd025-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="dd025-128">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="dd025-128">Configure an export</span></span>

<span data-ttu-id="dd025-129">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="dd025-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dd025-130">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dd025-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dd025-131">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="dd025-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dd025-132">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="dd025-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="dd025-133">**निर्यात के लिए कनेक्शन** में, Constant Contact अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="dd025-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="dd025-134">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="dd025-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dd025-135">[**Constant Contact सूची ID**](https://app.constantcontact.com/pages/contacts/ui#lists) दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="dd025-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="dd025-136">URL में सूची खोजने के लिए Constant Contact में एक सूची ID खोलें.</span><span class="sxs-lookup"><span data-stu-id="dd025-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="dd025-137">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="dd025-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="dd025-138">Constant Contact करने के लिए सेगमेंट का निर्यात करना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="dd025-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="dd025-139">वैकल्पिक रूप से, आप अधिक व्यक्तिगत ईमेल बनाने के लिए अतिरिक्त फ़ील्ड के रूप में पहला नाम और अंतिम नाम निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="dd025-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="dd025-140">इन फ़ील्ड को मैप करने के लिए **जोड़ें विशेषता** चुनें.</span><span class="sxs-lookup"><span data-stu-id="dd025-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="dd025-141">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="dd025-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="dd025-142">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="dd025-142">Select **Save**.</span></span>

<span data-ttu-id="dd025-143">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="dd025-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dd025-144">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="dd025-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dd025-145">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="dd025-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dd025-146">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="dd025-146">Data privacy and compliance</span></span>

<span data-ttu-id="dd025-147">जब आप Dynamics 365 Customer Insights को Constant Contact में डेटा प्रसारित करने में सक्षम बनाते हैं, तो आप गतिशीलता Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="dd025-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dd025-148">Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि Constant Contact आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="dd025-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dd025-149">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="dd025-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="dd025-150">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="dd025-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
