---
title: Common Data Service द्वारा प्रबंधित लेक में निकायों से कनेक्ट करें
description: Common Data Service प्रबंधित डेटा संग्रह से डेटा आयात करें.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267816"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="5132c-103">Common Data Service प्रबंधित डेटा संग्रह में डेटा से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="5132c-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="5132c-104">यह आलेख इस बात की जानकारी प्रदान करता है कि मौजूदा Dynamics 365 ग्राहक Common Data Service प्रबंधित संग्रह में किस तरह से अपने विश्लेषणात्मक निकायों से तुरंत कनेक्ट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5132c-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="5132c-105">आगे बढ़ने और प्रबंधित संग्रह में उपलब्ध निकायों की सूची देखने के लिए, आपको Common Data Service संगठन पर एक व्यवस्थापक होना होगा.</span><span class="sxs-lookup"><span data-stu-id="5132c-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="5132c-106">महत्वपूर्ण विचार</span><span class="sxs-lookup"><span data-stu-id="5132c-106">Important considerations</span></span>

<span data-ttu-id="5132c-107">ऑनलाइन सेवाओं में संग्रहित डेटा, जैसे कि Azure Data Lake Storage, को डेटा से संसाधित या Dynamics 365 Customer Insights में संग्रहित किए जाने की तुलना में किसी अन्य स्थान पर संग्रहित किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="5132c-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="5132c-108"> ऑनलाइन सेवाओं में संग्रहित डेटा को आयात या कनेक्ट करके, आप सहमत होते हैं कि डेटा को Dynamics 365 Customer Insights के साथ स्थानांतरित और संग्रहित किया जा सकता है. [Microsoft ट्रस्ट सेंटर में और जानें.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="5132c-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="5132c-109">एक Common Data Service प्रबंधित लेक से जोड़ें</span><span class="sxs-lookup"><span data-stu-id="5132c-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="5132c-110">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="5132c-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="5132c-111">**डेटा स्रोत जोड़ें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="5132c-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="5132c-112">**Common Data Service से कनेक्ट करें** को चुनें और **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="5132c-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="5132c-113">डेटा स्रोत के लिए एक **नाम** दर्ज करें एवं **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="5132c-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="5132c-114">नाम दिशानिर्देश:</span><span class="sxs-lookup"><span data-stu-id="5132c-114">Name guidelines:</span></span> 
   - <span data-ttu-id="5132c-115">अक्षर के साथ शुरू करें.</span><span class="sxs-lookup"><span data-stu-id="5132c-115">Start with a letter.</span></span>
   - <span data-ttu-id="5132c-116">केवल अक्षर और संख्याओं का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="5132c-116">Use letters and numbers only.</span></span> <span data-ttu-id="5132c-117">विशेष वर्ण और खाली जगह की अनुमति नहीं है.</span><span class="sxs-lookup"><span data-stu-id="5132c-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="5132c-118">3 से 64 वर्णों के बीच उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="5132c-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="5132c-119">अपने Common Data Service संगठन के लिए **सर्वर पता** उपलब्ध कराएं, और चुनें **साइन इन**.</span><span class="sxs-lookup"><span data-stu-id="5132c-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5132c-120">![Common Data Service सर्वर पता दर्ज करने के लिए संवाद बॉक्स](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="5132c-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="5132c-121">उन निकायों का चयन करें जो आप उपलब्ध सूची से इन्जेस्ट करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="5132c-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="5132c-122">यदि कुछ निकायों का पहले से ही चयन किया जा चुका है, तो उनका उपयोग अन्य Dynamics 365 अनुप्रयोगों (जैसे Dynamics 365 Sales Insights या Customer Service Insights) द्वारा किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="5132c-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="5132c-123">आप चयन को परिवर्तित नहीं कर सकते.</span><span class="sxs-lookup"><span data-stu-id="5132c-123">You can't change the selection.</span></span> <span data-ttu-id="5132c-124">डेटा स्रोत बनने के बाद, ये निकाय उपलब्ध होंगे.</span><span class="sxs-lookup"><span data-stu-id="5132c-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5132c-125">![Common Data Service संगठन में निकायों की सूची दिखाने वाला संवाद बॉक्स](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="5132c-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="5132c-126">Common Data Service प्रबंधित लेक में अपने चयनित निकायों का समन्वय चालू करने के लिए अपना चयन सहेजें.</span><span class="sxs-lookup"><span data-stu-id="5132c-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="5132c-127">नये जोड़े गए संबंध आप **डेटा स्रोत** पृष्ठ पर पाएंगे.</span><span class="sxs-lookup"><span data-stu-id="5132c-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="5132c-128">इसे रिफ्रेश होने के लिए कतारबद्ध किया जाएगा और जब तक सभी निकाय समन्वित नहीं हो जाते, तब तक निकायों की गिनती 0 दिखाई जाएगी.</span><span class="sxs-lookup"><span data-stu-id="5132c-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="5132c-129">एक परिवेश का केवल एक डेटा स्रोत एक साथ एक ही Common Data Service द्वारा प्रबंधित लेक का उपयोग कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="5132c-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="5132c-130">किसी Common Data Service प्रबंधित लेक डेटा स्रोत को संपादित करें</span><span class="sxs-lookup"><span data-stu-id="5132c-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="5132c-131">डेटा स्रोत बनाने के बाद आप केवल निकाय चयन को संपादित करते हैं.</span><span class="sxs-lookup"><span data-stu-id="5132c-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="5132c-132">उदाहरण के लिए, यदि Common Data Service में अतिरिक्त निकाय जोड़े गए थे और आप उन्हें आयात भी करना चाहते थे.</span><span class="sxs-lookup"><span data-stu-id="5132c-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="5132c-133">एक अलग Common Data Service से जुड़ने के लिए, [एक नया डेटा स्रोत बनाएं](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="5132c-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="5132c-134">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="5132c-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="5132c-135">आप जिस डेटा स्रोत को अपडेट करना चाहते हैं, उसके आगे दीर्घवृत्त का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="5132c-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="5132c-136">सूची से **संपादन करें** विकल्प चुनें.</span><span class="sxs-lookup"><span data-stu-id="5132c-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="5132c-137">निकायों की उपलब्ध सूची से अतिरिक्त संस्थाओं का चयन करें और **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="5132c-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]