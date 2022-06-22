---
title: SFTP कस्टम आयात के साथ एनरिचमेंट
description: SFTP कस्टम आयात एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 657afb6fcb68429680eb677734b4115e69769008
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953721"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>कस्टम डेटा (पूर्वावलोकन) के साथ ग्राहक प्रोफाइल को समृद्ध करें

सेक्योर फ़ाइल ट्रांसफर प्रोटोकॉल (SFTP) कस्टम आयात आपको डेटा आयात करने में सक्षम बनाता है जिसे डेटा एकीकरण की प्रक्रिया से गुजरना नहीं पड़ता है. यह आपके डेटा को लाने का एक लचीला, सुरक्षित और आसान तरीका है. SFTP कस्टम आयात का उपयोग [SFTP निर्यात](export-sftp.md) के संयोजन में किया जा सकता है जो आपको समृद्धता के लिए आवश्यक ग्राहक प्रोफ़ाइल डेटा का निर्यात करने देता है. तब डेटा को संसाधित और समृद्ध किया जा सकता है, और समृद्ध डेटा को वापस लाने के लिए SFTP कस्टम आयात का उपयोग किया जा सकता है।Dynamics 365 Customer Insights

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- फ़ाइल का नाम और SFTP होस्ट पर आयात की जाने वाली फ़ाइल का स्थान (पथ) ज्ञात है।

- ए *मॉडल.जेसन* फ़ाइल जो आयात किए जाने वाले डेटा के लिए सामान्य डेटा मॉडल स्कीमा निर्दिष्ट करती है, उपलब्ध है। यह फाइल आयात करने के लिए फ़ाइल के रूप में एक ही निर्देशिका में होना चाहिए.

- एक SFTP [संबंध](connections.md) है [विन्यस्त।](#configure-the-connection-for-sftp-custom-import)

## <a name="file-schema-example"></a>फ़ाइल स्कीमा उदाहरण

SFTP सर्वर पर आयात की जाने वाली फ़ाइल को शामिल करने वाली निर्देशिका में एक *model.json* फ़ाइल भी होनी चाहिए. यह फ़ाइल डेटा आयात करने के लिए उपयोग करने के लिए स्कीमा को परिभाषित करती है. फ़ील्ड मैपिंग निर्दिष्ट करने के लिए स्कीमा को [ सामान्य डेटा मॉडल](/common-data-model/) का उपयोग करना होगा। एक model.json फ़ाइल का एक सरल उदाहरण इस तरह दिखता है:

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP कस्टम आयात के लिए कनेक्शन को कॉन्फ़िगर करें

आप एक होना चाहिए [प्रशासक](permissions.md#admin) Customer Insights में और उस SFTP स्थान के लिए उपयोगकर्ता क्रेडेंशियल, URL और पोर्ट नंबर रखें जहाँ से आप डेटा आयात करना चाहते हैं।

1. चुनना**कनेक्शन जोड़ें** किसी संवर्धन को कॉन्फ़िगर करते समय या यहां जाएं **व्यवस्थापक** > **सम्बन्ध** और चुनें **स्थापित करना** कस्टम आयात टाइल पर।

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="कस्टम आयात कनेक्शन कॉन्फ़िगरेशन पृष्ठ।":::

1. कनेक्शन के लिए एक नाम दर्ज करें।

1. SFTP सर्वर के लिए एक मान्य उपयोगकर्ता नाम, पासवर्ड और होस्ट URL दर्ज करें, जिस पर आयात किया जाने वाला डेटा रहता है।

1. **मैं सहमत हूं** चयन करके [डेटा गोपनीयता और अनुपालन](#data-privacy-and-compliance) की समीक्षा करें और इसके लिए अपनी सहमति प्रदान करें।

1. चुनना**सत्यापित करना** कॉन्फ़िगरेशन को सत्यापित करने के लिए और फिर चुनें **बचाना**.

### <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप सक्षम करते हैं Dynamics 365 Customer Insights कस्टम आयात का उपयोग करके डेटा संचारित करने के लिए, आप अनुपालन सीमा के बाहर डेटा के हस्तांतरण की अनुमति देते हैं Dynamics 365 Customer Insights, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं। Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन यह सुनिश्चित करने के लिए आप ज़िम्मेदार हैं कि डेटा आपके किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है। अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.
आपका Dynamics 365 Customer Insights व्यवस्थापक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस संवर्धन को हटा सकता है.

## <a name="configure-the-import"></a>आयात कॉन्फ़िगर करें

1. **डेटा** > **समृद्ध** पर जाएं और **खोजें** टैब का चयन करें.

1. चुनना**मेरा डेटा समृद्ध करें** पर **एसएफ़टीपी कस्टम आयात** टाइल

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP कस्टम आयात टाइल.":::

1. ओवरव्यू की समीक्षा करें और फिर चुनें **अगला**.

1. कनेक्शन का चयन करें। यदि कोई उपलब्ध न हो तो किसी व्यवस्थापक से संपर्क करें।

1. को चुनिए **ग्राहक डेटा सेट** और वह प्रोफ़ाइल या खंड चुनें जिसे आप समृद्ध करना चाहते हैं। *ग्राहक* इकाई आपके सभी ग्राहक प्रोफाइल को समृद्ध करती है जबकि एक सेगमेंट केवल उस सेगमेंट में निहित ग्राहक प्रोफाइल को समृद्ध करता है।

1. **अगला** चुनें.

1. उसे दर्ज करें **रास्ता** तथा**फ़ाइल का नाम** उस डेटा फ़ाइल का जिसे आप आयात करना चाहते हैं।

1. **अगला** चुनें.

1. प्रदान करें एक **नाम** संवर्धन के लिए और **आउटपुट इकाई का नाम**.

1. अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** चुनें.

1. चुनना**दौड़ना** संवर्धन प्रक्रिया शुरू करने के लिए या वापस लौटने के करीब **संवर्धन** पृष्ठ।

## <a name="enrichment-results"></a>संवर्धन के परिणाम

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>अगले कदम

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
