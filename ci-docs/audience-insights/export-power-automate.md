---
title: Power Automate कनेक्टर | Microsoft Docs
description: Dynamics 365 Customer Insights से Microsoft Power Automate में प्रवाह बनाएं.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976090"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="d49b0-103">Power Automate कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="d49b0-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="d49b0-104">जब आपके डेटा में परिवर्तन होता है तो स्वचलित रूप से होने वाली विशिष्ट इवेंट स्वतः होने लगती हैं और [Power Automate](https://flow.microsoft.com/) में होने वाले प्रत्यक्ष जटिल प्रवाह को प्रबंधित करती हैं.</span><span class="sxs-lookup"><span data-stu-id="d49b0-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="d49b0-105">Power Automate ट्रिगर्स</span><span class="sxs-lookup"><span data-stu-id="d49b0-105">Power Automate triggers</span></span>

<span data-ttu-id="d49b0-106">क्लाउड प्रवाह बनाने के लिए ट्रिगर का उपयोग करें और बार-बार किए जाने वाले कार्यों को स्वचालित करें, जैसे सूचनाएं या अधिक एडवांस्ड एक्शन.</span><span class="sxs-lookup"><span data-stu-id="d49b0-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="d49b0-107">ट्रिगर जब डेटा स्रोत रिफ़्रेश विफल रहता है.</span><span class="sxs-lookup"><span data-stu-id="d49b0-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="d49b0-108">ट्रिगर जब डेटा स्रोत रिफ़्रेश सफल होता है.</span><span class="sxs-lookup"><span data-stu-id="d49b0-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="d49b0-109">ट्रिगर जब अनुभाग की सीमा पार की जाती है.</span><span class="sxs-lookup"><span data-stu-id="d49b0-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="d49b0-110">ट्रिगर सीमा के ऊपर जाने तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="d49b0-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="d49b0-111">ट्रिगर जब व्यावसायिक उपाय सीमा के पार हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="d49b0-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="d49b0-112">केवल बिना आयाम वाले व्यावसायिक उपाय समर्थित हैं.</span><span class="sxs-lookup"><span data-stu-id="d49b0-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="d49b0-113">ट्रिगर सीमा के ऊपर जाने तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="d49b0-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="d49b0-114">ट्रिगर जब (डेटा स्रोतों, खंडों, साधनों,...) का पूरा रिफ़्रेश पूरा हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="d49b0-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="d49b0-115">जब एकीकरण प्रक्रिया (मानचित्र, मिलान, मर्ज) का रिफ्रेश पूरा होता है तब ट्रिगर करें.</span><span class="sxs-lookup"><span data-stu-id="d49b0-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="d49b0-116">[Power Automate में अपने ट्रिगर कॉन्फ़िगर करें](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="d49b0-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="d49b0-117">Power Automate कार्रवाइयां</span><span class="sxs-lookup"><span data-stu-id="d49b0-117">Power Automate actions</span></span>
<span data-ttu-id="d49b0-118">Power Automate कनेक्टर उपलब्ध ट्रिगर्स से अलग कार्रवाइयां प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="d49b0-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="d49b0-119">अधिक जानकारी के लिए, [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/) देखें.</span><span class="sxs-lookup"><span data-stu-id="d49b0-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="d49b0-120">एक Power Automate प्रवाह बनाएँ</span><span class="sxs-lookup"><span data-stu-id="d49b0-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="d49b0-121">ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="d49b0-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d49b0-122">**Power Automate** टाइल पर, **सेट अप** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="d49b0-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="d49b0-123">Power Automate में Customer Insights कनेक्टर (पूर्वावलोकन) खुलता है.</span><span class="sxs-lookup"><span data-stu-id="d49b0-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="d49b0-124">Power Automate से **साइन इन** करें.</span><span class="sxs-lookup"><span data-stu-id="d49b0-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="d49b0-125">उपलब्ध ट्रिगर में से किसी एक को चुनें और अपने नए प्रवाह में और चरण जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="d49b0-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="d49b0-126">अधिक जानकारी के लिए, [Power Automate में क्लाउड प्रवाह बनाएं](/power-automate/get-started-logic-flow) देखें.</span><span class="sxs-lookup"><span data-stu-id="d49b0-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="d49b0-127">उदाहरण कि प्रवाह का उपयोग कैसे करें:</span><span class="sxs-lookup"><span data-stu-id="d49b0-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="d49b0-128">यदि डेटा स्रोत रीफ्रेश विफल रहता है, तो Microsoft Teams चैनल पर एक संदेश पोस्ट करें.</span><span class="sxs-lookup"><span data-stu-id="d49b0-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="d49b0-129">जब एक सेगमेंट पर सीमा पार हो जाती है, तो डेटा मालिकों को एक ईमेल भेजें.</span><span class="sxs-lookup"><span data-stu-id="d49b0-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
