---
title: Mailchimp के लिए Customer Insights डेटा निर्यात करें
description: Mailchimp के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267175"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="d9654-103">Mailchimp के लिए संबंधक (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="d9654-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="d9654-104">समाचार पत्र और ईमेल अभियान बनाने के लिए मेलचिम्प को एकीकृत ग्राहक प्रोफाइल के निर्यात खंड.</span><span class="sxs-lookup"><span data-stu-id="d9654-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d9654-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="d9654-105">Prerequisites</span></span>

-   <span data-ttu-id="d9654-106">आपके पास [Mailchimp खाता](https://mailchimp.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="d9654-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d9654-107">Mailchimp और संबंधित ID में मौजूदा ऑडिएंस हैं.</span><span class="sxs-lookup"><span data-stu-id="d9654-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="d9654-108">अधिक जानकारी के लिए, [Mailchimp ऑडिएंस](https://mailchimp.com/help/create-audience/) देखें.</span><span class="sxs-lookup"><span data-stu-id="d9654-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="d9654-109">आपके पास [कॉन्फ़िगर सेगमेंट](segments.md) है</span><span class="sxs-lookup"><span data-stu-id="d9654-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="d9654-110">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="d9654-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="d9654-111">Mailchimp से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="d9654-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="d9654-112">**व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="d9654-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d9654-113">**Mailchimp** के अंतर्गत, **सेट अप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d9654-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="d9654-114">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="d9654-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d9654-115">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d9654-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d9654-116">मेलचिम्प के कनेक्शन को शुरू करने के लिए अपनी **[मेलचिम्प ऑडियंस ID](https://mailchimp.com/help/find-audience-id/)** दर्ज करें और **कनेक्ट** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d9654-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="d9654-117">**मेलचिम्प के साथ प्रमाणित** चुनें और अपने मेलचिम्प क्रेडेंशियल्स प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="d9654-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="d9654-118">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="d9654-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="मेलचिम्प कनेक्शन के लिए निर्यात स्क्रीनशॉट":::

1. <span data-ttu-id="d9654-120">निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d9654-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d9654-121">कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="d9654-121">Configure the connector</span></span>

1. <span data-ttu-id="d9654-122">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="d9654-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="d9654-123">वैकल्पिक रूप से, आप अधिक व्यक्तिगत ईमेल बनाने के लिए अतिरिक्त फ़ील्ड के रूप में **पहला नाम** और **अंतिम नाम** निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d9654-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="d9654-124">इन फ़ील्ड को मैप करने के लिए **जोड़ें विशेषता** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d9654-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d9654-125">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="d9654-125">Select the segments you want to export.</span></span> <span data-ttu-id="d9654-126">आप कुल मिलाकर 1 मिलियन ग्राहक प्रोफ़ाइल को Mailchimp में निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d9654-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="मेलचिम्प को निर्यात करने के लिए क्षेत्रों और खंडों का चयन करें":::

1. <span data-ttu-id="d9654-128">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d9654-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d9654-129">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="d9654-129">Export the data</span></span>

<span data-ttu-id="d9654-130">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d9654-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d9654-131">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d9654-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d9654-132">मेलचिम्प में, अब आप [Mailchimp दर्शकों](https://mailchimp.com/help/create-audience/) के तहत अपने सेगमेंट पा सकते हैं .</span><span class="sxs-lookup"><span data-stu-id="d9654-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d9654-133">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="d9654-133">Known limitations</span></span>

- <span data-ttu-id="d9654-134">Mailchimp को प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक.</span><span class="sxs-lookup"><span data-stu-id="d9654-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="d9654-135">Mailchimp को निर्यात करना सेगमेंटों तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="d9654-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="d9654-136">प्रदाता पक्ष पर सीमाओं के कारण कुल 1 मिलियन प्रोफाइल वाले निर्यात खंडों में तीन घंटे तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="d9654-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="d9654-137">Mailchimp को निर्यात किए जा रहे प्रोफ़ाइल की संख्या Mailchimp के साथ आपके अनुबंध पर निर्भर और सीमित है.</span><span class="sxs-lookup"><span data-stu-id="d9654-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d9654-138">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="d9654-138">Data privacy and compliance</span></span>

<span data-ttu-id="d9654-139">जब आप Dynamics 365 Customer Insights को Mailchimp पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="d9654-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d9654-140">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Mailchimp आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="d9654-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d9654-141">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="d9654-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d9654-142">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="d9654-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]