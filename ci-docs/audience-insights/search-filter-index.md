---
title: ग्राहक की प्रोफ़ाइलों की खोज और उन्हें फिल्टर करें
description: निर्दिष्ट विशेषताओं के लिए एकीकृत कस्टमर प्रोफाइल और फ़िल्टर के बारे में त्वरित जानकारी प्राप्त करें.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270068"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="b1872-103">ग्राहक प्रोफाइल: खोज और फ़िल्टर सूचकांक</span><span class="sxs-lookup"><span data-stu-id="b1872-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="b1872-104">आपके ग्राहक डेटा को एकीकृत करने का परिणाम एक ग्राहक प्रोफ़ाइल निकाय है, जो आपके कुल ग्राहक आधार में एकीकृत दृश्य उपलब्ध करता है.</span><span class="sxs-lookup"><span data-stu-id="b1872-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="b1872-105">शीघ्र [एक विशिष्ट ग्राहक या ग्राहकों के समूह की जानकारी पाएं](customer-profiles.md), पाने के लिए आप **खोज** और **फ़िल्टर** क्षमताओं को **ग्राहक** पृष्ठ पर शीघ्र कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b1872-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="b1872-106">यह जानने के लिए कि पढ़ें कि व्यवस्थापक **खोज और फ़िल्टर सूचकांक** पृष्ठ पर विशेषताओं को कैसे संपादित कर सकते हैं, यह उपयोगकर्ताओं के लिए खोज और फ़िल्टर प्राप्त करने के लिए उपलब्ध हैं.</span><span class="sxs-lookup"><span data-stu-id="b1872-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1872-107">![खोज फ़ि‍ल्‍टर](media/search-filter.png "खोज फ़ि‍ल्‍टर")</span><span class="sxs-lookup"><span data-stu-id="b1872-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="b1872-108">फ़ील्ड जोड़ें और विशेषताएँ निर्दिष्ट करें</span><span class="sxs-lookup"><span data-stu-id="b1872-108">Add fields and specify attributes</span></span>

<span data-ttu-id="b1872-109">यदि आप खोज योग्य विशेषताओं को एक व्यवस्थापक के रूप में पहली बार निर्धारित कर रहे हैं, तो आपको पहले अनुक्रमित फ़ील्ड को निर्धारित करना होगा.</span><span class="sxs-lookup"><span data-stu-id="b1872-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="b1872-110">हमारा सुझाव है कि आप उन सभी विशेषताओं को चुनें जिनके द्वारा उपयोगकर्ता **ग्राहक** पृष्ठ पर ग्राहकों की खोज और उन्हें फ़िल्टर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b1872-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="b1872-111">आप केवल ग्राहक एकीकरण निकाय में मौजूद उन विशेषताओं को निर्दिष्ट कर सकते हैं जिन्हें आपने डेटा एकीकरण प्रक्रिया के दौरान बनाया था.</span><span class="sxs-lookup"><span data-stu-id="b1872-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="b1872-112">**ग्राहक** पृष्ठ खोलें और **खोज और फ़िल्टर संकेत** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b1872-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="b1872-113">क्रमबद्ध की गयी फ़ील्ड निर्दिष्ट करने के लिए **+ जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b1872-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="b1872-114">सूची में उन विशेषताओं का चयन करें जिन्हें आप अनुक्रमित फ़ील्ड के रूप में जोड़ना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="b1872-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="b1872-115">आप हमेशा **जोड़ें** का चयन करके अधिक विशेषताओं को जोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b1872-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="b1872-116">आप **हटाएं** प्रतीक को चुन कर किसी भी चयनित एट्रिब्यूट्स को हटा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b1872-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="b1872-117">अनुक्रमित ग्राहक फ़ील्ड तालिका देखें</span><span class="sxs-lookup"><span data-stu-id="b1872-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="b1872-118">निम्न जानकारी तालिका में प्रस्तुत की गई है.</span><span class="sxs-lookup"><span data-stu-id="b1872-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="b1872-119">**नाम**: विशेषता का नाम ग्राहक प्रोफ़ाइल निकाय में दिखाई देता है.</span><span class="sxs-lookup"><span data-stu-id="b1872-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="b1872-120">**डेटा प्रकार**: यह निर्दिष्ट करता है कि क्या डेटा प्रकार एक स्ट्रिंग, एक संख्या या एक तिथि है.</span><span class="sxs-lookup"><span data-stu-id="b1872-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="b1872-121">**खोज में शामिल**: यह निर्दिष्ट करता है कि क्या यह विशेषता **खोज** क्षेत्र का उपयोग करके **ग्राहक** पृष्ठ पर ग्राहकों को खोजने के लिए उपयोग की जा सकती है.</span><span class="sxs-lookup"><span data-stu-id="b1872-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="b1872-122">**फ़िल्टर जोड़ें**: इससे यह निर्धारित करने के लिए नियंत्रण कि इस विशेषता का उपयोग **ग्राहक** पृष्ठ पर फ़िल्टर करने के लिए कैसे किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="b1872-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="b1872-123">दी गयी विशेषता के लिए फ़िल्टरिंग विकल्प संपादित करना</span><span class="sxs-lookup"><span data-stu-id="b1872-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="b1872-124">**ग्राहक** पृष्ठ पर **फ़िल्टर** मेनू में विशेषता स्तरों की एक अलग संख्या शामिल हो सकती है (उदाहरण के लिए, ग्राहकों को फ़िल्टर करने के लिए अलग-अलग आयु समूह).</span><span class="sxs-lookup"><span data-stu-id="b1872-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="b1872-125">**खोज और फ़िल्टर सूचकांक** पृष्ठ पर दी गयी विशेषता के लिए **फ़िल्टर जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b1872-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="b1872-126">आप परिणामों की संख्या और उनके क्रम को निर्धारित कर सकते हैं, जिनमें उन्हें व्यवस्थित किया जाना है.</span><span class="sxs-lookup"><span data-stu-id="b1872-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="b1872-127">विशेषता के डेटा प्रकार के आधार पर, निम्न में से एक पैन दिखाई देता है.</span><span class="sxs-lookup"><span data-stu-id="b1872-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="b1872-128">स्ट्रिंग-प्रकार की विशेषताएं: **स्ट्रिंग फ़िल्टर विकल्प** फलक पर वांछित परिणामों की संख्या और उस क्रम को निर्दिष्ट करें जिसके द्वारा वे व्यवस्थित होंगे.</span><span class="sxs-lookup"><span data-stu-id="b1872-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="b1872-129">सांख्यिक प्रकार की विशेषताएँ: **नंबर फ़िल्टर विकल्प** फलक पर शामिल अंतरालों की संख्या और उस क्रम को निर्दिष्ट करें जिसके द्वारा उन्हें व्यवस्थित किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="b1872-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="b1872-130">दिनांक प्रकार की विशेषताएँ: **दिनांक फ़िल्टर विकल्प** फलक पर शामिल अंतरालों की संख्या और उस क्रम को निर्दिष्ट करें जिसके द्वारा उन्हें व्यवस्थित किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="b1872-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="b1872-131">अपने परिवर्तन लागू करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b1872-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="b1872-132">अपनी सेटिंग लागू करने हेतु तैयार होने के बाद **चलाएँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b1872-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b1872-133">अगले कदम</span><span class="sxs-lookup"><span data-stu-id="b1872-133">Next steps</span></span>

<span data-ttu-id="b1872-134">ग्राहक प्रोफ़ाइल खोजने के लिए **ग्राहक** पेज पर जाएं या सभी ग्राहक प्रोफ़ाइलों का सबसेट देखने के लिए अनुक्रमित फ़ील्ड का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="b1872-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]