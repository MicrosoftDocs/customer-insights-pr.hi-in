---
title: Adobe Campaign Standard में Customer Insights डेटा निर्यात करें
description: जानें कि Customer Insights सेगमेंट का उपयोग कैसे करें Adobe अभियान मानक।
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642712"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Adobe Campaign Standard (पूर्वावलोकन) में Customer Insights सेगमेंट का उपयोग करें

एक उपयोगकर्ता के रूप में Dynamics 365 Customer Insights, हो सकता है कि आपने प्रासंगिक ऑडियंस को लक्षित करके अपने मार्केटिंग अभियानों को अधिक कुशल बनाने के लिए सेगमेंट बनाए हों। Customer Insights से एक सेगमेंट का उपयोग करने के लिए Adobe Experience Platform और अनुप्रयोगों जैसे Adobe अभियान मानक, आपको इस लेख में उल्लिखित कुछ चरणों का पालन करना होगा।

:::image type="content" source="media/ACS-flow.png" alt-text="इस आलेख में उल्लिखित चरणों का प्रक्रिया आरेख":::

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

-   Dynamics 365 Customer Insights लाइसेंस
-   Adobe Campaign Standard लाइसेंस
-   Azure ब्लॉब स्टोरेज खाता

## <a name="campaign-overview"></a>अभियान पूर्वावलोकन

यह बेहतर ढंग से समझने के लिए कि आप इसमें Customer Insights से सेगमेंट का उपयोग कैसे कर सकते हैं Adobe Experience Platform, आइए एक काल्पनिक नमूना अभियान को देखें।

मान लें कि आपकी कंपनी अमेरिका में आपके ग्राहकों के लिए मासिक, सदस्यता-आधारित सेवा प्रदान करती है. आप उन ग्राहकों की पहचान करना चाहते हैं जिनकी सदस्यता का अगले आठ दिनों में नवीनीकरण किया जाना है, लेकिन अभी तक उनकी सदस्यता का नवीनीकरण नहीं हुआ है. इन ग्राहकों को बनाए रखने के लिए, आप उन्हें Adobe Campaign Standard का उपयोग करके ईमेल के माध्यम से प्रचार प्रस्ताव भेजना चाहते हैं.

इस उदाहरण में, हम एक बार प्रचार ईमेल अभियान चलाना चाहते हैं. यह आलेख अभियान को एक से अधिक बार चलाने के उपयोग के मामले को कवर नहीं करता है. हालांकि, ग्राहक अंतर्दृष्टि और Adobe अभियान मानक को पुनरावर्ती अभियान परिदृश्य के लिए भी काम करने के लिए कॉन्फ़िगर किया जा सकता है।

## <a name="identify-your-target-audience"></a>अपनी लक्षित ऑडियंस को पहचानें

हमारे परिदृश्य में, हम मानते हैं कि ग्राहकों के ईमेल पते उपलब्ध हैं और सेगमेंट के सदस्यों की पहचान करने के लिए उनकी प्रचार प्राथमिकताओं का विश्लेषण किया गया था।

[Customer Insights में आपके द्वारा परिभाषित खंड](segments.md) कहा जाता है **चर्नप्रोन ग्राहक** और आप इन ग्राहकों को ईमेल प्रचार भेजने की योजना बना रहे हैं।

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers सेगमेंट वाले सेगमेंट पेज का स्क्रीनशॉट बनाया गया है.":::

आप जो ईमेल भेजना चाहते हैं, उसमें पहला नाम, उपनाम और ग्राहक की सदस्यता समाप्ति तिथि शामिल होगी. यह ग्राहकों को उस छूट के बारे में सूचित करता है जिसे वे अपनी सदस्यता को समाप्त होने से पहले नवीनीकृत करने पर प्राप्त करते हैं.

## <a name="export-your-target-audience"></a>अपनी लक्षित ऑडियंस निर्यात करें

### <a name="configure-a-connection"></a>एक कनेक्शन कॉन्फ़िगर करें

हमारे लक्ष्य ऑडिएंस की पहचान के साथ, हम निर्यात को Azure Blob Storage खाते में कॉन्फ़िगर कर सकते हैं।

1. Customer Insights में, यहाँ जाएँ **व्यवस्थापक** > **सम्बन्ध।**

1. **कनेक्शन जोड़ें** चुनें और कनेक्शन कॉन्फ़िगर करने के लिए **Adobe Campaign** चुनें या **Adobe Campaign** टाइल में **सेट अप** चुनें.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard के लिए कॉन्फ़िगरेशन टाइल.":::

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. जहां आप सेगमेंट को निर्यात करना चाहते हैं वहां Azure ब्लॉब स्टोरेज के अकाउंट का **अकाउंट का नाम**, **अकाउंट कुंजी** और **कंटेनर** दर्ज करें.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="स्टोरेज खाता कॉन्फ़िगरेशन का स्क्रीनशॉट."::: 

   - Azure Blob संग्रहण खाते का नाम और खाता कुंजी का पता लगाने के बारे में अधिक जानने के लिए, [Azure पोर्टल में संग्रहण खाता सेटिंग व्यवस्थित करें](/azure/storage/common/storage-account-manage) देखें।

   - कंटेनर बनाने के बारे में जानने के लिए, [कंटेनर बनाएँ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) देखें.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

### <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **निर्यात जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** फ़ील्ड में, Adobe Campaign सेक्शन से एक कनेक्शन चुनें. यदि आपको यह अनुभाग नाम नहीं दिखता है, तो इस प्रकार का कोई भी कनेक्शन आपके लिए उपलब्ध नहीं है।

1. वह सेगमेंट चुनें, जिसे आप निर्यात करना चाहते हैं. इस उदाहरण में, यह **ChurnProneCustomers** है.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers अनुभाग चयनित के साथ अनुभाग चयन उपयोगकर्ता इंटरफ़ेस का स्क्रीनशॉट.":::

1. **अगला** चुनें.

1. अब हम नक्शा**स्रोत** Customer Insights सेगमेंट से फ़ील्ड तक **लक्ष्य** में फ़ील्ड नाम Adobe अभियान मानक प्रोफ़ाइल स्कीमा।

   :::image type="content" source="media/ACS-field-mapping.png" alt-text=" Adobe Campaign Standard कनेक्टर के लिए फ़ील्ड मैपिंग.":::

   यदि आप अधिक विशेषताएं जोड़ना चाहते हैं, तो **विशेषता जोड़ें** चुनें. लक्ष्य नाम स्रोत फ़ील्ड नाम से भिन्न हो सकता है ताकि आप अभी भी Customer Insights से सेगमेंट आउटपुट को मैप कर सकें Adobe अभियान मानक यदि दोनों प्रणालियों में फ़ील्ड का नाम समान नहीं है।

   > [!NOTE]
   > ईमेल पते का उपयोग पहचान फ़ील्ड के रूप में किया जाता है, लेकिन आप डेटा को मैप करने के लिए ग्राहक प्रोफ़ाइल से किसी अन्य पहचानकर्ता का उपयोग कर सकते हैं Adobe अभियान मानक।

1. **सहेजें** चुनें.

निर्यात डेस्टिनेशन को सहेजने के बाद, आप इसे **डेटा** > **निर्यात** पर पाते हैं.

अब आप [मांग पर सेगमेंट निर्यात कर सकते हैं](export-destinations.md#run-exports-on-demand). निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md).

> [!NOTE]
> सुनिश्चित करें कि निर्यात किए गए अनुभाग में रिकॉर्ड की संख्या आपके Adobe Campaign Standard लाइसेंस की अनुमति प्राप्त सीमा के भीतर है.

निर्यात किए गए डेटा को ऊपर कॉन्फ़िगर किए गए Azure ब्लॉब स्टोरेज कंटेनर में स्टोर किया जाता है। निम्न फ़ोल्डर पाथ स्वचालित रूप से आपके कंटेनर में बनाया गया है:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

उदाहरण: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>कॉन्फ़िगर Adobe Campaign Standard करें

निर्यात किए गए सेगमेंट में वे कॉलम होते हैं जिन्हें आपने पिछले चरण में निर्यात गंतव्य निर्धारित करते समय चुना था। इस डेटा का इस्तेमाल [Adobe Campaign Standard में प्रोफाइल बनाने](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) के लिए किया जा सकता है.

Adobe Campaign Standard में सेगमेंट का उपयोग करने के लिए, हमें दो अतिरिक्त फ़ील्ड्स को शामिल करने के लिए Adobe Campaign Standard में प्रोफ़ाइल स्कीमा का विस्तार करने की आवश्यकता है. जानें कि Adobe Campaign Standard में नए फ़ील्ड के साथ [प्रोफ़ाइल संसाधन का विस्तार](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) कैसे करें.

हमारे उदाहरण में, ये फ़ील्ड *सेगमेंट नाम और सेगमेंट दिनांक (वैकल्पिक)* हैं।

हम इन फ़ील्ड का उपयोग Adobe Campaign Standard में उन प्रोफ़ाइलों की पहचान करने के लिए करेंगे जिन्हें हम इस अभियान के लिए लक्षित करना चाहते हैं.

यदि आप जो आयात करने जा रहे हैं, उसके अलावा Adobe Campaign Standard में कोई अन्य रिकॉर्ड नहीं हैं, तो आप इस चरण को छोड़ सकते हैं.

## <a name="import-data-into-adobe-campaign-standard"></a>Adobe Campaign Standard में डेटा आयात करें

अब जबकि सब कुछ ठीक हो गया है, हमें Customer Insights से तैयार ऑडिएंस डेटा आयात करने की आवश्यकता है Adobe प्रोफाइल बनाने के लिए अभियान मानक। जानें कि कार्यप्रवाह का उपयोग करके [Adobe Campaign Standard में प्रोफ़ाइल कैसे आयात करें](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

नीचे दी गई छवि में आयात कार्यप्रवाह को हर आठ घंटे में चलाने और निर्यात किए गए Customer Insights सेगमेंट (Azure Blob Storage में.csv फ़ाइल) देखने के लिए कॉन्फ़िगर किया गया है। कार्यप्रवाह एक निर्दिष्ट कॉलम क्रम में .csv फ़ाइल की सामग्री निकालता है. यह कार्यप्रवाह बुनियादी त्रुटि प्रबंधन करने के लिए बनाया गया है और यह सुनिश्चित करता है कि Adobe Campaign Standard में डेटा को हाइड्रेट करने से पहले प्रत्येक रिकॉर्ड में एक ईमेल पता हो. Adobe Campaign Standard प्रोफ़ाइल डेटा में डालने से पहले कार्यप्रवाह फ़ाइल नाम से खंड का नाम भी निकालता है.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard उपयोगकर्ता इंटरफ़ेस में आयात कार्यप्रवाह का स्क्रीनशॉट.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard में दर्शकों को पुनः प्राप्त करें

Adobe Campaign Standard में डेटा आयात होने के बाद, आप हमारे नमूना कैंपेन के लिए पहचाने गए प्रोफ़ाइल का चयन करने के लिए ग्राहकों को *अनुभाग नाम* और *अनुभाग दिनांक* के आधार पर [कार्यप्रवाह बना सकते हैं](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) और [क्वेरी](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data).

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard का उपयोग करके ईमेल बनाएँ और भेजें

ईमेल सामग्री बनाएं और फिर अपना ईमेल [परीक्षण करें और भेजें](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard से नवीनीकरण प्रस्ताव के साथ नमूना ईमेल.":::