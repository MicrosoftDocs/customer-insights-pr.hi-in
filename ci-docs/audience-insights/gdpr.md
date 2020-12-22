---
title: GDPR के तहत डेटा सब्जेक्ट राइट्स(DSR) अनुरोध | Microsoft Docs
description: Dynamics 365 Customer Insights ऑडिएंस इनसाइट्स क्षमता के लिए डेटा विषय अनुरोधों का जवाब दें.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405952"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="f0290-103">GDPR के तहत डेटा विषय अधिकार (DSR) अनुरोध</span><span class="sxs-lookup"><span data-stu-id="f0290-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="f0290-104">जीडीपीआर डेटा विषय का जवाब देते हुए Dynamics 365 Customer Insights ऑडियंस इनसाइट्स क्षमता के अनुरोधों को हटाएं</span><span class="sxs-lookup"><span data-stu-id="f0290-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="f0290-105">“मिटाने का अधिकार” किसी संगठन के ग्राहक डेटा से व्यक्तिगत डेटा को हटाना जनरल डेटा प्रोटेक्शन रेग्यूलेशन (GDPR) में एक महत्वपूर्ण सुरक्षा है.</span><span class="sxs-lookup"><span data-stu-id="f0290-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="f0290-106">व्यक्तिगत डेटा निकालने में सभी व्यक्तिगत डेटा और सिस्टम-जनरेटेड लॉग निकालना शामिल है, जिनमें ऑडिट लॉग जानकारी शामिल नहीं है.</span><span class="sxs-lookup"><span data-stu-id="f0290-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="f0290-107">डेटा विषय हटाएं अनुरोध प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="f0290-107">Manage data subject delete requests</span></span>

<span data-ttu-id="f0290-108">ऑडियंस इनसाइट्स किसी विशिष्ट ग्राहक या उपयोगकर्ता के लिए व्यक्तिगत डेटा को हटाने के लिए निम्नलिखित इन-प्रोडक्ट अनुभव प्रदान करता है:</span><span class="sxs-lookup"><span data-stu-id="f0290-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="f0290-109">**ग्राहक डेटा के लिए अनुरोध हटाएं प्रबंधित करें**: Customer Insights में ग्राहक डेटा मूल डेटा स्रोतों से बाहरी Customer Insights तक पहुंचाया जाता है.</span><span class="sxs-lookup"><span data-stu-id="f0290-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="f0290-110">सभी GDPR हटाने के अनुरोधों को मूल डेटा स्रोत में पूरा किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="f0290-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="f0290-111">**ग्राहक इनसाइट उपयोगकर्ता डेटा के लिए हटाने के अनुरोधों का प्रबंधन करें**: उपयोगकर्ताओं के लिए डेटा Customer Insights द्वारा बनाया गया है.</span><span class="sxs-lookup"><span data-stu-id="f0290-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="f0290-112">सभी GDPR हटाने के अनुरोधों को Customer Insights में पूरा किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="f0290-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="f0290-113">ग्राहक डेटा के लिए अनुरोध हटाएं प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="f0290-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="f0290-114">Customer Insights व्यवस्थापक डेटा स्रोत में हटाए गए ग्राहक डेटा हटाने के लिए इन चरणों का पालन कर सकते हैं:</span><span class="sxs-lookup"><span data-stu-id="f0290-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="f0290-115">Dynamics 365 Customer Insights में साइन इन करें.</span><span class="sxs-lookup"><span data-stu-id="f0290-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="f0290-116">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं</span><span class="sxs-lookup"><span data-stu-id="f0290-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="f0290-117">सूची में प्रत्येक डेटा स्रोत के लिए जिसमें ग्राहक डेटा हटा दिया गया है:</span><span class="sxs-lookup"><span data-stu-id="f0290-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="f0290-118">(...) का चयन करें और फिर **रिफ़्रेश करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f0290-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="f0290-119">**स्थिति** के तहत डेटा स्रोत की स्थिति की जाँच करें.</span><span class="sxs-lookup"><span data-stu-id="f0290-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="f0290-120">चेक मार्क का मतलब है कि रिफ्रेश सफल था.</span><span class="sxs-lookup"><span data-stu-id="f0290-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="f0290-121">चेतावनी त्रिकोण का मतलब कुछ गलत हो गया.</span><span class="sxs-lookup"><span data-stu-id="f0290-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="f0290-122">यदि चेतावनी त्रिकोण प्रदर्शित होता है, तो D365CI@microsoft.com से संपर्क करें.</span><span class="sxs-lookup"><span data-stu-id="f0290-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f0290-123">![ग्राहक डेटा के लिए GDPR हटाने के अनुरोधों को संभालना](media/gdpr-data-sources.png "ग्राहक डेटा के लिए GDPR हटाने के अनुरोधों को संभालना")</span><span class="sxs-lookup"><span data-stu-id="f0290-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="f0290-124">उपयोगकर्ता डेटा के लिए अनुरोध हटाएं प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="f0290-124">Manage delete requests for user data</span></span>

<span data-ttu-id="f0290-125">एक Customer Insights व्यवस्थापक Customer Insights उपयोगकर्ता डेटा को हटाने के लिए इन चरणों का पालन कर सकता है:</span><span class="sxs-lookup"><span data-stu-id="f0290-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="f0290-126">Dynamics 365 Customer Insights में साइन इन करें.</span><span class="sxs-lookup"><span data-stu-id="f0290-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="f0290-127">ऑडियंस इनसाइट्स में, **व्यवस्थापक** > **अनुमतियाँ** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="f0290-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="f0290-128">उस उपयोगकर्ता के लिए चेक बॉक्स चुनें जिसे आप हटाना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="f0290-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="f0290-129">**निकालें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f0290-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f0290-130">![जीडीपीआर से अनुरोधों को हटाएं अनुरोधों को संभालना](media/gdpr-permissions.png "जीडीपीआर को उपयोगकर्ता डेटा के लिए हटाने के अनुरोधों को संभालना")</span><span class="sxs-lookup"><span data-stu-id="f0290-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="f0290-131">जीडीपीआर डेटा विषय निर्यात अनुरोधों का जवाब देना</span><span class="sxs-lookup"><span data-stu-id="f0290-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="f0290-132">जनरल डेटा प्रोटेक्शन रेग्यूलेशन (GDPR) के लिए आपकी यात्रा पर आपके साथ भागीदारी करने के लिए हमारी प्रतिबद्धता के हिस्से के रूप में, हमने आपको तैयार करने में मदद करने के लिए दस्तावेज विकसित किए हैं.</span><span class="sxs-lookup"><span data-stu-id="f0290-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="f0290-133">यह दस्तावेज़ीकरण उन कदमों का वर्णन करता है जो आप ऑडियंस इनसाइट्स का उपयोग करते समय जीडीपीआर अनुपालन का समर्थन करने के लिए आज ले सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f0290-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="f0290-134">एक्सपोर्ट प्रबंधित करें और अनुरोध देखें</span><span class="sxs-lookup"><span data-stu-id="f0290-134">Manage export and view requests</span></span>

<span data-ttu-id="f0290-135">डेटा पोर्टेबिलिटी का अधिकार एक इलेक्ट्रॉनिक प्रारूप व्यक्तिगत डेटा की एक प्रति का अनुरोध करने की अनुमति देता है("एक संरचित, आमतौर पर इस्तेमाल किया जाने वाला, मशीन पठनीय और इंटरऑपरेबल प्रारूप")जिसे दूसरे डेटा कंट्रोलर को प्रेषित किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="f0290-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="f0290-136">ग्राहक डेटा (टेनेंट व्यवस्थापक) निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="f0290-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="f0290-137">एक टेनेंट व्यवस्थापक डेटा एक्सपोर्ट करने के लिए इन चरणों का पालन कर सकता है:</span><span class="sxs-lookup"><span data-stu-id="f0290-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="f0290-138">अनुरोध में ग्राहक के ईमेल पते को निर्दिष्ट करते हुए D365CI@microsoft.com पर एक ईमेल भेजें.</span><span class="sxs-lookup"><span data-stu-id="f0290-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="f0290-139">Customer Insights टीम पंजीकृत टेनेंट व्यवस्थापक ईमेल पते पर एक ईमेल भेजेगी, जिसमें डेटा निर्यात करने के लिए पुष्टि की मांग की जाएगी.</span><span class="sxs-lookup"><span data-stu-id="f0290-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="f0290-140">अनुरोधित ग्राहक के लिए डेटा एक्सपोर्ट करने की पुष्टि को स्वीकार करें.</span><span class="sxs-lookup"><span data-stu-id="f0290-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="f0290-141">टेनेंट व्यवस्थापक ईमेल पते के माध्यम से एक्सपोर्ट किए गए डेटा प्राप्त करें.</span><span class="sxs-lookup"><span data-stu-id="f0290-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="f0290-142">उपयोगकर्ता डेटा (टेनेंट व्यवस्थापक) एक्सपोर्ट करें</span><span class="sxs-lookup"><span data-stu-id="f0290-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="f0290-143">अनुरोध में उपयोगकर्ता के ईमेल पते को निर्दिष्ट करते हुए D365CI@microsoft.com पर एक ईमेल भेजें.</span><span class="sxs-lookup"><span data-stu-id="f0290-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="f0290-144">Customer Insights टीम पंजीकृत टेनेंट व्यवस्थापक ईमेल पते पर एक ईमेल भेजेगी, जिसमें डेटा निर्यात करने के लिए पुष्टि की मांग की जाएगी.</span><span class="sxs-lookup"><span data-stu-id="f0290-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="f0290-145">अनुरोधित उपयोगकर्ता के लिए डेटा एक्सपोर्ट करने की पुष्टि को स्वीकार करें.</span><span class="sxs-lookup"><span data-stu-id="f0290-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="f0290-146">टेनेंट व्यवस्थापक ईमेल पते के माध्यम से एक्सपोर्ट किए गए डेटा प्राप्त करें.</span><span class="sxs-lookup"><span data-stu-id="f0290-146">Receive the exported data through the tenant admin email address.</span></span>
