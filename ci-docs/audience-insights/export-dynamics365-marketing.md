---
title: Dynamics 365 Marketing के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Dynamics 365 Marketing को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759639"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="be7fb-103">Dynamics 365 Marketing (पूर्वावलोकन) में सेगमेंट का उपयोग करें</span><span class="sxs-lookup"><span data-stu-id="be7fb-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="be7fb-104">अभियान उत्पन्न करने और Dynamics 365 Marketing वाले ग्राहकों के विशिष्ट समूहों से संपर्क करने के लिए [सेगमेंट](segments.md) का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="be7fb-105">अधिक जानकारी के लिए, देखें [Dynamics 365 Customer Insights से Dynamics 365 Marketing का उपयोग करें](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="be7fb-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="be7fb-106">कनेक्शन के लिए पहले से ज़रूरी चीजें</span><span class="sxs-lookup"><span data-stu-id="be7fb-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="be7fb-107">इससे पहले कि आप Customer Insights से मार्केटिंग में एक सेगमेंट निर्यात करें, संपर्क रिकॉर्ड Dynamics 365 Marketing में मौजूद होने चाहिए.</span><span class="sxs-lookup"><span data-stu-id="be7fb-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="be7fb-108">[Common Data Services का उपयोग करके Dynamics 365 Marketing](connect-power-query.md) में संपर्कों को कैसे अंतर्ग्रहण करना है, पर अधिक पढ़ें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="be7fb-109">ऑडियंस से मार्केटिंग तक सेगमेंट निर्यात करने से मार्केटिंग इंस्टेंस में नए संपर्क रिकॉर्ड नहीं बनेंगे.</span><span class="sxs-lookup"><span data-stu-id="be7fb-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="be7fb-110">मार्केटिंग से संपर्क रिकॉर्ड ऑडियंस इनसाइट्स में निहित होना चाहिए और डेटा स्रोत के रूप में उपयोग किए जाने चाहिए.</span><span class="sxs-lookup"><span data-stu-id="be7fb-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="be7fb-111">सेगमेंट को निर्यात करने से पहले ID से संपर्क करने के लिए ग्राहक ID को मैप करने के लिए उन्हें एकीकृत ग्राहक निकाय में शामिल करने की भी ज़रूरत है.</span><span class="sxs-lookup"><span data-stu-id="be7fb-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="be7fb-112">मार्केटिंग में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="be7fb-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="be7fb-113">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="be7fb-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="be7fb-114">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Dynamics 365 Marketing** चुनें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="be7fb-115">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="be7fb-116">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="be7fb-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="be7fb-117">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="be7fb-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="be7fb-118">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="be7fb-118">Choose who can use this connection.</span></span> <span data-ttu-id="be7fb-119">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="be7fb-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="be7fb-120">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="be7fb-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="be7fb-121">**सर्वर का पता** फ़ील्ड में अपने संगठन का मार्केटिंग URL दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="be7fb-122">**सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Marketing खाता चुनें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="be7fb-123">Dynamics 365 कॉन्टैक्ट ID पर ग्राहक ID फ़ील्ड का मैप करें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="be7fb-124">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="be7fb-125">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="be7fb-125">Configure an export</span></span>

<span data-ttu-id="be7fb-126">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="be7fb-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="be7fb-127">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="be7fb-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="be7fb-128">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="be7fb-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="be7fb-129">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="be7fb-130">**निर्यात के लिए कनेक्शन** में, Dynamics 365 Marketing अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="be7fb-131">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="be7fb-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="be7fb-132">एक या अधिक सेगमेंट चुनें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="be7fb-133">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="be7fb-133">Select **Save**.</span></span>

<span data-ttu-id="be7fb-134">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="be7fb-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="be7fb-135">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="be7fb-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="be7fb-136">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="be7fb-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
