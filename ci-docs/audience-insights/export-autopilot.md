---
title: Autopilot के लिए Customer Insights डेटा निर्यात करें
description: Autopilot के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596132"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="d99aa-103">Autopilot के लिए संबंधक (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="d99aa-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="d99aa-104">एकीकृत ग्राहक प्रोफ़ाइल के सेगमेंट Autopilot में निर्यात करें और उन्हें Autopilot में ईमेल मार्केटिंग के लिए उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="d99aa-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d99aa-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="d99aa-105">Prerequisites</span></span>

-   <span data-ttu-id="d99aa-106">आपके पास [Autopilot खाता](https://www.autopilothq.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="d99aa-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d99aa-107">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="d99aa-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d99aa-108">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="d99aa-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="d99aa-109">Autopilot से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="d99aa-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="d99aa-110">**व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="d99aa-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d99aa-111">**Autopilot** के अंतर्गत, **सेट अप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d99aa-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="d99aa-112">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="d99aa-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot कनेक्शन के लिए कॉन्फ़िगरेशन फलक.":::

1. <span data-ttu-id="d99aa-114">अपनी **Autopilot API कुंजी** दर्ज करें [Autopilot API कुंजी](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="d99aa-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="d99aa-115">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d99aa-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d99aa-116">Autopilot से कनेक्शन को शुरू करने के लिए **जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d99aa-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="d99aa-117">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="d99aa-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d99aa-118">निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d99aa-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d99aa-119">कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="d99aa-119">Configure the connector</span></span>

1. <span data-ttu-id="d99aa-120">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="d99aa-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d99aa-121">अन्य वैकल्पिक फ़ील्ड जैसे **प्रथम नाम**, **अंतिम नाम** के लिए इन्हीं चरणों को दोहराएं.</span><span class="sxs-lookup"><span data-stu-id="d99aa-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="d99aa-122">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="d99aa-122">Select the segments you want to export.</span></span> <span data-ttu-id="d99aa-123">हम दृढ़ता से Autopilot में **कुल 100'000 से अधिक ग्राहक प्रोफ़ाइल निर्यात नहीं करने की सलाह देते हैं**.</span><span class="sxs-lookup"><span data-stu-id="d99aa-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="d99aa-124">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d99aa-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d99aa-125">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="d99aa-125">Export the data</span></span>

<span data-ttu-id="d99aa-126">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d99aa-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d99aa-127">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d99aa-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d99aa-128">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="d99aa-128">Known limitations</span></span>

- <span data-ttu-id="d99aa-129">आप Autopilot में कुल 100'000 प्रोफ़ाइल तक निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d99aa-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="d99aa-130">Autopilot को निर्यात करना सेगमेंटों तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="d99aa-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="d99aa-131">Autopilot को 100'000 प्रोफ़ाइल तक निर्यात करने में कुछ घंटे लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d99aa-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="d99aa-132">Autopilot को निर्यात किए जा रहे प्रोफ़ाइल की संख्या Autopilot के साथ आपके अनुबंध पर निर्भर और सीमित है.</span><span class="sxs-lookup"><span data-stu-id="d99aa-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d99aa-133">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="d99aa-133">Data privacy and compliance</span></span>

<span data-ttu-id="d99aa-134">जब आप Dynamics 365 Customer Insights को Autopilot पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="d99aa-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d99aa-135">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Autopilot आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="d99aa-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d99aa-136">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="d99aa-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d99aa-137">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="d99aa-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]