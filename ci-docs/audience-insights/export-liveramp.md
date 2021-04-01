---
title: LiveRamp कनेक्टर
description: LiveRamp को डेटा निर्यात करना सीखें.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597559"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="afc70-103">LiveRamp&reg; कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="afc70-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="afc70-104">डिजिटल, सोशल और TV इकोसिस्टम में 500 से अधिक मंचों से जुड़ने के लिए अपने डेटा को LiveRamp में सक्रिय करें.</span><span class="sxs-lookup"><span data-stu-id="afc70-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="afc70-105">विज्ञापन अभियानों को लक्षित करने, दबाने और निजीकृत करने के लिए LiveRamp में अपने डेटा के साथ काम करें.</span><span class="sxs-lookup"><span data-stu-id="afc70-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="afc70-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="afc70-106">Prerequisites</span></span>

- <span data-ttu-id="afc70-107">इस कनेक्टर का उपयोग करने के लिए आपको एक LiveRamp सदस्यता की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="afc70-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="afc70-108">सदस्यता पाने के लिए, सीधे [LiveRamp से संपर्क करें](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="afc70-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="afc70-109">[LiveRamp ऑनबोर्डिंग के बारे में अधिक जानें](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="afc70-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="afc70-110">LiveRamp से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="afc70-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="afc70-111">ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="afc70-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="afc70-112">**LiveRamp** टाइल में, **सेट अप** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="afc70-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="afc70-113">अपने गंतव्य-स्थल को **प्रदर्शन नाम** फील्ड में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="afc70-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="afc70-114">अपने LiveRamp सुरक्षित FTP (SFTP) खाते के लिए **उपयोगकर्ता** और **पासवर्ड** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="afc70-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="afc70-115">ये क्रेडेंशियल्स आपके LiveRamp ऑनबोर्डिंग क्रेडेंशियल्स से अलग हो सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="afc70-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="afc70-116">LiveRamp के कनेक्शन का परीक्षण करने के लिए **सत्यापित करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="afc70-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="afc70-117">सफल सत्यापन के बाद,  **मैं सहमत हूं**  चेकबॉक्स का चयन करके **डेटा गोपनीयता और अनुपालन** के लिए अपनी सहमति प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="afc70-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="afc70-118">LiveRamp कनेक्टर स्थापित करने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="afc70-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="afc70-119">कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="afc70-119">Configure the connector</span></span>

1. <span data-ttu-id="afc70-120">**अपना प्रमुख पहचानकर्ता चुनें** फ़ील्ड में, पहचान विश्लेषण के लिए LiveRamp पर भेजने के लिए **ईमेल**, **नाम और पता** , या **फोन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="afc70-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="afc70-121">चयनित मुख्य पहचानकर्ता के लिए अपने एकीकृत ग्राहक निकाय से संबंधित एट्रिब्यूट्स को मैप करें.</span><span class="sxs-lookup"><span data-stu-id="afc70-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="afc70-122">LiveRamp को भेजने के लिए अतिरिक्त एट्रिब्यूट्स को मैप करने के लिए  **एट्रिब्यूट जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="afc70-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="afc70-123">LiveRamp के लिए अधिक महत्वपूर्ण पहचानकर्ता एट्रिब्यूट को भेजने से आपको उच्च मैच दर मिलने की संभावना है.</span><span class="sxs-lookup"><span data-stu-id="afc70-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="afc70-124">उन सेगमेंट का चयन करें, जिन्हें आप LiveRamp को निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="afc70-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="afc70-125">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="afc70-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="afc70-126">![एट्रिब्यूट मैपिंग के साथ LiveRamp कनेक्टर](media/export-liveramp-segments.png "एट्रिब्यूट मैपिंग के साथ LiveRamp कनेक्टर")</span><span class="sxs-lookup"><span data-stu-id="afc70-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="afc70-127">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="afc70-127">Export the data</span></span>

<span data-ttu-id="afc70-128">यदि निर्यात के लिए सभी पूर्वअपेक्षाएँ पूरी हो गई हैं तो निर्यात शीघ्र ही शुरू हो जाएगा.</span><span class="sxs-lookup"><span data-stu-id="afc70-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="afc70-129">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="afc70-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="afc70-130">एक बार सफलतापूर्वक निर्यात पूरा हो जाने के बाद, आप अपने डेटा को सक्रिय और वितरित करने के लिए LiveRamp ऑनबोर्डिंग में साइन इन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="afc70-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="afc70-131">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="afc70-131">Data privacy and compliance</span></span>

<span data-ttu-id="afc70-132">जब आप Dynamics 365 Customer Insights को Liveramp पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="afc70-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="afc70-133">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Liveramp आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="afc70-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="afc70-134">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="afc70-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="afc70-135">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="afc70-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]