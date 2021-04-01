---
title: Dynamics 365 Sales के लिए Customer Insights डेटा निर्यात करें
description: Dynamics 365 Sales से कनेक्शन कॉन्फ़िगर करना सीखें.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598111"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="78344-103">Dynamics 365 Sales के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="78344-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="78344-104">अपने ग्राहक डेटा को मार्केटिंग सूची बनाने, कार्यप्रवाह के फ़ॉलो अप और Dynamics 365 Sales के साथ प्रचार भेजने के लिए इस्तेमाल करें.</span><span class="sxs-lookup"><span data-stu-id="78344-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="78344-105">पूर्वावश्यकता</span><span class="sxs-lookup"><span data-stu-id="78344-105">Prerequisite</span></span>

1. <span data-ttu-id="78344-106">इससे पहले कि आप Customer Insights से विक्रय में सेगमेंट निर्यात करें, संपर्क रिकॉर्ड Dynamics 365 Sales में मौजूद होने चाहिए.</span><span class="sxs-lookup"><span data-stu-id="78344-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="78344-107">[Common Data Services का उपयोग करके Dynamics 365 Sales](connect-power-query.md) में संपर्क कैसे अंतर्ग्रहण करने हैं, पर अधिक पढ़ें.</span><span class="sxs-lookup"><span data-stu-id="78344-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="78344-108">ऑडियंस इनसाइट्स से विक्रय में सेगमेंट को निर्यात करने से विक्रय इंस्टेंस में नए संपर्क रिकॉर्ड नहीं बनेंगे.</span><span class="sxs-lookup"><span data-stu-id="78344-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="78344-109">विक्रय से संपर्क रिकॉर्ड ऑडियंस इनसाइट्स में निहित होना चाहिए और डेटा स्रोत के रूप में उपयोग किए जाने चाहिए.</span><span class="sxs-lookup"><span data-stu-id="78344-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="78344-110">सेगमेंट को निर्यात करने से पहले ID से संपर्क करने के लिए ग्राहक ID को मैप करने के लिए उन्हें एकीकृत ग्राहक निकाय में शामिल करने की भी ज़रूरत है.</span><span class="sxs-lookup"><span data-stu-id="78344-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="78344-111">विक्रय के लिए कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="78344-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="78344-112">ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="78344-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="78344-113">**Dynamics 365 Sales** के तहत, **सेट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="78344-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="78344-114">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="78344-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="78344-115">**सर्वर का पता** फ़ील्ड में अपने संगठन का बिक्री URL दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="78344-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="78344-116">**सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Sales खाता चुनें.</span><span class="sxs-lookup"><span data-stu-id="78344-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="78344-117">Dynamics 365 कॉन्टैक्ट ID पर ग्राहक ID फ़ील्ड का मैप करें.</span><span class="sxs-lookup"><span data-stu-id="78344-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="78344-118">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="78344-118">Select **Next**.</span></span>

1. <span data-ttu-id="78344-119">एक या अधिक सेगमेंट चुनें.</span><span class="sxs-lookup"><span data-stu-id="78344-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="78344-120">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="78344-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="78344-121">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="78344-121">Export the data</span></span>

<span data-ttu-id="78344-122">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="78344-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="78344-123">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="78344-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]