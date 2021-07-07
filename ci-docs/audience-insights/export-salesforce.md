---
title: Salesforce मार्केटिंग क्लाउड में Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Salesforce Marketing Cloud को निर्यात करने का तरीका जानें।
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314621"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="f1bae-103">Salesforce Marketing Cloud में निर्यात अनुभाग और अन्य डेटा (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="f1bae-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="f1bae-104">Salesforce Marketing Cloud में अपने ग्राहक डेटा को सुरक्षित फ़ाइल स्थानांतरण प्रोटोकॉल (SFTP) स्थान के माध्यम से निर्यात करके उपयोग करें।</span><span class="sxs-lookup"><span data-stu-id="f1bae-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="f1bae-105">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="f1bae-105">Prerequisites for connection</span></span>

- <span data-ttu-id="f1bae-106">एक SFTP होस्ट और संबंधित व्यवस्थापक क्रेडेंशियल की उपलब्धता।</span><span class="sxs-lookup"><span data-stu-id="f1bae-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="f1bae-107">Salesforce मार्केटिंग क्लाउड के लिए SFTP लोकेशन सेट करने का तरीका जानें</span><span class="sxs-lookup"><span data-stu-id="f1bae-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="f1bae-108">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="f1bae-108">Known limitations</span></span>

- <span data-ttu-id="f1bae-109">निर्यात का रनटाइम आपके सिस्टम के प्रदर्शन पर निर्भर करता है.</span><span class="sxs-lookup"><span data-stu-id="f1bae-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="f1bae-110">हम आपके सर्वर के न्यूनतम कॉन्फ़िगरेशन के रूप में दो CPU कोर और 1 Gb मेमोरी की सलाह देते हैं.</span><span class="sxs-lookup"><span data-stu-id="f1bae-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="f1bae-111">अनुशंसित न्यूनतम कॉन्फ़िगरेशन का उपयोग करते समय 100 मिलियन ग्राहक प्रोफ़ाइल तक निर्यात करने वाली निकायों को 90 मिनट लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f1bae-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="f1bae-112">Salesforce Marketing Cloud से कनेक्शन सेट करें</span><span class="sxs-lookup"><span data-stu-id="f1bae-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="f1bae-113">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="f1bae-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f1bae-114">कनेक्शन को कॉन्फ़िगर करने के लिए **कनेक्शन जोड़ें** चुनें और **Salesforce मार्केटिंग क्लाउड** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f1bae-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="f1bae-115">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="f1bae-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f1bae-116">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="f1bae-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f1bae-117">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="f1bae-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f1bae-118">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="f1bae-118">Choose who can use this connection.</span></span> <span data-ttu-id="f1bae-119">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="f1bae-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f1bae-120">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f1bae-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f1bae-121">अपने SFTP खाते के लिए **उपयोगकर्ता नाम**, **पासवर्ड**, **होस्टनाम** और **निर्यात फ़ोल्डर** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="f1bae-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="f1bae-122">कनेक्शन का परीक्षण करने के लिए **सत्यापन करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f1bae-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="f1bae-123">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f1bae-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f1bae-124">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f1bae-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f1bae-125">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="f1bae-125">Configure an export</span></span>

<span data-ttu-id="f1bae-126">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f1bae-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f1bae-127">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f1bae-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f1bae-128">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="f1bae-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f1bae-129">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f1bae-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f1bae-130">**निर्यात के लिए कनेक्शन** में, SFTP अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f1bae-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="f1bae-131">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="f1bae-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f1bae-132">अगर आप निर्यात की गई फ़ाइलों के लिए अपने डेटा **ज़िप** या **अनज़िप** और **फ़ील्ड डिलिमिटर** का निर्यात करना चाहते हैं तो चुनें.</span><span class="sxs-lookup"><span data-stu-id="f1bae-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="f1bae-133">निकायों का चयन करें, उदाहरण के लिए वे सेगमेंट जिनका आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="f1bae-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f1bae-134">प्रत्येक चयनित निकाय को निर्यात किए जाने पर पांच आउटपुट फाइलों में विभाजित किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="f1bae-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="f1bae-135">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f1bae-135">Select **Save**.</span></span>

<span data-ttu-id="f1bae-136">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="f1bae-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f1bae-137">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="f1bae-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f1bae-138">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f1bae-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="f1bae-139">Salesforce Marketing Cloud में SFTP स्थान से Customer Insights डेटा आयात करें</span><span class="sxs-lookup"><span data-stu-id="f1bae-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="f1bae-140">Customer Insights डेटा फ़ाइल को SFTP स्थान से आयात करने के लिए [Salesforce Marketing Cloud में डेटा एक्सटेंशन](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) बनाएँ।</span><span class="sxs-lookup"><span data-stu-id="f1bae-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="f1bae-141">Salesforce मार्केटिंग क्लाउड डेटा एक्सटेंशन में [SFTP स्थान से डेटा आयात करें](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)।</span><span class="sxs-lookup"><span data-stu-id="f1bae-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="f1bae-142">डेटा एक्सटेंशन में डेटा आयात करने के लिए स्वचालन सेट करें।</span><span class="sxs-lookup"><span data-stu-id="f1bae-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="f1bae-143">[फ़ाइल ड्रॉप ऑटोमेशन और शेड्यूल्ड ऑटोमेशन](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) के बारे में अधिक जानें।</span><span class="sxs-lookup"><span data-stu-id="f1bae-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="f1bae-144">एक [ फ़ाइल ड्रॉप स्वचालन](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) या [ अनुसूचित स्वचालन ](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) को परिभाषित करें।</span><span class="sxs-lookup"><span data-stu-id="f1bae-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="f1bae-145">[SFTP के साथ स्वचालन ](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) का यहाँ एक उदाहरण है।</span><span class="sxs-lookup"><span data-stu-id="f1bae-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f1bae-146">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="f1bae-146">Data privacy and compliance</span></span>

<span data-ttu-id="f1bae-147">जब आप Dynamics 365 Customer Insights को SFTP द्वारा डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="f1bae-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f1bae-148">Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि निर्यात गंतव्य आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="f1bae-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f1bae-149">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="f1bae-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f1bae-150">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="f1bae-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
