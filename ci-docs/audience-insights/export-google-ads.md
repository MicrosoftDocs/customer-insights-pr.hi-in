---
title: Google Ads के लिए Customer Insights डेटा निर्यात करें
description: Google Ads के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568448"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="94dea-103">Google Ads के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="94dea-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="94dea-104">Google Ads ऑडियंस सूची में एकीकृत ग्राहक प्रोफ़ाइल के निर्यात सेगमेंट और Google खोज, जीमेल, YouTube और Google डिस्प्ले नेटवर्क पर AD देने के लिए उनका उपयोग करते हैं.</span><span class="sxs-lookup"><span data-stu-id="94dea-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="94dea-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="94dea-105">Prerequisites</span></span>

-   <span data-ttu-id="94dea-106">आपके पास [Google Ads खाता](https://ads.google.com/) और इसी प्रशासक के क्रेडेन्सियल्स हैं.</span><span class="sxs-lookup"><span data-stu-id="94dea-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="94dea-107">Google Ads और संबंधित आईडी में मौजूदा ऑडियंस हैं.</span><span class="sxs-lookup"><span data-stu-id="94dea-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="94dea-108">अधिक जानकारी के लिए, [Google Ads ऑडिएंस](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) देखें.</span><span class="sxs-lookup"><span data-stu-id="94dea-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="94dea-109">आपके पास [कॉन्फ़िगर सेगमेंट](segments.md) है</span><span class="sxs-lookup"><span data-stu-id="94dea-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="94dea-110">निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते, पहला नाम और अंतिम नाम का प्रतिनिधित्व करने वाले क्षेत्र होते हैं</span><span class="sxs-lookup"><span data-stu-id="94dea-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="94dea-111">Google Ads से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="94dea-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="94dea-112">**व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="94dea-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="94dea-113">**Google Ads** अंतर्गत, **सेट अप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="94dea-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="94dea-114">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="94dea-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="94dea-115">अपनी **[Google Ads ग्राहक ID](https://support.google.com/google-ads/answer/1704344)** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="94dea-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="94dea-116">अपने **[Google AD अनुमोदित डेवलपर टोकन](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="94dea-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="94dea-117">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="94dea-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="94dea-118">अपने **[Google Ads ऑडियंस ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** और Google Ads से कनेक्शन शुरू करने के लिए **कनेक्ट** चुनें.</span><span class="sxs-lookup"><span data-stu-id="94dea-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="94dea-119">**Google Ads के साथ प्रमाणीकरण** चुनें और अपने Google Ads परिचय पत्र प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="94dea-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="94dea-120">**अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .</span><span class="sxs-lookup"><span data-stu-id="94dea-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Google Ads कनेक्शन के लिए निर्यात स्क्रीनशॉट":::

1. <span data-ttu-id="94dea-122">निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="94dea-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="94dea-123">कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="94dea-123">Configure the connector</span></span>

1. <span data-ttu-id="94dea-124">**डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है.</span><span class="sxs-lookup"><span data-stu-id="94dea-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="94dea-125">**पहले नाम** और **अंतिम नाम** फ़ील्ड के लिए एक ही कदम दोहराएं.</span><span class="sxs-lookup"><span data-stu-id="94dea-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="94dea-126">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="94dea-126">Select the segments you want to export.</span></span> <span data-ttu-id="94dea-127">आप कुल मिलाकर 1 मिलियन ग्राहक प्रोफ़ाइल को Google Ads में निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="94dea-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="94dea-128">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="94dea-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="94dea-129">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="94dea-129">Export the data</span></span>

<span data-ttu-id="94dea-130">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="94dea-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="94dea-131">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="94dea-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="94dea-132">Google Ads में अब आप [Google Ads ऑडियंस](https://support.google.com/google-ads/answer/7558048?hl=en/) के तहत अपने सेगमेंट पा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="94dea-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="94dea-133">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="94dea-133">Known limitations</span></span>

- <span data-ttu-id="94dea-134">Google Ads को प्रति निर्यात 1 मिलियन प्रोफ़ाइल तक.</span><span class="sxs-lookup"><span data-stu-id="94dea-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="94dea-135">Google Ads को निर्यात करना सेगमेंटों तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="94dea-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="94dea-136">प्रदाता पक्ष पर सीमाओं के कारण कुल 1 मिलियन प्रोफाइल वाले निर्यात खंडों में 5 मिनट तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="94dea-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="94dea-137">Google Ads में मिलान में 48 घंटे तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="94dea-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="94dea-138">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="94dea-138">Data privacy and compliance</span></span>

<span data-ttu-id="94dea-139">जब आप Dynamics 365 Customer Insights को Google Ads पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="94dea-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="94dea-140">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Google Ads विज्ञापन आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="94dea-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="94dea-141">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="94dea-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="94dea-142">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="94dea-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
