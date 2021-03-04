---
title: Microsoft Teams के लिए बॉट
description: एक बॉट की मदद से Microsoft Teams में एकीकृत ग्राहक प्रोफाइल देखें.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267954"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="327e7-103">Dynamics 365 Customer Insights के लिए Teams बॉट (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="327e7-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="327e7-104">एक बॉट को टीम चैनलों में एकीकृत ग्राहक प्रोफाइल देखने देने के लिए Microsoft Teams के साथ जुड़ें.</span><span class="sxs-lookup"><span data-stu-id="327e7-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="327e7-105">![Teams बॉट एक ग्राहक रिकॉर्ड दिखाती हैं](media/teams-bot.png "Teams बॉट एक ग्राहक रिकॉर्ड दिखाती हैं")</span><span class="sxs-lookup"><span data-stu-id="327e7-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="327e7-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="327e7-106">Prerequisites</span></span>

<span data-ttu-id="327e7-107">बॉट को सेट और कॉन्फ़िगर करने के लिए, निम्नलिखित पूर्वअपेक्षाएँ पूरी की जानी चाहिए:</span><span class="sxs-lookup"><span data-stu-id="327e7-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="327e7-108">कम से कम एक है [डेटा स्रोत जोड़ा गया](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="327e7-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="327e7-109">[एकीकरण प्रक्रिया](data-unification.md) पूरी हो गयी है.</span><span class="sxs-lookup"><span data-stu-id="327e7-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="327e7-110">फ़ील्ड [खोज और फ़िल्टर इंडेक्स](search-filter-index.md) में जोड़े जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="327e7-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="327e7-111">Customer Insights और टीम एक ही संगठन में हैं.</span><span class="sxs-lookup"><span data-stu-id="327e7-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="327e7-112">बॉट कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="327e7-112">Configure the bot</span></span>

1. <span data-ttu-id="327e7-113">ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="327e7-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="327e7-114">Microsoft Teams टाइल पर, **सेट अप** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="327e7-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="327e7-115">आप टीम में **अनुप्रयोग** क्षेत्र में वापस भेजे गए हैं.</span><span class="sxs-lookup"><span data-stu-id="327e7-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="327e7-116">आप टीम भी खोल सकते हैं और नीचे-बाएँ कोने में **अनुप्रयोग** का चयन करें या सीधे [AppSource से प्राप्त करें](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="327e7-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="327e7-117">**Customer Insights** को खोजें और ऐप चुनें.</span><span class="sxs-lookup"><span data-stu-id="327e7-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="327e7-118">**जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="327e7-118">Select **Add**.</span></span>
1. <span data-ttu-id="327e7-119">Teams में Customer Insights में साइन इन करने के बाद, आप एक स्वागत संदेश देखेंगे और शुरू कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="327e7-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="327e7-120">चीज़ें जो आप बॉट के साथ कर सकते हैं</span><span class="sxs-lookup"><span data-stu-id="327e7-120">Things you can do with the bot</span></span>

<span data-ttu-id="327e7-121">बॉट एकीकृत ग्राहक प्रोफाइल के लिए लुकअप क्षमताएं प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="327e7-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="327e7-122">खोज और फ़िल्टर इंडेक्स में जोड़े गए एकीकृत ग्राहक प्रोफ़ाइल पर नाम, ईमेल पता, या किसी अन्य क्षेत्र के बाद **खोज**  दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="327e7-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="327e7-123">आपको परिणामी ग्राहक प्रोफ़ाइल से अधिकतम 15 फ़ील्ड के साथ एक कार्ड मिलेगा.</span><span class="sxs-lookup"><span data-stu-id="327e7-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="327e7-124">एकाधिक मिलान परिणामों की एक सूची देते हैं जहां आप एक प्रोफ़ाइल का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="327e7-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="327e7-125">सटीक मिलान देखने के लिए आप खोज शब्द को दोहरे उद्धरण में जोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="327e7-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="327e7-126">यदि आपका संगठन एक ही संगठन में कई Customer Insights परिवेश रखता है, तो आप यह चुनने के लिए **switchinstance** दर्ज कर सकते हैं कि आप बॉट को किस परिवेश से जोड़ना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="327e7-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="327e7-127">बॉट के लिए उपलब्ध आदेशों की एक सूची देखने के लिए **मदद** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="327e7-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]