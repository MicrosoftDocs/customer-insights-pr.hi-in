---
title: Google Ads के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Google Ads को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c23c8b4e6758df08e04bf1e3ae0cba4dee06fe2b
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305342"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="593cb-103">Google Ads (पूर्वावलोकन) में निर्यात अनुभाग</span><span class="sxs-lookup"><span data-stu-id="593cb-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="593cb-104">एकीकृत ग्राहक प्रोफ़ाइल के अनुभाग को Google Ads ऑडिएंस सूची में निर्यात करें और Google खोज, Gmail, YouTube, और Google प्रदर्शन नेटवर्क पर विज्ञापन देने के लिए उनका उपयोग करें।</span><span class="sxs-lookup"><span data-stu-id="593cb-104">Export segments of unified customer profiles to a Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="593cb-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="593cb-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="593cb-106">आपके पास [Google Ads खाता](https://ads.google.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="593cb-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="593cb-107">आपके पास एक [अनुमोदित Google Ads डेवलपर टोकन](https://developers.google.com/google-ads/api/docs/first-call/dev-token) है।</span><span class="sxs-lookup"><span data-stu-id="593cb-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span></span> 
-   <span data-ttu-id="593cb-108">आप [ग्राहक मिलान नीति](https://support.google.com/adspolicy/answer/6299717) की आवश्यकताओं को पूरा करते हैं।</span><span class="sxs-lookup"><span data-stu-id="593cb-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717).</span></span>
-   <span data-ttu-id="593cb-109">आप [रीमार्केटिंग सूची के आकार](https://support.google.com/google-ads/answer/7558048) की आवश्यकताओं को पूरा करते हैं।</span><span class="sxs-lookup"><span data-stu-id="593cb-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048).</span></span>
-   <span data-ttu-id="593cb-110">Google Ads और संबंधित आईडी में मौजूदा ऑडियंस हैं.</span><span class="sxs-lookup"><span data-stu-id="593cb-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="593cb-111">अधिक जानकारी के लिए, [Google Ads ऑडिएंस](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) देखें.</span><span class="sxs-lookup"><span data-stu-id="593cb-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="593cb-112">आपके पास [कॉन्फ़िगर सेगमेंट](segments.md) है.</span><span class="sxs-lookup"><span data-stu-id="593cb-112">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="593cb-113">निर्यात किए गए अनुभागों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते, पहला नाम और अंतिम नाम का प्रतिनिधित्व करने वाले क्षेत्र होते हैं।</span><span class="sxs-lookup"><span data-stu-id="593cb-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="593cb-114">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="593cb-114">Known limitations</span></span>

- <span data-ttu-id="593cb-115">Google Ads को प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक.</span><span class="sxs-lookup"><span data-stu-id="593cb-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="593cb-116">Google Ads को निर्यात करना सेगमेंटों तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="593cb-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="593cb-117">प्रदाता पक्ष पर सीमाओं के कारण कुल 1 मिलियन प्रोफाइल वाले निर्यात खंडों में 5 मिनट तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="593cb-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="593cb-118">Google Ads में मिलान में 48 घंटे तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="593cb-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="593cb-119">Google Ads के लिए कनेक्शन सेट करें</span><span class="sxs-lookup"><span data-stu-id="593cb-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="593cb-120">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="593cb-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="593cb-121">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Google Ads** चुनें.</span><span class="sxs-lookup"><span data-stu-id="593cb-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="593cb-122">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="593cb-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="593cb-123">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="593cb-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="593cb-124">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="593cb-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="593cb-125">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="593cb-125">Choose who can use this connection.</span></span> <span data-ttu-id="593cb-126">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="593cb-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="593cb-127">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="593cb-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="593cb-128">अपनी **[Google Ads ग्राहक ID](https://support.google.com/google-ads/answer/1704344)** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="593cb-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="593cb-129">अपने **[Google AD अनुमोदित डेवलपर टोकन](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="593cb-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="593cb-130">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="593cb-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="593cb-131">**Google Ads के साथ प्रमाणीकरण** चुनें और अपने Google Ads परिचय पत्र प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="593cb-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="593cb-132">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="593cb-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="593cb-133">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="593cb-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="593cb-134">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="593cb-134">Configure an export</span></span>

<span data-ttu-id="593cb-135">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="593cb-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="593cb-136">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="593cb-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="593cb-137">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="593cb-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="593cb-138">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="593cb-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="593cb-139">**निर्यात के लिए कनेक्शन** में, Google Ads अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="593cb-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="593cb-140">यदि आपको यह अनुभाग नाम नहीं दिखता है, तो इस प्रकार का कोई भी कनेक्शन आपके लिए उपलब्ध नहीं है।</span><span class="sxs-lookup"><span data-stu-id="593cb-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="593cb-141">अपने **[Google Ads ऑडियंस ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** और Google Ads से कनेक्शन शुरू करने के लिए **कनेक्ट** चुनें.</span><span class="sxs-lookup"><span data-stu-id="593cb-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="593cb-142">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="593cb-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="593cb-143">**पहला नाम** और **अंतिम नाम** फ़ील्ड के लिए एक ही चरण दोहराएं.</span><span class="sxs-lookup"><span data-stu-id="593cb-143">Repeat the same steps for **First name** and **Last name** fields.</span></span>

1. <span data-ttu-id="593cb-144">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="593cb-144">Select the segments you want to export.</span></span> <span data-ttu-id="593cb-145">आप कुल मिलाकर 1 मिलियन ग्राहक प्रोफ़ाइल को Google Ads में निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="593cb-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="593cb-146">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="593cb-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="593cb-147">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="593cb-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="593cb-148">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="593cb-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="593cb-149">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="593cb-149">Data privacy and compliance</span></span>

<span data-ttu-id="593cb-150">जब आप Dynamics 365 Customer Insights को Google Ads पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="593cb-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="593cb-151">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Google Ads विज्ञापन आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="593cb-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="593cb-152">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="593cb-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="593cb-153">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="593cb-153">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
