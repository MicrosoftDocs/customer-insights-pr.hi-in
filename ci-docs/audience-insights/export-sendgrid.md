---
title: SendGrid के लिए Customer Insights डेटा निर्यात करें
description: SendGrid के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597283"
---
# <a name="connector-for-sendgrid-preview"></a>SendGrid के लिए संबंधक (पूर्वावलोकन)

एकीकृत ग्राहक प्रोफ़ाइल के सेगमेंट SendGrid संपर्क सूचियों में निर्यात करें और उन्हें SendGrid में अभियानों और ईमेल मार्केटिंग के लिए उपयोग करें. 

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

-   आपके पास [SendGrid अकाउंट](https://sendgrid.com/) और संबंधित एडमिनिस्ट्रेटर के क्रेडेन्सियल्स हैं.
-   SendGrid और संबंधित ID में मौजूदा संपर्क सूचियां हैं. अधिक जानकारी के लिए, [SendGrid - संपर्क प्रबंधित करें](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) देखें.
-   आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.
-   निर्यात किए गए खंडों में एकीकृत ग्राहक प्रोफाइल में ईमेल पते का प्रतिनिधित्व करने वाला क्षेत्र होता है.

## <a name="connect-to-sendgrid"></a>SendGrid से कनेक्ट करें

1. **व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.

1. **SendGrid** के अंतर्गत, **सेट अप** चुनें.

1. अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid निर्यात कॉन्फ़िगरेशन फलक.":::

1. अपनी **SendGrid API कुंजी** दर्ज करें [SendGrid API कुंजी](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. अपनी **[SendGrid सूची ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** दर्ज करें.

1. **डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.

1. SendGrid से कनेक्शन को शुरू करने के लिए **जोड़ें** का चयन करें.

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.

## <a name="configure-the-connector"></a>कनेक्टर कॉन्फ़िगर करें

1. **डेटा मिलान** अनुभाग में, **ईमेल** फ़ील्ड में, अपने एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करता है. अन्य वैकल्पिक फ़ील्ड जैसे कि **प्रथम नाम**, **अंतिम नाम**, **देश/क्षेत्र**, **राज्य**, **शहर** और **पोस्ट कोड** के लिए समान चरणों को दोहराएं.

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं. हम दृढ़ता से SendGrid में **कुल 100'000 से अधिक ग्राहक प्रोफ़ाइल निर्यात नहीं करने की सलाह देते हैं**. 

1. **सहेजें** चुनें.

## <a name="export-the-data"></a>डेटा निर्यात करें

आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं. निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- SendGrid में कुल 100'000 प्रोफ़ाइल तक.
- SendGrid को निर्यात करना सेगमेंटों तक सीमित है.
- SendGrid को 100'000 प्रोफ़ाइल तक निर्यात करने में कुछ घंटे लग सकते हैं. 
- SendGrid को निर्यात किए जा रहे प्रोफ़ाइल की संख्या SendGrid के साथ आपके अनुबंध पर निर्भर और सीमित है.

## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को SendGrid पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं. Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि SendGrid आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.
आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.


[!INCLUDE[footer-include](../includes/footer-banner.md)]