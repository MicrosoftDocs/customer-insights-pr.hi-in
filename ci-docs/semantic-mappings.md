---
title: सिमेंटिक मैपिंग (पूर्वावलोकन)
description: सिमेंटिक मैपिंग का अवलोकन और उनका इस्तेमाल कैसे करें.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: a60855f6d5616ca9b958752836d1071ae3433db0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642754"
---
# <a name="semantic-mappings-preview"></a>सिमेंटिक मैपिंग (पूर्वावलोकन)

सिमेंटिक मैपिंग से आप अपने गैर-गतिविधि डेटा को पूर्व-निर्धारित स्कीमा से मैप कर सकते हैं. ये स्कीमा Customer Insights को आपकी डेटा विशेषताओं को बेहतर ढंग से समझने में मदद करती हैं। सिमेंटिक मैपिंग और प्रदान किया गया डेटा Customer Insights में नई अंतर्दृष्टि और सुविधाओं को सक्षम करता है। अपने गतिविधि डेटा को स्कीमा में मैप करने के लिए, [गतिविधियां](activities.md) दस्तावेज़ीकरण की समीक्षा करें.

**सिमेंटिक मैपिंग वर्तमान में व्यावसायिक खातों पर आधारित परिवेशों के लिए सक्षम हैं**. *संपर्क प्रोफ़ाइल* Customer Insights में वर्तमान में उपलब्ध सिमेंटिक मैपिंग का एकमात्र प्रकार है।

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile सिमेंटिक निकाय मैपिंग को परिभाषित करें

1. के लिए जाओ **जानकारी** > **सिमेंटिक मैपिंग (पूर्वावलोकन)।**

1. निर्देशित अनुभव शुरू करने के लिए **सिमेंटिक मैपिंग जोड़ें** चुनें.

1. **निकाय डेटा** चरण में, निम्न फ़ील्ड के लिए मान सेट करें:

   - **सिमेंटिक निकाय मैपिंग नाम**: अपने सिमेंटिक निकाय मैपिंग के लिए एक नाम दें.
   - **स्रोत निकाय**: एक ऐसा निकाय चुनें जिसमें संपर्क डेटा शामिल हो.
   - **प्राथमिक कुंजी**: उस फ़ील्ड का चयन करें जो विशिष्ट रूप से किसी संपर्क रिकॉर्ड की पहचान करती है. इसमें कोई डुप्लिकेट मान, खाली मान या अनुपलब्ध मान नहीं होना चाहिए.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="नाम, स्रोत निकाय और प्राथमिक कुंजी के साथ सिमेंटिक निकाय मैपिंग सेट करें.":::

1. जारी रखने के लिए, **अगला** चुनें.

1. **संबंध** चरण में, अपने संपर्क डेटा को उसके संबंधित खाता डेटा से कनेक्ट करने के लिए विवरण कॉन्फ़िगर करें. यह कदम निकायों के बीच संबंध की कल्पना करता है.  

   दो प्रकार के संबंध पथ हैं जिन्हें कार्यान्वित किया जा सकता है: **प्रत्यक्ष संबंध** और **अप्रत्यक्ष संबंध**. अधिक जानकारी के लिए [प्रत्यक्ष और अप्रत्यक्ष संबंध पथ](relationships.md#relationship-paths) पर जाएं.

   1. **संबंध जोड़ें** संबंध कॉन्फ़िगर करें चुनें.
   1. अपने स्रोत निकाय से वह एट्रिब्यूट चुनें जो आपके संपर्क निकाय को किसी अन्य निकाय से जोड़ती है.
   1. अपनी संपर्क निकाय को कनेक्ट करने के लिए निकाय चुनें. आप **खाता निकाय** या **मध्यवर्ती निकाय** सेक्शन से एक निकाय चुन सकते हैं. अगर आप मध्यवर्ती निकाय का चयन करते हैं, तो आपको अपने लक्षित खाता निकाय से कनेक्ट करने के लिए दूसरा संबंध निर्धारित करना होगा.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text=" खाता निकाय या मध्यवर्ती निकाय का चयन करें.":::

   1. **संबंध नाम** दें. अगर आपके निकायों के बीच संबंध पहले से मौजूद है, तो संबंध नाम रीड-ऑनली है. अगर कोई संबंध मौजूद नहीं है, तो आपके द्वारा प्रदान किए गए नाम से एक नया संबंध बनाया जाएगा.
   1. संबंध कॉन्फ़िगरेशन समाप्त करने के लिए **लागू करें** चुनें.

   > [!NOTE]
   > आप संपर्क निकाय और मध्यवर्ती निकायों के साथ अन्य खाता निकायों के बीच अधिक संबंध कॉन्फ़िगर कर सकते हैं.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="विभिन्न संबंधों का दृश्य संपर्क निकायों को खाता निकायों से जोड़ता है.":::

1. जब आप संबंध कॉन्फ़िगरेशन के साथ काम कर लें तो **अगला** चुनें.

1. **सिमेंटिक प्रकार सेट करें** चरण में, **सिमेंटिक प्रकार** चुनें. वर्तमान में, एक **सिमेंटिक प्रकार** है जिसे *ContactProfile* कहा जाता है.

1. दिखाए गए फ़ील्ड के लिए अपने डेटा को *ContactProfile* **सिमेंटिक प्रकार** में मानचित्र करें.
   - आवश्यक फ़ील्ड: संपर्क ID
   - वैकल्पिक फ़ील्ड: प्रथम नाम, उपनाम, जन्म तिथि, लिंग, प्राथमिक ईमेल और प्राथमिक फ़ोन

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="अपने संपर्क डेटा एट्रिब्यूट को प्रदान किए गए आवश्यक और वैकल्पिक क्षेत्रों में मैप करें.":::

1. जारी रखने के लिए, **अगला** चुनें.

1. **समीक्षा** चरण में, सिमेंटिक मैपिंग के कॉन्फ़िगरेशन पर एक नज़र डालें. परिवर्तन करने के लिए संबंधित सेक्शन के लिए **संपादित करें** चुनें.

1. अपना नया **सिमेंटिक मैपिंग** सहेजने के लिए **सहेजें** चुनें.

1. सहेजने के बाद, आप सिमेंटिक मैपिंग को संसाधित करने के लिए **रन** का चयन कर सकते हैं या आप बिना संसाधित किए अपने सिमेंटिक मैपिंग को सहेजने के लिए **बंद** का चयन कर सकते हैं.

1. सिमेंटिक मैपिंग को बाद में चलाने के लिए, सिमेंटिक मैपिंग चुनें और **रीफ़्रेश** चुनें.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>मौजूदा सिमेंटिक मैपिंग प्रबंधित करें

**डेटा** > **सिमेंटिक मैपिंग (पूर्वावलोकन)** पर, आप अपने सभी सहेजे गए सिमेंटिक मैपिंग देख सकते हैं और उन्हें प्रबंधित कर सकते हैं. प्रत्येक सिमेंटिक मैपिंग को एक अलग पंक्ति द्वारा दर्शाया जाता है. आपको स्रोत निकाय, सिमेंटिक प्रकार, मानचित्रण प्रकार और उसकी स्थिति के बारे में विवरण मिलेगा.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="सिमेंटिक मैपिंग को प्रबंधित करने के विकल्प.":::

- **संपादित करें**: समीक्षा चरण में सिमेंटिक मैपिंग सेटअप के कॉन्फ़िगरेशन को खोलता है. आप वर्तमान कॉन्फ़िगरेशन को बदल सकते हैं. परिवर्तनों को संसाधित करने के लिए **सहेजें** और **रन** चुनें.

- **रीफ़्रेश**: चयनित सिमेंटिक मैपिंग को उन निकायों के सबसे अप-टू-डेट डेटा के साथ रीफ़्रेश करता है जो इसके कॉन्फ़िगरेशन का हिस्सा हैं. किसी दिए गए सिमेंटिक मैपिंग को रीफ़्रेश करने से एक ही प्रकार के सभी सिमेंटिक मैपिंग रीफ़्रेश हो जाएंगे.

- **नाम बदलें**: एक संवाद खोलता है जहां आप चयनित सिमेंटिक मैपिंग के लिए एक अलग नाम दर्ज कर सकते हैं. अपने परिवर्तन लागू करने के लिए **सहेजें** का चयन करें.

- **हटाएं**: चयनित सिमेंटिक मैपिंग को हटाने की पुष्टि करने के लिए एक संवाद खोलता है. आप सिमेंटिक मैपिंग और डिलीट आइकन का चयन करके एक साथ एक से अधिक सिमेंटिक मैपिंग को भी हटा सकते हैं. हटाने की पुष्टि करें, **हटाएँ** चयन करें.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>संपर्क-स्तर की गतिविधियों को बनाने के लिए कॉन्टैक्टप्रोफाइल सिमेंटिक एंटिटी मैपिंग का उपयोग करें

A . बनाने के बाद *संपर्क प्रोफ़ाइल* सिमेंटिक इकाई मानचित्रण, आप संपर्कों की गतिविधियों को कैप्चर कर सकते हैं। यह आपको एक खाते के लिए गतिविधि समयरेखा में देखने में सक्षम बनाता है कि प्रत्येक गतिविधि के लिए कौन सा संपर्क जिम्मेदार था। अधिकांश चरण विशिष्ट गतिविधि मानचित्रण कॉन्फ़िगरेशन का अनुसरण करते हैं।

   > [!NOTE]
   > संपर्क-स्तर की गतिविधियों के काम करने के लिए, आपके पास दोनों होना चाहिए **खाता पहचान** और **संपर्क आईडी** आपके गतिविधि डेटा में प्रत्येक रिकॉर्ड के लिए विशेषताएँ।

1. [एक को परिभाषित करें *संपर्क प्रोफ़ाइल* सिमेंटिक इकाई मानचित्रण।](#define-a-contactprofile-semantic-entity-mapping) और सिमेंटिक मैपिंग चलाएँ।

1. के लिए जाओ **जानकारी** > **गतिविधियां**.

1. चुनना**गतिविधि जोड़ें** एक नई गतिविधि बनाने के लिए।

1. गतिविधि को नाम दें, स्रोत गतिविधि निकाय का चयन करें और गतिविधि निकाय की प्राथमिक कुंजी चुनें.

1. में **संबंध** कदम, एक मध्यस्थ इकाई के रूप में अपने संपर्क डेटा का उपयोग करते हुए, अपने गतिविधि स्रोत डेटा और खातों के बीच एक अप्रत्यक्ष संबंध बनाएं। अधिक जानकारी के लिए देखें [प्रत्यक्ष और अप्रत्यक्ष संबंध पथ](relationships.md#relationship-paths).
   - नामक गतिविधि के लिए उदाहरण संबंध *खरीद*:
      - **खरीद स्रोत गतिविधि डेटा** > **संपर्क डेटा** विशेषता पर **संपर्क आईडी**
      - **संपर्क डेटा** > **खाता डेटा** विशेषता पर **खाता पहचान**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="उदाहरण संबंध सेटअप।":::

1. संबंध सेट करने के बाद, चुनें **अगला** और अपनी गतिविधि मैपिंग कॉन्फ़िगरेशन को पूरा करें। गतिविधि निर्माण पर विस्तृत चरणों के लिए, देखें [गतिविधि को परिभाषित करें](activities.md).

1. अपनी गतिविधि मैपिंग चलाएँ।

1. आपकी संपर्क-स्तरीय गतिविधियां अब आपकी ग्राहक टाइमलाइन पर दिखाई देंगी।

   :::image type="content" source="media/Contact_Activities2.png" alt-text="संपर्क गतिविधियों को कॉन्फ़िगर करने के बाद अंतिम परिणाम":::

### <a name="contact-level-activity-timeline-filtering"></a>संपर्क-स्तरीय गतिविधि समयरेखा फ़िल्टरिंग

संपर्क-स्तरीय गतिविधि मैपिंग को कॉन्फ़िगर करने और उसे चलाने के बाद, आपके ग्राहकों के लिए गतिविधि समयरेखा अपडेट की जाएगी। इसमें आपकी आईडी या नाम शामिल हैं, जो आपके पर निर्भर करता है *संपर्क प्रोफ़ाइल* कॉन्फ़िगरेशन, उन गतिविधियों के लिए जिन पर उन्होंने कार्य किया। आप जिन विशिष्ट संपर्कों में रुचि रखते हैं, उन्हें देखने के लिए आप टाइमलाइन में संपर्कों द्वारा गतिविधियों को फ़िल्टर कर सकते हैं। इसके अतिरिक्त, आप उन सभी गतिविधियों को देख सकते हैं जो किसी विशिष्ट संपर्क को असाइन नहीं की गई हैं . का चयन करके **संपर्क के लिए मैप नहीं की गई गतिविधियां**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="संपर्क-स्तर की गतिविधियों के लिए उपलब्ध फ़िल्टरिंग विकल्प।":::

[!INCLUDE [footer-include](includes/footer-banner.md)]