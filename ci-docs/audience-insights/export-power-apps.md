---
title: Power Apps कनेक्टर
description: Power Apps और Power Automate से जुड़ें.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405923"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="79c40-103">Microsoft Power Apps कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="79c40-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="79c40-104">Power Apps के साथ अपने व्यक्तिगत अनुप्रयोगों में एकीकृत ग्राहक प्रोफ़ाइल्स लाएं.</span><span class="sxs-lookup"><span data-stu-id="79c40-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="79c40-105">Power Apps और Dynamics 365 Customer Insights को कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="79c40-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="79c40-106">Customer Insights [Power Apps में डेटा के कई उपलब्ध स्रोतों](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources) में से एक है.</span><span class="sxs-lookup"><span data-stu-id="79c40-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="79c40-107">[किसी अनुप्रयोग में डेटा कनेक्शन जोड़ना](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection) सीखने के लिए Power Apps प्रलेखन देखें.</span><span class="sxs-lookup"><span data-stu-id="79c40-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="79c40-108">हम आपको यह भी सलाह देते हैं कि आप [कैनवास अनुप्रयोग में बड़े डेटासेट को संभालने के लिए Power Apps डेलिगेशन का उपयोग कैसे करता है](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview) की भी समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="79c40-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="79c40-109">उपलब्ध एंटिटी</span><span class="sxs-lookup"><span data-stu-id="79c40-109">Available entities</span></span>

<span data-ttu-id="79c40-110">Customer Insights को डेटा कनेक्शन के रूप में जोड़ने के बाद, आप Power Apps में निम्नलिखित निकायों को चुन सकते हैं:</span><span class="sxs-lookup"><span data-stu-id="79c40-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="79c40-111">ग्राहक: [एकीकृत ग्राहक प्रोफ़ाइल](customer-profiles.md) से डेटा का उपयोग करने के लिए.</span><span class="sxs-lookup"><span data-stu-id="79c40-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="79c40-112">एकीकृत ग्राहक गतिविधि: अनुप्रयोग पर [गतिविधि समयसीमा](activities.md) प्रदर्शित करने के लिए.</span><span class="sxs-lookup"><span data-stu-id="79c40-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="79c40-113">सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="79c40-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="79c40-114">पुनर्प्राप्ति योग्य निकायें</span><span class="sxs-lookup"><span data-stu-id="79c40-114">Retrievable entities</span></span>

<span data-ttu-id="79c40-115">आप केवल **ग्राहक**, **UnifiedActivity**, और **सेगमेंट** निकायों को Power Apps कनेक्टर के माध्यम से पुन: प्राप्त कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="79c40-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="79c40-116">अन्य निकायों को दिखाया गया है क्योंकि अंतर्निहित कनेक्टर Power Automate में ट्रिगर के माध्यम से उनका समर्थन करता है.</span><span class="sxs-lookup"><span data-stu-id="79c40-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="79c40-117">प्रत्यायोजन</span><span class="sxs-lookup"><span data-stu-id="79c40-117">Delegation</span></span>

<span data-ttu-id="79c40-118">डेलीगेशन ग्राहक निकाय और UnifiedActivity निकाय के लिए काम करता है.</span><span class="sxs-lookup"><span data-stu-id="79c40-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="79c40-119">**ग्राहक** निकाय के लिए प्रतिनिधिमंडल: इस निकाय के लिए प्रतिनिधिमंडल का उपयोग करने के लिए, क्षेत्रों को [खोज और फिल्टर सूचकांक](search-filter-index.md) में अनुक्रमित करने की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="79c40-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="79c40-120">**UnifiedActivity** के लिए डेलीगेशन: इस निकाय के लिए डेलिगेशन केवल **ActivityId** और **CustomerId** फ़ील्ड्स के लिए काम करता है.</span><span class="sxs-lookup"><span data-stu-id="79c40-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="79c40-121">डेलीगेशन के बारे में अधिक जानकारी के लिए, [Power Apps डेलीगेट करने योग्य कार्य और संचालन](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps) देखें.</span><span class="sxs-lookup"><span data-stu-id="79c40-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="79c40-122">उदाहरण गैलरी नियंत्रण</span><span class="sxs-lookup"><span data-stu-id="79c40-122">Example gallery control</span></span>

<span data-ttu-id="79c40-123">उदाहरण के लिए, आप ग्राहक प्रोफाइल को [गैलरी नियंत्रण](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery) में जोड़ते हैं .</span><span class="sxs-lookup"><span data-stu-id="79c40-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="79c40-124">आपके द्वारा बनाए जा रहे अनुप्रयोग में **गैलरी** नियंत्रण जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="79c40-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79c40-125">![गैलरी तत्व जोड़ना](media/connector-powerapps9.png "गैलरी तत्व जोड़ें")</span><span class="sxs-lookup"><span data-stu-id="79c40-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="79c40-126">आइटमों के डेटा स्रोत के रूप में **ग्राहक** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="79c40-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="79c40-127">![कोई डेटा स्रोत चुनें](media/choose-datasource-powerapps.png "कोई डेटा स्रोत चुनें")</span><span class="sxs-lookup"><span data-stu-id="79c40-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="79c40-128">आप यह चुनने के लिए कि ग्राहक इकाई के किस फ़ील्ड को गैलरी में दिखाना है, दाईं ओर दिए गए डेटा पैनल में बदलाव कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="79c40-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="79c40-129">अगर आप चुने गए ग्राहक के किसी भी फ़ील्ड को गैलरी में दिखाना चाहते हैं, तो लेबल के पाठ गुण को भरें:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="79c40-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="79c40-130">उदाहरण: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="79c40-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="79c40-131">ग्राहक के लिए एकीकृत टाइमलाइन प्रदर्शित करने के लिए, गैलरी तत्व जोड़ें और आइटम गुण जोड़ें: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="79c40-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="79c40-132">उदाहरण: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="79c40-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
