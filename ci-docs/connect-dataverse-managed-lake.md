---
title: Microsoft Dataverse प्रबंधित डेटा संग्रह में डेटा से कनेक्ट करें
description: Microsoft Dataverse प्रबंधित डेटा संग्रह से डेटा आयात करें.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206955"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse प्रबंधित डेटा संग्रह में डेटा से कनेक्ट करें

Microsoft Dataverse उपयोगकर्ता जल्दी से विश्लेषणात्मक संस्थाओं से जुड़ सकते हैं a Microsoft Dataverse प्रबंधित झील। एक परिवेश का केवल एक डेटा स्रोत एक साथ एक ही Dataverse द्वारा प्रबंधित लेक का उपयोग कर सकता है.

> [!NOTE]
> आपको इस पर एक व्यवस्थापक होना चाहिए Dataverse आगे बढ़ने और प्रबंधित झील में उपलब्ध संस्थाओं की सूची देखने के लिए संगठन।

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- ऑनलाइन सेवाओं में संग्रहित डेटा, जैसे कि Azure Data Lake Storage, को डेटा से संसाधित या Dynamics 365 Customer Insights में संग्रहित किए जाने की तुलना में किसी अन्य स्थान पर संग्रहित किया जा सकता है.ऑनलाइन सेवाओं में संग्रहीत डेटा को आयात या कनेक्ट करके, आप सहमत हैं कि डेटा को स्थानांतरित और संग्रहीत किया जा सकता है Dynamics 365 Customer Insights . [माइक्रोसॉफ्ट ट्रस्ट सेंटर पर और जानें।](https://www.microsoft.com/trust-center)

- सिर्फ़ Dataverse संस्थाओं के साथ [ट्रैकिंग बदलें](/power-platform/admin/enable-change-tracking-control-data-synchronization) सक्षम दिखाई दे रहे हैं। इन संस्थाओं को निर्यात किया जा सकता है Dataverse -प्रबंधित डेटा लेक और Customer Insights में उपयोग किया जाता है। लीक से हटकर Dataverse तालिकाओं में परिवर्तन ट्रैकिंग डिफ़ॉल्ट रूप से सक्षम होती है। आपको कस्टम तालिकाओं के लिए परिवर्तन ट्रैकिंग चालू करनी होगी. जाँच करने के लिए कि क्या a Dataverse परिवर्तन ट्रैकिंग के लिए तालिका सक्षम है, यहां जाएं [Power Apps](https://make.powerapps.com) > **जानकारी** > **टेबल**. अपनी रुचि की तालिका ढूंढें और उसका चयन करें। के लिए जाओ **समायोजन** > **उन्नत विकल्प** और समीक्षा करें **रास्ता बदलता है** स्थापना।

## <a name="connect-to-a-dataverse-managed-lake"></a>एक Dataverse प्रबंधित लेक से जोड़ें

1. **डेटा** > **डेटा स्रोत** पर जाएँ.

1. **डेटा स्रोत जोड़ें** को चुनें.

1. **Microsoft Dataverse** का चयन करें.

1. प्रवेश करें **नाम** डेटा स्रोत और एक वैकल्पिक के लिए **विवरण**.

1. Dataverse संगठन के लिए **सर्वर पता** प्रदान करें और **साइन इन** चुनें.

1. उपलब्ध सूची से उन तालिकाओं का चयन करें जिन्हें आप Customer Insights में निकायों के रूप में अंतर्ग्रहण करना चाहते हैं।

   > [!NOTE]
   > यदि कुछ तालिकाएँ पहले से चयनित हैं, तो उनका उपयोग अन्य Dynamics 365 एप्लिकेशनों (जैसे कि Dynamics 365 Sales Insights या Customer Service Insights) द्वारा किया जा सकता है. आप चयन को परिवर्तित नहीं कर सकते. डेटा स्रोत बनने के बाद ये तालिकाएँ निकायों के रूप में उपलब्ध होंगी.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dataverse परिवेश में निकायों की सूची दिखाने वाला संवाद बॉक्स.":::

1. चयनित तालिकाओं को Dataverse से सिंक करना शुरू करने के लिए अपना चयन सहेजें. नये जोड़े गए संबंध आप **डेटा स्रोत** पृष्ठ पर पाएंगे. इसे रीफ़्रेश करने के लिए कतार में रखा जाएगा और जब तक सभी चयनित तालिकाएँ सिंक नहीं हो जातीं, तब तक निकाय की गिनती 0 के रूप में दिखाई देगी.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

डेटा लोड होने में समय लग सकता है। एक सफल रीफ़्रेश के बाद, अंतर्ग्रहीत डेटा की समीक्षा की जा सकती है [**संस्थाओं**](entities.md) पृष्ठ।

## <a name="edit-a-dataverse-managed-lake-data-source"></a>किसी Dataverse प्रबंधित लेक डेटा स्रोत को संपादित करें

डेटा स्रोत बनाने के बाद आप केवल निकाय चयन को संपादित करते हैं. उदाहरण के लिए, यदि Dataverse में अतिरिक्त निकाय जोड़े गए थे और आप उन्हें आयात भी करना चाहते थे.
किसी भिन्न Dataverse Data Lake से कनेक्ट करने के लिए, [एक नया डेटा स्रोत बनाएँ](#connect-to-a-dataverse-managed-lake).

1. **डेटा** > **डेटा स्रोत** पर जाएँ.

1. आप जिस डेटा स्रोत को अपडेट करना चाहते हैं उसके आगे, चुनें **संपादन करना**.

1. निकायों की उपलब्ध सूची से अतिरिक्त निकायों का चयन करें.

1. क्लिक **बचाना** अपने परिवर्तनों को लागू करने के लिए और पर वापस लौटने के लिए **डेटा स्रोत** पृष्ठ।

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
