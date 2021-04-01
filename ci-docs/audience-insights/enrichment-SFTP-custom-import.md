---
title: SFTP कस्टम आयात के साथ एनरिचमेंट
description: SFTP कस्टम आयात एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595857"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>कस्टम डेटा (पूर्वावलोकन) के साथ ग्राहक प्रोफाइल को समृद्ध करें

सेक्योर फ़ाइल ट्रांसफर प्रोटोकॉल (SFTP) कस्टम आयात आपको डेटा आयात करने में सक्षम बनाता है जिसे डेटा एकीकरण की प्रक्रिया से गुजरना नहीं पड़ता है. यह आपके डेटा को लाने का एक लचीला, सुरक्षित और आसान तरीका है. SFTP कस्टम आयात का उपयोग [SFTP निर्यात](export-sftp.md) के संयोजन में किया जा सकता है जो आपको समृद्धता के लिए आवश्यक ग्राहक प्रोफ़ाइल डेटा का निर्यात करने देता है. डेटा तो संसाधित किया जा सकता है, समृद्ध, और SFTP कस्टम आयात Dynamics 365 Customer Insights की ऑडियंस इनसाइट्स क्षमता को वापस लाने के लिए समृद्ध डेटा लाने के लिए इस्तेमाल किया जा सकता है .

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

SFTP कस्टम आयात को कॉन्फ़िगर करने के लिए, निम्नलिखित आवश्यकताओं को पूरा किया जाना चाहिए:

- आपके पास SFTP स्थान के लिए उपयोगकर्ता क्रेडेंशियल्स (उपयोगकर्ता नाम और पासवर्ड) है जहां से डेटा आयात किया जा रहा है.
- आपके पास SFTP होस्ट के लिए URL और पोर्ट नंबर (सामान्य तौर पर 22) है.
- आपके पास SFTP होस्ट पर आयात की जाने वाली फ़ाइल का नाम और स्थान है.
- एक *model.json* फ़ाइल है जो आयात किए जाने वाले डेटा के लिए स्कीमा निर्दिष्ट करती है. यह फाइल आयात करने के लिए फ़ाइल के रूप में एक ही निर्देशिका में होना चाहिए.
- आपके पास [प्रशासक](permissions.md#administrator) की अनुमति है.

## <a name="configuration"></a>कॉन्फ़िगरेशन

1. **डेटा** > **समृद्ध** पर जाएं और **खोजें** टैब का चयन करें.

1. **SFTP कस्टम आयात टाइल** पर, **मेरे डेटा को समृद्ध करें**.

   > [!div class="mx-imgBorder"]
   > ![SFTP कस्टम आयात टाइल](media/SFTP_Custom_Import_tile.png "SFTP कस्टम आयात टाइल")

1. **शुरू करें** चुनें और SFTP सर्वर के लिए क्रेडेंशियल्स और पता प्रदान करें. उदाहरण के लिए, sftp://mysftpserver.com:22.

1. यदि यह रूट फ़ोल्डर में नहीं है तो SFTP सर्वर पर फ़ाइल के लिए डेटा और पाथ शामिल फ़ाइल का नाम दर्ज करें.

1. **कस्टम आयात से कनेक्ट करें** का चयन करके सभी इनपुटों की पुष्टि करें.

   > [!div class="mx-imgBorder"]
   > ![SFTP कस्टम आयात कॉन्फ़िगरेशन फ्लाईआउट](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP कस्टम आयात कॉन्फ़िगरेशन फ्लाईआउट")

## <a name="defining-field-mappings"></a>फील्ड मैपिंग को परिभाषित करना 

SFTP सर्वर पर आयात की जाने वाली फ़ाइल को शामिल करने वाली निर्देशिका में एक *model.json* फ़ाइल भी होनी चाहिए. यह फ़ाइल डेटा आयात करने के लिए उपयोग करने के लिए स्कीमा को परिभाषित करती है. स्कीमा को फील्ड मैपिंग को निर्दिष्ट करने के लिए [सामान्य डेटा मॉडल](/common-data-model/) का उपयोग करना होता है . एक model.json फ़ाइल का एक सरल उदाहरण इस तरह दिखता है:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>संवर्धन के परिणाम

संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें. आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं. प्रोसेस करने के समय आयात किए जाने वाले डेटा के आकार और SFTP सर्वर से कनेक्शन पर निर्भर करेगा.

एनरिचमेंट प्रक्रिया पूरी होने के बाद, आप **मेरे एनरिचमेंट्स** के तहत अपने नए आयात किए गए कस्टम एनरिचमेंट डेटा की समीक्षा कर सकते हैं. इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.

आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.

## <a name="next-steps"></a>अगले चरण

अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं. अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [सेगमेंट](segments.md), [साधन](measures.md), और [डेटा निर्यात](export-destinations.md) बनाएं .




[!INCLUDE[footer-include](../includes/footer-banner.md)]