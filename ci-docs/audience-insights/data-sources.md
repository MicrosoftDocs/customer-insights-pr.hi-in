---
title: डेटा को इन्जेस्ट करने के लिए डेटा स्रोतों का उपयोग करें
description: विभिन्न स्रोतों से डेटा आयात करना सीखें.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304698"
---
# <a name="data-sources-overview"></a><span data-ttu-id="0fe0b-103">डेटा स्रोत ओवरव्यू</span><span class="sxs-lookup"><span data-stu-id="0fe0b-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0fe0b-104">Dynamics 365 Customer Insights में ऑडियंस इनसाइट्स क्षमता स्रोतों के एक व्यापक सेट से डेटा से जोड़ती है.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="0fe0b-105">डेटा स्रोत से कनेक्ट करने को अक्सर *डेटा अंतर्ग्रहण* प्रक्रिया कहा जाता है.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="0fe0b-106">डेटा इंजेस्ट करने के बाद, आप [एकीकृत](data-unification.md) कर सकते हैं और उस पर कार्रवाई कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="0fe0b-107">डेटा स्रोत में जोड़ें</span><span class="sxs-lookup"><span data-stu-id="0fe0b-107">Add a data source</span></span>

<span data-ttu-id="0fe0b-108">आप किस विकल्प को चुनते हैं, इसके आधार पर डेटा स्रोत को जोड़ने के बारे में विस्तृत आलेख देखें.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="0fe0b-109">आप तीन मुख्य तरीकों से एक डेटा स्रोत जोड़ सकते हैं:</span><span class="sxs-lookup"><span data-stu-id="0fe0b-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="0fe0b-110">दर्जनों Power Query कनेक्टर के माध्यम से</span><span class="sxs-lookup"><span data-stu-id="0fe0b-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="0fe0b-111">सामान्य डेटा मॉडल फ़ोल्डर से</span><span class="sxs-lookup"><span data-stu-id="0fe0b-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="0fe0b-112">अपने Microsoft Dataverse lake से</span><span class="sxs-lookup"><span data-stu-id="0fe0b-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="0fe0b-113">ऑन-प्रीमाइसेस डेटा स्रोतों से डेटा जोड़ें</span><span class="sxs-lookup"><span data-stu-id="0fe0b-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="0fe0b-114">ऑडिएंस इनसाइट्स में ऑन-प्रीमाइसेस डेटा स्रोतों से डेटा को इनजेस्ट करना, Microsoft Power Platform डेटाप्रवाहों के आधार पर समर्थित है.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="0fe0b-115">डेटाफ़्लो को परिवेश स्थापित करते समय [Microsoft Dataverse परिवेश का URL प्रदान करके](manage-environments.md#create-an-environment-in-an-existing-organization) Customer Insights में सक्षम किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="0fe0b-116">डेटा स्रोत जो Dataverse परिवेश को Customer Insights के साथ जोड़ने के बाद बनाए जाते हैं, वे डिफ़ॉल्ट रूप से [Power Platform डेटाफ़्लो](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) का उपयोग करेंगे.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="0fe0b-117">डेटा प्रवाह डेटा गेटवे का उपयोग करके ऑन-प्रिमाइसेस कनेक्टिविटी का समर्थन करते हैं.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="0fe0b-118">[ऑन-प्रिमाइसेस डेटा गेटवे का उपयोग करने के लिए Dataverse परिवेश के संबद्ध होने से पहले मौजूद डेटा स्रोतों को निकालें और पुन: बनाएँ](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="0fe0b-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="0fe0b-119">मौजूदा Power BI या Power Apps परिवेश से डेटा गेटवे दिखाई देंगे और आप Customer Insights में पुन: उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="0fe0b-120">डेटा स्रोत पृष्ठ Microsoft Power Platform परिवेश पर जाने के लिए लिंक दिखाता है जहां आप ऑन-प्रीमाइसेस डेटा गेटवे देख और कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="0fe0b-121">अंतर्ग्रहित डेटा की समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="0fe0b-121">Review ingested data</span></span>

<span data-ttu-id="0fe0b-122">आप प्रत्येक अंतर्ग्रहित डेटा स्रोत का नाम, उसकी स्थिति और वह अंतिम समय, जब उस स्रोत के लिए डेटा रीफ़्रेश किया गया था देखेंगे.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="0fe0b-123">आप हर कॉलम द्वारा डेटा स्रोतों की सूची सॉर्ट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0fe0b-124">![डेटा स्रोत जोड़ा गया](media/configure-data-datasource-added.png "डेटा स्रोत जोड़ा गया")</span><span class="sxs-lookup"><span data-stu-id="0fe0b-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="0fe0b-125">स्थिति</span><span class="sxs-lookup"><span data-stu-id="0fe0b-125">Status</span></span>  |<span data-ttu-id="0fe0b-126">विवरण</span><span class="sxs-lookup"><span data-stu-id="0fe0b-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0fe0b-127">सफल रहा</span><span class="sxs-lookup"><span data-stu-id="0fe0b-127">Successful</span></span>   |<span data-ttu-id="0fe0b-128">यदि **रिफ़्रेश किए गए** कॉलम में एक समय का उल्लेख किया जाता है तो डेटा स्रोत को सफलतापूर्वक इन्जेस्ट किया गया था.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="0fe0b-129">प्रारंभ नहीं हुआ</span><span class="sxs-lookup"><span data-stu-id="0fe0b-129">Not started</span></span>   |<span data-ttu-id="0fe0b-130">डेटा स्रोत का अभी तक या अभी भी ड्राफ्ट मोड में कोई इन्जेस्ट किया गया डेटा नहीं है.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="0fe0b-131">रिफ्रेशिंग</span><span class="sxs-lookup"><span data-stu-id="0fe0b-131">Refreshing</span></span>    |<span data-ttu-id="0fe0b-132">डेटा अंतर्ग्रहण जारी है.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-132">Data ingestion is in progress.</span></span> <span data-ttu-id="0fe0b-133">आप **एक्शन** कॉलम में **रीफ़्रेश करना रोकें** का चयन करके इस ऑपरेशन को रद्द कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="0fe0b-134">किसी डेटा स्रोत के रिफ्रेश होने से रोकना उसे अपनी अंतिम रिफ्रेश अवस्था में वापस ला देगा.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="0fe0b-135">में विफल</span><span class="sxs-lookup"><span data-stu-id="0fe0b-135">Failed</span></span>     |<span data-ttu-id="0fe0b-136">डेटा अंतर्ग्रहण में त्रुटियों मे चला गया.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="0fe0b-137">और ज़्यादा विवरणों की समीक्षा करने के लिए किसी भी डेटा स्रोत के **स्थिति** कॉलम में मान चुनें.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="0fe0b-138">**प्रगति विवरण** फ़लक में, **डेटा स्रोत** का विस्तार करें.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="0fe0b-139">त्रुटि विवरण और डाउनस्ट्रीम प्रक्रिया अपडेट सहित रिफ़्रेश स्थिति के बारे में और जानकारी के लिए **विवरण देखें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="0fe0b-140">डेटा लोड होने में समय लग सकता है।</span><span class="sxs-lookup"><span data-stu-id="0fe0b-140">Loading data can take time.</span></span> <span data-ttu-id="0fe0b-141">सफल रिफ्रेश होने के बाद, इन्टिग्रेटेड डेटा की समीक्षा **एंटिटीज़** पेज से की जा सकती है.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="0fe0b-142">अधिक जानकारी के लिए, [निकाय](entities.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="0fe0b-143">किसी डेटा स्रोत को रिफ्रेश करें</span><span class="sxs-lookup"><span data-stu-id="0fe0b-143">Refresh a data source</span></span>

<span data-ttu-id="0fe0b-144">डेटा स्रोतों को स्वचालित शेड्यूल पर रिफ़्रेश किया जा सकता है या मांग पर मैन्युअल रूप से रिफ़्रेश किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="0fe0b-145">**व्यवस्थापक** > **सिस्टम** > [**शेड्यूल**](system.md#schedule-tab) पर जाएं ताकि अपने सभी इन्जेस्ट किए गए डेटा स्रोतों के शेड्यूल हुए रिफ़्रेशों को कॉन्फ़िगर किया जा सके.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="0fe0b-146">मांग पर डेटा स्रोत को रिफ़्रेश करने के लिए, इन चरणों का पालन करें:</span><span class="sxs-lookup"><span data-stu-id="0fe0b-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="0fe0b-147">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0fe0b-148">आप जिस डेटा स्रोत को रीफ्रेश करना चाहते हैं, उसके बगल में वर्टिकल एलिप्सिस का चयन करें और ड्रॉपडाउन सूची से **रीफ्रेश करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="0fe0b-149">डेटा स्रोत अब मैन्युअल रिफ्रेश के लिए ट्रिगर किया गया है.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="0fe0b-150">डेटा स्रोत को ताज़ा करने से डेटा स्रोत में निर्दिष्ट सभी निकायों के लिए इकाई स्कीमा और डेटा दोनों को अपडेट किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="0fe0b-151">यदि आप किसी मौजूदा रिफ़्रेश को रद्द करना चाहते हैं और डेटा स्रोत अपनी अंतिम रिफ़्रेश स्थिति में वापस आ जाएगा तो **रिफ्रेश करना बंद करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="0fe0b-152">डेटा स्रोत हटाएं</span><span class="sxs-lookup"><span data-stu-id="0fe0b-152">Delete a data source</span></span>

1. <span data-ttu-id="0fe0b-153">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0fe0b-154">आप जिस डेटा स्रोत को निकालना चाहते हैं, उसके बगल में वर्टिकल एलिप्सिस का चयन करें और ड्रॉपडाउन मेनू से **हटाएँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="0fe0b-155">हटाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
