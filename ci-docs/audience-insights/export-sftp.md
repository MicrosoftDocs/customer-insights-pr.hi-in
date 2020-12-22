---
title: SFTP होस्ट के लिए Customer Insights डेटा निर्यात करें
description: SFTP होस्ट पर कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643505"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="edf9c-103">SFTP के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="edf9c-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="edf9c-104">अपने ग्राहक डेटा का उपयोग तीसरे पक्ष के अनुप्रयोगों में एक सुरक्षित फ़ाइल हस्तांतरण प्रोटोकॉल (SFTP) होस्ट को निर्यात करके करें.</span><span class="sxs-lookup"><span data-stu-id="edf9c-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="edf9c-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="edf9c-105">Prerequisites</span></span>

- <span data-ttu-id="edf9c-106">SFTP होस्ट और संगत क्रेडेंशियल्स की उपलब्धता.</span><span class="sxs-lookup"><span data-stu-id="edf9c-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="edf9c-107">SFTP से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="edf9c-107">Connect to SFTP</span></span>

1. <span data-ttu-id="edf9c-108">**व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="edf9c-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="edf9c-109">**SFTP** के अंतर्गत, **सेट अप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="edf9c-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="edf9c-110">अपने गंतव्य-स्थल को **प्रदर्शन नाम** फील्ड में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="edf9c-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="edf9c-111">अपने SFTP खाते के लिए एक **उपयोगकर्ता नाम**, **पासवर्ड** और **होस्टनेम** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="edf9c-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="edf9c-112">उदाहरण: यदि आपके SFTP सर्वर का रूट फ़ोल्डर/रूट/फ़ोल्डर है, और आप चाहते हैं कि डेटा को/रूट/फ़ोल्डर/ci_export_destination_folder निर्यात किया जाए, तो मेजबान को sftp:///ci_export_destination_folder होना चाहिए " .</span><span class="sxs-lookup"><span data-stu-id="edf9c-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="edf9c-113">कनेक्शन का परीक्षण करने के लिए **सत्यापन करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="edf9c-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="edf9c-114">सफल सत्यापन के बाद, यह चुनें कि आप अपना डेटा **ज़िप** या **अनज़िप** करके निर्यात करना चाहते हैं, और निर्यात की गई फ़ाइलों के लिए **फ़ील्ड डिलिमिटर** चुनें.</span><span class="sxs-lookup"><span data-stu-id="edf9c-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="edf9c-115">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="edf9c-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="edf9c-116">निर्यात को कॉन्फ़िगर करना शुरू करने के लिए **अगला** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="edf9c-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="edf9c-117">कनेक्शन को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="edf9c-117">Configure the connection</span></span>

1. <span data-ttu-id="edf9c-118">वे **ग्राहक एट्रिब्यूट** चुनें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="edf9c-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="edf9c-119">आप एक या कई एट्रिब्यूट निर्यात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="edf9c-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="edf9c-120">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="edf9c-120">Select **Next**.</span></span>

1. <span data-ttu-id="edf9c-121">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="edf9c-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="edf9c-122">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="edf9c-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="edf9c-123">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="edf9c-123">Export the data</span></span>

<span data-ttu-id="edf9c-124">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="edf9c-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="edf9c-125">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="edf9c-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="edf9c-126">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="edf9c-126">Data privacy and compliance</span></span>

<span data-ttu-id="edf9c-127">जब आप Dynamics 365 Customer Insights को SFTP द्वारा डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="edf9c-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="edf9c-128">Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि निर्यात गंतव्य आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="edf9c-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="edf9c-129">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="edf9c-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="edf9c-130">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="edf9c-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
