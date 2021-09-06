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
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031797"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps कनेक्टर (पूर्वावलोकन)

Power Apps के साथ अपने व्यक्तिगत अनुप्रयोगों में एकीकृत ग्राहक प्रोफ़ाइल्स लाएं.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps और Dynamics 365 Customer Insights को कनेक्ट करें

Customer Insights [Power Apps में डेटा के कई उपलब्ध स्रोतों](/powerapps/maker/canvas-apps/working-with-data-sources) में से एक है.

[किसी अनुप्रयोग में डेटा कनेक्शन जोड़ना](/powerapps/maker/canvas-apps/add-data-connection) सीखने के लिए Power Apps प्रलेखन देखें. हम आपको यह भी सलाह देते हैं कि आप [कैनवास अनुप्रयोग में बड़े डेटासेट को संभालने के लिए Power Apps डेलिगेशन का उपयोग कैसे करता है](/powerapps/maker/canvas-apps/delegation-overview) की भी समीक्षा करें.

## <a name="available-entities"></a>उपलब्ध एंटिटी

Customer Insights को डेटा कनेक्शन के रूप में जोड़ने के बाद, आप Power Apps में निम्नलिखित निकायों को चुन सकते हैं:

- ग्राहक: [एकीकृत ग्राहक प्रोफ़ाइल](customer-profiles.md) से डेटा का उपयोग करने के लिए.
- UnifiedActivity: ऐप पर [गतिविधि टाइमलाइन](activities.md) प्रदर्शित करने के लिए.

## <a name="limitations"></a>सीमाएँ

### <a name="retrievable-entities"></a>पुनर्प्राप्ति योग्य निकायें

आप केवल **ग्राहक**, **UnifiedActivity**, और **सेगमेंट** निकायों को Power Apps कनेक्टर के माध्यम से पुन: प्राप्त कर सकते हैं. अन्य निकायों को दिखाया गया है क्योंकि अंतर्निहित कनेक्टर Power Automate में ट्रिगर के माध्यम से उनका समर्थन करता है.  

### <a name="delegation"></a>प्रत्यायोजन

डेलीगेशन ग्राहक निकाय और UnifiedActivity निकाय के लिए काम करता है. 

- **ग्राहक** निकाय के लिए प्रतिनिधिमंडल: इस निकाय के लिए प्रतिनिधिमंडल का उपयोग करने के लिए, क्षेत्रों को [खोज और फिल्टर सूचकांक](search-filter-index.md) में अनुक्रमित करने की आवश्यकता है.  

- **UnifiedActivity** के लिए डेलीगेशन: इस निकाय के लिए डेलिगेशन केवल **ActivityId** और **CustomerId** फ़ील्ड्स के लिए काम करता है.  

- डेलीगेशन के बारे में अधिक जानकारी के लिए, [Power Apps डेलीगेट करने योग्य कार्य और संचालन](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps) देखें. 

## <a name="example-gallery-control"></a>उदाहरण गैलरी नियंत्रण

उदाहरण के लिए, आप ग्राहक प्रोफाइल को [गैलरी नियंत्रण](/powerapps/maker/canvas-apps/add-gallery) में जोड़ते हैं .

1. आपके द्वारा बनाए जा रहे अनुप्रयोग में **गैलरी** नियंत्रण जोड़ें.

> [!div class="mx-imgBorder"]
> ![गैलरी तत्व जोड़ना.](media/connector-powerapps9.png "गैलरी तत्व जोड़ें")

1. आइटमों के डेटा स्रोत के रूप में **ग्राहक** का चयन करें.

    > [!div class="mx-imgBorder"]
    > ![कोई डेटा स्रोत चुनें.](media/choose-datasource-powerapps.png "कोई डेटा स्रोत चुनें")

1. आप यह चुनने के लिए कि ग्राहक इकाई के किस फ़ील्ड को गैलरी में दिखाना है, दाईं ओर दिए गए डेटा पैनल में बदलाव कर सकते हैं.

1. अगर आप चुने गए ग्राहक के किसी भी फ़ील्ड को गैलरी में दिखाना चाहते हैं, तो लेबल के पाठ गुण को भरें:  **{Name_of_the_gallery}.Selected.{property_name}**

    उदाहरण: Gallery1.Selected.address1_city

1. ग्राहक के लिए एकीकृत टाइमलाइन प्रदर्शित करने के लिए, गैलरी तत्व जोड़ें और आइटम गुण जोड़ें: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    उदाहरण: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]