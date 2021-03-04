---
title: निकायें और डेटासेट
description: निकायों के पेज पर डेटा देखें.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269378"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="01746-103">ऑडियंस इनसाइट्स में मौजूद निकायें</span><span class="sxs-lookup"><span data-stu-id="01746-103">Entities in audience insights</span></span>

<span data-ttu-id="01746-104">[अपने डेटा स्रोतों को कॉन्फ़िगर](data-sources.md) करने के बाद, अंतर्ग्रहीत डेटा की गुणवत्ता का मूल्यांकन करने के लिए **निकाय** पृष्ठ पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="01746-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="01746-105">निकायों को डेटासेट माना जाता है.</span><span class="sxs-lookup"><span data-stu-id="01746-105">Entities are considered datasets.</span></span> <span data-ttu-id="01746-106">Dynamics 365 Customer Insights की कई क्षमताएं इन निकायों के आसपास बनाई गई हैं.</span><span class="sxs-lookup"><span data-stu-id="01746-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="01746-107">उनकी बारीकी से समीक्षा करने से आपको उन क्षमताओं के उत्पादन को मान्य करने में मदद मिल सकती है.</span><span class="sxs-lookup"><span data-stu-id="01746-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="01746-108">**निकाय** पृष्ठ में निकायों की सूची होती है और कई कॉलम शामिल होते हैं:</span><span class="sxs-lookup"><span data-stu-id="01746-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="01746-109">**नाम**: आपके डेटा निकाय का नाम.</span><span class="sxs-lookup"><span data-stu-id="01746-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="01746-110">यदि आपको किसी निकाय के नाम के आगे एक चेतावनी चिन्ह दिखाई देता है, तो इसका मतलब है कि उस निकाय का डेटा सफलतापूर्वक लोड नहीं हुआ है.</span><span class="sxs-lookup"><span data-stu-id="01746-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="01746-111">**स्रोत**: डेटा स्रोत का वह प्रकार जो निकाय में मिलाया गया</span><span class="sxs-lookup"><span data-stu-id="01746-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="01746-112">**द्वारा निर्मित**: उस व्यक्ति का नाम, जिसने निकाय बनाया</span><span class="sxs-lookup"><span data-stu-id="01746-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="01746-113">**निर्मित**: निकाय निर्माण की तिथि और समय</span><span class="sxs-lookup"><span data-stu-id="01746-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="01746-114">**अद्यतन**: उस व्यक्ति का नाम जिसने निकाय को अद्यतन किया</span><span class="sxs-lookup"><span data-stu-id="01746-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="01746-115">**अंतिम अद्यतन**: निकाय के अंतिम अद्यतन की तिथि और समय</span><span class="sxs-lookup"><span data-stu-id="01746-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="01746-116">**अंतिम रिफ्रेश**: अंतिम डाटा रिफ्रेश की तिथि और समय</span><span class="sxs-lookup"><span data-stu-id="01746-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="01746-117">एक विशिष्ट निकाय के डेटा की खोज</span><span class="sxs-lookup"><span data-stu-id="01746-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="01746-118">उस निकाय के भीतर शामिल विभिन्न क्षेत्रों और रिकॉर्ड का पता लगाने के लिए एक निकाय का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="01746-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="01746-119">![एक निकाय चुनें](media/data-manager-entities-data.png "एक निकाय चुनें")</span><span class="sxs-lookup"><span data-stu-id="01746-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="01746-120">**डेटा** टैब को डिफ़ॉल्ट रूप से चुना जाता है और निकाय के व्यक्तिगत रिकॉर्ड के बारे में एक तालिका सूची विवरण दिखाता है.</span><span class="sxs-lookup"><span data-stu-id="01746-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="01746-121">![फ़ील्ड तालिका](media/data-manager-entities-fields.PNG "फ़ील्ड तालिका")</span><span class="sxs-lookup"><span data-stu-id="01746-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="01746-122">**फ़ील्ड्स** टैब चयनित निकाय के लिए विवरणों की समीक्षा करने के लिए एक तालिका दिखाता है, जैसे कि फ़ील्ड नाम, डेटा प्रकार और प्रकार.</span><span class="sxs-lookup"><span data-stu-id="01746-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="01746-123">**टाइप** कॉलम कॉमन डेटा मॉडल से जुड़े प्रकारों को दिखाता है, जो या तो सिस्टम द्वारा ऑटो-आइडेंटिफाई किए जाते हैं या उपयोगकर्ता द्वारा [मैन्युअल रूप से मैप किए जाते हैं](map-entities.md).</span><span class="sxs-lookup"><span data-stu-id="01746-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="01746-124">ये अर्थ-संबंधी प्रकार होते हैं जो कि विशेषताओं के डेटा प्रकारों से भिन्न हो सकते हैं- उदाहरण के लिए, नीचे दिए गए फ़ील्ड *ईमेल* में डेटा प्रकार *टेक्स्ट* होता है, लेकिन इसका (अर्थ) सामान्य डेटा मॉडल प्रकार *ईमेल* या *ईमेल पता* हो सकता है.</span><span class="sxs-lookup"><span data-stu-id="01746-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="01746-125">दोनों तालिकाएं आपके निकाय के डेटा का केवल एक नमूना दिखाती हैं.</span><span class="sxs-lookup"><span data-stu-id="01746-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="01746-126">पूरा डेटा सेट देखने के लिए, **डेटा स्रोत** पृष्ठ पर जाएं, एक निकाय का चयन करें, **संपादन** का चयन करें, और फिर पावर पूछताछ संपादक के साथ इस निकाय के डेटा को देखें [डेटा स्रोत](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="01746-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="01746-127">निकाय में निहित डेटा के बारे में अधिक जानने के लिए, **सारांश** कॉलम आपको डेटा की कुछ महत्वपूर्ण विशेषताओं को उपलब्ध कराता है- जैसे शून्य, अनुपस्थित मान, विशिष्ट मान, गणना और वितरण, जैसा कि आपके डेटा पर लागू होता है.</span><span class="sxs-lookup"><span data-stu-id="01746-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="01746-128">डेटा का सारांश देखने के लिए चार्ट आइकन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="01746-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="01746-129">![सारांश प्रतीक](media/data-manager-entities-summary.png "डेटा सारांश तालिका")</span><span class="sxs-lookup"><span data-stu-id="01746-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="01746-130">अगला स्टेप</span><span class="sxs-lookup"><span data-stu-id="01746-130">Next step</span></span>

<span data-ttu-id="01746-131">*मैप*, *मिलान*, और *मर्ज* किए गए डेटा को जानने के लिए [एकीकृत](data-unification.md) विषय देखें.</span><span class="sxs-lookup"><span data-stu-id="01746-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]