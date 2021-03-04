---
title: रीयल-टाइम डेटा इन्जेस्चन और सीमाएं
description: ऑडियंस इनसाइट्स में रीयल-टाइम क्षमताओं के बारे में सामान्य जानकारी.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270282"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="e9578-103">वास्तविक-समय डेटा अंतर्ग्रहण (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="e9578-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="e9578-104">लगभग वास्तविक-समय कार्यक्षमता आपको कुछ सेकंड के भीतर ही, आपके ग्राहकों के द्वारा आपके उत्पादों या सेवाओं से किए गए नवीनतम इंटरैक्शन को देखने देती है.</span><span class="sxs-lookup"><span data-stu-id="e9578-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="e9578-105">[शेड्यूल किए गए रीफ़्रेश](system.md#schedule-tab) जिसमें बड़ी संख्या में रिकॉर्ड और कई जटिल परिचालन शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="e9578-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="e9578-106">सबसे पहले, डेटा स्रोत से डेटा को निकाल लिया जाता है.</span><span class="sxs-lookup"><span data-stu-id="e9578-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="e9578-107">फिर, डेटा को एकीकृत किया जाता है, और फिर अतिरिक्त जानकारी के साथ समृद्ध किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="e9578-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="e9578-108">इस प्रक्रिया का हर रन में एक मिनट से लेकर घंटे तक लग सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e9578-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="e9578-109">रीयल-टाइम कार्यक्षमता इस्तेमाल के लिए तुरंत डेटा प्रदान करती है, जब तक कि बाद में शेड्यूल किया गया रीफ़्रेश इस डेटा को डेटा स्रोत से नहीं निकालता.</span><span class="sxs-lookup"><span data-stu-id="e9578-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="e9578-110">वास्तविक-समय अपडेट की समय सीमा होती है जिसके बाद वे डेटा स्रोत से मान को ओवरराइड नहीं करते हैं:</span><span class="sxs-lookup"><span data-stu-id="e9578-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="e9578-111">प्रोफाइल अपडेट को 4 घंटे तक रखा जाएगा</span><span class="sxs-lookup"><span data-stu-id="e9578-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="e9578-112">गतिविधियों को 30 दिनों तक रखा जाएगा</span><span class="sxs-lookup"><span data-stu-id="e9578-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="e9578-113">ये मान API कॉल पैरामीटर हैं जिन्हें आप बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e9578-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="e9578-114">उनका उद्देश्य यह सुनिश्चित करना है कि आपका स्रोत डेटा आपके सत्य का स्रोत बना रहे.</span><span class="sxs-lookup"><span data-stu-id="e9578-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="e9578-115">यदि आप चाहते हैं कि रियल-टाइम अद्यतन अधिक समय के लिए शामिल किया जाएं, तो आपको उन्हें डेटा स्रोत में जोड़ना होगा, ताकि उनको अगले शेड्यूल किए गए रीफ़्रेश के दौरान खींच लिया जाए.</span><span class="sxs-lookup"><span data-stu-id="e9578-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="e9578-116">एकीकृत ग्राहक प्रोफ़ाइल फ़ील्ड का वास्तविक-समय अपडेट</span><span class="sxs-lookup"><span data-stu-id="e9578-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="e9578-117">अद्यतन किए गए प्रोफ़ाइल कुछ सेकंड के भीतर ग्राहक कार्ड दृश्य, या किसी अन्य दृश्य में दिखाई देंगे.</span><span class="sxs-lookup"><span data-stu-id="e9578-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="e9578-118">क्योंकि डेटा एकीकरण हो जाने के बाद वास्तविक-समय संचालन होते हैं, इसलिए वे केवल एकीकृत ग्राहक प्रोफाइल पर लागू होते हैं.</span><span class="sxs-lookup"><span data-stu-id="e9578-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="e9578-119">परिणामस्वरूप, वास्तविक-समय प्रोफ़ाइल परिवर्तन उपायों, खंड सदस्यता, या संवर्धन को अपडेट नहीं करेंगे.</span><span class="sxs-lookup"><span data-stu-id="e9578-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="e9578-120">सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="e9578-120">Limitations</span></span>

- <span data-ttu-id="e9578-121">ग्राहक प्रोफाइल को अपडेट किया जा सकता है, लेकिन बनाया या हटाया नहीं जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="e9578-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="e9578-122">वास्तविक-समय अपडेट को बाहरी सिस्टम जैसे Power BI में निर्यात करना अभी संभव नहीं है.</span><span class="sxs-lookup"><span data-stu-id="e9578-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="e9578-123">गतिविधियों का वास्तविक-समय निर्माण</span><span class="sxs-lookup"><span data-stu-id="e9578-123">Real-time creation of activities</span></span>

<span data-ttu-id="e9578-124">रीयल-टाइम API आपको अपने स्रोत सिस्टम (एक व्यक्तिगत स्रोत रिकॉर्ड) से एकीकृत ग्राहक प्रोफ़ाइल में नई गतिविधि प्रकाशित करने देता है.</span><span class="sxs-lookup"><span data-stu-id="e9578-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="e9578-125">नई गतिविधि सेकंडों के भीतर उस एकीकृत ग्राहक प्रोफ़ाइल की एकीकृत गतिविधि के रूप में उपलब्ध हो जाएगी.</span><span class="sxs-lookup"><span data-stu-id="e9578-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="e9578-126">आप ग्राहक कार्ड दृश्य में समयरेखा या आपके द्वारा कॉन्फ़िगर किए गए किसी अन्य समयरेखा एकीकरण को देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e9578-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="e9578-127">गतिविधियाँ अपरिवर्तनीय हैं.</span><span class="sxs-lookup"><span data-stu-id="e9578-127">Activities are immutable.</span></span> <span data-ttu-id="e9578-128">एक बार बनने के बाद वे बदलती नहीं हैं.</span><span class="sxs-lookup"><span data-stu-id="e9578-128">They don't change once created.</span></span>
> - <span data-ttu-id="e9578-129">वर्तमान में, नई गतिविधि के आधार पर सेगमेंट और उपाय अपडेट नहीं होंगे.</span><span class="sxs-lookup"><span data-stu-id="e9578-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="e9578-130">केवल वास्तविक-समय API के माध्यम से जोड़ी गई गतिविधियां निर्यात का हिस्सा नहीं हैं और PowerBI में दिखाई नहीं देंगी.</span><span class="sxs-lookup"><span data-stu-id="e9578-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="e9578-131">रीयल-टाइम API से कनेक्ट करने के दो तरीके हैं:</span><span class="sxs-lookup"><span data-stu-id="e9578-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="e9578-132">[अप्रत्यक्ष रूप से](#connect-via-the-dynamics-365-customer-insights-connector), [Dynamics 365 Customer Insights कनेक्टर](https://docs.microsoft.com/connectors/customerinsights/) का उपयोग करते हुए</span><span class="sxs-lookup"><span data-stu-id="e9578-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="e9578-133">[सीधे](#connect-directly-to-the-real-time-api), कोड के साथ</span><span class="sxs-lookup"><span data-stu-id="e9578-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="e9578-134">दोनों तरीके निम्नलिखित पूर्वआश्यकताएं साझा करते हैं:</span><span class="sxs-lookup"><span data-stu-id="e9578-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="e9578-135">एक Customer Insights परिवेश</span><span class="sxs-lookup"><span data-stu-id="e9578-135">A Customer Insights environment</span></span>
- <span data-ttu-id="e9578-136">एकीकृत ग्राहक प्रोफाइल</span><span class="sxs-lookup"><span data-stu-id="e9578-136">Unified customer profiles</span></span>
- <span data-ttu-id="e9578-137">गतिविधियाँ कॉन्फ़िगर की गई और चलाई गई हैं</span><span class="sxs-lookup"><span data-stu-id="e9578-137">Activities configured and run</span></span>
- <span data-ttu-id="e9578-138">अपने खाते को प्रमाणित करने के लिए योगदानकर्ता या प्रशासक की अनुमति</span><span class="sxs-lookup"><span data-stu-id="e9578-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="e9578-139">Dynamics 365 Customer Insights कनेक्टर के माध्यम से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="e9578-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="e9578-140">वास्तविक-समय API किसी भी कोड को लिखने और लगाए जाने की आवश्यकता के बिना, एक समर्पित Power Platform कनेक्टर, [Dynamics 365 Customer Insights कनेक्टर](https://docs.microsoft.com/connectors/customerinsights/) से डेटा को इनजेस्ट कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="e9578-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="e9578-141">कनेक्टर, API के समान वास्तविकृसमय की क्रियाएं कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="e9578-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="e9578-142">आपको प्रीमियम कनेक्टर्स के लिए एक वैध लाइसेंस की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="e9578-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="e9578-143">अधिक जानकारी के लिए, [Power Apps और Power Automate लाइसेंसिंग FAQ](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) देखें.</span><span class="sxs-lookup"><span data-stu-id="e9578-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="e9578-144">Power Platform [Power Apps और/या Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="e9578-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="e9578-145">Azure [लॉजिक अनुप्रयोग](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="e9578-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="e9578-146">प्रवाह बनाने के बारे में विवरण के लिए, [Power Automate दस्तावेज़ीकरण](https://docs.microsoft.com/power-automate/) देखें.</span><span class="sxs-lookup"><span data-stu-id="e9578-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="e9578-147">सीधे वास्तविक-समय API से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="e9578-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="e9578-148">आप खुद की पाइपलाइन का निर्माण करके और रीयल-टाइम API से सीधे जुड़कर रीयल-टाइम क्षमताओं का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e9578-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="e9578-149">आप अपने स्रोत प्रणाली के प्रारूप में या UnifiedActivity प्रारूप में गतिविधि पोस्ट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e9578-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="e9578-150">/api/instances/{instanceId}/manage/entities/UnifiedActivity पर API कॉल करके प्रारूप प्राप्त करें.</span><span class="sxs-lookup"><span data-stu-id="e9578-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="e9578-151">मापदंड और प्रतिक्रियाओं सहित इस API के विवरण, [Customer Insights API संदर्भ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) पर **EntityData** अनुभाग में पाया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="e9578-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="e9578-152">अधिक जानकारी के लिए, [Customer Insights API के साथ काम करें](apis.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="e9578-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="e9578-153">टेलीमेट्री के साथ अपने वास्तविक समय के उपयोग को समझें</span><span class="sxs-lookup"><span data-stu-id="e9578-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="e9578-154">रीयल-टाइम API के अनुरोधों की मात्रा का अवलोकन प्राप्त करें और सिस्टम के सामने आने वाली समस्याओं के बारे में जानकारी प्राप्त कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="e9578-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="e9578-155">आप [रीयल-टाइम टेलीमेट्री को एक्सेस कर सकते हैं](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="e9578-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]