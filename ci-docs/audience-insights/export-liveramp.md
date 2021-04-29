---
title: LiveRamp कनेक्टर
description: कनेक्शन को कॉन्फ़िगर करने और LiveRamp को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760329"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="b03b2-103">LiveRamp&reg; को निर्यात खंड (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="b03b2-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="b03b2-104">डिजिटल, सोशल और टीवी पर 500 से अधिक प्लेटफार्मों के साथ जुड़ने के लिए LiveRamp में अपने डेटा को सक्रिय करें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="b03b2-105">विज्ञापन अभियानों को लक्षित करने, दबाने और निजीकृत करने के लिए LiveRamp में अपने डेटा के साथ काम करें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b03b2-106">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="b03b2-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="b03b2-107">इस कनेक्टर का उपयोग करने के लिए आपको एक LiveRamp सदस्यता की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="b03b2-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="b03b2-108">सदस्यता पाने के लिए, सीधे [LiveRamp से संपर्क करें](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="b03b2-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="b03b2-109">[LiveRamp ऑनबोर्डिंग के बारे में अधिक जानें](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="b03b2-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="b03b2-110">LiveRamp में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="b03b2-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="b03b2-111">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="b03b2-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b03b2-112">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **LiveRamp** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="b03b2-113">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b03b2-114">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="b03b2-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b03b2-115">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="b03b2-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b03b2-116">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="b03b2-116">Choose who can use this connection.</span></span> <span data-ttu-id="b03b2-117">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="b03b2-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b03b2-118">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b03b2-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b03b2-119">अपने LiveRamp सुरक्षित FTP (SFTP) खाते के लिए **उपयोगकर्ता** और **पासवर्ड** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="b03b2-120">ये क्रेडेंशियल्स आपके LiveRamp ऑनबोर्डिंग क्रेडेंशियल्स से अलग हो सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b03b2-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="b03b2-121">LiveRamp के कनेक्शन का परीक्षण करने के लिए **सत्यापित करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="b03b2-122">सफल सत्यापन के बाद,  **मैं सहमत हूं**  चेकबॉक्स का चयन करके **डेटा गोपनीयता और अनुपालन** के लिए अपनी सहमति प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="b03b2-123">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b03b2-124">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="b03b2-124">Configure an export</span></span>

<span data-ttu-id="b03b2-125">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b03b2-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b03b2-126">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b03b2-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b03b2-127">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="b03b2-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b03b2-128">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b03b2-129">**निर्यात के लिए कनेक्शन** में, LiveRamp अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="b03b2-130">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="b03b2-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b03b2-131">**अपना प्रमुख पहचानकर्ता चुनें** फ़ील्ड में, पहचान विश्लेषण के लिए LiveRamp पर भेजने के लिए **ईमेल**, **नाम और पता** , या **फोन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b03b2-132">![एट्रिब्यूट मैपिंग के साथ LiveRamp कनेक्टर](media/export-liveramp-segments.png "एट्रिब्यूट मैपिंग के साथ LiveRamp कनेक्टर")</span><span class="sxs-lookup"><span data-stu-id="b03b2-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="b03b2-133">चयनित मुख्य पहचानकर्ता के लिए अपने एकीकृत ग्राहक निकाय से संबंधित एट्रिब्यूट्स को मैप करें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="b03b2-134">LiveRamp को भेजने के लिए अधिक विशेषताओं को मैप करने के लिए **विशेषता जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="b03b2-135">LiveRamp के लिए अधिक महत्वपूर्ण पहचानकर्ता एट्रिब्यूट को भेजने से आपको उच्च मैच दर मिलने की संभावना है.</span><span class="sxs-lookup"><span data-stu-id="b03b2-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="b03b2-136">उन सेगमेंट का चयन करें, जिन्हें आप LiveRamp को निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="b03b2-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="b03b2-137">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-137">Select **Save**.</span></span>

<span data-ttu-id="b03b2-138">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="b03b2-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b03b2-139">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="b03b2-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b03b2-140">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b03b2-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b03b2-141">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="b03b2-141">Data privacy and compliance</span></span>

<span data-ttu-id="b03b2-142">जब आप Dynamics 365 Customer Insights को Liveramp पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="b03b2-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b03b2-143">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Liveramp आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="b03b2-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b03b2-144">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="b03b2-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b03b2-145">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="b03b2-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
