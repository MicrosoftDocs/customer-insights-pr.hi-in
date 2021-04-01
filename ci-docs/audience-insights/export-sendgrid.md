---
title: SendGrid के लिए Customer Insights डेटा निर्यात करें
description: SendGrid के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597283"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="53297-103">SendGrid के लिए संबंधक (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="53297-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="53297-104">एकीकृत ग्राहक प्रोफ़ाइल के सेगमेंट SendGrid संपर्क सूचियों में निर्यात करें और उन्हें SendGrid में अभियानों और ईमेल मार्केटिंग के लिए उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="53297-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="53297-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="53297-105">Prerequisites</span></span>

-   <span data-ttu-id="53297-106">आपके पास [SendGrid अकाउंट](https://sendgrid.com/) और संबंधित एडमिनिस्ट्रेटर के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="53297-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="53297-107">SendGrid और संबंधित ID में मौजूदा संपर्क सूचियां हैं.</span><span class="sxs-lookup"><span data-stu-id="53297-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="53297-108">अधिक जानकारी के लिए, [SendGrid - संपर्क प्रबंधित करें](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) देखें.</span><span class="sxs-lookup"><span data-stu-id="53297-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="53297-109">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="53297-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="53297-110">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="53297-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="53297-111">SendGrid से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="53297-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="53297-112">**व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="53297-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="53297-113">**SendGrid** के अंतर्गत, **सेट अप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="53297-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="53297-114">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="53297-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid निर्यात कॉन्फ़िगरेशन फलक.":::

1. <span data-ttu-id="53297-116">अपनी **SendGrid API कुंजी** दर्ज करें [SendGrid API कुंजी](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="53297-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="53297-117">अपनी **[SendGrid सूची ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="53297-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="53297-118">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="53297-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="53297-119">SendGrid से कनेक्शन को शुरू करने के लिए **जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="53297-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="53297-120">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="53297-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="53297-121">निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="53297-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="53297-122">कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="53297-122">Configure the connector</span></span>

1. <span data-ttu-id="53297-123">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="53297-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="53297-124">अन्य वैकल्पिक फ़ील्ड जैसे कि **प्रथम नाम**, **अंतिम नाम**, **देश/क्षेत्र**, **राज्य**, **शहर** और **पोस्ट कोड** के लिए समान चरणों को दोहराएं.</span><span class="sxs-lookup"><span data-stu-id="53297-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="53297-125">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="53297-125">Select the segments you want to export.</span></span> <span data-ttu-id="53297-126">हम दृढ़ता से SendGrid में **कुल 100'000 से अधिक ग्राहक प्रोफ़ाइल निर्यात नहीं करने की सलाह देते हैं**.</span><span class="sxs-lookup"><span data-stu-id="53297-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="53297-127">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="53297-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="53297-128">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="53297-128">Export the data</span></span>

<span data-ttu-id="53297-129">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="53297-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="53297-130">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="53297-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="53297-131">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="53297-131">Known limitations</span></span>

- <span data-ttu-id="53297-132">SendGrid में कुल 100'000 प्रोफ़ाइल तक.</span><span class="sxs-lookup"><span data-stu-id="53297-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="53297-133">SendGrid को निर्यात करना सेगमेंटों तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="53297-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="53297-134">SendGrid को 100'000 प्रोफ़ाइल तक निर्यात करने में कुछ घंटे लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="53297-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="53297-135">SendGrid को निर्यात किए जा रहे प्रोफ़ाइल की संख्या SendGrid के साथ आपके अनुबंध पर निर्भर और सीमित है.</span><span class="sxs-lookup"><span data-stu-id="53297-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="53297-136">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="53297-136">Data privacy and compliance</span></span>

<span data-ttu-id="53297-137">जब आप Dynamics 365 Customer Insights को SendGrid पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="53297-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="53297-138">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि SendGrid आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="53297-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="53297-139">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="53297-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="53297-140">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="53297-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]