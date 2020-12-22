---
title: Dynamics 365 Marketing के लिए Customer Insights डेटा निर्यात करें
description: Dynamics 365 Marketing से कनेक्शन कॉन्फ़िगर करना सीखें.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643775"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="580a4-103">Dynamics 365 Marketing के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="580a4-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="580a4-104">अभियान उत्पन्न करने और Dynamics 365 Marketing वाले ग्राहकों के विशिष्ट समूहों से संपर्क करने के लिए [सेगमेंट](segments.md) का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="580a4-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="580a4-105">अधिक जानकारी के लिए, देखें [Dynamics 365 Customer Insights से Dynamics 365 Marketing का उपयोग करें](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="580a4-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="580a4-106">पूर्वावश्यकता</span><span class="sxs-lookup"><span data-stu-id="580a4-106">Prerequisite</span></span>

<span data-ttu-id="580a4-107">संपर्क रिकॉर्ड [Dynamics 365 Marketing से इन्जेस्ट किए गए Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="580a4-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="580a4-108">मार्केटिंग के लिए कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="580a4-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="580a4-109">ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="580a4-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="580a4-110">**Dynamics 365 Marketing** के तहत, **सेट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="580a4-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="580a4-111">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="580a4-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="580a4-112">**सर्वर का पता** फ़ील्ड में अपने संगठन का मार्केटिंग URL दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="580a4-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="580a4-113">**सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Marketing खाता चुनें.</span><span class="sxs-lookup"><span data-stu-id="580a4-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="580a4-114">Dynamics 365 कॉन्टैक्ट ID पर ग्राहक ID फ़ील्ड का मैप करें.</span><span class="sxs-lookup"><span data-stu-id="580a4-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="580a4-115">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="580a4-115">Select **Next**.</span></span>

1. <span data-ttu-id="580a4-116">एक या अधिक सेगमेंट चुनें.</span><span class="sxs-lookup"><span data-stu-id="580a4-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="580a4-117">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="580a4-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="580a4-118">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="580a4-118">Export the data</span></span>

<span data-ttu-id="580a4-119">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="580a4-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="580a4-120">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="580a4-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
