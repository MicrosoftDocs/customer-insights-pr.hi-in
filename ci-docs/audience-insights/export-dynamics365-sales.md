---
title: Dynamics 365 Sales के लिए Customer Insights डेटा निर्यात करें
description: Dynamics 365 Sales से कनेक्शन कॉन्फ़िगर करना सीखें.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643820"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="a13df-103">Dynamics 365 Sales के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="a13df-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a13df-104">अपने ग्राहक डेटा को मार्केटिंग सूची बनाने, कार्यप्रवाह के फ़ॉलो अप और Dynamics 365 Sales के साथ प्रचार भेजने के लिए इस्तेमाल करें.</span><span class="sxs-lookup"><span data-stu-id="a13df-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a13df-105">पूर्वावश्यकता</span><span class="sxs-lookup"><span data-stu-id="a13df-105">Prerequisite</span></span>

<span data-ttu-id="a13df-106">संपर्क रिकॉर्ड [Common Data Service का उपयोग करके Dynamics 365 Sales से इन्जेस्ट किया गया](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a13df-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="a13df-107">विक्रय के लिए कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="a13df-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="a13df-108">ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="a13df-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a13df-109">**Dynamics 365 Sales** के तहत, **सेट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="a13df-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="a13df-110">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="a13df-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a13df-111">**सर्वर का पता** फ़ील्ड में अपने संगठन का बिक्री URL दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="a13df-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a13df-112">**सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Sales खाता चुनें.</span><span class="sxs-lookup"><span data-stu-id="a13df-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="a13df-113">Dynamics 365 कॉन्टैक्ट ID पर ग्राहक ID फ़ील्ड का मैप करें.</span><span class="sxs-lookup"><span data-stu-id="a13df-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a13df-114">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="a13df-114">Select **Next**.</span></span>

1. <span data-ttu-id="a13df-115">एक या अधिक सेगमेंट चुनें.</span><span class="sxs-lookup"><span data-stu-id="a13df-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="a13df-116">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="a13df-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a13df-117">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="a13df-117">Export the data</span></span>

<span data-ttu-id="a13df-118">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a13df-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a13df-119">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a13df-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
