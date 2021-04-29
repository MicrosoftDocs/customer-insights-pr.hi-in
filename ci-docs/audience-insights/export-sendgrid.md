---
title: SendGrid के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और SendGrid को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759767"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="c6032-103">SendGrid को निर्यात खंड (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="c6032-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="c6032-104">एकीकृत ग्राहक प्रोफ़ाइल के सेगमेंट SendGrid संपर्क सूचियों में निर्यात करें और उन्हें SendGrid में अभियानों और ईमेल मार्केटिंग के लिए उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="c6032-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="c6032-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="c6032-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="c6032-106">आपके पास [SendGrid अकाउंट](https://sendgrid.com/) और संबंधित एडमिनिस्ट्रेटर के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="c6032-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c6032-107">SendGrid और संबंधित ID में मौजूदा संपर्क सूचियां हैं.</span><span class="sxs-lookup"><span data-stu-id="c6032-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="c6032-108">अधिक जानकारी के लिए, [SendGrid - संपर्क प्रबंधित करें](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) देखें.</span><span class="sxs-lookup"><span data-stu-id="c6032-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="c6032-109">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="c6032-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c6032-110">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="c6032-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c6032-111">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="c6032-111">Known limitations</span></span>

- <span data-ttu-id="c6032-112">SendGrid में कुल 100'000 प्रोफ़ाइल तक.</span><span class="sxs-lookup"><span data-stu-id="c6032-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="c6032-113">SendGrid को निर्यात करना सेगमेंटों तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="c6032-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="c6032-114">SendGrid को 100'000 प्रोफ़ाइल तक निर्यात करने में कुछ घंटे लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c6032-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="c6032-115">SendGrid को निर्यात किए जा रहे प्रोफ़ाइल की संख्या SendGrid के साथ आपके अनुबंध पर निर्भर और सीमित है.</span><span class="sxs-lookup"><span data-stu-id="c6032-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="c6032-116">SendGrid में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="c6032-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="c6032-117">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="c6032-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c6032-118">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **SendGrid** चुनें.</span><span class="sxs-lookup"><span data-stu-id="c6032-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="c6032-119">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="c6032-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c6032-120">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="c6032-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c6032-121">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="c6032-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c6032-122">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="c6032-122">Choose who can use this connection.</span></span> <span data-ttu-id="c6032-123">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="c6032-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c6032-124">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c6032-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c6032-125">अपनी **SendGrid API कुंजी** दर्ज करें [SendGrid API कुंजी](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="c6032-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="c6032-126">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="c6032-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c6032-127">SendGrid से कनेक्शन को शुरू करने के लिए **जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="c6032-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="c6032-128">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="c6032-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c6032-129">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="c6032-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c6032-130">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="c6032-130">Configure an export</span></span>

<span data-ttu-id="c6032-131">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c6032-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c6032-132">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c6032-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c6032-133">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="c6032-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c6032-134">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="c6032-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c6032-135">**निर्यात के लिए कनेक्शन** में, SendGrid अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="c6032-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="c6032-136">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="c6032-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c6032-137">अपनी **[SendGrid सूची ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="c6032-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="c6032-138">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="c6032-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c6032-139">अन्य वैकल्पिक फ़ील्ड जैसे कि **प्रथम नाम**, **अंतिम नाम**, **देश/क्षेत्र**, **राज्य**, **शहर** और **पोस्ट कोड** के लिए समान चरणों को दोहराएं.</span><span class="sxs-lookup"><span data-stu-id="c6032-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="c6032-140">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="c6032-140">Select the segments you want to export.</span></span> <span data-ttu-id="c6032-141">हम दृढ़ता से SendGrid में **कुल 100'000 से अधिक ग्राहक प्रोफ़ाइल निर्यात नहीं करने की सलाह देते हैं**.</span><span class="sxs-lookup"><span data-stu-id="c6032-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="c6032-142">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="c6032-142">Select **Save**.</span></span>

<span data-ttu-id="c6032-143">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="c6032-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c6032-144">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="c6032-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c6032-145">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c6032-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c6032-146">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="c6032-146">Data privacy and compliance</span></span>

<span data-ttu-id="c6032-147">जब आप Dynamics 365 Customer Insights को SendGrid पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="c6032-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c6032-148">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि SendGrid आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="c6032-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c6032-149">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="c6032-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c6032-150">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="c6032-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]