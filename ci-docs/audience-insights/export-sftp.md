---
title: SFTP होस्ट के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और SFTP स्थान को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760421"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="8ee2d-103">अनुभाग सूचियां और अन्य डेटा को SFTP (पूर्वावलोकन) में निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="8ee2d-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="8ee2d-104">अपने ग्राहक डेटा का उपयोग तीसरे पक्ष के अनुप्रयोगों में सुरक्षित फ़ाइल ट्रांसफर प्रोटोकॉल (SFTP) लोकेशन पर निर्यात करके करें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="8ee2d-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="8ee2d-105">Prerequisites for connection</span></span>

- <span data-ttu-id="8ee2d-106">एक SFTP होस्ट और संबंधित क्रेडेंशियल्स की उपलब्धता.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8ee2d-107">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="8ee2d-107">Known limitations</span></span>

- <span data-ttu-id="8ee2d-108">निर्यात का रनटाइम आपके सिस्टम के प्रदर्शन पर निर्भर करता है.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="8ee2d-109">हम आपके सर्वर के न्यूनतम कॉन्फ़िगरेशन के रूप में दो CPU कोर और 1 Gb मेमोरी की सलाह देते हैं.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="8ee2d-110">दो CPU कोर और मेमोरी के 1 Gb के अनुशंसित न्यूनतम कॉन्फ़िगरेशन का उपयोग करके 100 मिलियन ग्राहक प्रोफ़ाइल के साथ निर्यात करने वाले निकायों को 90 मिनट लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="8ee2d-111">SFTP में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="8ee2d-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="8ee2d-112">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8ee2d-113">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **SFTP** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="8ee2d-114">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8ee2d-115">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8ee2d-116">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="8ee2d-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8ee2d-117">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-117">Choose who can use this connection.</span></span> <span data-ttu-id="8ee2d-118">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8ee2d-119">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8ee2d-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8ee2d-120">अपने SFTP खाते के लिए **उपयोगकर्ता नाम**, **पासवर्ड**, **होस्टनाम** और **निर्यात फ़ोल्डर** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="8ee2d-121">कनेक्शन का परीक्षण करने के लिए **सत्यापन करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="8ee2d-122">अगर आप निर्यात की गई फ़ाइलों के लिए अपने डेटा **ज़िप** या **अनज़िप** और **फ़ील्ड डिलिमिटर** का निर्यात करना चाहते हैं तो चुनें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="8ee2d-123">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8ee2d-124">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8ee2d-125">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="8ee2d-125">Configure an export</span></span>

<span data-ttu-id="8ee2d-126">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8ee2d-127">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8ee2d-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8ee2d-128">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8ee2d-129">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8ee2d-130">**निर्यात के लिए कनेक्शन** में, SFTP अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="8ee2d-131">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8ee2d-132">निकायों का चयन करें, उदाहरण के लिए वे सेगमेंट जिनका आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8ee2d-133">प्रत्येक चयनित निकाय को निर्यात किए जाने पर पांच आउटपुट फाइलों में विभाजित किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="8ee2d-134">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-134">Select **Save**.</span></span>

<span data-ttu-id="8ee2d-135">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8ee2d-136">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8ee2d-137">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8ee2d-138">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="8ee2d-138">Data privacy and compliance</span></span>

<span data-ttu-id="8ee2d-139">जब आप Dynamics 365 Customer Insights को SFTP द्वारा डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8ee2d-140">Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि निर्यात गंतव्य आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8ee2d-141">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8ee2d-142">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="8ee2d-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
