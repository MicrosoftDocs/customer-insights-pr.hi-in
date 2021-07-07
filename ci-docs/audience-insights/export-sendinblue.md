---
title: Sendinblue में Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Sendinblue को निर्यात करने का तरीका जानें।
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314622"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="9bb17-103">Sendinblue में अनुभाग निर्यात करें (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="9bb17-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="9bb17-104">अभियान बनाने के लिए एकाकृत ग्राहक प्रोफ़ाइलों के अनुभागों को निर्यात करें, Sendinblue के साथ ई-मेल मार्केटिंग उपलब्ध कराएं और ग्राहक के विशिष्ट समूह का उपयोग करें।</span><span class="sxs-lookup"><span data-stu-id="9bb17-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="9bb17-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="9bb17-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="9bb17-106">आपके पास [Sendinblue खाता](https://www.sendinblue.com/) है और संबंधित व्यवस्थापक क्रेडेंशियल है।</span><span class="sxs-lookup"><span data-stu-id="9bb17-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9bb17-107">Sendinblue और संबंधित ID में मौजूदा सूचियां हैं।</span><span class="sxs-lookup"><span data-stu-id="9bb17-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="9bb17-108">आपके पास [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="9bb17-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="9bb17-109">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="9bb17-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9bb17-110">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="9bb17-110">Known limitations</span></span>

- <span data-ttu-id="9bb17-111">Sendinblue को प्रति निर्यात 1 मिलियन प्रोफाइल तक।</span><span class="sxs-lookup"><span data-stu-id="9bb17-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="9bb17-112">Sendinblue में निर्यात करना अनुभागों तक सीमित है।</span><span class="sxs-lookup"><span data-stu-id="9bb17-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="9bb17-113">कुल 1 मिलियन प्रोफ़ाइल वाले निर्यात अनुभागों में 90 मिनट तक का समय लग सकता है।</span><span class="sxs-lookup"><span data-stu-id="9bb17-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="9bb17-114">आपके द्वारा Sendinblue में निर्यात की जा सकने वाली प्रोफ़ाइलों की संख्या Sendinblue के साथ आपके अनुबंध पर निर्भर और सीमित है।</span><span class="sxs-lookup"><span data-stu-id="9bb17-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="9bb17-115">Sendinblue पर कनेक्शन सेट करें</span><span class="sxs-lookup"><span data-stu-id="9bb17-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="9bb17-116">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="9bb17-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9bb17-117">कनेक्शन को कॉन्फ़िगर करने के लिए **कनेक्शन जोड़ें** चुनें और **Sendinblue** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9bb17-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="9bb17-118">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="9bb17-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9bb17-119">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="9bb17-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9bb17-120">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="9bb17-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9bb17-121">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="9bb17-121">Choose who can use this connection.</span></span> <span data-ttu-id="9bb17-122">डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं.</span><span class="sxs-lookup"><span data-stu-id="9bb17-122">By default it's only administrators.</span></span> <span data-ttu-id="9bb17-123">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9bb17-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9bb17-124">अपना **[ SendinBlue API कुंजी](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="9bb17-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="9bb17-125">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूं** चुनें और Sendinblue से कनेक्शन प्रारंभ करने के लिए **कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9bb17-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="9bb17-126">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="9bb17-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9bb17-127">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9bb17-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9bb17-128">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="9bb17-128">Configure an export</span></span>

<span data-ttu-id="9bb17-129">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9bb17-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9bb17-130">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9bb17-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9bb17-131">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="9bb17-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9bb17-132">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9bb17-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9bb17-133">**निर्यात के लिए कनेक्शन** फ़ील्ड में, Sendinblue अनुभाग से एक कनेक्शन चुनें.</span><span class="sxs-lookup"><span data-stu-id="9bb17-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="9bb17-134">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="9bb17-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9bb17-135">अपना **Sendinblue सूची ID** दर्ज करें</span><span class="sxs-lookup"><span data-stu-id="9bb17-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="9bb17-136">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="9bb17-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="9bb17-137">वैकल्पिक रूप से, आप अधिक वैयक्तिकृत ईमेल बनाने के लिए **प्रथम नाम**, **अंतिम नाम**, और **फ़ोन** निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9bb17-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="9bb17-138">इन फ़ील्ड को मैप करने के लिए **जोड़ें विशेषता** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9bb17-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9bb17-139">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="9bb17-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="9bb17-140">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9bb17-140">Select **Save**.</span></span>

<span data-ttu-id="9bb17-141">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="9bb17-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9bb17-142">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="9bb17-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9bb17-143">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9bb17-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9bb17-144">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="9bb17-144">Data privacy and compliance</span></span>

<span data-ttu-id="9bb17-145">जब आप Sendinblue पर डेटा संचारित करने के लिए Dynamics 365 Customer Insights सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="9bb17-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9bb17-146">Microsoft आपके निर्देश पर ऐसा डेटा स्थानांतरित करेगा, लेकिन यह सुनिश्चित करने के लिए आप ज़िम्मेदार हैं कि Sendinblue किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="9bb17-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9bb17-147">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="9bb17-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9bb17-148">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="9bb17-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
