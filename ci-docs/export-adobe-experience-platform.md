---
title: निर्यात खंड Adobe Experience Platform (पूर्व दर्शन)
description: में Customer Insights सेगमेंट का उपयोग करना सीखें।Adobe Experience Platform
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195292"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>निर्यात खंड Adobe Experience Platform (पूर्व दर्शन)

उन सेगमेंट को निर्यात करें जो प्रासंगिक ऑडियंस को पर लक्षित करते हैं Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="इस आलेख में उल्लिखित चरणों का प्रक्रिया आरेख.":::

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- एक Adobe Experience Platform लाइसेंस।
- एक Adobe अभियान मानक लाइसेंस।
- एक [Azure ब्लॉब संग्रहण खाता](/azure/storage/blobs/create-data-lake-storage-account) नाम और खाता कुंजी। नाम और कुंजी खोजने के लिए, देखें [Azure पोर्टल में संग्रहण खाता सेटिंग प्रबंधित करें।](/azure/storage/common/storage-account-manage)
- एक [Azure ब्लॉब संग्रहण कंटेनर](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>अभियान पूर्वावलोकन

यह बेहतर ढंग से समझने के लिए कि आप इसमें Customer Insights से सेगमेंट का उपयोग कैसे कर सकते हैं Adobe Experience Platform, आइए एक काल्पनिक नमूना अभियान को देखें।

मान लें कि आपकी कंपनी अमेरिका में आपके ग्राहकों के लिए मासिक, सदस्यता-आधारित सेवा प्रदान करती है. आप उन ग्राहकों की पहचान करना चाहते हैं जिनकी सदस्यता का अगले आठ दिनों में नवीनीकरण किया जाना है, लेकिन अभी तक उनकी सदस्यता का नवीनीकरण नहीं हुआ है. इन ग्राहकों को बनाए रखने के लिए, आप उन्हें Adobe Experience Platform का उपयोग करके ईमेल के माध्यम से प्रचार प्रस्ताव भेजना चाहते हैं.

इस उदाहरण में, हम एक बार प्रचार ईमेल अभियान चलाना चाहते हैं. यह आलेख अभियान को एक से अधिक बार चलाने के उपयोग के मामले को कवर नहीं करता है.

## <a name="identify-your-target-audience"></a>अपनी लक्षित ऑडियंस को पहचानें

हमारे परिदृश्य में, हम मानते हैं कि ग्राहकों के ईमेल पते Customer Insights में उपलब्ध हैं और खंड के सदस्यों की पहचान करने के लिए उनकी प्रचार प्राथमिकताओं का विश्लेषण किया गया था।

[Customer Insights में आपके द्वारा परिभाषित खंड](segments.md) कहा जाता है **चर्नप्रोन ग्राहक** और आप इन ग्राहकों को ईमेल प्रचार भेजने की योजना बना रहे हैं।

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers सेगमेंट वाले सेगमेंट पेज का स्क्रीनशॉट बनाया गया है.":::

आप जो ईमेल भेजना चाहते हैं, उसमें पहला नाम, उपनाम और ग्राहक की सदस्यता समाप्ति तिथि शामिल होगी. यह ग्राहकों को उस छूट के बारे में सूचित करता है जिसे वे अपनी सदस्यता को समाप्त होने से पहले नवीनीकृत करने पर प्राप्त करते हैं.

## <a name="export-your-target-audience"></a>अपनी लक्षित ऑडियंस निर्यात करें

हम Customer Insights से Azure Blob Storage खाते में निर्यात को कॉन्फ़िगर करेंगे।

### <a name="set-up-connection-to-azure-blob-storage"></a>Azure ब्लॉब संग्रहण से कनेक्शन सेट करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **Azure ब्लॉब संग्रहण**.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. जहां आप अनुभाग को निर्यात करना चाहते हैं वहां अपने Blob संग्रहण खाते के लिए **अकाउंट का नाम**, **अकाउंट कुंजी** और **कंटेनर** दर्ज करें।  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="स्टोरेज खाता कॉन्फ़िगरेशन का स्क्रीनशॉट.":::

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

### <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** में, Azure Blob Storage अनुभाग से एक कनेक्शन का चयन करें. यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. वह सेगमेंट चुनें, जिसे आप निर्यात करना चाहते हैं. इस उदाहरण में, यह **ChurnProneCustomers** है.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers अनुभाग चयनित के साथ अनुभाग चयन उपयोगकर्ता इंटरफ़ेस का स्क्रीनशॉट.":::

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> सुनिश्चित करें कि निर्यात किए गए अनुभाग में रिकॉर्ड की संख्या आपके Adobe Campaign Standard लाइसेंस की अनुमति प्राप्त सीमा के भीतर है.

निर्यात किया गया डेटा आपके द्वारा कॉन्फ़िगर किए गए Azure ब्लॉब संग्रहण कंटेनर में संग्रहीत किया जाता है। आपके कंटेनर में निम्नलिखित फोल्डर पथ अपने आप बनेंगे:

- स्रोत निकायों और सिस्टम द्वारा उत्पन्न स्रोत निकायों के लिए:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  उदाहरण: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- *model.json* निर्यात किए गए निकायों के लिए *%ExportDestinationName%* स्तर पर रहता है.

  उदाहरण: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Adobe Experience Platform में अनुभव डेटा मॉडल (XDM) को परिभाषित करें

Customer Insights से निर्यात किए गए डेटा का उपयोग करने से पहले Adobe Experience Platform, अनुभव डेटा मॉडल स्कीमा को परिभाषित करें और [रीयल-टाइम ग्राहक प्रोफ़ाइल के लिए डेटा कॉन्फ़िगर करें](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

[XDM क्या है](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) जानें और [स्कीमा संरचना की मूल बातें](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) को समझें.

## <a name="import-data-into-adobe-experience-platform"></a>Adobe Experience Platform में डेटा आयात करें

Customer Insights से तैयार ऑडिएंस डेटा आयात करें Adobe Experience Platform.

1. [एक Azure ब्लॉब संग्रहण स्रोत कनेक्शन बनाएं](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [डेटा प्रवाह कॉन्फ़िगर करें](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) Customer Insights से सेगमेंट आउटपुट आयात करने के लिए क्लाउड स्टोरेज बैच कनेक्शन के लिए Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard में ऑडियंस बनाएँ

इस अभियान के लिए ईमेल भेजने हेतु, हम Adobe Campaign Standard का उपयोग करेंगे.

1. [एक ऑडिएंस . बनाएं](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) में Adobe में डेटा का उपयोग कर अभियान मानक Adobe Experience Platform.

1. [खंड निर्माता का प्रयोग करें](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) में Adobe डेटा के आधार पर ऑडिएंस परिभाषित करने के लिए अभियान मानक Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard का उपयोग करके ईमेल बनाएँ और भेजें

ईमेल सामग्री बनाएं और फिर अपना ईमेल [परीक्षण करें और भेजें](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard से नवीनीकरण प्रस्ताव के साथ नमूना ईमेल.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
