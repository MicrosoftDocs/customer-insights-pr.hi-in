---
title: Power Apps कनेक्टर
description: Power Apps और Power Automate से जुड़ें.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 18cc32a169e79794d2d3203d462620ab41efaafe
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455954"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps कनेक्टर (पूर्वावलोकन)

Power Apps के साथ अपने व्यक्तिगत अनुप्रयोगों में एकीकृत ग्राहक प्रोफ़ाइल्स लाएं.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps और Dynamics 365 Customer Insights को कनेक्ट करें

Customer Insights [Power Apps में डेटा के कई उपलब्ध स्रोतों](/powerapps/maker/canvas-apps/working-with-data-sources) में से एक है.

[किसी अनुप्रयोग में डेटा कनेक्शन जोड़ना](/powerapps/maker/canvas-apps/add-data-connection) सीखने के लिए Power Apps प्रलेखन देखें. हम आपको यह भी सलाह देते हैं कि आप [कैनवास अनुप्रयोग में बड़े डेटासेट को संभालने के लिए Power Apps डेलिगेशन का उपयोग कैसे करता है](/powerapps/maker/canvas-apps/delegation-overview) की भी समीक्षा करें.

## <a name="available-entities"></a>उपलब्ध एंटिटी

Customer Insights को डेटा कनेक्शन के रूप में जोड़ने के बाद, आप Power Apps में निम्नलिखित निकायों को चुन सकते हैं:

- **ग्राहक**: [एकीकृत ग्राहक प्रोफ़ाइल](customer-profiles.md) से डेटा का उपयोग करने के लिए.
- **UnifiedActivity**: ऐप में [गतिविधि टाइमलाइन](activities.md) दिखाना.
- **ContactProfile**: ग्राहक के संपर्क दिखाना. यह निकाय केवल व्यावसायिक खातों के लिए ऑडियंस इनसाइट्स परिवेश में मौजूद है.

## <a name="limitations"></a>सीमाएँ

### <a name="retrievable-entities"></a>पुनर्प्राप्ति योग्य निकायें

आप Power Apps कनेक्टर के द्वारा सिर्फ **ग्राहक**, **UnifiedActivity**, **सेगमेंट** और **ContactProfile** निकायों को पुनर्प्राप्त कर सकते हैं. ContactProfile ऑडिएंस इनसाइट्स इंस्टेंस में सिर्फ व्यावसायिक खातों के लिए उपलब्ध है. अन्य निकायों को दिखाया गया है क्योंकि अंतर्निहित कनेक्टर Power Automate में ट्रिगर के माध्यम से उनका समर्थन करता है.

आप प्रति 60 सेकंड में अधिकतम 100 कॉल कर सकते हैं। आप $स्किप पैरामीटर का उपयोग करके API एंडपॉइंट को कई बार कॉल कर सकते हैं। [$स्किप पैरामीटर के बारे में और जानें।](/connectors/customerinsights/#get-items-from-an-entity)

### <a name="delegation"></a>प्रत्यायोजन

डेलीगेशन **ग्राहक** निकाय और **UnifiedActivity** निकाय के लिए काम करता है. 

- **ग्राहक** निकाय के लिए प्रतिनिधिमंडल: इस निकाय के लिए प्रतिनिधिमंडल का उपयोग करने के लिए, क्षेत्रों को [खोज और फिल्टर सूचकांक](search-filter-index.md) में अनुक्रमित करने की आवश्यकता है.  
- **UnifiedActivity** के लिए डेलीगेशन: इस निकाय के लिए डेलिगेशन केवल **ActivityId** और **CustomerId** फ़ील्ड्स के लिए काम करता है.  
- **ContactProfile** के लिए डेलीगेशन: इस इकाई के लिए डेलीगेशन सिर्फ **ContactId** और **CustomerId** फ़ील्ड के लिए काम करता है. ContactProfile व्यावसायिक खातों के लिए सिर्फ ऑडिएंस इनसाइट्स परिवेश में उपलब्ध है.

डेलीगेशन के बारे में अधिक जानकारी के लिए, [Power Apps प्रत्यायोजित फंक्शन और ऑपरेशन](/powerapps/maker/canvas-apps/delegation-overview) पर जाएं. 

## <a name="example-gallery-control"></a>उदाहरण गैलरी नियंत्रण

आप [गैलरी नियंत्रण](/powerapps/maker/canvas-apps/add-gallery) में ग्राहक प्रोफ़ाइल जोड़ सकते हैं.

1. आपके द्वारा बनाए जा रहे अनुप्रयोग में **गैलरी** नियंत्रण जोड़ें.

    > [!div class="mx-imgBorder"]
    > ![गैलरी तत्व जोड़ना.](media/connector-powerapps9.png "गैलरी तत्व जोड़ें.")

2. आइटमों के डेटा स्रोत के रूप में **ग्राहक** का चयन करें.

    > [!div class="mx-imgBorder"]
    > ![कोई डेटा स्रोत चुनें.](media/choose-datasource-powerapps.png "कोई डेटा स्रोत चुनें.")

3. आप यह चुनने के लिए कि ग्राहक इकाई के किस फ़ील्ड को गैलरी में दिखाना है, दाईं ओर दिए गए डेटा पैनल में बदलाव कर सकते हैं.

4. अगर आप चयनित ग्राहक से गैलरी में कोई फ़ील्ड दिखाना चाहते हैं, तो **{Name_of_the_gallery}.Selected.{property_name}** का इस्तेमाल करके लेबल की **टेक्स्ट** प्रॉपर्टी भरें  
    - उदाहरण: _Gallery1.Selected.address1_city_

5. किसी ग्राहक के लिए एकीकृत टाइमलाइन दिखाने के लिए, गैलरी एलीमेंट जोड़ें और **Filter('UnifiedActivity', CustomerId = {Customer_Id})** का इस्तेमाल करके **आइटम** प्रॉपर्टी जोड़ें  
    - उदाहरण: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
