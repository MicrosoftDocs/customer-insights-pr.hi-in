---
title: DotDigital को Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और DotDigital को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759961"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="33b49-103">सेगमेंट सूचियां को DotDigital (पूर्वावलोकन) में निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="33b49-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="33b49-104">एकीकृत ग्राहक प्रोफाइल के निर्यात सेगमेंट DotDigital पता पुस्तकों के लिए और उन्हें अभियानों, ईमेल विपणन के लिए उपयोग करते हैं, और DotDigital के साथ ग्राहक वाले सेगमेंटों का निर्माण करने के लिए.</span><span class="sxs-lookup"><span data-stu-id="33b49-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="33b49-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="33b49-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="33b49-106">आपके पास [DotDigital खाता](https://dotdigital.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="33b49-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="33b49-107">DotDigital और संबंधित AD में मौजूदा पते की किताबें हैं.</span><span class="sxs-lookup"><span data-stu-id="33b49-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="33b49-108">पता बुक सिलने और खोलने पर ID यूआरएल में मिल सकती है.</span><span class="sxs-lookup"><span data-stu-id="33b49-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="33b49-109">अधिक जानकारी के लिए देखें [DotDigital पता किताबें](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="33b49-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="33b49-110">आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="33b49-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="33b49-111">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.</span><span class="sxs-lookup"><span data-stu-id="33b49-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="33b49-112">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="33b49-112">Known limitations</span></span>

- <span data-ttu-id="33b49-113">DotDigital को प्रति निर्यात 1 मिलियन प्रोफाइल तक.</span><span class="sxs-lookup"><span data-stu-id="33b49-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="33b49-114">DotDigital को निर्यात करना खंडों तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="33b49-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="33b49-115">प्रदाता पक्ष पर सीमाओं के कारण कुल 1 मिलियन प्रोफाइल वाले निर्यात खंडों में 3 घंटे तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="33b49-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="33b49-116">DotDigital को निर्यात किए जा रहे प्रोफाइल की संख्या DotDigital के साथ आपके अनुबंध पर निर्भर और सीमित है.</span><span class="sxs-lookup"><span data-stu-id="33b49-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="33b49-117">DotDigital में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="33b49-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="33b49-118">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="33b49-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="33b49-119">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **DotDigital** चुनें.</span><span class="sxs-lookup"><span data-stu-id="33b49-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="33b49-120">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="33b49-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="33b49-121">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="33b49-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="33b49-122">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="33b49-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="33b49-123">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="33b49-123">Choose who can use this connection.</span></span> <span data-ttu-id="33b49-124">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="33b49-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="33b49-125">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="33b49-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="33b49-126">अपना **DotDigital उपयोगकर्ता नाम और पासवर्ड** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="33b49-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="33b49-127">अपने **[DotDigital पता पुस्तक ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** दर्ज करें .</span><span class="sxs-lookup"><span data-stu-id="33b49-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="33b49-128">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="33b49-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="33b49-129">DotDigital के लिए कनेक्शन शुरू करने के लिए **कनेक्ट** चुनें.</span><span class="sxs-lookup"><span data-stu-id="33b49-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="33b49-130">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="33b49-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="33b49-131">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="33b49-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="33b49-132">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="33b49-132">Configure an export</span></span>

<span data-ttu-id="33b49-133">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="33b49-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="33b49-134">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="33b49-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="33b49-135">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="33b49-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="33b49-136">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="33b49-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="33b49-137">**निर्यात के लिए कनेक्शन** में, DotDigital अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="33b49-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="33b49-138">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="33b49-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="33b49-139">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="33b49-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="33b49-140">अन्य वैकल्पिक फ़ील्ड जैसे **फर्स्ट नाम**, **अंतिम नाम**, **पूरा नाम**, **लिंग**, और **पोस्ट कोड** के लिए भी यही कदम दोहराएं.</span><span class="sxs-lookup"><span data-stu-id="33b49-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="33b49-141">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="33b49-141">Select the segments you want to export.</span></span> <span data-ttu-id="33b49-142">आप कुल मिलाकर 1 मिलियन ग्राहक प्रोफाइल को DotDigital में निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="33b49-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="33b49-143">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="33b49-143">Select **Save**.</span></span>

<span data-ttu-id="33b49-144">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="33b49-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="33b49-145">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="33b49-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="33b49-146">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="33b49-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="33b49-147">DotDigital में, अब आप [DotDigital पता किताबें](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) में अपने खंडों पा सकते हैं .</span><span class="sxs-lookup"><span data-stu-id="33b49-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="33b49-148">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="33b49-148">Data privacy and compliance</span></span>

<span data-ttu-id="33b49-149">जब आप Dynamics 365 Customer Insights को DotDigital में डेटा संचारित करने में सक्षम बनाते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="33b49-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="33b49-150">Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि DotDigital आपके किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करे.</span><span class="sxs-lookup"><span data-stu-id="33b49-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="33b49-151">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="33b49-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="33b49-152">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="33b49-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
