---
title: डेटा एकीकरण के लिए निकायों का मिलान करें
description: एकीकृत ग्राहक प्रोफाइल बनाने के लिए निकायों का मिलान करें.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: 44f030f69b84a00438e92aa5fddca832f4e54c41
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642672"
---
# <a name="match-entities"></a>निकायों का मिलान करें

मैच चरण यह निर्दिष्ट करता है कि आपके डेटासेट को एकीकृत कस्टमर प्रोफ़ाइल डेटासेट से कैसे संयोजित किया जाए. डेटा एकीकरण प्रक्रिया में [मानचित्र कदम](map-entities.md) को पूरा करने के बाद, आप अपनी निकायों से मिलान के लिए तैयार हैं. मैच के चरण के लिए कम से कम मैप किए हुए दो निकाय की आवश्यकता होगी.

मिलान पेज में तीन सेगमेंट होते हैं: 
- मुख्य मेट्रिक्स जो मिलान किए गए रिकॉर्ड की संख्या को सारांशित करते हैं
- क्रॉस-निकाय मिलान के लिए क्रम और नियमों का मिलान करें
- मिलान वाली निकायों की डीडुप्लीकेशन के नियम

## <a name="specify-the-match-order"></a>सॉर्ट मिलान निर्दिष्ट करें

प्रत्येक मिलान एक एकल, समेकित निकाय में दो या अधिक निकायों को एकीकृत करता है. इसी समय, यह विशिष्ट ग्राहक रिकॉर्ड रखता है. मिलान क्रम उस क्रम को इंगित करता है जिसमें सिस्टम अभिलेखों से मिलान करने का प्रयास करता है।

> [!IMPORTANT]
> वह निकाय जिसे आप अपने प्राथमिक निकाय के रूप में चुनते हैं, आपके एकीकृत प्रोफ़ाइल डेटासेट के आधार के रूप में काम करेगा. मिलान निकाय के दौरान चुने जाने वाले अतिरिक्त निकाय इस निकाय में जुड़ेंगे. इसका मतलब यह नहीं है कि एकीकृत निकाय में इस निकाय में शामिल *सभी* डेटा शामिल होंगे.
>
> दो अवधारणाएं हैं जो आपके निकाय के पदानुक्रम को चुनने में आपकी सहायता कर सकते हैं:
>
> - अपने ग्राहकों के बारे में प्राथमिक निकाय के रूप में सबसे पूर्ण और विश्वसनीय प्रोफ़ाइल डेटा वाला निकाय चुनें.
> - वह निकाय चुनें जिसमें प्राथमिक निकाय के रूप में अन्य निकायों (उदाहरण के लिए, नाम, फ़ोन नंबर, या ईमेल पता) के साथ कई विशेषताएं समान हों।

1. **डेटा** > **Unify** > **मैच** पर जाएं और मैच चरण शुरू करने के लिए **क्रम सेट करें** का चयन करें.
1. चुनना**इकाई आदेश।** उदाहरण के लिए, चुनें **ईकामर्स: ईकामर्स संपर्क** प्राथमिक इकाई के रूप में और **वफादारी योजना: loyCustomers** दूसरी इकाई के रूप में। 
1. निकाय में प्रत्येक रिकॉर्ड को एक अद्वितीय ग्राहक के रूप में रखने और प्रत्येक निम्न निकाय से मिलान करने के लिए, चुनें **सभी शामिल।**
1. **पूर्ण** चयन करें. 

मिलान क्रम निर्दिष्ट करने के बाद, परिभाषित मिलान जोड़े में प्रदर्शित होते हैं **मिलान किए गए रिकॉर्ड विवरण** खंड पर **जानकारी** > **यूनिफाई** > **मिलान**. मिलान की प्रक्रिया पूरी होने तक मुख्य मेट्रिक खाली रहती हैं.

:::image type="content" source="media/match-page.png" alt-text="डेटा एकीकरण प्रक्रिया के Unify क्षेत्र में मैच पृष्ठ का स्क्रीनशॉट.":::
  
प्राथमिक निकाय *eCommerce:eCommerceContacts* का मिलान अगले निकाय *LoyaltyScheme:loyCustomers* के साथ किया जाता है. यदि आपके पास दो से अधिक निकाय हैं, तो पहले मिलान चरण से प्राप्त होने वाले डेटासेट का मिलान निम्न निकाय से किया जाता है।

## <a name="define-rules-for-match-pairs"></a>मिलान जोड़े के लिए नियम परिभाषित करें

मिलान के नियम तर्क को निर्दिष्ट करते हैं जिसके द्वारा एक विशिष्ट जोड़ीदार निकायों का मिलान किया जाएगा.

निकाय नाम के बगल में **नियमों की आवश्यकता है** चेतावनी यह दर्शाती है कि मिलान जोड़ी के लिए कोई मिलान नियम परिभाषित नहीं है. 

:::image type="content" source="media/match-rule-add.png" alt-text="नियमों को जोड़ने के लिए नियंत्रण के साथ मिलान रिकॉर्ड विवरण अनुभाग का स्क्रीनशॉट.":::

1. चुनना**नियम जोड़ें** में एक इकाई के तहत **मिलान किए गए रिकॉर्ड विवरण** मैच के नियमों को परिभाषित करने के लिए अनुभाग।

1. **नियम बनाएं** फलक में, नियम के लिए शर्तों को कॉन्फ़िगर करें.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="शर्तों के साथ एक खुले मैच नियम का स्क्रीनशॉट जोड़ा गया.":::

   - **निकाय/फ़ील्ड (पहली पंक्ति)**: एक संबंधित निकाय और एक रिकॉर्ड परिसंपत्ति को निर्दिष्ट करने के लिए वह विशेषता चुनें जो ग्राहक के लिए विशिष्ट है. उदाहरण के लिए, एक फ़ोन नंबर या ईमेल पता. गतिविधि-प्रकार विशेषताओं के अनुसार मिलान से बचें. उदाहरण के लिए, खरीद ID को अन्य रिकॉर्ड प्रकारों में कोई मिलान नहीं मिलेगा.

   - **निकाय/फ़ील्ड (दूसरी पंक्ति)**: पहली पंक्ति में निर्दिष्ट निकाय की विशेषता से संबंधित विशेषता चुनें.

   - **सामान्यीकृत**: चयनित विशेषताओं के लिए सामान्यीकरण विकल्प चुनें. 
     - अंक: अन्य अंक प्रणालियों को बदलता है, जैसे कि रोमन अंकों को अरबी अंकों में. *VIII* *8* बन जाता है.
     - प्रतीक: सभी प्रतीकों और विशेष अक्षरों को हटाता है. *Head&Shoulder* *HeadShoulder* बन जाता है.
     - लोअर केस में टेक्स्ट: सभी अक्षरों को लोअर केस में बदलता है. *सभी कैप्स और टाइटल केस* *सभी कैप्स और टाइटल केस* बन जाता है.
     - प्रकार (फोन, नाम, पता, संगठन): नाम, शीर्षक, फोन नंबर, पते आदि का मानकीकरण करता है। 
     - ASCII से यूनिकोड: यूनिकोड संकेतन को ASCII अक्षरों में बदलता है. */u00B2* *2* बन जाता है.
     - व्हाइटस्पेस: सभी स्पेस को हटाता है. *हैलो   वर्ल्ड* *हैलोवर्ल्ड* बन जाता है.

   - **परिशुद्धता**: इस शर्त को लागू करने के लिए सटीक स्तर निर्धारित करें. 
     - **बुनियादी**: *कम*, *मध्यम*, *उच्च* और *सटीक* से चुनें. चुनना**सटीक** केवल उन रिकॉर्डों से मेल खाने के लिए जो 100 प्रतिशत से मेल खाते हैं। रिकॉर्ड से मेल खाने के लिए अन्य स्तरों में से एक का चयन करें,जो 100 प्रतिशत समान नहीं हैं.
     - **कस्टम**: एक प्रतिशत सेट करें जिसे रिकॉर्ड्स से मेल खाना चाहिए. सिस्टम केवल इस सीमा को पार करने वाले रिकॉर्ड का मिलान करेगा.

1. **नियम** के लिए एक नाम दें.

1. नियम को अंतिम रूप देने के लिए [और शर्तें जोड़ें](#add-conditions-to-a-rule) या **पूर्ण** चुनें.

1. वैकल्पिक रूप से, [और नियम जोड़ें](#add-rules-to-a-match-pair).

1. अपने परिवर्तन लागू करने के लिए **सहेजें** का चयन करें.

### <a name="add-conditions-to-a-rule"></a>किसी नियम में शर्तें जोड़ें

यदि विशेषताएं कई शर्तों को पूरा करती हैं तो ही निकायों से मिलान करने के लिए, मिलान नियम में और शर्तें जोड़ें. शर्तों को तार्किक AND ऑपरेटर से जोड़ा जाता है और इस प्रकार केवल तब निष्पादित किया जाता है जब सभी शर्तें पूरी होती हैं.

1. **डेटा** > **Unify** > **मिलान** में जाएं और जिस नियम को आप शर्तों में जोड़ना चाहते हैं, उस पर **संपादित करें** का चयन करें.

1. **संपादन नियम** फलक में **शर्त जोड़ें** चुनें.

1. नियम सहेजने के लिए **संपन्न** का चयन करें.

### <a name="add-rules-to-a-match-pair"></a>मिलान जोड़ी में नियम जोड़ें

वे मिलान नियम जो शर्तों के सेट को दर्शाते हैं. एक से अधिक विशेषताओं के आधार पर शर्तों के आधार पर निकायों का मिलान करने के लिए, और नियम जोड़ें.

1.  **डेटा** > **Unify** > **मिलान** में जाएं और जिस निकाय में आप नियम जोड़ना चाहते हैं, उस पर **नियम जोड़ें** चुनें.

2. [मिलान जोड़ियों के लिए नियमों को परिभाषित करें](#define-rules-for-match-pairs) में चरणों का पालन करें.

> [!NOTE]
> नियमों का क्रम मायने रखता है. मिलान एल्गोरिदम आपके पहले नियम के आधार पर मिलान करने का प्रयास करता है और दूसरे नियम तक केवल तब जारी रहता है जब पहले नियम से कोई मिलान पहचाना नहीं जाता है.

### <a name="change-the-entity-order-in-match-rules"></a>मिलान नियमों में निकाय क्रम बदलें

आप मिलान नियमों के लिए निकायों को पुन: क्रमित कर सकते हैं ताकि वे संसाधित होने के क्रम को बदल सकें। बदले गए क्रम के कारण परस्पर विरोधी नियम हटा दिए जाएंगे. आपको एक अद्यतन कॉन्फ़िगरेशन के साथ हटाए गए नियमों को फिर से बनाना होगा.

1. **डेटा** > **Unify** > **मिलान** पर जाएं और **संपादित करें** चुनें.

1. क्रम को परिवर्तित करने के लिए **नियम संपादित करें** फलक में, ऑर्डर बदलने के लिए **ऊपर/नीचे जाएं** नियंत्रण चुनें या निकायों को खींचें और छोड़ें.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="वह विकल्प जिस क्रम में निकायों को मिलान चरण में संसाधित किया जाता है.":::

1. नियम सहेजने के लिए **संपन्न** का चयन करें.

## <a name="define-deduplication-on-a-match-entity"></a>मैच निकाय पर डिडुप्लीकेशन को परिभाषित करें

[क्रॉस-निकाय मिलान नियम](#define-rules-for-match-pairs) के अलावा, आप डीडुप्लीकेशन नियम भी निर्दिष्ट कर सकते हैं. *डीडुप्लीकेशन* रिकॉर्ड मिलान करते समय एक और प्रक्रिया है. यह डुप्लिकेट रिकॉर्ड की पहचान करता है और उन्हें एक रिकॉर्ड में मिलाता है. स्रोत रिकॉर्ड वैकल्पिक ID के साथ मिलाए गए रिकॉर्ड से जुड़े होते हैं.

डुप्लिकेट किए गए रिकॉर्ड का उपयोग क्रॉस-एंटिटी मिलान प्रक्रिया में किया जाता है। डीडुप्लिकेशन अलग-अलग निकायों पर होता है और मिलान जोड़े में उपयोग की जाने वाली प्रत्येक इकाई के लिए कॉन्फ़िगर किया जा सकता है।

डिडुप्लीकेशन नियम निर्दिष्ट करना अनिवार्य नहीं है. यदि ऐसे किसी नियम को कॉन्फ़िगर नहीं किया जाता है, तो सिस्टम-परिभाषित नियम लागू किए जाते हैं. वे बेहतर प्रदर्शन के लिए निकाय डेटा को क्रास-निकाय मिलान से पहले सभी रिकॉर्ड को एक ही रिकॉर्ड में जोड़ते हैं.

### <a name="add-deduplication-rules"></a>समर्पण नियम जोड़ें

1. **डेटा** > **Unify** > **मिलान** पर जाएं.

1. में **डुप्लीकेट रिकॉर्ड विवरण** अनुभाग, चुनें **संस्थाएं सेट करें**. यदि डीडुप्लीकेशन नियम पहले से बने हुए हैं, तो **संपादित करें** चुनें.

1. **वरीयताएं विलय करें** फलक में, उन निकायों को चुनें जिन पर आप डीडुप्लीकेशन करना चाहते हैं.

   1. निर्दिष्ट करें कि डुप्लीकेट रिकॉर्ड कैसे जोड़ें और तीन विकल्पों में से एक चुनें:
      - **सबसे अधिक भरा हुआ**: विजेता रिकॉर्ड के रूप में सबसे अधिक आबादी वाले विशेषता फ़ील्ड वाले रिकॉर्ड को पहचानता है. यह डिफ़ॉल्ट मर्ज विकल्प है.
      - **सबसे हाल ही में**: सबसे अधिक रीसेंसी के आधार पर विजेता रिकॉर्ड की पहचान करता है. रीजेंसी को परिभाषित करने के लिए एक तारीख या संख्यात्मक क्षेत्र की आवश्यकता होती है.
      - **कम से कम हाल**: कम से कम रीसेंसी के आधार पर विजेता रिकॉर्ड की पहचान करता है. रीजेंसी को परिभाषित करने के लिए एक तारीख या संख्यात्मक क्षेत्र की आवश्यकता होती है.

   1. वैकल्पिक रूप से, किसी निकाय की अलग-अलग विशेषताओं पर डुप्लीकेशन नियमों को परिभाषित करने के लिए, चुनें **विकसित**. उदाहरण के लिए, आप नवीनतम ईमेल और विभिन्न रिकॉर्ड से सबसे पूर्ण पता रखना चुन सकते हैं। इसकी सभी विशेषताओं को देखने के लिए इकाई का विस्तार करें और परिभाषित करें कि अलग-अलग विशेषताओं के लिए किस विकल्प का उपयोग करना है। यदि आप एक रीसेंसी-आधारित विकल्प चुनते हैं, तो आपको एक तिथि/समय फ़ील्ड भी निर्दिष्ट करना होगा जो रीसेंसी को परिभाषित करता है। 
 
      > [!div class="mx-imgBorder"]
      > ![डेडुप्लीकेशन नियम चरण 1.](media/match-selfconflation.png "डिडुप्लीकेशन नियम चरण 1")

   1. चुनना**पूर्ण** डुप्लीकेशन के लिए अपनी मर्ज प्राथमिकताएं लागू करने के लिए।
 
1. जब निकायों का चयन कर लिया जाता है और उनकी विलय वरीयता निर्धारित कर दी जाती है, तो निकाय स्तर पर डीडुप्लीकेशन नियमों को परिभाषित करने के लिए **नियम जोड़ें** का चयन करें.
   - **फ़ील्ड चुनें** उस निकाय से सभी उपलब्ध फ़ील्ड सूचीबद्ध करता है. वह फ़ील्ड चुनें जिसे आप डुप्लीकेट के लिए जांचना चाहते हैं. उन फ़ील्ड को चुनें, जो हर एक ग्राहक के लिए विशिष्ट हैं. उदाहरण के लिए, एक ईमेल पता, या नाम, शहर और फ़ोन नंबर का संयोजन.
   - सामान्यीकरण और सटीक सेटिंग्स निर्दिष्ट करें.
   - **शर्त जोड़ें** को चुनकर अधिक शर्तों को परिभाषित करें.
 
   > [!div class="mx-imgBorder"]
   > ![डेडुप्लीकेशन नियम चरण 2.](media/match-selfconflation-rules.png "डेडुप्लीकेशन नियम चरण 2")

  आप किसी निकाय के लिए कई डिडुप्लीकेशन नियम बना सकते हैं. 

1. मैच प्रक्रिया चलाना अब डिडुप्लीकेशन नियमों में परिभाषित शर्तों के आधार पर रिकॉर्ड समूहों . रिकॉर्ड को समूहित करने के बाद, विजेता रिकॉर्ड की पहचान करने के लिए मर्ज पॉलिसी लागू की जाती है.

1. इस विजेता रिकॉर्ड को तब क्रॉस-निकाय मिलान के साथ-साथ गैर-विजेता रिकॉर्ड (उदाहरण के लिए, वैकल्पिक ID) के साथ मिलान गुणवत्ता में सुधार करने के लिए पास किया जाता है.

1. परिभाषित किया गया कोई भी कस्टम मिलान नियम डिडुप्लीकेशन नियमों को ओवरराइट करता है. यदि एक डिडुप्लीकेशन नियम मिलान रिकॉर्ड की पहचान करता है, और एक कस्टम मैच नियम उन रिकॉर्ड से मेल नहीं खाते हैं, तो इन दो रिकॉर्ड का मिलान नहीं किया जाएगा .

1. बाद में [मैच प्रक्रिया चल रहा है](#run-the-match-process), आपको मुख्य मीट्रिक टाइलों में डुप्लीकेशन आँकड़े दिखाई देंगे।

### <a name="deduplication-output-as-an-entity"></a>एक निकाय के रूप में डीडुप्लिकेशन आउटपुट

डीडुप्लीकेटेड रिकॉर्ड की पहचान करने के लिए डीडुप्लीकेशन प्रक्रिया मिलान जोड़े से हर निकाय के लिए एक नया निकाय बनाती है. इन निकायों को **निकाय** पेज में **सिस्टम** अनुभाग में **ConflationMatchPairs:CustomerInsights** के साथ **Deduplication_DataSource_Entity** नाम के साथ पाया जा सकता है.

एक डिडुप्लिकेशन आउटपुट निकाय में निम्नलिखित जानकारी होती है:
- ID / कुंजी
  - प्राथमिक कुंजी फ़ील्ड और उसकी वैकल्पिक ID फ़ील्ड. वैकल्पिक ID फ़ील्ड में रिकॉर्ड के लिए पहचानी गई सभी वैकल्पिक ID शामिल हैं.
  - Deduplication_GroupId फ़ील्ड एक समूह के भीतर पहचाने गए समूह या क्लस्टर को दिखाता है जो निर्दिष्ट डुप्लिकेशन फ़ील्ड के आधार पर सभी समान रिकॉर्ड को समूह करता है. इसका उपयोग सिस्टम प्रोसेसिंग उद्देश्यों के लिए किया जाता है. यदि कोई मैनुअल डिडुप्लिकेशन नियम निर्दिष्ट नहीं हैं और सिस्टम डिडुप्लिकेशन नियम लागू होते हैं, तो आपको यह फ़ील्ड डिडुप्लिकेशन आउटपुट निकाय में नहीं मिल सकता है.
  - Deduplication_WinnerId: इस फ़ील्ड में पहचाने गए समूहों या समूहों से विजेता ID होती है. यदि Deduplication_WinnerId रिकॉर्ड के लिए प्राथमिक कुंजी मान के समान है, तो इसका मतलब है कि रिकॉर्ड विजेता रिकॉर्ड है.
- डिडुप्लिकेशन नियमों को परिभाषित करने के लिए फ़ील्ड का उपयोग किया जाता है.
- यह दर्शाने के लिए नियम और स्कोर फ़ील्ड कि कौन से डिडुप्लिकेशन नियम लागू हुए और मिलान एल्गोरिथम द्वारा स्कोर वापस आ गया.
 
## <a name="include-enriched-entities-preview"></a>समृद्ध इकाइयां शामिल करें (पूर्वावलोकन)

यदि आपने डेटा स्रोत स्तर पर संस्थाओं को समृद्ध किया है, तो मिलान प्रक्रिया चलाने से पहले उनका चयन करें। समृद्ध निकाय आपके एकीकरण परिणामों में सुधार कर सकते हैं। अधिक जानकारी के लिए देखें [डेटा स्रोतों के लिए संवर्धन](data-sources-enrichment.md). 

समृद्ध इकाई में मूल डेटा स्रोत फ़ील्ड और समृद्ध फ़ील्ड शामिल हैं। इसलिए यदि आप समृद्ध निकाय के साथ काम करना चुनते हैं, तो मौजूदा कॉन्फ़िगरेशन प्रभावित नहीं होता है। हालांकि, आपको इसके बजाय समृद्ध फ़ील्ड का उपयोग करने के लिए मिलान नियमों को अपडेट करने की आवश्यकता हो सकती है।

1. के लिए जाओ **जानकारी** > **यूनिफाई** > **मिलान** और चुनें **समृद्ध संस्थाओं का उपयोग करें** पन्ने के शीर्ष पर।

1. से **समृद्ध संस्थाओं का उपयोग करें** फलक में, एक या अधिक समृद्ध निकाय चुनें।

1. **पूर्ण** चयन करें. जहां कहीं भी स्रोत निकाय का उपयोग किया जाता है (जैसे मिलान आदेश या नियम), यह स्वतः ही समृद्ध निकाय में बदल जाता है।
  
## <a name="run-the-match-process"></a>मिलान की प्रक्रिया चलाएं

आप क्रॉस-निकाय मिलान और डुप्लीकेशन नियमों सहित कॉन्फ़िगर किए गए मिलान नियमों के साथ, मिलान प्रक्रिया चला सकते हैं. 

प्रक्रिया शुरू करने के लिए **डेटा** > **Unify** > **मिलान** पर जाएं और **रन** चुनें. मिलान एल्गोरिदम को पूरा होने में कुछ समय लगता है और जब तक यह पूरा नहीं हो जाता है आप कॉन्फ़िगरेशन को बदल नहीं सकते. बदलाव करने के लिए, आप रन को रद्द कर सकते हैं. जॉब की स्थिति का चयन करें और **प्रगति विवरण** फलक पर **जॉब रद्द करें** का चयन करें.

आपको **निकाय** पेज पर सफल रन, एकीकृत ग्राहक प्रोफ़ाइल निकाय का परिणाम मिलेगा. आपके एकीकृत ग्राहक निकाय को **प्रोफ़ाइल** अनुभाग में **ग्राहक** कहा जाता है. पहला सफल मिलान रन एकीकृत *ग्राहक* निकाय बनाता है. बाद के सभी मिलान रन उस निकाय का विस्तार करते हैं.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>अपने मिलानों की समीक्षा करें और उन्हें सत्यापित करें

अपने मिलान जोड़े की गुणवत्ता का मूल्यांकन करने और यदि आवश्यक हो तो उन्हें परिष्कृत करने के लिए **डेटा** > **Unify** > **मिलान** पर जाएं.

पेज के सबसे ऊपर स्थित टाइलें मिलान किए गए रिकॉर्ड और डुप्लीकेट की संख्या को संक्षेप में प्रस्तुत करते हुए मुख्य मैट्रिक्स दिखाती हैं.

:::image type="content" source="media/match-KPIs.png" alt-text="संख्या और विवरण के साथ मिलान पृष्ठ पर प्रमुख मेट्रिक्स का क्रॉप्ड स्क्रीनशॉट.":::

- **विशिष्ट स्रोत रिकॉर्ड** उन व्यक्तिगत स्रोत रिकॉर्ड की संख्या को दर्शाता है जिन्हें पिछले मिलान रन में प्रोसेस किया गया था.
- **मिलान हुए और गैर-मिलान हुए रिकॉर्ड** इसे हाइलाइट करता है कि मिलान के नियमों को संसाधित करने के बाद कितने विशिष्ट रिकॉर्ड रहते हैं.
- **केवल मिलान हुए रिकॉर्ड** आपके सभी मिलान जोड़े में मिलानों की संख्या दर्शाता है.

आप **मिलान हुए रिकॉर्ड विवरण** टेबल में प्रत्येक मिलान जोड़ी और उसके नियमों के परिणामों का आकलन कर सकते हैं. सफलतापूर्वक मिलान किए गए रिकॉर्ड के प्रतिशत के मुकाबले मिलान जोड़ी से आए रिकॉर्ड की संख्या की तुलना करें.

नियम स्तर पर सफलतापूर्वक मिलान किए गए रिकॉर्ड का प्रतिशत देखने के लिए मिलान जोड़ी के नियमों की समीक्षा करें. नियम स्तर पर इन सभी रिकॉर्डों को देखने के लिए एलिप्सिस (...) का चयन करें और फिर **मिलान पूर्वावलोकन** का चयन करें. हम यह सत्यापित करने के लिए सिफारिश करते हैं कि आप कुछ रिकॉर्डों पर गौर करें कि वे सही ढंग से मिलान किए गए थे.

सबसे बेहतर मान खोजने की शर्तों पर विभिन्न सटीक सीमाएं आजमाएं.

  1. उस नियम के लिए एलिप्सिस (...) का चयन करें जिसके साथ आप प्रयोग करना चाहते हैं और **संपादित करें** का चयन करें.

  2. जिन शर्तों को आप सुधारना चाहते हैं, उनमें स्टीकता के मानों को बदलें.

  3. **पूर्वावलोकन** चुनें ताकि चयनित शर्त के लिए मिलान और बेमेल रिकॉर्ड की संख्या देख सकें.

## <a name="manage-match-rules"></a>मिलान नियम प्रबंधित करें

आप मिलान के अधिकांश मापदंडों को फिर से कॉन्फ़िगर और सुधार सकते हैं.

:::image type="content" source="media/match-rules-management.png" alt-text="मिलान नियम विकल्पों के साथ ड्रॉपडाउन मेनू का स्क्रीनशॉट।":::

- **अपने नियमों का क्रम बदलें** यदि आपने कई नियमों को निर्दिष्ट किया है. आप **ऊपर जाएं** और **नीचे जाएं** विकल्प चुनकर या खींचकर और छोड़कर मिलान के नियमों को फिर से क्रमबद्ध कर सकते हैं.

- **संपादित करें** का चयन करके और विभिन्न फ़ील्ड का चयन करके **नियम शर्तें बदलें**.

- मिलान प्रक्रिया से बाहर रखते हुए एक मिलान नियम बनाए रखने के लिए **एक नियम को निष्क्रिय करें**.

- **अपने नियमों को डुप्लीकेट करें** यदि आपने मिलान नियम को परिभाषित किया है और संशोधनों के साथ एक जैसा नियम बनाना चाहते हैं, तो **डुप्लीकेट** का चयन करें.

- **हटाएं** प्रतीक का चयन करके **एक नियम हटाएं**.

## <a name="advanced-options"></a>उन्नत विकल्प

### <a name="add-exceptions-to-a-rule"></a>नियम में अपवाद जोड़ें

ज्यादातर मामलों में, इकाई मिलान समेकित डेटा के साथ अद्वितीय उपयोगकर्ता प्रोफ़ाइल की ओर ले जाता है। झूठी सकारात्मक और झूठी नकारात्मक के दुर्लभ मामलों को गतिशील रूप से संबोधित करने के लिए, आप मिलान नियम के अपवादों को परिभाषित कर सकते हैं। अपवाद मिलान नियमों को संसाधित करने के बाद लागू किए जाते हैं और अपवाद मानदंड को पूरा करने वाले सभी रिकॉर्ड के मिलान से बचते हैं।

उदाहरण के लिए, यदि आपका मिलान नियम अंतिम नाम, शहर और जन्म तिथि को जोड़ता है, तो सिस्टम समान अंतिम नाम वाले जुड़वां बच्चों की पहचान करेगा जो एक ही प्रोफ़ाइल वाले शहर में रहते हैं। आप एक अपवाद निर्दिष्ट कर सकते हैं जो प्रोफाइल से मेल नहीं खाता है यदि आपके द्वारा संयोजित इकाइयों में प्रथम नाम समान नहीं हैं।

1. **डेटा** > **Unify** > **मिलान** में जाएं और जिस नियम को आप शर्तों में जोड़ना चाहते हैं, उस पर **संपादित करें** का चयन करें.

1. में **नियम संपादित करें** फलक, चुनें **अपवाद जोड़ना**.

1. अपवाद मानदंड निर्दिष्ट करें। 

1. नियम को सहेजने **संपन्न** का चयन करें.

### <a name="specify-custom-match-conditions"></a>कस्टम मिलान शर्तों को निर्दिष्ट करें

आप ऐसी शर्तें निर्दिष्ट कर सकते हैं जो डिफ़ॉल्ट मिलान तर्क को ओवरराइड करती हैं। चार विकल्प उपलब्ध हैं: 

|विकल्प  |विवरण |उदाहरण  |
|---------|---------|---------|
|हमेशा मिलान करें     | हमेशा मेल खाने वाले मानों को परिभाषित करता है।         |  हमेशा मेल करें *माइक* और *माइकआर*.       |
|कभी मिलान नहीं     | उन मानों को परिभाषित करता है जो कभी मेल नहीं खाते।        | कभी मेल न करें *जॉन* और *जोनाथन*.        |
|कस्टम बाईपास     | उन मानों को परिभाषित करता है जिन्हें सिस्टम को मैच चरण में हमेशा अनदेखा करना चाहिए। |  मूल्यों पर ध्यान न दें *11111* और *अनजान* मैच के दौरान।        |
|उर्फ मैपिंग    | उन मानों को परिभाषित करना जिन पर सिस्टम को समान मान के रूप में विचार करना चाहिए।         | विचार करना*जो* के बराबर होना*यूसुफ*.        |

1. **डेटा** > **Unify** > **मिलान** पर जाएं और **मिलान किए गए रिकॉर्ड विवरण** अनुभाग में **कस्टम मिलान** का चयन करें.

   :::image type="content" source="media/custom-match-create.png" alt-text="कस्टम मिलान नियंत्रण के साथ मैच नियम अनुभाग का स्क्रीनशॉट हाइलाइट किया गया.":::

1. में **रिवाज़** फलक, पर जाएँ **अभिलेख** टैब।

1. से कस्टम मिलान विकल्प चुनें **कस्टम प्रकार** ड्रॉपडाउन और चुनें **टेम्पलेट डाउनलोड करें**. आपको प्रत्येक मिलान विकल्प के लिए एक अलग टेम्पलेट की आवश्यकता है।

1. डाउनलोड की गई टेम्प्लेट फ़ाइल खोलें और विवरण भरें। टेम्पलेट में फ़ील्ड और निकाय प्राथमिक कुंजी मान निर्दिष्ट करने के लिए कस्टम मिलान में उपयोग किए जाने वाले फ़ील्ड होते हैं. उदाहरण के लिए, यदि आप चाहते हैं कि *विक्रय* निकाय से प्राथमिक कुंजी *12345* हमेशा *संपर्क* निकाय से प्राथमिक कुंजी *34567* से मेल खाए, तो टेम्पलेट भरें:
    - निकाय1: विक्रय
    - निकाय1कुंजी: 12345
    - निकाय2: संपर्क
    - निकाय2कुंजी: 34567

   एक ही टेम्प्लेट फ़ाइल कई निकायों से कस्टम मिलान रिकॉर्ड निर्दिष्ट कर सकती है.
   
   यदि आप किसी निकाय पर डिडुप्लिकेशन के लिए कस्टम मिलान निर्दिष्ट करना चाहते हैं, तो Entity1 और Entity2 दोनों के समान निकाय प्रदान करें और विभिन्न प्राथमिक कुंजी मान सेट करें.

1. सभी ओवरराइड जोड़ने के बाद, टेम्प्लेट फ़ाइल को सहेजें।

1. **डेटा** > **डेटा स्रोत** पर जाएं और टेम्पलेट फ़ाइलों को नए निकायों के रूप में अंतर्ग्रहण करें.

1. अपलोड करने के बाद फाइलें और निकाय उपलब्ध हैं, फिर से **कस्टम मिलान** विकल्प चुनें. आप जिन निकायों को शामिल करना चाहते हैं उन्हें निर्दिष्ट करने के लिए विकल्प देखेंगे. ड्रॉपडाउन मेनू से आवश्यक निकाय चुनें और चुनें **पूर्ण**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="कस्टम मिलान परिदृश्य के लिए ओवरराइड चुनने के लिए संवाद का स्क्रीनशॉट.":::

1. कस्टम मिलान लागू करना उस मिलान विकल्प पर निर्भर करता है जिसका आप उपयोग करना चाहते हैं। 

   - के लिए **हमेशा मेल करें** या**कभी मेल न करें**, अगले चरण पर आगे बढ़ें।
   - के लिए **कस्टम बाईपास** या**उपनाम मानचित्रण**, चुनते हैं **संपादन करना** किसी मौजूदा मिलान नियम पर या एक नया नियम बनाएँ। सामान्यीकरण ड्रॉपडाउन में, चुनें **कस्टम बाईपास** या**उपनाम मानचित्रण** विकल्प और चुनें **पूर्ण**.

1. कस्टम मिलान कॉन्फ़िगरेशन को लागू करने के लिए **मिलान** पृष्ठ पर **सहेजें** चुनें.

1. मिलान प्रक्रिया शुरू करने के लिए **मिलान** पेज पर **रन करें** चुनें. अन्य निर्दिष्ट मिलान नियम कस्टम मिलान कॉन्फ़िगरेशन द्वारा ओवरराइड किए जाते हैं.

#### <a name="known-issues"></a>ज्ञात समस्याएँ

- सेल्फ-कंफ्लेशन डिडुप्लीकेशन निकायों में सामान्यीकृत डेटा नहीं दिखाता है। हालांकि, यह डुप्लीकेशन के दौरान आंतरिक रूप से सामान्यीकरण को लागू करता है। यह सभी सामान्यीकरणों के लिए डिज़ाइन द्वारा है। 
- यदि सिमेंटिक प्रकार की सेटिंग को इसमें हटा दिया जाता है **नक्शा** जब कोई मिलान नियम एलियास मैपिंग या कस्टम बायपास का उपयोग करता है, तो सामान्यीकरण लागू नहीं किया जाएगा। यह केवल तभी होता है जब आप मिलान नियम में सामान्यीकरण को कॉन्फ़िगर करने के बाद सिमेंटिक प्रकार को साफ़ करते हैं क्योंकि सिमेंटिक प्रकार अज्ञात होगा।


## <a name="next-step"></a>अगला कदम

कम से कम एक मैच जोड़ी के लिए मैच प्रक्रिया पूरी करने के बाद, जारी रखें [**मर्ज**](merge-entities.md) कदम।


[!INCLUDE [footer-include](includes/footer-banner.md)]