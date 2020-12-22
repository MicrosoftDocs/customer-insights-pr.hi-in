---
title: ग्राहक की प्रोफ़ाइलों की खोज और उन्हें फिल्टर करें
description: निर्दिष्ट विशेषताओं के लिए एकीकृत कस्टमर प्रोफाइल और फ़िल्टर के बारे में त्वरित जानकारी प्राप्त करें.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405968"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="dca3c-103">ग्राहक प्रोफाइल: खोज और फ़िल्टर सूचकांक</span><span class="sxs-lookup"><span data-stu-id="dca3c-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="dca3c-104">आपके ग्राहक डेटा को एकीकृत करने का परिणाम एक ग्राहक प्रोफ़ाइल निकाय है, जो आपके कुल ग्राहक आधार में एकीकृत दृश्य उपलब्ध करता है.</span><span class="sxs-lookup"><span data-stu-id="dca3c-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="dca3c-105">शीघ्र [एक विशिष्ट ग्राहक या ग्राहकों के समूह की जानकारी पाएं](customer-profiles.md), पाने के लिए आप **खोज** और **फ़िल्टर** क्षमताओं को **ग्राहक** पृष्ठ पर शीघ्र कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="dca3c-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="dca3c-106">यह जानने के लिए कि पढ़ें कि व्यवस्थापक **खोज और फ़िल्टर सूचकांक** पृष्ठ पर विशेषताओं को कैसे संपादित कर सकते हैं, यह उपयोगकर्ताओं के लिए खोज और फ़िल्टर प्राप्त करने के लिए उपलब्ध हैं.</span><span class="sxs-lookup"><span data-stu-id="dca3c-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca3c-107">![खोज फ़ि‍ल्‍टर](media/search-filter.png "खोज फ़ि‍ल्‍टर")</span><span class="sxs-lookup"><span data-stu-id="dca3c-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="dca3c-108">फ़ील्ड जोड़ें और विशेषताएँ निर्दिष्ट करें</span><span class="sxs-lookup"><span data-stu-id="dca3c-108">Add fields and specify attributes</span></span>

<span data-ttu-id="dca3c-109">यदि आप खोज योग्य विशेषताओं को एक व्यवस्थापक के रूप में पहली बार निर्धारित कर रहे हैं, तो आपको पहले अनुक्रमित फ़ील्ड को निर्धारित करना होगा.</span><span class="sxs-lookup"><span data-stu-id="dca3c-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="dca3c-110">हमारा सुझाव है कि आप उन सभी विशेषताओं को चुनें जिनके द्वारा उपयोगकर्ता **ग्राहक** पृष्ठ पर ग्राहकों की खोज और उन्हें फ़िल्टर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="dca3c-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="dca3c-111">आप केवल ग्राहक एकीकरण निकाय में मौजूद उन विशेषताओं को निर्दिष्ट कर सकते हैं जिन्हें आपने डेटा एकीकरण प्रक्रिया के दौरान बनाया था.</span><span class="sxs-lookup"><span data-stu-id="dca3c-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="dca3c-112">**ग्राहक** पृष्ठ खोलें और **खोज और फ़िल्टर संकेत** चुनें.</span><span class="sxs-lookup"><span data-stu-id="dca3c-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="dca3c-113">हम मानचित्र पृष्ठ पर परिभाषित निम्नलिखित अर्थ-संबंधी प्रकारों से ग्राहक निकाय में उपलब्ध एट्रिब्यूट्स पर एक डिफ़ॉल्ट खोज संकेत कॉन्फ़िगरेशन बनाते हैं.</span><span class="sxs-lookup"><span data-stu-id="dca3c-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="dca3c-114">व्यक्ति का पहला नाम, अंतिम नाम, मध्य नाम, पूरा नाम</span><span class="sxs-lookup"><span data-stu-id="dca3c-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="dca3c-115">संगठन का नाम</span><span class="sxs-lookup"><span data-stu-id="dca3c-115">Organization Name</span></span>
> - <span data-ttu-id="dca3c-116">ईमेल पता</span><span class="sxs-lookup"><span data-stu-id="dca3c-116">Email address</span></span>
> - <span data-ttu-id="dca3c-117">फ़ोन नंबर</span><span class="sxs-lookup"><span data-stu-id="dca3c-117">Phone number</span></span>
> - <span data-ttu-id="dca3c-118">स्थान की जानकारी</span><span class="sxs-lookup"><span data-stu-id="dca3c-118">Location information</span></span>

2. <span data-ttu-id="dca3c-119">क्रमबद्ध की गयी फ़ील्ड निर्दिष्ट करने के लिए **+ जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="dca3c-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="dca3c-120">सूची में उन विशेषताओं का चयन करें जिन्हें आप अनुक्रमित फ़ील्ड के रूप में जोड़ना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="dca3c-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="dca3c-121">आप हमेशा **जोड़ें** का चयन करके अधिक विशेषताओं को जोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="dca3c-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="dca3c-122">आप **हटाएं** प्रतीक को चुन कर किसी भी चयनित एट्रिब्यूट्स को हटा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="dca3c-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="dca3c-123">अनुक्रमित ग्राहक फ़ील्ड तालिका देखें</span><span class="sxs-lookup"><span data-stu-id="dca3c-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="dca3c-124">निम्न जानकारी तालिका में प्रस्तुत की गई है.</span><span class="sxs-lookup"><span data-stu-id="dca3c-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="dca3c-125">**नाम**: विशेषता का नाम ग्राहक प्रोफ़ाइल निकाय में दिखाई देता है.</span><span class="sxs-lookup"><span data-stu-id="dca3c-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="dca3c-126">**डेटा प्रकार**: यह निर्दिष्ट करता है कि क्या डेटा प्रकार एक स्ट्रिंग, एक संख्या या एक तिथि है.</span><span class="sxs-lookup"><span data-stu-id="dca3c-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="dca3c-127">**खोज में शामिल**: यह निर्दिष्ट करता है कि क्या यह विशेषता **खोज** क्षेत्र का उपयोग करके **ग्राहक** पृष्ठ पर ग्राहकों को खोजने के लिए उपयोग की जा सकती है.</span><span class="sxs-lookup"><span data-stu-id="dca3c-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="dca3c-128">**फ़िल्टर जोड़ें**: इससे यह निर्धारित करने के लिए नियंत्रण कि इस विशेषता का उपयोग **ग्राहक** पृष्ठ पर फ़िल्टर करने के लिए कैसे किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="dca3c-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="dca3c-129">दी गयी विशेषता के लिए फ़िल्टरिंग विकल्प संपादित करना</span><span class="sxs-lookup"><span data-stu-id="dca3c-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="dca3c-130">**ग्राहक** पृष्ठ पर **फ़िल्टर** मेनू में विशेषता स्तरों की एक अलग संख्या शामिल हो सकती है (उदाहरण के लिए, ग्राहकों को फ़िल्टर करने के लिए अलग-अलग आयु समूह).</span><span class="sxs-lookup"><span data-stu-id="dca3c-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="dca3c-131">**खोज और फ़िल्टर सूचकांक** पृष्ठ पर दी गयी विशेषता के लिए **फ़िल्टर जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="dca3c-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="dca3c-132">आप परिणामों की संख्या और उनके क्रम को निर्धारित कर सकते हैं, जिनमें उन्हें व्यवस्थित किया जाना है.</span><span class="sxs-lookup"><span data-stu-id="dca3c-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="dca3c-133">विशेषता के डेटा प्रकार के आधार पर, निम्न में से एक पैन दिखाई देता है.</span><span class="sxs-lookup"><span data-stu-id="dca3c-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="dca3c-134">स्ट्रिंग-प्रकार की विशेषताएं: **स्ट्रिंग फ़िल्टर विकल्प** फलक पर वांछित परिणामों की संख्या और उस क्रम को निर्दिष्ट करें जिसके द्वारा वे व्यवस्थित होंगे.</span><span class="sxs-lookup"><span data-stu-id="dca3c-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="dca3c-135">सांख्यिक प्रकार की विशेषताएँ: **नंबर फ़िल्टर विकल्प** फलक पर शामिल अंतरालों की संख्या और उस क्रम को निर्दिष्ट करें जिसके द्वारा उन्हें व्यवस्थित किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="dca3c-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="dca3c-136">दिनांक प्रकार की विशेषताएँ: **दिनांक फ़िल्टर विकल्प** फलक पर शामिल अंतरालों की संख्या और उस क्रम को निर्दिष्ट करें जिसके द्वारा उन्हें व्यवस्थित किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="dca3c-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="dca3c-137">अपने परिवर्तन लागू करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="dca3c-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="dca3c-138">अपनी सेटिंग लागू करने हेतु तैयार होने के बाद **चलाएँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="dca3c-138">Select **Run** once you're ready to apply your settings.</span></span>
