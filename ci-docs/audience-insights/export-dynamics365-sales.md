---
title: Dynamics 365 Sales के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Dynamics 365 Sales को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759606"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="40f68-103">Dynamics 365 Sales (पूर्वावलोकन) में सेगमेंटों का उपयोग करें</span><span class="sxs-lookup"><span data-stu-id="40f68-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="40f68-104">अपने ग्राहक डेटा को मार्केटिंग सूची बनाने, कार्यप्रवाह के फ़ॉलो अप और Dynamics 365 Sales के साथ प्रचार भेजने के लिए इस्तेमाल करें.</span><span class="sxs-lookup"><span data-stu-id="40f68-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="40f68-105">कनेक्शन के लिए पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="40f68-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="40f68-106">इससे पहले कि आप Customer Insights से विक्रय में सेगमेंट निर्यात करें, संपर्क रिकॉर्ड Dynamics 365 Sales में मौजूद होने चाहिए.</span><span class="sxs-lookup"><span data-stu-id="40f68-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="40f68-107">[Common Data Services का उपयोग करके Dynamics 365 Sales](connect-power-query.md) में संपर्क कैसे अंतर्ग्रहण करने हैं, पर अधिक पढ़ें.</span><span class="sxs-lookup"><span data-stu-id="40f68-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="40f68-108">ऑडियंस इनसाइट्स से विक्रय में सेगमेंट को निर्यात करने से विक्रय इंस्टेंस में नए संपर्क रिकॉर्ड नहीं बनेंगे.</span><span class="sxs-lookup"><span data-stu-id="40f68-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="40f68-109">विक्रय से संपर्क रिकॉर्ड ऑडियंस इनसाइट्स में निहित होना चाहिए और डेटा स्रोत के रूप में उपयोग किए जाने चाहिए.</span><span class="sxs-lookup"><span data-stu-id="40f68-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="40f68-110">सेगमेंट को निर्यात करने से पहले ID से संपर्क करने के लिए ग्राहक ID को मैप करने के लिए उन्हें एकीकृत ग्राहक निकाय में शामिल करने की भी ज़रूरत है.</span><span class="sxs-lookup"><span data-stu-id="40f68-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="40f68-111">विक्रय के लिए कनेक्शन सेट करें</span><span class="sxs-lookup"><span data-stu-id="40f68-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="40f68-112">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="40f68-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="40f68-113">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Dynamics 365 Sales** चुनें.</span><span class="sxs-lookup"><span data-stu-id="40f68-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="40f68-114">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="40f68-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="40f68-115">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="40f68-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="40f68-116">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="40f68-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="40f68-117">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="40f68-117">Choose who can use this connection.</span></span> <span data-ttu-id="40f68-118">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="40f68-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="40f68-119">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="40f68-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="40f68-120">**सर्वर का पता** फ़ील्ड में अपने संगठन का बिक्री URL दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="40f68-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="40f68-121">**सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Sales खाता चुनें.</span><span class="sxs-lookup"><span data-stu-id="40f68-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="40f68-122">Dynamics 365 कॉन्टैक्ट ID पर ग्राहक ID फ़ील्ड का मैप करें.</span><span class="sxs-lookup"><span data-stu-id="40f68-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="40f68-123">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="40f68-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="40f68-124">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="40f68-124">Configure an export</span></span>

<span data-ttu-id="40f68-125">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="40f68-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="40f68-126">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="40f68-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="40f68-127">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="40f68-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="40f68-128">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="40f68-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="40f68-129">**निर्यात के लिए कनेक्शन** में, Dynamics 365 Sales अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="40f68-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="40f68-130">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="40f68-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="40f68-131">एक या अधिक सेगमेंट चुनें.</span><span class="sxs-lookup"><span data-stu-id="40f68-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="40f68-132">**सहेजें** चुनें</span><span class="sxs-lookup"><span data-stu-id="40f68-132">Select **Save**</span></span>

<span data-ttu-id="40f68-133">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="40f68-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="40f68-134">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="40f68-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="40f68-135">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="40f68-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
