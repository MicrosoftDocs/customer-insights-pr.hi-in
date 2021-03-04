---
title: Marketo के लिए Customer Insights डेटा निर्यात करें
description: Marketo के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267083"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="17618-103">Marketo के लिए कनेक्ट (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="17618-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="17618-104">अभियान उत्पन्न करने, ईमेल मार्केटिंग प्रदान करने और Marketo के साथ ग्राहकों के विशिष्ट समूहों का उपयोग करने के लिए एकीकृत ग्राहक प्रोफाइल के निर्यात खंड.</span><span class="sxs-lookup"><span data-stu-id="17618-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="17618-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="17618-105">Prerequisites</span></span>

-   <span data-ttu-id="17618-106">आपके पास [Marketo खाता](https://login.marketo.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="17618-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="17618-107">Marketo और संबंधित ID में मौजूदा सूचियां हैं.</span><span class="sxs-lookup"><span data-stu-id="17618-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="17618-108">अधिक जानकारी के लिए, [Marketo सूचियां](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) देखें.</span><span class="sxs-lookup"><span data-stu-id="17618-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="17618-109">आपके पास [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="17618-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="17618-110">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="17618-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="17618-111">Marketo से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="17618-111">Connect to Marketo</span></span>

1. <span data-ttu-id="17618-112">**व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="17618-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="17618-113">**Marketo** के अंतर्गत, **सेट अप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="17618-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="17618-114">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="17618-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="17618-115">अपने **[Marketo क्लाइंट ID, क्लाइंट सीक्रेट और रेस्ट एंडपॉइंट होस्टनेम](https://developers.marketo.com/rest-api/authentication/)** दर्ज करें .</span><span class="sxs-lookup"><span data-stu-id="17618-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="17618-116">अपनी **[Marketo सूची ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** दर्ज करें</span><span class="sxs-lookup"><span data-stu-id="17618-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="17618-117">मैं **डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **सहमत हूं** चुनें और Marketo से कनेक्शन को शुरू करने के लिए **कनेक्ट** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="17618-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="17618-118">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="17618-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Marketo कनेक्शन के लिए निर्यात स्क्रीनशॉट":::

1. <span data-ttu-id="17618-120">निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="17618-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="17618-121">कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="17618-121">Configure the connector</span></span>

1. <span data-ttu-id="17618-122">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="17618-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="17618-123">वैकल्पिक रूप से, आप अधिक व्यक्तिगत ईमेल बनाने के लिए अतिरिक्त फ़ील्ड के रूप में **प्रथम नाम**, **अंतिम नाम**, **शहर**, **राज्य** और **देश/क्षेत्र** को निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="17618-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="17618-124">इन फ़ील्ड को मैप करने के लिए **जोड़ें विशेषता** चुनें.</span><span class="sxs-lookup"><span data-stu-id="17618-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="17618-125">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="17618-125">Select the segments you want to export.</span></span> <span data-ttu-id="17618-126">आप कुल मिलाकर 1 मिलियन ग्राहक प्रोफ़ाइल को Marketo में निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="17618-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Marketo को निर्यात करने के लिए क्षेत्रों और खंडों का चयन करें":::

1. <span data-ttu-id="17618-128">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="17618-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="17618-129">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="17618-129">Export the data</span></span>

<span data-ttu-id="17618-130">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="17618-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="17618-131">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="17618-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="17618-132">Marketo में, अब आप [Marketo सूचियों](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) के तहत अपने सेगमेंट पा सकते हैं .</span><span class="sxs-lookup"><span data-stu-id="17618-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="17618-133">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="17618-133">Known limitations</span></span>

- <span data-ttu-id="17618-134">Marketo को प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक.</span><span class="sxs-lookup"><span data-stu-id="17618-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="17618-135">Marketo को निर्यात करना सेगमेंटों तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="17618-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="17618-136">कुल 1 मिलियन प्रोफाइल वाले निर्यात खंडों में 3 घंटे तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="17618-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="17618-137">Marketo को निर्यात किए जा रहे प्रोफ़ाइल की संख्या Marketo के साथ आपके अनुबंध पर निर्भर और सीमित है.</span><span class="sxs-lookup"><span data-stu-id="17618-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="17618-138">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="17618-138">Data privacy and compliance</span></span>

<span data-ttu-id="17618-139">जब आप Dynamics 365 Customer Insights को Marketo पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="17618-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="17618-140">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Marketo आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="17618-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="17618-141">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="17618-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="17618-142">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="17618-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]