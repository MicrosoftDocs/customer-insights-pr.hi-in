---
title: डेटा को इन्जेस्ट करने के लिए डेटा स्रोतों का उपयोग करें
description: विभिन्न स्रोतों से डेटा आयात करना सीखें.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269700"
---
# <a name="data-sources-overview"></a><span data-ttu-id="bedf0-103">डेटा स्रोत ओवरव्यू</span><span class="sxs-lookup"><span data-stu-id="bedf0-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bedf0-104">Dynamics 365 Customer Insights में ऑडियंस इनसाइट्स क्षमता स्रोतों के एक व्यापक सेट से डेटा से जोड़ती है.</span><span class="sxs-lookup"><span data-stu-id="bedf0-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="bedf0-105">डेटा स्रोत से कनेक्ट करने को अक्सर *डेटा अंतर्ग्रहण* प्रक्रिया कहा जाता है.</span><span class="sxs-lookup"><span data-stu-id="bedf0-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="bedf0-106">डेटा इंजेस्ट करने के बाद, आप [एकीकृत](data-unification.md) कर सकते हैं और उस पर कार्रवाई कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="bedf0-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="bedf0-107">डेटा स्रोत में जोड़ें</span><span class="sxs-lookup"><span data-stu-id="bedf0-107">Add a data source</span></span>

<span data-ttu-id="bedf0-108">आप किस विकल्प को चुनते हैं, इसके आधार पर डेटा स्रोत को जोड़ने के बारे में विस्तृत आलेख देखें.</span><span class="sxs-lookup"><span data-stu-id="bedf0-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="bedf0-109">आप तीन मुख्य तरीकों से एक डेटा स्रोत जोड़ सकते हैं:</span><span class="sxs-lookup"><span data-stu-id="bedf0-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="bedf0-110">दर्जनों Power Query कनेक्टर के माध्यम से</span><span class="sxs-lookup"><span data-stu-id="bedf0-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="bedf0-111">सामान्य डेटा मॉडल फ़ोल्डर से</span><span class="sxs-lookup"><span data-stu-id="bedf0-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="bedf0-112">अपने Common Data Service lake से</span><span class="sxs-lookup"><span data-stu-id="bedf0-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="bedf0-113">आप अभी तक ऑन-प्रिमाइसेस डेटा स्रोतों से डेटा नहीं जोड़ सकते.</span><span class="sxs-lookup"><span data-stu-id="bedf0-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="bedf0-114">अंतर्ग्रहित डेटा की समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="bedf0-114">Review ingested data</span></span>

<span data-ttu-id="bedf0-115">आप प्रत्येक अंतर्ग्रहित डेटा स्रोत का नाम, उसकी स्थिति और वह अंतिम समय, जब उस स्रोत के लिए डेटा रीफ़्रेश किया गया था देखेंगे.</span><span class="sxs-lookup"><span data-stu-id="bedf0-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="bedf0-116">आप हर कॉलम द्वारा डेटा स्रोतों की सूची सॉर्ट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="bedf0-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bedf0-117">![डेटा स्रोत जोड़ा गया](media/configure-data-datasource-added.png "डेटा स्रोत जोड़ा गया")</span><span class="sxs-lookup"><span data-stu-id="bedf0-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="bedf0-118">स्थिति</span><span class="sxs-lookup"><span data-stu-id="bedf0-118">Status</span></span>  |<span data-ttu-id="bedf0-119">विवरण</span><span class="sxs-lookup"><span data-stu-id="bedf0-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="bedf0-120">सफल रहा</span><span class="sxs-lookup"><span data-stu-id="bedf0-120">Successful</span></span>   |<span data-ttu-id="bedf0-121">यदि **रिफ़्रेश किए गए** कॉलम में एक समय का उल्लेख किया जाता है तो डेटा स्रोत को सफलतापूर्वक इन्जेस्ट किया गया था.</span><span class="sxs-lookup"><span data-stu-id="bedf0-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="bedf0-122">प्रारंभ नहीं हुआ</span><span class="sxs-lookup"><span data-stu-id="bedf0-122">Not started</span></span>   |<span data-ttu-id="bedf0-123">डेटा स्रोत का अभी तक या अभी भी ड्राफ्ट मोड में कोई इन्जेस्ट किया गया डेटा नहीं है.</span><span class="sxs-lookup"><span data-stu-id="bedf0-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="bedf0-124">रिफ्रेशिंग</span><span class="sxs-lookup"><span data-stu-id="bedf0-124">Refreshing</span></span>    |<span data-ttu-id="bedf0-125">डेटा अंतर्ग्रहण जारी है.</span><span class="sxs-lookup"><span data-stu-id="bedf0-125">Data ingestion is in progress.</span></span> <span data-ttu-id="bedf0-126">आप **एक्शन** कॉलम में **रीफ़्रेश करना रोकें** का चयन करके इस ऑपरेशन को रद्द कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="bedf0-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="bedf0-127">किसी डेटा स्रोत के रिफ्रेश होने से रोकना उसे अपनी अंतिम रिफ्रेश अवस्था में वापस ला देगा.</span><span class="sxs-lookup"><span data-stu-id="bedf0-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="bedf0-128">में विफल</span><span class="sxs-lookup"><span data-stu-id="bedf0-128">Failed</span></span>     |<span data-ttu-id="bedf0-129">डेटा अंतर्ग्रहण में त्रुटियों मे चला गया.</span><span class="sxs-lookup"><span data-stu-id="bedf0-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="bedf0-130">और ज़्यादा विवरणों की समीक्षा करने के लिए किसी भी डेटा स्रोत के **स्थिति** कॉलम में मान चुनें.</span><span class="sxs-lookup"><span data-stu-id="bedf0-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="bedf0-131">**प्रगति विवरण** फ़लक में, **डेटा स्रोत** का विस्तार करें.</span><span class="sxs-lookup"><span data-stu-id="bedf0-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="bedf0-132">त्रुटि विवरण और डाउनस्ट्रीम प्रक्रिया अपडेट सहित रिफ़्रेश स्थिति के बारे में और जानकारी के लिए **विवरण देखें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="bedf0-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="bedf0-133">डेटा लोड होने में कुछ समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="bedf0-133">Loading data can take some time.</span></span> <span data-ttu-id="bedf0-134">सफल रिफ्रेश होने के बाद, इन्टिग्रेटेड डेटा की समीक्षा **एंटिटीज़** पेज से की जा सकती है.</span><span class="sxs-lookup"><span data-stu-id="bedf0-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="bedf0-135">अधिक जानकारी के लिए, [निकाय](entities.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="bedf0-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="bedf0-136">किसी डेटा स्रोत को रिफ्रेश करें</span><span class="sxs-lookup"><span data-stu-id="bedf0-136">Refresh a data source</span></span>

<span data-ttu-id="bedf0-137">डेटा स्रोतों को स्वचालित शेड्यूल पर रिफ़्रेश किया जा सकता है या मांग पर मैन्युअल रूप से रिफ़्रेश किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="bedf0-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="bedf0-138">**व्यवस्थापक** > **सिस्टम** > [**शेड्यूल**](system.md#schedule-tab) पर जाएं ताकि अपने सभी इन्जेस्ट किए गए डेटा स्रोतों के शेड्यूल हुए रिफ़्रेशों को कॉन्फ़िगर किया जा सके.</span><span class="sxs-lookup"><span data-stu-id="bedf0-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="bedf0-139">मांग पर डेटा स्रोत को रिफ़्रेश करने के लिए, इन चरणों का पालन करें:</span><span class="sxs-lookup"><span data-stu-id="bedf0-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="bedf0-140">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं</span><span class="sxs-lookup"><span data-stu-id="bedf0-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="bedf0-141">आप जिस डेटा स्रोत को रिफ़्रेश करना चाहते हैं उसके बगल में वर्टिकल एलिप्सिस का चयन करें और ड्रॉप-डाउन सूची से **रिफ़्रेश** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="bedf0-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="bedf0-142">डेटा स्रोत अब मैन्युअल रिफ्रेश के लिए ट्रिगर किया गया है.</span><span class="sxs-lookup"><span data-stu-id="bedf0-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="bedf0-143">डेटा स्रोत को रिफ़्रेश करने से डेटा स्रोत में निर्दिष्ट सभी निकायों के लिए निकाय स्कीमा के साथ-साथ डेटा दोनों को अपडेट किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="bedf0-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="bedf0-144">यदि आप किसी मौजूदा रिफ़्रेश को रद्द करना चाहते हैं और डेटा स्रोत अपनी अंतिम रिफ़्रेश स्थिति में वापस आ जाएगा तो **रिफ्रेश करना बंद करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="bedf0-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="bedf0-145">डेटा स्रोत हटाएं</span><span class="sxs-lookup"><span data-stu-id="bedf0-145">Delete a data source</span></span>

1. <span data-ttu-id="bedf0-146">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="bedf0-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="bedf0-147">जिस डेटा स्रोत को आप हटाना चाहते हैं, उसके बगल में दिये लंबवत एलिप्सिस का चयन करें और ड्रॉप-डाउन मेनू से **हटाएँ** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="bedf0-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="bedf0-148">हटाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="bedf0-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]