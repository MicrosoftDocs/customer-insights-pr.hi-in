---
title: Power Apps कनेक्टर
description: Power Apps और Power Automate से जुड़ें.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598157"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="bbbd1-103">Microsoft Power Apps कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="bbbd1-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="bbbd1-104">Power Apps के साथ अपने व्यक्तिगत अनुप्रयोगों में एकीकृत ग्राहक प्रोफ़ाइल्स लाएं.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="bbbd1-105">Power Apps और Dynamics 365 Customer Insights को कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="bbbd1-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="bbbd1-106">Customer Insights [Power Apps में डेटा के कई उपलब्ध स्रोतों](/powerapps/maker/canvas-apps/working-with-data-sources) में से एक है.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="bbbd1-107">[किसी अनुप्रयोग में डेटा कनेक्शन जोड़ना](/powerapps/maker/canvas-apps/add-data-connection) सीखने के लिए Power Apps प्रलेखन देखें.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="bbbd1-108">हम आपको यह भी सलाह देते हैं कि आप [कैनवास अनुप्रयोग में बड़े डेटासेट को संभालने के लिए Power Apps डेलिगेशन का उपयोग कैसे करता है](/powerapps/maker/canvas-apps/delegation-overview) की भी समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="bbbd1-109">उपलब्ध एंटिटी</span><span class="sxs-lookup"><span data-stu-id="bbbd1-109">Available entities</span></span>

<span data-ttu-id="bbbd1-110">Customer Insights को डेटा कनेक्शन के रूप में जोड़ने के बाद, आप Power Apps में निम्नलिखित निकायों को चुन सकते हैं:</span><span class="sxs-lookup"><span data-stu-id="bbbd1-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="bbbd1-111">ग्राहक: [एकीकृत ग्राहक प्रोफ़ाइल](customer-profiles.md) से डेटा का उपयोग करने के लिए.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="bbbd1-112">UnifiedActivity: ऐप पर [गतिविधि टाइमलाइन](activities.md) प्रदर्शित करने के लिए.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="bbbd1-113">सीमाएँ</span><span class="sxs-lookup"><span data-stu-id="bbbd1-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="bbbd1-114">पुनर्प्राप्ति योग्य निकायें</span><span class="sxs-lookup"><span data-stu-id="bbbd1-114">Retrievable entities</span></span>

<span data-ttu-id="bbbd1-115">आप केवल **ग्राहक**, **UnifiedActivity**, और **सेगमेंट** निकायों को Power Apps कनेक्टर के माध्यम से पुन: प्राप्त कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="bbbd1-116">अन्य निकायों को दिखाया गया है क्योंकि अंतर्निहित कनेक्टर Power Automate में ट्रिगर के माध्यम से उनका समर्थन करता है.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="bbbd1-117">प्रत्यायोजन</span><span class="sxs-lookup"><span data-stu-id="bbbd1-117">Delegation</span></span>

<span data-ttu-id="bbbd1-118">डेलीगेशन ग्राहक निकाय और UnifiedActivity निकाय के लिए काम करता है.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="bbbd1-119">**ग्राहक** निकाय के लिए प्रतिनिधिमंडल: इस निकाय के लिए प्रतिनिधिमंडल का उपयोग करने के लिए, क्षेत्रों को [खोज और फिल्टर सूचकांक](search-filter-index.md) में अनुक्रमित करने की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="bbbd1-120">**UnifiedActivity** के लिए डेलीगेशन: इस निकाय के लिए डेलिगेशन केवल **ActivityId** और **CustomerId** फ़ील्ड्स के लिए काम करता है.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="bbbd1-121">डेलीगेशन के बारे में अधिक जानकारी के लिए, [Power Apps डेलीगेट करने योग्य कार्य और संचालन](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps) देखें.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="bbbd1-122">उदाहरण गैलरी नियंत्रण</span><span class="sxs-lookup"><span data-stu-id="bbbd1-122">Example gallery control</span></span>

<span data-ttu-id="bbbd1-123">उदाहरण के लिए, आप ग्राहक प्रोफाइल को [गैलरी नियंत्रण](/powerapps/maker/canvas-apps/add-gallery) में जोड़ते हैं .</span><span class="sxs-lookup"><span data-stu-id="bbbd1-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="bbbd1-124">आपके द्वारा बनाए जा रहे अनुप्रयोग में **गैलरी** नियंत्रण जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bbbd1-125">![गैलरी तत्व जोड़ना](media/connector-powerapps9.png "गैलरी तत्व जोड़ें")</span><span class="sxs-lookup"><span data-stu-id="bbbd1-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="bbbd1-126">आइटमों के डेटा स्रोत के रूप में **ग्राहक** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bbbd1-127">![कोई डेटा स्रोत चुनें](media/choose-datasource-powerapps.png "कोई डेटा स्रोत चुनें")</span><span class="sxs-lookup"><span data-stu-id="bbbd1-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="bbbd1-128">आप यह चुनने के लिए कि ग्राहक इकाई के किस फ़ील्ड को गैलरी में दिखाना है, दाईं ओर दिए गए डेटा पैनल में बदलाव कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="bbbd1-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="bbbd1-129">अगर आप चुने गए ग्राहक के किसी भी फ़ील्ड को गैलरी में दिखाना चाहते हैं, तो लेबल के पाठ गुण को भरें:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="bbbd1-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="bbbd1-130">उदाहरण: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="bbbd1-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="bbbd1-131">ग्राहक के लिए एकीकृत टाइमलाइन प्रदर्शित करने के लिए, गैलरी तत्व जोड़ें और आइटम गुण जोड़ें: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="bbbd1-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="bbbd1-132">उदाहरण: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="bbbd1-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]