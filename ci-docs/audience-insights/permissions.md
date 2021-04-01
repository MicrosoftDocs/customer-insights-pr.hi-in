---
title: उपयोगकर्ता अनुमति प्रबंधित करें
description: उपयोगकर्ता भूमिकाएँ और अनुमतियों के बारे में जानें.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595704"
---
# <a name="user-permissions"></a><span data-ttu-id="616d3-103">उपयोगकर्ता की अनुमतियाँ</span><span class="sxs-lookup"><span data-stu-id="616d3-103">User permissions</span></span>

<span data-ttu-id="616d3-104">**अनुमतियां** पृष्ठ वह जगह है जहां आप ऑडियंस इनसाइट्स का उपयोग करने के लिए भूमिकाएं और अनुमतिएं सेट करेंगे.</span><span class="sxs-lookup"><span data-stu-id="616d3-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="616d3-105">पृष्ठ को देखने के लिए आपके पास व्यवस्थापक अनुमतियां होनी चाहिए.</span><span class="sxs-lookup"><span data-stu-id="616d3-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="616d3-106">ऑडियंस इनसाइट्स में अनुमति पृष्ठ तक पहुंचने के लिए, **व्यवस्थापक** > **अनुमतियों** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="616d3-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="616d3-107">भूमिकाएँ तीन प्रकार के होते हैं:</span><span class="sxs-lookup"><span data-stu-id="616d3-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="616d3-108">दर्शक</span><span class="sxs-lookup"><span data-stu-id="616d3-108">Viewer</span></span>

- <span data-ttu-id="616d3-109">**होम** और **सेगमेंट** पेज के अंतर्गत इनसाइट और सेगमेंट के बारे में जानकारी हासिल करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="616d3-110">**ग्राहक** पेज का उपयोग करके ग्राहक की प्रोफ़ाइलों की खोज करें और उन्हें फिल्टर करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="616d3-111">फ़ील्ड खोज योग्य होनी चाहिए.</span><span class="sxs-lookup"><span data-stu-id="616d3-111">Fields must be searchable.</span></span>
- <span data-ttu-id="616d3-112">**संवर्द्धन** पृष्ठ को देखें और अन्वेषण करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="616d3-113">**प्रविष्टियां** पेज का उपयोग करके इकाइयों का पता लगाएं और उन्हें एक्सपोर्ट करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="616d3-114">**सिस्टम** पेज का उपयोग करके सिस्टम प्रक्रियाओं की स्थिति देखें.</span><span class="sxs-lookup"><span data-stu-id="616d3-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="616d3-115">**सेगमेंट** पेज से निर्यात सेगमेंट.</span><span class="sxs-lookup"><span data-stu-id="616d3-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="616d3-116">**Power BI Customer Insights** डैशबोर्ड को इंस्टॉल और उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="616d3-117">योगदानकर्ता</span><span class="sxs-lookup"><span data-stu-id="616d3-117">Contributor</span></span>

- <span data-ttu-id="616d3-118">दर्शकों के लिए उपलब्ध सभी अनुमतियां.</span><span class="sxs-lookup"><span data-stu-id="616d3-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="616d3-119">**डेटा स्रोत** पृष्ठ का उपयोग करके डेटा लोड करें और रूपांतरित करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="616d3-120">*डेटा एकीकरण* अनुभाग (**मैप करें**, **मिलान करें**, और **मर्ज करें**) पूरे करें, जिनके परिणामस्वरूप एकीकृत ग्राहक प्रोफ़ाइल इकाई बनती है.</span><span class="sxs-lookup"><span data-stu-id="616d3-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="616d3-121">**संबंध** और **गतिविधियां** को परिभाषित करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="616d3-122">**अनुभागपृष्ठ** का उपयोग करके अनुभाग बनाएं.</span><span class="sxs-lookup"><span data-stu-id="616d3-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="616d3-123">**उपाय** पेज का उपयोग करके उपाय बनाएं.</span><span class="sxs-lookup"><span data-stu-id="616d3-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="616d3-124">कॉन्फ़िगरेशन प्रबंधित करें और **संवर्धन** पृष्ठ से ग्राहक प्रोफ़ाइल संवर्धित करें (केवल प्रथम पक्ष संवर्धन के लिए).</span><span class="sxs-lookup"><span data-stu-id="616d3-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="616d3-125">व्यवस्थापक</span><span class="sxs-lookup"><span data-stu-id="616d3-125">Administrator</span></span>

- <span data-ttu-id="616d3-126">योगदानकर्ताओं के लिए उपलब्ध सभी अनुमतियां.</span><span class="sxs-lookup"><span data-stu-id="616d3-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="616d3-127">कार्यशील भाषा को शामिल करके **सिस्टम** पेज पर सेटिंग बदलें और अपनी सिस्टम प्रक्रियाओं के लिए शेड्यूल रीफ़्रेश करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="616d3-128">अनुमति पेज का उपयोग करके **अनुमतियां** देखें और जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="616d3-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="616d3-129">खोज और फ़िल्टर संकेतपृष्ठ (**ग्राहक** पृष्ठ के माध्यम मिली) का उपयोग करके ग्राहक पृष्ठ के लिए **खोज और फ़िल्टर इंडेक्स** की परिभाषाएं सेट करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="616d3-130">**निर्यात स्थान** पृष्ठ का उपयोग करके Dynamics 365 Sales अनुभाग स्थान को परिभाषित करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="616d3-131">कॉन्फ़िगरेशन प्रबंधित करें और सभी ग्राहक प्रोफ़ाइल का **संवर्धन** पृष्ठ (सभी संवर्धन के लिए) से संवर्धन करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="616d3-132">**ग्राहक कार्ड एड-इन** इंस्टॉल करें और उसका उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="616d3-133">**Power Apps कनेक्टर** जोड़ें और उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="616d3-134">[Customer Insights APIs](apis.md) उपयोग को सक्षम करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="616d3-135">भूमिकाएं और अनुमतियां असाइन करें</span><span class="sxs-lookup"><span data-stu-id="616d3-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="616d3-136">ऑडियंस इनसाइट्स में, **व्यवस्थापक** > **अनुमतियाँ** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="616d3-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="616d3-137">**जोड़ें उपयोगकर्ताओं** को खोलने के लिए **ऐड/एडिट अनुमतियां** फलक चुनें.</span><span class="sxs-lookup"><span data-stu-id="616d3-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="616d3-138">Azure Active Directory उपयोगकर्ता या समूह को खोजने के लिए उन **खोज** फ़ील्ड का उपयोग करें, जिनकी अनुमतियां आप समायोजित करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="616d3-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="616d3-139">उस उपयोगकर्ता या समूह को असाइन करने के लिए **भूमिका** चुनें.</span><span class="sxs-lookup"><span data-stu-id="616d3-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="616d3-140">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="616d3-140">Select **Save**.</span></span> <span data-ttu-id="616d3-141">वर्तमान परिवेश स्वचालित रूप से उस उपयोगकर्ता या समूह के सदस्यों के साथ साझा किया जाएगा, जिनकी अनुमतियां आपने बदल दी हैं.</span><span class="sxs-lookup"><span data-stu-id="616d3-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="616d3-142">उपयोगकर्ता Customer Insights अनुप्रयोग तक पहुंच सकते हैं और अपनी निर्दिष्ट भूमिका के अनुसार काम कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="616d3-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="616d3-143">मौजूदा अनुमतियां देखें</span><span class="sxs-lookup"><span data-stu-id="616d3-143">View current permissions</span></span>

<span data-ttu-id="616d3-144">ऑडियंस इनसाइट्स में, यह देखने के लिए **व्यवस्थापक** > जाएं **अनुमतियां** यह देखने के लिए कि वर्तमान में कौन से रोल असाइनमेंट सक्रिय हैं.</span><span class="sxs-lookup"><span data-stu-id="616d3-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="616d3-145">**प्रकार** स्तंभ, एकल उपयोगकर्ता, समूह या ऐप्लिकेशन निर्दिष्ट करता है.</span><span class="sxs-lookup"><span data-stu-id="616d3-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="616d3-146">सिस्टम व्यक्तिगत उपयोगकर्ताओं और समूहों का समर्थन करता है.</span><span class="sxs-lookup"><span data-stu-id="616d3-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="616d3-147">भूमिकाएं, **भूमिका** स्तंभ के तहत निर्दिष्ट की जाती हैं.</span><span class="sxs-lookup"><span data-stu-id="616d3-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="616d3-148">उस स्तंभ के मान द्वारा परिणामों को सॉर्ट करने के लिए किसी भी स्तंभ शीर्षक का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="616d3-149">विशिष्ट उपयोगकर्ताओं का पता लगाने के लिए पृष्ठ के शीर्ष पर **खोज** फ़ील्ड का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="616d3-149">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]