---
title: Customer Insights डेटा को Adobe एक्सपीरियंस प्लेटफ़ॉर्म में निर्यात करें
description: Adobe एक्सपीरियंस प्लेटफ़ॉर्म में ऑडियंस इनसाइट्स सेगमेंट का उपयोग करना सीखें.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596271"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Adobe एक्सपीरियंस प्लेटफ़ॉर्म (पूर्वावलोकन) में Customer Insights सेगमेंट का उपयोग करें

ऑडियंस Insights for Dynamics 365 Customer Insights के यूज़र के रूप में, आपने प्रासंगिक ऑडियंस को लक्षित करके अपने मार्केटिंग अभियानों को अधिक कुशल बनाने के लिए सेगमेंट बनाए होंगे. Adobe एक्सपीरियंस प्लेटफ़ॉर्म में ऑडियंस इनसाइट्स से सेगमेंट उपयोग करने और Adobe Campaign स्टैंडर्ड जैसे अनुप्रयोगों के लिए, आपको इस आलेख में बताए गए कुछ चरणों का पालन करना होगा.

:::image type="content" source="media/AEP-flow.png" alt-text="इस आलेख में उल्लिखित चरणों का प्रक्रिया आरेख.":::

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

-   Dynamics 365 Customer Insights लाइसेंस
-   Adobe एक्सपीरियंस प्लेटफ़ॉर्म लाइसेंस
-   Adobe अभियान स्टैंडर्ड लाइसेंस
-   Azure ब्लॉब स्टोरेज खाता

## <a name="campaign-overview"></a>अभियान ओवरव्यू

यह समझने के लिए कि आप Adobe एक्सपीरियंस प्लेटफ़ॉर्म में ऑडियंस इनसाइट्स के सेगमेंट का उपयोग कैसे कर सकते हैं, चलिए एक काल्पनिक नमूना अभियान पर नज़र डालें.

मान लें कि आपकी कंपनी अमेरिका में आपके ग्राहकों के लिए मासिक, सदस्यता-आधारित सेवा प्रदान करती है. आप उन ग्राहकों की पहचान करना चाहते हैं जिनकी सदस्यता का अगले आठ दिनों में नवीनीकरण किया जाना है, लेकिन अभी तक उनकी सदस्यता का नवीनीकरण नहीं हुआ है. इन ग्राहकों को रखने के लिए, आप उन्हें Adobe एक्सपीरियंस प्लेटफ़ॉर्म का उपयोग करके ईमेल के माध्यम से प्रचार प्रस्ताव भेजना चाहते हैं.

इस उदाहरण में, हम एक बार प्रचार ईमेल अभियान चलाना चाहते हैं. यह आलेख अभियान को एक से अधिक बार चलाने के उपयोग के मामले को कवर नहीं करता है.

## <a name="identify-your-target-audience"></a>अपनी लक्षित ऑडियंस को पहचानें

हमारे परिदृश्य में, हम मानते हैं कि ग्राहकों के ईमेल पते ऑडियंस इनसाइट्स में उपलब्ध हैं और सेगमेंट के सदस्यों की पहचान करने के लिए उनकी प्रचार संबंधी वरीयताओं का विश्लेषण किया गया था.

[आपके द्वारा ऑडियंस इनसाइट्स में परिभाषित किया गया सेगमेंट](segments.md) को **ChurnProneCustomers** कहा जाता है और आप इन ग्राहकों को ईमेल प्रमोशन भेजने की योजना बनाते हैं.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers सेगमेंट वाले सेगमेंट पेज का स्क्रीनशॉट बनाया गया है.":::

आप जो ईमेल भेजना चाहते हैं, उसमें पहला नाम, उपनाम और ग्राहक की सदस्यता समाप्ति तिथि शामिल होगी. यह ग्राहकों को उस छूट के बारे में सूचित करता है जिसे वे अपनी सदस्यता को समाप्त होने से पहले नवीनीकृत करने पर प्राप्त करते हैं.

## <a name="export-your-target-audience"></a>अपनी लक्षित ऑडियंस निर्यात करें

पहचानी गई हमारी लक्षित ऑडियंस के साथ, हम ऑडियंस इनसाइट्स से Azure ब्लॉब स्टोरेज खाते में निर्यात को कॉन्फ़िगर कर सकते हैं.

1. ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.

1. **Azure ब्लॉब स्टोरेज** टाइल में, **सेट अप** चुनें.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure ब्लॉब स्टोरेज के लिए कॉन्फ़िगरेशन टाइल.":::

1. इस नए निर्यात डेस्टिनेशन के लिए एक **प्रदर्शन नाम** प्रदान करें और फिर **खाता नाम**, **खाता कुंजी**, और Azure ब्लॉब स्टोरेज खाते का **कंटेनर** दर्ज करें जहां आप सेगमेंट को निर्यात करना चाहते हैं.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="स्टोरेज खाता कॉन्फ़िगरेशन का स्क्रीनशॉट."::: 

   - Azure Blob संग्रहण खाते का नाम और खाता कुंजी का पता लगाने के बारे में अधिक जानने के लिए, [Azure पोर्टल में संग्रहण खाता सेटिंग व्यवस्थित करें](/azure/storage/common/storage-account-manage) देखें.

   - कंटेनर बनाने के बारे में जानने के लिए, [कंटेनर बनाएँ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) देखें.

1. **अगला** चुनें.

1. वह सेगमेंट चुनें, जिसे आप निर्यात करना चाहते हैं. इस उदाहरण में, यह **ChurnProneCustomers** है.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers अनुभाग चयनित के साथ अनुभाग चयन उपयोगकर्ता इंटरफ़ेस का स्क्रीनशॉट.":::

1. **सहेजें** चुनें.

निर्यात डेस्टिनेशन को सेव करने के बाद, आप इसे **व्यवस्थापक** > **निर्यात** > **मेरे निर्यात डेस्टिनेशन** पर पाते हैं.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="निर्यात और नमूना अनुभाग की सूची के साथ स्क्रीनशॉट पर प्रकाश डाला गया.":::

अब आप [मांग पर सेगमेंट निर्यात कर सकते हैं](export-destinations.md#export-data-on-demand). निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md).

> [!NOTE]
> सुनिश्चित करें कि निर्यात किए गए सेगमेंट में रिकॉर्ड की संख्या आपके Adobe कैंपेन स्टैंडर्ड लाइसेंस की अनुमत सीमा के अंदर है.

निर्यात किए गए डेटा को ऊपर कॉन्फ़िगर किए गए Azure ब्लॉब स्टोरेज कंटेनर में स्टोर किया जाता है. निम्न फ़ोल्डर पाथ स्वचालित रूप से आपके कंटेनर में बनाया गया है:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

उदाहरण: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* निर्यात किए गए निकायों के लिए *%ExportDestinationName%* स्तर पर रहता है.

उदाहरण: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Adobe एक्सपीरियंस प्लेटफ़ॉर्म में एक्सपीरियंस डेटा मॉडल (XDM) को परिभाषित करें

Adobe एक्सपीरियंस प्लेटफ़ॉर्म में ऑडियंस इनसाइट्स से निर्यात किए गए डेटा का उपयोग करने से पहले हमें एक्सपीरियंस डेटा मॉडल स्कीमा को परिभाषित करने और [रियल टाइम ग्राहक प्रोफ़ाइल के लिए डेटा कॉन्फ़िगर करें](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) की आवश्यकता है.

[XDM क्या है](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) जानें और [स्कीमा संरचना की मूल बातें](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) को समझें.

## <a name="import-data-into-adobe-experience-platform"></a>Adobe एक्सपीरियंस प्लेटफ़ॉर्म में डेटा आयात करें

अब जब सब कुछ अपनी जगह पर है, हमें ऑडियंस इनसाइट्स से तैयार ऑडियंस डेटा को Adobe एक्सपीरियंस प्लेटफ़ॉर्म में इंपोर्ट करने की जरूरत है.

सबसे पहले, [एक Azure ब्लॉब स्टोरेज स्रोत कनेक्शन बनाएं](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

स्रोत कनेक्शन को परिभाषित करने के बाद, क्लाउड स्टोरेज बैच कनेक्शन के लिए [डेटा प्रवाह कॉन्फ़िगर करें](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials), ताकि ऑडियंस से सेगमेंट आउटपुट को Adobe एक्सपीरियंस प्लेटफ़ॉर्म में आयात किया जा सके.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe कैंपेन स्टैंडर्ड में एक ऑडियंस बनाएं

इस अभियान के लिए ईमेल भेजने के लिए, हम Adobe कैंपेन स्टैंडर्ड का उपयोग करेंगे. Adobe एक्सपीरियंस प्लेटफ़ॉर्म में डेटा आयात करने के बाद, हमें Adobe कैंपेन स्टैंडर्ड में Adobe एक्सपीरियंस प्लेटफ़ॉर्म में डेटा का उपयोग करते हुए [एक ऑडियंस बनाने](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) की आवश्यकता है.

Adobe एक्सपीरियंस प्लेटफ़ॉर्म में डेटा पर आधारित ऑडियंस को परिभाषित करने के लिए Adobe कैंपेन स्टैंडर्ड में [सेगमेंट बिल्डर इस्तेमाल](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) करने के बारे में जानें.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe कैंपेन स्टैंडर्ड का उपयोग करके ईमेल बनाएं और भेजें

ईमेल सामग्री बनाएं और फिर अपना ईमेल [परीक्षण करें और भेजें](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe कैंपेन स्टैंडर्ड से नवीकरण प्रस्ताव के साथ नमूना ईमेल.":::