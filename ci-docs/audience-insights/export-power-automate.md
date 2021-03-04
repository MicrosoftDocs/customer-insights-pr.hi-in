---
title: Power Automate कनेक्टर | Microsoft Docs
description: Dynamics 365 Customer Insights से Microsoft Power Automate में प्रवाह बनाएं.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268826"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="76f3d-103">Power Automate कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="76f3d-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="76f3d-104">जब आपके डेटा में परिवर्तन होता है तो स्वचलित रूप से होने वाली विशिष्ट इवेंट स्वतः होने लगती हैं और [Power Automate](https://flow.microsoft.com/) में होने वाले प्रत्यक्ष जटिल प्रवाह को प्रबंधित करती हैं.</span><span class="sxs-lookup"><span data-stu-id="76f3d-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="76f3d-105">Power Automate ट्रिगर्स</span><span class="sxs-lookup"><span data-stu-id="76f3d-105">Power Automate triggers</span></span>

<span data-ttu-id="76f3d-106">क्लाउड प्रवाह बनाने के लिए ट्रिगर का उपयोग करें और बार-बार किए जाने वाले कार्यों को स्वचालित करें, जैसे सूचनाएं या अधिक एडवांस्ड एक्शन.</span><span class="sxs-lookup"><span data-stu-id="76f3d-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="76f3d-107">ट्रिगर जब डेटा स्रोत रिफ़्रेश विफल रहता है.</span><span class="sxs-lookup"><span data-stu-id="76f3d-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="76f3d-108">ट्रिगर जब डेटा स्रोत रिफ़्रेश सफल होता है.</span><span class="sxs-lookup"><span data-stu-id="76f3d-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="76f3d-109">ट्रिगर जब अनुभाग की सीमा पार की जाती है.</span><span class="sxs-lookup"><span data-stu-id="76f3d-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="76f3d-110">ट्रिगर सीमा के ऊपर जाने तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="76f3d-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="76f3d-111">ट्रिगर जब व्यावसायिक उपाय सीमा के पार हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="76f3d-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="76f3d-112">ट्रिगर सीमा के ऊपर जाने तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="76f3d-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="76f3d-113">ट्रिगर जब (डेटा स्रोतों, खंडों, साधनों,...) का पूरा रिफ़्रेश पूरा हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="76f3d-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="76f3d-114">जब एकीकरण प्रक्रिया (मानचित्र, मिलान, मर्ज) का रिफ्रेश पूरा होता है तब ट्रिगर करें.</span><span class="sxs-lookup"><span data-stu-id="76f3d-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="76f3d-115">[Power Automate में अपने ट्रिगर कॉन्फ़िगर करें](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="76f3d-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="76f3d-116">Power Automate कार्रवाइयां</span><span class="sxs-lookup"><span data-stu-id="76f3d-116">Power Automate actions</span></span>
<span data-ttu-id="76f3d-117">Power Automate कनेक्टर उपलब्ध ट्रिगर्स से अलग कार्रवाइयां प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="76f3d-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="76f3d-118">अधिक जानकारी के लिए, [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/) देखें.</span><span class="sxs-lookup"><span data-stu-id="76f3d-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="76f3d-119">एक Power Automate प्रवाह बनाएँ</span><span class="sxs-lookup"><span data-stu-id="76f3d-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="76f3d-120">ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="76f3d-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="76f3d-121">**Power Automate** टाइल पर, **सेट अप** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="76f3d-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="76f3d-122">Power Automate में Customer Insights कनेक्टर (पूर्वावलोकन) खुलता है.</span><span class="sxs-lookup"><span data-stu-id="76f3d-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="76f3d-123">Power Automate से **साइन इन** करें.</span><span class="sxs-lookup"><span data-stu-id="76f3d-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="76f3d-124">उपलब्ध ट्रिगर में से किसी एक को चुनें और अपने नए प्रवाह में और चरण जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="76f3d-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="76f3d-125">अधिक जानकारी के लिए, [Power Automate में क्लाउड प्रवाह बनाएं](https://docs.microsoft.com/power-automate/get-started-logic-flow) देखें.</span><span class="sxs-lookup"><span data-stu-id="76f3d-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="76f3d-126">उदाहरण कि प्रवाह का उपयोग कैसे करें:</span><span class="sxs-lookup"><span data-stu-id="76f3d-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="76f3d-127">यदि डेटा स्रोत रीफ्रेश विफल रहता है, तो Microsoft Teams चैनल पर एक संदेश पोस्ट करें.</span><span class="sxs-lookup"><span data-stu-id="76f3d-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="76f3d-128">जब एक सेगमेंट पर सीमा पार हो जाती है, तो डेटा मालिकों को एक ईमेल भेजें.</span><span class="sxs-lookup"><span data-stu-id="76f3d-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]