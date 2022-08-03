---
title: Customer Insights सेगमेंट को यहां निर्यात करें Adobe अभियान मानक (पूर्वावलोकन)
description: जानें कि Customer Insights सेगमेंट का उपयोग कैसे करें Adobe अभियान मानक।
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195522"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Customer Insights सेगमेंट को यहां निर्यात करें Adobe अभियान मानक (पूर्वावलोकन)

प्रासंगिक ऑडियंस को लक्षित करने वाले सेगमेंट निर्यात करें Adobe अभियान मानक।

:::image type="content" source="media/ACS-flow.png" alt-text="इस आलेख में उल्लिखित चरणों का प्रक्रिया आरेख":::

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- एक Adobe अभियान मानक लाइसेंस।
- एक [Azure ब्लॉब संग्रहण खाता](/azure/storage/blobs/create-data-lake-storage-account) नाम और खाता कुंजी। नाम और कुंजी खोजने के लिए, देखें [Azure पोर्टल में संग्रहण खाता सेटिंग प्रबंधित करें।](/azure/storage/common/storage-account-manage)
- एक [Azure ब्लॉब संग्रहण कंटेनर](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>अभियान पूर्वावलोकन

यह बेहतर ढंग से समझने के लिए कि आप इसमें Customer Insights से सेगमेंट का उपयोग कैसे कर सकते हैं Adobe Experience Platform, आइए एक काल्पनिक नमूना अभियान को देखें।

मान लें कि आपकी कंपनी अमेरिका में आपके ग्राहकों के लिए मासिक, सदस्यता-आधारित सेवा प्रदान करती है. आप उन ग्राहकों की पहचान करना चाहते हैं जिनकी सदस्यता का अगले आठ दिनों में नवीनीकरण किया जाना है, लेकिन अभी तक उनकी सदस्यता का नवीनीकरण नहीं हुआ है. इन ग्राहकों को बनाए रखने के लिए, आप उन्हें Adobe Campaign Standard का उपयोग करके ईमेल के माध्यम से प्रचार प्रस्ताव भेजना चाहते हैं.

इस उदाहरण में, हम एक बार प्रचार ईमेल अभियान चलाना चाहते हैं. यह आलेख अभियान को एक से अधिक बार चलाने के उपयोग के मामले को कवर नहीं करता है. हालांकि, ग्राहक अंतर्दृष्टि और Adobe अभियान मानक को पुनरावर्ती अभियान परिदृश्य के लिए भी काम करने के लिए कॉन्फ़िगर किया जा सकता है।

## <a name="identify-your-target-audience"></a>अपनी लक्षित ऑडियंस को पहचानें

हमारे परिदृश्य में, हम मानते हैं कि ग्राहकों के ईमेल पते Customer Insights में उपलब्ध हैं और खंड के सदस्यों की पहचान करने के लिए उनकी प्रचार प्राथमिकताओं का विश्लेषण किया गया था।

[Customer Insights में आपके द्वारा परिभाषित खंड](segments.md) कहा जाता है **चर्नप्रोन ग्राहक** और आप इन ग्राहकों को ईमेल प्रचार भेजने की योजना बना रहे हैं।

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers सेगमेंट वाले सेगमेंट पेज का स्क्रीनशॉट बनाया गया है.":::

आप जो ईमेल भेजना चाहते हैं, उसमें पहला नाम, उपनाम और ग्राहक की सदस्यता समाप्ति तिथि शामिल होगी. यह ग्राहकों को उस छूट के बारे में सूचित करता है जिसे वे अपनी सदस्यता को समाप्त होने से पहले नवीनीकृत करने पर प्राप्त करते हैं.

## <a name="export-your-target-audience"></a>अपनी लक्षित ऑडियंस निर्यात करें

### <a name="set-up-connection-to-adobe-campaign"></a>से कनेक्शन सेट करें Adobe अभियान

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **Adobe अभियान।**

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. उसे दर्ज करें **खाता नाम**, **ाता कुंजी**, तथा**पात्र** आपके ब्लॉब संग्रहण खाते के लिए।  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="स्टोरेज खाता कॉन्फ़िगरेशन का स्क्रीनशॉट.":::

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

### <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** फ़ील्ड में, Adobe Campaign सेक्शन से एक कनेक्शन चुनें. यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. वह सेगमेंट चुनें, जिसे आप निर्यात करना चाहते हैं. इस उदाहरण में, यह **ChurnProneCustomers** है.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers अनुभाग चयनित के साथ अनुभाग चयन उपयोगकर्ता इंटरफ़ेस का स्क्रीनशॉट.":::

1. **अगला** चुनें.

1. नक्शा**स्रोत** Customer Insights सेगमेंट से फ़ील्ड तक **लक्ष्य** में फ़ील्ड नाम Adobe अभियान मानक प्रोफ़ाइल स्कीमा।

   :::image type="content" source="media/ACS-field-mapping.png" alt-text=" Adobe Campaign Standard कनेक्टर के लिए फ़ील्ड मैपिंग.":::

   यदि आप अधिक विशेषताएं जोड़ना चाहते हैं, तो **विशेषता जोड़ें** चुनें. लक्ष्य नाम स्रोत फ़ील्ड नाम से भिन्न हो सकता है ताकि आप अभी भी Customer Insights से सेगमेंट आउटपुट को मैप कर सकें Adobe अभियान मानक यदि दो प्रणालियों में फ़ील्ड का नाम समान नहीं है।

   > [!NOTE]
   > ईमेल पते का उपयोग पहचान फ़ील्ड के रूप में किया जाता है, लेकिन आप डेटा को मैप करने के लिए ग्राहक प्रोफ़ाइल से किसी अन्य पहचानकर्ता का उपयोग कर सकते हैं Adobe अभियान मानक।

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> सुनिश्चित करें कि निर्यात किए गए अनुभाग में रिकॉर्ड की संख्या आपके Adobe Campaign Standard लाइसेंस की अनुमति प्राप्त सीमा के भीतर है.

निर्यात किए गए डेटा को ऊपर कॉन्फ़िगर किए गए Azure ब्लॉब स्टोरेज कंटेनर में स्टोर किया जाता है। आपके कंटेनर में निम्न फ़ोल्डर पथ अपने आप बन जाता है: *%ContainerName% /ग्राहकों की अंतर्दृष्टि_%instanceID% /% निर्यात गंतव्य-नाम%_%segmentname%_%timestamp% .सीएसवी*

उदाहरण: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>कॉन्फ़िगर Adobe Campaign Standard करें

निर्यात किए गए सेगमेंट में वे कॉलम होते हैं जिन्हें आपने निर्यात को कॉन्फ़िगर करते समय चुना था। इस डेटा का इस्तेमाल [Adobe Campaign Standard में प्रोफाइल बनाने](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) के लिए किया जा सकता है.

में खंड का उपयोग करने के लिए Adobe अभियान मानक, [प्रोफ़ाइल स्कीमा का विस्तार करें](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) में Adobe दो अतिरिक्त क्षेत्रों को शामिल करने के लिए अभियान मानक।

हमारे उदाहरण में, ये फ़ील्ड सेगमेंट नाम और सेगमेंट दिनांक हैं। हम इन फ़ील्ड का उपयोग Adobe Campaign Standard में उन प्रोफ़ाइलों की पहचान करने के लिए करेंगे जिन्हें हम इस अभियान के लिए लक्षित करना चाहते हैं.

अगर में कोई अन्य रिकॉर्ड नहीं हैं Adobe आप जो आयात करने जा रहे हैं, उसके अलावा अभियान मानक, इस चरण को छोड़ दें।

## <a name="import-data-into-adobe-campaign-standard"></a>Adobe Campaign Standard में डेटा आयात करें

Customer Insights से तैयार ऑडिएंस डेटा आयात करें Adobe अभियान मानक to [वर्कफ़्लो का उपयोग करके प्रोफ़ाइल बनाएं](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

नीचे दी गई छवि में आयात कार्यप्रवाह को हर आठ घंटे में चलाने और निर्यात किए गए Customer Insights सेगमेंट (. Azure Blob Storage में .csv फ़ाइल) देखने के लिए कॉन्फ़िगर किया गया है। कार्यप्रवाह एक निर्दिष्ट कॉलम क्रम में .csv फ़ाइल की सामग्री निकालता है. यह कार्यप्रवाह बुनियादी त्रुटि प्रबंधन करने के लिए बनाया गया है और यह सुनिश्चित करता है कि Adobe Campaign Standard में डेटा को हाइड्रेट करने से पहले प्रत्येक रिकॉर्ड में एक ईमेल पता हो. Adobe Campaign Standard प्रोफ़ाइल डेटा में डालने से पहले कार्यप्रवाह फ़ाइल नाम से खंड का नाम भी निकालता है.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard उपयोगकर्ता इंटरफ़ेस में आयात कार्यप्रवाह का स्क्रीनशॉट.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard में दर्शकों को पुनः प्राप्त करें

एक बार डेटा आयात हो जाने के बाद Adobe अभियान मानक, [एक कार्यप्रवाह बनाएँ](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) तथा[सवाल](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) हमारे नमूना अभियान के लिए पहचाने गए प्रोफाइल का चयन करने के लिए सेगमेंट नाम और सेगमेंट तिथि के आधार पर ग्राहक।

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard का उपयोग करके ईमेल बनाएँ और भेजें

ईमेल सामग्री बनाएं और फिर अपना ईमेल [परीक्षण करें और भेजें](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard से नवीनीकरण प्रस्ताव के साथ नमूना ईमेल.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
