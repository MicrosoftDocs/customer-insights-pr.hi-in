---
title: Microsoft Advertising को Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Microsoft Advertising को निर्यात करने का तरीका जानें.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124498"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="d50ba-103">Microsoft Advertising को सेगमेंट निर्यात करें (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="d50ba-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="d50ba-104">ग्राहक मिलान ऑडिएंस बनाने के लिए Customer Insights सेगमेंट को Microsoft Advertising में निर्यात करें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="d50ba-105">अपने विज्ञापन अभियानों के लिए इन ऑडिएंस का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d50ba-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="d50ba-106">Prerequisites</span></span>

-   <span data-ttu-id="d50ba-107">[Microsoft Advertising खाता](https://ads.microsoft.com/) और संबंधित व्यवस्थापक क्रेडेंशियल्स.</span><span class="sxs-lookup"><span data-stu-id="d50ba-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d50ba-108">आपने ग्राहक मिलान की उपयोग की शर्तें स्वीकार कर ली हैं.</span><span class="sxs-lookup"><span data-stu-id="d50ba-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="d50ba-109">ऑडिएंस इनसाइट में [कॉन्फ़िगर किए गए सेगमेंट](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d50ba-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d50ba-110">निर्यात किए गए सेगमेंट में एकीकृत ग्राहक प्रोफ़ाइल में ईमेल पते वाली एक फ़ील्ड होती है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d50ba-111">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="d50ba-111">Known limitations</span></span>

- <span data-ttu-id="d50ba-112">आप Microsoft Advertising में प्रति निर्यात 500 K प्रोफ़ाइल तक निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d50ba-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="d50ba-113">Microsoft Advertising को निर्यात करना सेगमेंट तक ही सीमित है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="d50ba-114">Microsoft Advertising में 500 K प्रोफ़ाइल तक निर्यात पूरा करनें में 10 मिनट तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="d50ba-115">Microsoft Advertising के लिए कनेक्शन को सेट करें</span><span class="sxs-lookup"><span data-stu-id="d50ba-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="d50ba-116">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="d50ba-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d50ba-117">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Microsoft विज्ञापन प्रक्रिया** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="d50ba-118">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d50ba-119">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d50ba-120">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="d50ba-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d50ba-121">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-121">Choose who can use this connection.</span></span> <span data-ttu-id="d50ba-122">डिफ़ॉल्ट व्यवस्थापक है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-122">The default is administrators.</span></span> <span data-ttu-id="d50ba-123">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d50ba-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d50ba-124">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d50ba-125">Microsoft Advertising से कनेक्शन शुरू करने के लिए **कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="d50ba-126">**Microsoft Advertising के साथ प्रमाणित करें** चुनें और Microsoft Advertising के लिए अपने व्यवस्थापक क्रेडेंशियल्स प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="d50ba-127">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="d50ba-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d50ba-128">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d50ba-129">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="d50ba-129">Configure an export</span></span>

<span data-ttu-id="d50ba-130">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d50ba-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d50ba-131">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d50ba-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d50ba-132">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="d50ba-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d50ba-133">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d50ba-134">**निर्यात के लिए कनेक्शन** फ़ील्ड में, Microsoft Advertising सेक्शन से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="d50ba-135">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d50ba-136">निर्यात करने के लिए सेगमेंट चुनें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-136">Select the segments to export.</span></span> <span data-ttu-id="d50ba-137">Microsoft विज्ञापन में ग्राहक मैच ऑडियंस निर्यात के लिए चयनित खंड के नाम के साथ स्वचालित रूप से बनाई जाती हैं.</span><span class="sxs-lookup"><span data-stu-id="d50ba-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="d50ba-138">प्रत्येक अनुभाग के परिणामस्वरूप एक अलग ग्राहक मिलान ऑडिएंस होगी.</span><span class="sxs-lookup"><span data-stu-id="d50ba-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="d50ba-139">अपना **Microsoft विज्ञापन ग्राहक ID और खाता ID** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="d50ba-140">आप ग्राहक ID (`cid`) और खाता ID (`aid`) URL के पैरामीटर में पा सकते हैं जब आप Microsoft Advertising में साइन इन होते हैं.</span><span class="sxs-lookup"><span data-stu-id="d50ba-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="d50ba-141">**ईमेल** फ़ील्ड में, **डेटा मिलान सेक्शन** में, ग्राहक के ईमेल पते के साथ अपने एकीकृत ग्राहक प्रोफ़ाइल में फ़ील्ड चुनें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="d50ba-142">Microsoft Advertising में अनुभाग का निर्यात करना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="d50ba-143">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-143">Select **Save**.</span></span>

<span data-ttu-id="d50ba-144">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d50ba-145">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d50ba-146">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="d50ba-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d50ba-147">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="d50ba-147">Data privacy and compliance</span></span>

<span data-ttu-id="d50ba-148">जब आप Dynamics 365 Customer Insights को Microsoft विज्ञापन में डेटा प्रसारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के ट्रांसफ़र की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="d50ba-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d50ba-149">Microsoft आपके निर्देश पर ऐसे डेटा को ट्रांसफ़र करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि Microsoft Advertising आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d50ba-150">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="d50ba-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d50ba-151">इस कार्यक्षमता का उपयोग बंद करने के लिए आपका Dynamics 365 Customer Insights व्यवस्थापक किसी भी समय इस निर्यात गंतव्य-स्थल को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="d50ba-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
