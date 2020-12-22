---
title: Power Automate कनेक्टर | Microsoft Docs
description: Dynamics 365 Customer Insights से Microsoft Power Automate में प्रवाह बनाएं.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405921"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="c5eaa-103">Power Automate कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="c5eaa-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="c5eaa-104">जब आपके डेटा में परिवर्तन होता है तो स्वचलित रूप से होने वाली विशिष्ट इवेंट स्वतः होने लगती हैं और [Power Automate](https://flow.microsoft.com/) में होने वाले प्रत्यक्ष जटिल प्रवाह को प्रबंधित करती हैं.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="c5eaa-105">Power Automate ट्रिगर्स</span><span class="sxs-lookup"><span data-stu-id="c5eaa-105">Power Automate triggers</span></span>

<span data-ttu-id="c5eaa-106">आप विभिन्न प्रकार के ट्रिगर्स का उपयोग कर सकते हैं जो आपको दोहराए जाने वाले कार्यों को स्वचालित करने के लिए फ़्लो बनाने की अनुमति देते हैं, जैसे कि अधिसूचनाएं या अधिक उन्नत क्रियाएं.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="c5eaa-107">ट्रिगर जब डेटा स्रोत रिफ़्रेश विफल रहता है.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="c5eaa-108">ट्रिगर जब डेटा स्रोत रिफ़्रेश सफल होता है.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="c5eaa-109">ट्रिगर जब अनुभाग की सीमा पार की जाती है.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="c5eaa-110">ट्रिगर सीमा के ऊपर जाने तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="c5eaa-111">ट्रिगर जब व्यावसायिक उपाय सीमा के पार हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="c5eaa-112">ट्रिगर सीमा के ऊपर जाने तक सीमित है.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="c5eaa-113">ट्रिगर जब (डेटा स्रोतों, खंडों, साधनों,...) का पूरा रिफ़्रेश पूरा हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="c5eaa-114">जब एकीकरण प्रक्रिया (मानचित्र, मिलान, मर्ज) का रिफ्रेश पूरा होता है तब ट्रिगर करें.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="c5eaa-115">[Power Automate में अपने ट्रिगर कॉन्फ़िगर करें](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="c5eaa-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="c5eaa-116">Power Automate कार्रवाइयां</span><span class="sxs-lookup"><span data-stu-id="c5eaa-116">Power Automate actions</span></span>
<span data-ttu-id="c5eaa-117">Power Automate कनेक्टर उपलब्ध ट्रिगर्स से अलग कार्रवाइयां प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="c5eaa-118">अधिक जानकारी के लिए, [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/) देखें.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="c5eaa-119">ऑडियंस इनसाइट्स में एक Power Automate प्रवाह बनाएं</span><span class="sxs-lookup"><span data-stu-id="c5eaa-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="c5eaa-120">ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **सिस्टम** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="c5eaa-121">**सिस्टम** पेज पर, **स्थिति** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="c5eaa-122">**डेटा स्रोत** खंड में, **प्रवाह** चुनें और ड्रॉपडाउन सूची से **एक प्रवाह बनाएँ** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c5eaa-123">![Power Automate कनेक्टर फ़्लो क्रिया बनाएं दर्शा रहा है](media/power-automate-connector-create-flow.png "प्रवाह बनाएं कार्रवाई दर्शाता Power Automate कनेक्टर")</span><span class="sxs-lookup"><span data-stu-id="c5eaa-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="c5eaa-124">Power Automate में, अपना पसंदीदा प्रवाह बनाने के लिए उपलब्ध ट्रिगर में से एक को चुनें.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="c5eaa-125">यदि आप अपना पहला प्रवाह बना रहे हैं तो आपको पहले Power Automate कनेक्टर के साथ अनुप्रमाणन करना होगा.</span><span class="sxs-lookup"><span data-stu-id="c5eaa-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
