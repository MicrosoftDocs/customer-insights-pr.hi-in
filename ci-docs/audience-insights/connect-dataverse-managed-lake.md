---
title: Microsoft Dataverse में तालिकाएं से Connect करें
description: Microsoft Dataverse प्रबंधित डेटा संग्रह से डेटा आयात करें.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692576"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse प्रबंधित डेटा संग्रह में डेटा से कनेक्ट करें

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

यह आलेख इस बारे में जानकारी प्रदान करता है कि कैसे Dataverse उपयोगकर्ता Dataverse प्रबंधित लेक में अपनी विश्लेषणात्मक निकायों से जल्दी से जुड़ सकते हैं. आगे बढ़ने और प्रबंधित संग्रह में उपलब्ध निकायों की सूची देखने के लिए, आपको Dataverse संगठन पर एक व्यवस्थापक होना होगा.

## <a name="important-considerations"></a>महत्वपूर्ण विचार

ऑनलाइन सेवाओं में संग्रहित डेटा, जैसे कि Azure Data Lake Storage, को डेटा से संसाधित या Dynamics 365 Customer Insights में संग्रहित किए जाने की तुलना में किसी अन्य स्थान पर संग्रहित किया जा सकता है. ऑनलाइन सेवाओं में संग्रहित डेटा को आयात या कनेक्ट करके, आप सहमत होते हैं कि डेटा को Dynamics 365 Customer Insights के साथ स्थानांतरित और संग्रहित किया जा सकता है. [Microsoft ट्रस्ट सेंटर में और जानें.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>एक Dataverse प्रबंधित लेक से जोड़ें

1. ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.

2. **डेटा स्रोत जोड़ें** को चुनें.

3. **Microsoft Dataverse प्रबंधित लेक से कनेक्ट करें** चुनें और **अगला** चुनें.

4. डेटा स्रोत के लिए एक **नाम** दर्ज करें एवं **अगला** चुनें. नाम दिशानिर्देश: 
   - अक्षर के साथ शुरू करें.
   - केवल अक्षर और संख्याओं का उपयोग करें. विशेष वर्ण और खाली जगह की अनुमति नहीं है.
   - 3 से 64 वर्णों के बीच उपयोग करें.

5. Dataverse संगठन के लिए **सर्वर पता** प्रदान करें और **साइन इन** चुनें.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="डेटा अंतर्ग्रहण चरण में वह स्क्रीन जहां उपयोगकर्ता Dataverse परिवेश URL दर्ज कर सकता है.":::

6. उपलब्ध सूची से उन तालिकाओं को चुनें जिन्हें आप निकाय के रूप में ऑडियंस इनसाइट के रूप में अंतर्ग्रहण करना चाहते हैं.    

   > [!NOTE]
   > यदि कुछ तालिकाएँ पहले से चयनित हैं, तो उनका उपयोग अन्य Dynamics 365 एप्लिकेशनों (जैसे कि Dynamics 365 Sales Insights या Customer Service Insights) द्वारा किया जा सकता है. आप चयन को परिवर्तित नहीं कर सकते. डेटा स्रोत बनने के बाद ये तालिकाएँ निकायों के रूप में उपलब्ध होंगी.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dataverse परिवेश में निकायों की सूची दिखाने वाला संवाद बॉक्स.":::

7. चयनित तालिकाओं को Dataverse से सिंक करना शुरू करने के लिए अपना चयन सहेजें. नये जोड़े गए संबंध आप **डेटा स्रोत** पृष्ठ पर पाएंगे. इसे रीफ़्रेश करने के लिए कतार में रखा जाएगा और जब तक सभी चयनित तालिकाएँ सिंक नहीं हो जातीं, तब तक निकाय की गिनती 0 के रूप में दिखाई देगी.

एक परिवेश का केवल एक डेटा स्रोत एक साथ एक ही Dataverse द्वारा प्रबंधित लेक का उपयोग कर सकता है.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>किसी Dataverse प्रबंधित लेक डेटा स्रोत को संपादित करें

डेटा स्रोत बनाने के बाद आप केवल निकाय चयन को संपादित करते हैं. उदाहरण के लिए, यदि Dataverse में अतिरिक्त निकाय जोड़े गए थे और आप उन्हें आयात भी करना चाहते थे.    
किसी भिन्न Dataverse Data Lake से कनेक्ट करने के लिए, [एक नया डेटा स्रोत बनाएँ](#connect-to-a-dataverse-managed-lake).

1. ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.

2. आप जिस डेटा स्रोत को अपडेट करना चाहते हैं, उसके आगे दीर्घवृत्त का चयन करें.

3. सूची से **संपादन करें** विकल्प चुनें.

4. निकायों की उपलब्ध सूची से अतिरिक्त संस्थाओं का चयन करें और **सहेजें** चुनें.

[!INCLUDE[footer-include](../includes/footer-banner.md)]