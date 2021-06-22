---
title: Customer Insights डेटा को LinkedIn Ads में निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और LinkedIn Ads को निर्यात करने का तरीका जानें.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124500"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="846b2-103">सेगमेंट LinkedIn Ads (पूर्वावलोकन) में निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="846b2-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="846b2-104">Matched Audiences बनाने के लिए एकीकृत ग्राहक प्रोफ़ाइल के सेगमेंट को LinkedIn Ads में निर्यात करें.</span><span class="sxs-lookup"><span data-stu-id="846b2-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="846b2-105">कंपनी लक्ष्यीकरण और संपर्क लक्ष्यीकरण के लिए matched audiences का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="846b2-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="846b2-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="846b2-106">Prerequisites</span></span>

-   <span data-ttu-id="846b2-107">आपके पास एक [LinkedIn Campaign Manager खाता](https://business.linkedin.com/marketing-solutions/ads) और संबंधित व्यवस्थापक क्रेडेंशियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="846b2-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="846b2-108">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="846b2-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="846b2-109">निर्यात किए गए सेगमेंट में ग्राहक प्रोफ़ाइल में ईमेल पते वाली एक फ़ील्ड होती है.</span><span class="sxs-lookup"><span data-stu-id="846b2-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="846b2-110">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="846b2-110">Known limitations</span></span>

- <span data-ttu-id="846b2-111">आप LinkedIn Ads को प्रति निर्यात में 100K प्रोफ़ाइल तक निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="846b2-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="846b2-112">LinkedIn Ads को निर्यात करना सेगमेंट तक ही सीमित है.</span><span class="sxs-lookup"><span data-stu-id="846b2-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="846b2-113">LinkedIn Ads को 100K प्रोफ़ाइल तक निर्यात पूरा करनें में 10 मिनट तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="846b2-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="846b2-114">LinkedIn Ads में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="846b2-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="846b2-115">ऑडियंस इनसाइट्स में, **व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="846b2-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="846b2-116">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **LinkedIn विज्ञापन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="846b2-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="846b2-117">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="846b2-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="846b2-118">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="846b2-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="846b2-119">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="846b2-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="846b2-120">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="846b2-120">Choose who can use this connection.</span></span> <span data-ttu-id="846b2-121">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होते हैं.</span><span class="sxs-lookup"><span data-stu-id="846b2-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="846b2-122">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="846b2-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="846b2-123">अपनी [LinkedIn Campaign Manager खाता ID](https://www.linkedin.com/help/lms/answer/a424270) प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="846b2-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="846b2-124">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="846b2-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="846b2-125">Campaign Monitor से कनेक्शन शुरू करने के लिए **कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="846b2-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="846b2-126">**LinkedIn के साथ प्रमाणित करें** चुनें और LinkedIn Campaign Manager के लिए अपने व्यवस्थापक क्रेडेंशियल्स प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="846b2-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="846b2-127">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="846b2-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="846b2-128">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="846b2-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="846b2-129">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="846b2-129">Configure an export</span></span>

<span data-ttu-id="846b2-130">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप किसी निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="846b2-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="846b2-131">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="846b2-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="846b2-132">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="846b2-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="846b2-133">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="846b2-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="846b2-134">**निर्यात के लिए कनेक्शन** फ़ील्ड में, LinkedIn Ads सेक्शन से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="846b2-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="846b2-135">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="846b2-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="846b2-136">चुनें कि आप LinkedIn पर [संपर्क लक्ष्य](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) के लिए डेटा निर्यात करना चाहते हैं या [कंपनी लक्ष्य](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) के लिए.</span><span class="sxs-lookup"><span data-stu-id="846b2-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="846b2-137">**डेटा मिलान** सेक्शन में, अपनी एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करती है.</span><span class="sxs-lookup"><span data-stu-id="846b2-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="846b2-138">LinkedIn विज्ञापन को खंडों को निर्यात करना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="846b2-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="846b2-139">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="846b2-139">Select the segments you want to export.</span></span> <span data-ttu-id="846b2-140">LinkedIn Campaign Manager में matched audiences, निर्यात करने के लिए आपके द्वारा चुने गए सेगमेंट के नाम के साथ स्वचालित रूप से बन जाएगी.</span><span class="sxs-lookup"><span data-stu-id="846b2-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="846b2-141">प्रत्येक सेगमेंट के परिणामस्वरूप एक अलग matched audience होगी.</span><span class="sxs-lookup"><span data-stu-id="846b2-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="846b2-142">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="846b2-142">Select **Save**.</span></span>

<span data-ttu-id="846b2-143">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="846b2-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="846b2-144">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="846b2-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="846b2-145">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="846b2-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="846b2-146">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="846b2-146">Data privacy and compliance</span></span>

<span data-ttu-id="846b2-147">जब आप Dynamics 365 Customer Insights को LinkedIn Ads में डेटा प्रसारित करने में सक्षम बनाते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के ट्रांसफ़र की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="846b2-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="846b2-148">Microsoft आपके निर्देश पर ऐसे डेटा को ट्रांसफ़र करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि LinkedIn Ads आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करे.</span><span class="sxs-lookup"><span data-stu-id="846b2-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="846b2-149">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="846b2-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="846b2-150">इस कार्यक्षमता का उपयोग बंद करने के लिए आपका Dynamics 365 Customer Insights व्यवस्थापक किसी भी समय इस निर्यात गंतव्य-स्थल को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="846b2-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
