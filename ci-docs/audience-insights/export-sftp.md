---
title: SFTP होस्ट के लिए Customer Insights डेटा निर्यात करें
description: SFTP होस्ट पर कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598387"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="fbd86-103">SFTP के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="fbd86-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="fbd86-104">अपने ग्राहक डेटा का उपयोग तीसरे पक्ष के अनुप्रयोगों में एक सुरक्षित फ़ाइल हस्तांतरण प्रोटोकॉल (SFTP) होस्ट को निर्यात करके करें.</span><span class="sxs-lookup"><span data-stu-id="fbd86-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fbd86-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="fbd86-105">Prerequisites</span></span>

- <span data-ttu-id="fbd86-106">एक SFTP होस्ट और संबंधित क्रेडेंशियल्स की उपलब्धता.</span><span class="sxs-lookup"><span data-stu-id="fbd86-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="fbd86-107">SFTP से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="fbd86-107">Connect to SFTP</span></span>

1. <span data-ttu-id="fbd86-108">**व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="fbd86-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fbd86-109">**SFTP** के अंतर्गत, **सेट अप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fbd86-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="fbd86-110">अपने गंतव्य-स्थल को **प्रदर्शन नाम** फील्ड में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="fbd86-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="fbd86-111">अपने SFTP खाते के लिए **उपयोगकर्ता नाम**, **पासवर्ड**, **होस्टनाम** और **निर्यात फ़ोल्डर** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="fbd86-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="fbd86-112">कनेक्शन का परीक्षण करने के लिए **सत्यापन करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fbd86-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="fbd86-113">सफल सत्यापन के बाद, चुनें कि क्या आप अपना डेटा **जिप किया गया** या **बिना जिप किया गया** निर्यात करना चाहते हैं और निर्यात की गई फ़ाइलों के लिए **फ़ील्ड परिसीमन** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fbd86-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="fbd86-114">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fbd86-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fbd86-115">निर्यात को कॉन्फ़िगर करना शुरू करने के लिए **अगला** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fbd86-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="fbd86-116">निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="fbd86-116">Configure the export</span></span>

1. <span data-ttu-id="fbd86-117">निकायों का चयन करें, उदाहरण के लिए वे सेगमेंट जिनका आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="fbd86-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fbd86-118">प्रत्येक चयनित निकाय निर्यात होने पर पांच आउटपुट फ़ाइलों तक होगा.</span><span class="sxs-lookup"><span data-stu-id="fbd86-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="fbd86-119">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fbd86-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fbd86-120">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="fbd86-120">Export the data</span></span>

<span data-ttu-id="fbd86-121">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fbd86-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="fbd86-122">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fbd86-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fbd86-123">ज्ञात सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="fbd86-123">Known limitations</span></span>

- <span data-ttu-id="fbd86-124">निर्यात का रनटाइम आपके सिस्टम के प्रदर्शन पर निर्भर करता है.</span><span class="sxs-lookup"><span data-stu-id="fbd86-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="fbd86-125">हम आपके सर्वर के न्यूनतम कॉन्फ़िगरेशन के रूप में दो CPU कोर और 1 Gb मेमोरी की सलाह देते हैं.</span><span class="sxs-lookup"><span data-stu-id="fbd86-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="fbd86-126">दो CPU कोर और मेमोरी के 1 Gb के अनुशंसित न्यूनतम कॉन्फ़िगरेशन का उपयोग करके 100 मिलियन ग्राहक प्रोफ़ाइल के साथ निर्यात करने वाले निकायों को 90 मिनट लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fbd86-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fbd86-127">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="fbd86-127">Data privacy and compliance</span></span>

<span data-ttu-id="fbd86-128">जब आप Dynamics 365 Customer Insights को SFTP द्वारा डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="fbd86-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fbd86-129">Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि निर्यात गंतव्य आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="fbd86-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fbd86-130">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="fbd86-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fbd86-131">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="fbd86-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]