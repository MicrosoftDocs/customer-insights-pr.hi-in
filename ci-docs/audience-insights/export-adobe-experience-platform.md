---
title: Customer Insights डेटा निर्यात करें Adobe Experience Platform
description: Adobe Experience Platform में ऑडिएंस इनसाइट सेगमेंट का उपयोग करने का तरीका जानें.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9010af3c42823ce0dd8685bf71c109aef8d3f635
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227714"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Adobe Experience Platform (पूर्वावलोकन) में Customer Insights सेगमेंट का उपयोग करें

Dynamics 365 Customer Insights में ऑडिएंस इनसाइट्स के उपयोगकर्ता के रूप में, आपने प्रासंगिक ऑडियंस को लक्षित करके अपने मार्केटिंग अभियानों को अधिक कुशल बनाने के लिए अनुभाग बनाए होंगे। Adobe Experience Platform और Adobe Campaign Standard जैसे एप्लिकेशन में ऑडियंस इनसाइट्स से सेगमेंट का उपयोग करने के लिए, आपको इस आलेख में उल्लिखित कुछ चरणों का पालन करने की आवश्यकता है.

:::image type="content" source="media/AEP-flow.png" alt-text="इस आलेख में उल्लिखित चरणों का प्रक्रिया आरेख.":::

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

-   Dynamics 365 Customer Insights लाइसेंस
-   Adobe Experience Platform लाइसेंस
-   Adobe Campaign Standard लाइसेंस
-   Azure ब्लॉब स्टोरेज खाता

## <a name="campaign-overview"></a>अभियान पूर्वावलोकन

यह समझने के लिए कि आप Adobe Experience Platform में ऑडियंस इनसाइट्स के सेगमेंट का उपयोग कैसे कर सकते हैं, चलिए एक काल्पनिक नमूना अभियान पर नज़र डालें.

मान लें कि आपकी कंपनी अमेरिका में आपके ग्राहकों के लिए मासिक, सदस्यता-आधारित सेवा प्रदान करती है. आप उन ग्राहकों की पहचान करना चाहते हैं जिनकी सदस्यता का अगले आठ दिनों में नवीनीकरण किया जाना है, लेकिन अभी तक उनकी सदस्यता का नवीनीकरण नहीं हुआ है. इन ग्राहकों को बनाए रखने के लिए, आप उन्हें Adobe Experience Platform का उपयोग करके ईमेल के माध्यम से प्रचार प्रस्ताव भेजना चाहते हैं.

इस उदाहरण में, हम एक बार प्रचार ईमेल अभियान चलाना चाहते हैं. यह आलेख अभियान को एक से अधिक बार चलाने के उपयोग के मामले को कवर नहीं करता है.

## <a name="identify-your-target-audience"></a>अपनी लक्षित ऑडियंस को पहचानें

हमारे परिदृश्य में, हम मानते हैं कि ग्राहकों के ईमेल पते ऑडियंस इनसाइट्स में उपलब्ध हैं और सेगमेंट के सदस्यों की पहचान करने के लिए उनकी प्रचार संबंधी वरीयताओं का विश्लेषण किया गया था.

[आपके द्वारा ऑडियंस इनसाइट्स में परिभाषित किया गया सेगमेंट](segments.md) को **ChurnProneCustomers** कहा जाता है और आप इन ग्राहकों को ईमेल प्रमोशन भेजने की योजना बनाते हैं.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers सेगमेंट वाले सेगमेंट पेज का स्क्रीनशॉट बनाया गया है.":::

आप जो ईमेल भेजना चाहते हैं, उसमें पहला नाम, उपनाम और ग्राहक की सदस्यता समाप्ति तिथि शामिल होगी. यह ग्राहकों को उस छूट के बारे में सूचित करता है जिसे वे अपनी सदस्यता को समाप्त होने से पहले नवीनीकृत करने पर प्राप्त करते हैं.

## <a name="export-your-target-audience"></a>अपनी लक्षित ऑडियंस निर्यात करें

पहचानी गई हमारी लक्षित ऑडियंस के साथ, हम ऑडियंस इनसाइट्स से Azure ब्लॉब स्टोरेज खाते में निर्यात को कॉन्फ़िगर कर सकते हैं.

### <a name="configure-a-connection"></a>एक कनेक्शन कॉन्फ़िगर करें

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. कनेक्शन को कॉन्फ़िगर करने के लिए **कनेक्शन जोड़ें** का चयन करें और **Azure Blob संग्रहण** चुनें या **Azure Blob संग्रहण** टाइल में **सेट अप करें** का चयन करें।

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure ब्लॉब स्टोरेज के लिए कॉन्फ़िगरेशन टाइल."::: 

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. जहां आप अनुभाग को निर्यात करना चाहते हैं वहां अपने Blob संग्रहण खाते के लिए **अकाउंट का नाम**, **अकाउंट कुंजी** और **कंटेनर** दर्ज करें।  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="स्टोरेज खाता कॉन्फ़िगरेशन का स्क्रीनशॉट."::: 
   
    - Blob संग्रहण खाते का नाम और खाता कुंजी खोजने के तरीके के बारे में अधिक जानने के लिए, [Azure पोर्टल में संग्रहण खाता सेटिंग्स का प्रबंधन करें](/azure/storage/common/storage-account-manage) देखें।
    - कंटेनर बनाने के बारे में जानने के लिए, [कंटेनर बनाएँ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) देखें.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें. 

### <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **निर्यात जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** में, Azure Blob Storage अनुभाग से एक कनेक्शन का चयन करें. यदि आपको यह अनुभाग नाम नहीं दिखता है, तो इस प्रकार का कोई भी कनेक्शन आपके लिए उपलब्ध नहीं है।

1. वह सेगमेंट चुनें, जिसे आप निर्यात करना चाहते हैं. इस उदाहरण में, यह **ChurnProneCustomers** है.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers अनुभाग चयनित के साथ अनुभाग चयन उपयोगकर्ता इंटरफ़ेस का स्क्रीनशॉट.":::

1. **सहेजें** चुनें.

निर्यात डेस्टिनेशन को सहेजने के बाद, आप इसे **डेटा** > **निर्यात** पर पाते हैं.

अब आप [मांग पर सेगमेंट निर्यात कर सकते हैं](export-destinations.md#run-exports-on-demand). निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md).

> [!NOTE]
> सुनिश्चित करें कि निर्यात किए गए अनुभाग में रिकॉर्ड की संख्या आपके Adobe Campaign Standard लाइसेंस की अनुमति प्राप्त सीमा के भीतर है.

निर्यात किए गए डेटा को ऊपर कॉन्फ़िगर किए गए Azure ब्लॉब स्टोरेज कंटेनर में स्टोर किया जाता है। निम्न फ़ोल्डर पाथ स्वचालित रूप से आपके कंटेनर में बनाया गया है:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

उदाहरण: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* निर्यात किए गए निकायों के लिए *%ExportDestinationName%* स्तर पर रहता है.

उदाहरण: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Adobe Experience Platform में अनुभव डेटा मॉडल (XDM) को परिभाषित करें

इससे पहले कि ऑडियंस इनसाइट्स से निर्यात किए गए डेटा को Adobe Experience Platform में उपयोग किया जा सके, हमें अनुभव डेटा मॉडल स्कीमा को परिभाषित करना होगा और [रीयल-टाइम ग्राहक प्रोफ़ाइल के लिए डेटा कॉन्फ़िगर करना होगा](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

[XDM क्या है](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) जानें और [स्कीमा संरचना की मूल बातें](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) को समझें.

## <a name="import-data-into-adobe-experience-platform"></a>Adobe Experience Platform में डेटा आयात करें

अब जब सब कुछ ठीक हो गया है, हमें ऑडिएंस इनसाइट्स से तैयार ऑडिएंस डेटा को Adobe Experience Platform में आयात करने की आवश्यकता है.

सबसे पहले, [एक Azure ब्लॉब स्टोरेज स्रोत कनेक्शन बनाएं](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

स्रोत कनेक्शन को परिभाषित करने के बाद, क्लाउड संग्रहण बैच कनेक्शन के लिए [डेटा प्रवाह कॉन्फ़िगर करें](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) जिससे ऑडियंस इनसाइट्स से सेगमेंट आउटपुट को Adobe Experience Platform में आयात किया जा सके.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard में ऑडियंस बनाएँ

इस अभियान के लिए ईमेल भेजने हेतु, हम Adobe Campaign Standard का उपयोग करेंगे. Adobe Experience Platform में डेटा आयात करने के बाद, हमें Adobe Experience Platform में डेटा का उपयोग करते हुए Adobe Campaign Standard में [ऑडिएंस बनाना](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) होगा.


Adobe Experience Platform में डेटा के आधार पर दर्शकों को परिभाषित करने के लिए Adobe Campaign Standard में [अनुभाग बिल्डर का उपयोग](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) करना सीखें.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard का उपयोग करके ईमेल बनाएँ और भेजें

ईमेल सामग्री बनाएं और फिर अपना ईमेल [परीक्षण करें और भेजें](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard से नवीनीकरण प्रस्ताव के साथ नमूना ईमेल.":::
