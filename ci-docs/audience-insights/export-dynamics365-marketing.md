---
title: Dynamics 365 Marketing के लिए Customer Insights डेटा निर्यात करें
description: Dynamics 365 Marketing से कनेक्शन कॉन्फ़िगर करना सीखें.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269056"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="70973-103">Dynamics 365 Marketing के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="70973-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="70973-104">अभियान उत्पन्न करने और Dynamics 365 Marketing वाले ग्राहकों के विशिष्ट समूहों से संपर्क करने के लिए [सेगमेंट](segments.md) का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="70973-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="70973-105">अधिक जानकारी के लिए, देखें [Dynamics 365 Customer Insights से Dynamics 365 Marketing का उपयोग करें](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="70973-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="70973-106">पूर्वावश्यकता</span><span class="sxs-lookup"><span data-stu-id="70973-106">Prerequisite</span></span>

- <span data-ttu-id="70973-107">इससे पहले कि आप Customer Insights से मार्केटिंग में एक सेगमेंट निर्यात करें, संपर्क रिकॉर्ड Dynamics 365 Marketing में मौजूद होने चाहिए.</span><span class="sxs-lookup"><span data-stu-id="70973-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="70973-108">[Common Data Services का उपयोग करके Dynamics 365 Marketing](connect-power-query.md) में संपर्कों को कैसे अंतर्ग्रहण करना है, पर अधिक पढ़ें.</span><span class="sxs-lookup"><span data-stu-id="70973-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="70973-109">ऑडियंस से मार्केटिंग तक सेगमेंट निर्यात करने से मार्केटिंग इंस्टेंस में नए संपर्क रिकॉर्ड नहीं बनेंगे.</span><span class="sxs-lookup"><span data-stu-id="70973-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="70973-110">मार्केटिंग से संपर्क रिकॉर्ड ऑडियंस इनसाइट्स में निहित होना चाहिए और डेटा स्रोत के रूप में उपयोग किए जाने चाहिए.</span><span class="sxs-lookup"><span data-stu-id="70973-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="70973-111">सेगमेंट को निर्यात करने से पहले ID से संपर्क करने के लिए ग्राहक ID को मैप करने के लिए उन्हें एकीकृत ग्राहक निकाय में शामिल करने की भी ज़रूरत है.</span><span class="sxs-lookup"><span data-stu-id="70973-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="70973-112">मार्केटिंग के लिए कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="70973-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="70973-113">ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="70973-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="70973-114">**Dynamics 365 Marketing** के तहत, **सेट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="70973-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="70973-115">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="70973-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="70973-116">**सर्वर का पता** फ़ील्ड में अपने संगठन का मार्केटिंग URL दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="70973-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="70973-117">**सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Marketing खाता चुनें.</span><span class="sxs-lookup"><span data-stu-id="70973-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="70973-118">Dynamics 365 कॉन्टैक्ट ID पर ग्राहक ID फ़ील्ड का मैप करें.</span><span class="sxs-lookup"><span data-stu-id="70973-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="70973-119">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="70973-119">Select **Next**.</span></span>

1. <span data-ttu-id="70973-120">एक या अधिक सेगमेंट चुनें.</span><span class="sxs-lookup"><span data-stu-id="70973-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="70973-121">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="70973-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="70973-122">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="70973-122">Export the data</span></span>

<span data-ttu-id="70973-123">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="70973-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="70973-124">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="70973-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]