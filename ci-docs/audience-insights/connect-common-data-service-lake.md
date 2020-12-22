---
title: Common Data Service द्वारा प्रबंधित लेक में निकायों से कनेक्ट करें
description: Common Data Service प्रबंधित डेटा संग्रह से डेटा आयात करें.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643400"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Common Data Service प्रबंधित डेटा संग्रह में डेटा से कनेक्ट करें

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

यह आलेख इस बात की जानकारी प्रदान करता है कि मौजूदा Dynamics 365 ग्राहक Common Data Service प्रबंधित संग्रह में किस तरह से अपने विश्लेषणात्मक निकायों से तुरंत कनेक्ट कर सकते हैं. आगे बढ़ने और प्रबंधित संग्रह में उपलब्ध निकायों की सूची देखने के लिए, आपको Common Data Service संगठन पर एक व्यवस्थापक होना होगा.

## <a name="important-considerations"></a>महत्वपूर्ण विचार

ऑनलाइन सेवाओं में संग्रहित डेटा, जैसे कि Azure Data Lake Storage, को डेटा से संसाधित या Dynamics 365 Customer Insights में संग्रहित किए जाने की तुलना में किसी अन्य स्थान पर संग्रहित किया जा सकता है. ऑनलाइन सेवाओं में संग्रहित डेटा को आयात या कनेक्ट करके, आप सहमत होते हैं कि डेटा को Dynamics 365 Customer Insights के साथ स्थानांतरित और संग्रहित किया जा सकता है. [Microsoft ट्रस्ट सेंटर में और जानें.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>एक Common Data Service प्रबंधित लेक से जोड़ें

1. ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.

2. **डेटा स्रोत जोड़ें** को चुनें.

3. **Common Data Service से कनेक्ट करें** को चुनें और **अगला** चुनें.

4. डेटा स्रोत के लिए एक **नाम** दर्ज करें एवं **अगला** चुनें.

5. अपने Common Data Service संगठन के लिए **सर्वर पता** उपलब्ध कराएं, और चुनें **साइन इन**.

   > [!div class="mx-imgBorder"]
   > ![Common Data Service सर्वर पता दर्ज करने के लिए संवाद बॉक्स](media/enter-CDS-org-details.png)

6. उन निकायों का चयन करें जो आप उपलब्ध सूची से इन्जेस्ट करना चाहते हैं.    

   > [!NOTE]
   > यदि कुछ निकायों का पहले से ही चयन किया जा चुका है, तो उनका उपयोग अन्य Dynamics 365 अनुप्रयोगों (जैसे Dynamics 365 Sales Insights या Customer Service Insights) द्वारा किया जा सकता है. आप चयन को परिवर्तित नहीं कर सकते. डेटा स्रोत बनने के बाद, ये निकाय उपलब्ध होंगे.

   > [!div class="mx-imgBorder"]
   > ![Common Data Service संगठन में निकायों की सूची दिखाने वाला संवाद बॉक्स](media/select-analytical-entities.png)

7. Common Data Service प्रबंधित लेक में अपने चयनित निकायों का समन्वय चालू करने के लिए अपना चयन सहेजें. नये जोड़े गए संबंध आप **डेटा स्रोत** पृष्ठ पर पाएंगे. इसे रिफ्रेश होने के लिए कतारबद्ध किया जाएगा और जब तक सभी निकाय समन्वित नहीं हो जाते, तब तक निकायों की गिनती 0 दिखाई जाएगी.

एक परिवेश का केवल एक डेटा स्रोत एक साथ एक ही Common Data Service द्वारा प्रबंधित लेक का उपयोग कर सकता है.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>किसी Common Data Service प्रबंधित लेक डेटा स्रोत को संपादित करें

डेटा स्रोत बनाने के बाद आप केवल निकाय चयन को संपादित करते हैं. उदाहरण के लिए, यदि Common Data Service में अतिरिक्त निकाय जोड़े गए थे और आप उन्हें आयात भी करना चाहते थे.    
एक अलग Common Data Service से जुड़ने के लिए, [एक नया डेटा स्रोत बनाएं](#connect-to-a-common-data-service-managed-lake).

1. ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.

2. आप जिस डेटा स्रोत को अपडेट करना चाहते हैं, उसके आगे दीर्घवृत्त का चयन करें.

3. सूची से **संपादन करें** विकल्प चुनें.

4. निकायों की उपलब्ध सूची से अतिरिक्त संस्थाओं का चयन करें और **सहेजें** चुनें.
