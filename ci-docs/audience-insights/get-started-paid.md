---
title: Customer Insights का सशुल्क लाइसेंस बनाएँ और कॉन्फ़िगर करें
description: Dynamics 365 Customer Insights के लिए लाइसेंस वाली सदस्यता प्राप्त करने और उसे कॉन्फ़िगर करने के चरण.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f8cf1be97ee8af46145a450009fd278b1821f8fe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650476"
---
# <a name="get-started-with-a-paid-subscription"></a>सशुल्क सदस्यता के साथ शुरू करें

यह आलेख बताता है कि आपके संगठन द्वारा Dynamics 365 Customer Insights सदस्यता खरीदने के बाद एक नया परिवेश कैसे बनाया जाए. यदि आप Customer Insights खरीदना चाहते हैं, तो हमारे संपर्क विकल्प [Dynamics 365 Customer Insights वेबसाइट](https://dynamics.microsoft.com/ai/customer-insights/) पर दिए गए हैं. 

यदि आप सेवा और सुविधाओं को आज़माना चाहते हैं, तो [परीक्षण परिवेश सेट करें](get-started-trial.md) देखें.

## <a name="create-an-environment-in-an-existing-organization"></a>किसी मौजूदा संगठन में एक परिवेश बनाएँ

Customer Insights के लिए सदस्यता लाइसेंस खरीदने के बाद, Microsoft 365 टेनेंट के वैश्विक व्यवस्थापक को एक ईमेल प्राप्त होता है जो उन्हें परिवेश बनाने के लिए आमंत्रित करता है. शुरू करने के लिए [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) पर जाएँ. 

Customer Insights प्रति उपयोगकर्ता लाइसेंसी प्राप्त नहीं है, इसलिए यह लाइसेंस क्षेत्र में प्रदर्शित नहीं होगा. यदि आप Microsoft 365 व्यवस्थापन केंद्र में लाइसेंस की तलाश कर रहे हैं, तो **आपके उत्पाद** पर जाएँ. 

> [!NOTE]
> संगठन हर Customer Insights लाइसेंस के लिए *दो* परिवेश बना सकते हैं. यदि आपका संगठन एक से अधिक बार लाइसेंस खरीदता है, तो कृपया उपलब्ध परिवेश की संख्या बढ़ाने के लिए [हमारी सहायता टीम](https://go.microsoft.com/fwlink/?linkid=2079641) से संपर्क करें. क्षमता और ऐड-ऑन क्षमता के बारे में अधिक जानकारी के लिए, [Dynamics 365 लाइसेंसिंग मार्गदर्शिका](https://go.microsoft.com/fwlink/?LinkId=866544) डाउनलोड करें.

एक परिवेश बनाएँ:

1. **एक परिवेश बनाएं** संवाद में, **नया परिवेश** चुनें।

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="नया Customer Insights परिवेश बनाने के लिए संवाद.":::

   हम सिफारिश करते हैं कि शुरू से ही परिवेश स्थापित करना प्रारंभ करें. हालांकि, यदि आप एक परीक्षण परिवेश के व्यवस्थापक या सदस्य हैं, तो आप **मौजूदा परिवेश से कॉपी करें** चुनकर [किसी अन्य परिवेश से डेटा कॉपी करें](manage-environments.md#copy-the-environment-configuration) कर सकते हैं. आपको अपने संगठन के सभी उपलब्ध परिवेशों की एक सूची दिखाई देगी जहां से आप डेटा कॉपी कर सकते हैं.

1. निम्न विवरण प्रदान करें:
   - **नाम**: इस वातावरण का नाम है. यदि आपने मौजूदा परिवेश को कॉपी किया है, तो यह फ़ील्ड पहले से ही भरी हुई होती है, लेकिन आप इसे बदल सकते हैं.
   - **क्षेत्र**: वह क्षेत्र जिसमें सेवा को तैनात और होस्ट किया गया है.
   - **प्रकार**: चुनें कि क्या आप प्रोडक्शन परिवेश बनाना चाहते हैं या सैंडबॉक्स. सैंडबॉक्स परिवेश शेड्यूल किए गए डेटा को रीफ़्रेश करने की अनुमति नहीं देते हैं और पूर्व-कार्यान्वयन और परीक्षण के लिए अभिप्रेत हैं.
   
1. वैकल्पिक रूप से, आप **उन्नत सेटिंग** चुन सकते हैं:

   - **सभी डेटा को सहेजें**: यह निर्दिष्ट करता है कि आप Customer Insights से जनित आउटपुट डेटा को कहां संग्रहीत करना चाहते हैं. आपके पास दो विकल्प होंगे: **Customer Insights संग्रहण** (एक Azure Data Lake जिसे Customer Insights टीम द्वारा प्रबंधित किया जाता है) और **Azure Data Lake Storage** (अपना खुद का Azure Data Lake Storage). डिफ़ॉल्ट रूप से, Customer Insights संग्रहण विकल्प चुना जाता है.

     > [!NOTE]
     > Azure Data Lake Storage में डेटा को सहेजकर, आप सहमत होते हैं कि डेटा उस Azure संग्रहण खाते के लिए उपयुक्त भौगोलिक स्थान पर स्थानांतरित और संग्रहित किया जाएगा, जो कि Dynamics 365 Customer Insights में डेटा संग्रहित करने से भिन्न हो सकता है. [Microsoft विश्वास केन्द्र पर अधिक जानें.](https://www.microsoft.com/trust-center)
     >
     > वर्तमान में, Power BI डेटा प्रवाह से अंतर्ग्रहित निकाय Microsoft Dataverse-प्रबंधित Data Lake में स्टोर किए जाते हैं. 
     > 
     > हम केवल उसी Azure क्षेत्र के Azure Data Lake Storage खातों का समर्थन करते हैं, जिसे आपने परिवेश बनाते समय चुना था। 
     > 
     > हम केवल उन Azure Data Lake Storage खातों का समर्थन करते हैं जिनमें पदानुक्रमित नाम स्थान सक्षम है।


   - Azure Data Lake Storage विकल्प के लिए, आप प्रमाणीकरण के लिए संसाधन-आधारित विकल्प और सदस्यता-आधारित विकल्प के बीच चयन कर सकते हैं। अधिक जानकारी के लिए, देखें [एक Azure Data Lake Storage Gen2 खाते के लिए एक Azure service principal के साथ ऑडियंस इन्साइट्स को कनेक्ट करें](connect-service-principal.md). **कंटेनर** का नाम बदला नहीं जा सकता है और यह `customerinsights` रहेगा.
   
   - यदि आप [आउट-ऑफ़-बॉक्स मॉडल](predictions-overview.md#out-of-box-models) का उपयोग करना चाहते हैं, तो Microsoft Dataverse के साथ डेटा साझाकरण कॉन्फ़िगर करें या ऑन-प्रिमाइसेस डेटा स्रोतों से डेटा अंतर्ग्रहण सक्षम करें, **Microsoft Dataverse के साथ डेटा साझाकरण कॉन्फ़िगर करें और अतिरिक्त क्षमताएं सक्षम करें** के अंतर्गत Microsoft Dataverse परिवेश URL प्रदान करें. **डेटा साझाकरण सक्षम करें** को चुनें, ताकि Microsoft Dataverse प्रबंधित Data Lake के साथ Customer Insights आउटपुट डेटा साझा किया जा सके.

     > [!NOTE]
     > - जब आप सभी डेटा को अपने Azure Data Lake Storage में सहेजते हैं, Microsoft Dataverse प्रबंधित डेटा लेक के साथ डेटा साझाकरण वर्तमान में समर्थित नहीं है.
     > - जब आप Microsoft Dataverse प्रबंधित Data Lake के साथ डेटा साझा करना सक्षम करते हैं तो ऐसे में [एक निकाय में लापता मानों का पूर्वानुमान](predictions.md) वर्तमान में समर्थित नहीं है.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text=" Microsoft Dataverse के साथ डेटा साझा करने में सक्षम करने का कॉन्फ़िगरेशन विकल्प.":::

   जब सिस्टम प्रक्रिया जैसे डेटा अंतर्ग्रहण पूर्ण हो जाता है, तो सिस्टम आपके द्वारा निर्दिष्ट स्टोरेज खाते में संगत फ़ोल्डर बनाता है. डेटा फ़ाइलें और model.json फ़ाइलें प्रक्रिया नाम के आधार पर बनाई और फ़ोल्डर में जोड़ी जाती हैं.

   यदि आप Customer Insights के कई परिवेश बनाते हैं और अपने स्टोरेज खाते में उन परिवेशों से आउटपुट निकायों को सहेजना चुनते हैं, तो कंटेनर में ci_<environmentid> के साथ प्रत्येक परिवेश के लिए अलग-अलग फ़ोल्डर बनाए जाएंगे.

1. परिवेश सेट करने के लिए **बनाएँ** चुनें. 

## <a name="configure-an-environment"></a>एक परिवेश कॉन्फ़िगर करें

Customer Insights को कॉन्फ़िगर करने के साथ शुरू करने में आपकी मदद के लिए निम्नलिखित आलेखों की समीक्षा करें. 

- [अधिक उपयोगकर्ता जोड़ें और अनुमतियां असाइन करें](permissions.md).
- [अपने डेटा स्रोतों को अंतर्ग्रहण करना](data-sources.md) और [एकीकृत ग्राहक प्रोफ़ाइल](data-unification.md) प्राप्त करने के लिए उन्हें [डेटा एकीकरण प्रक्रिया](customer-profiles.md) में से चलाएं.
- [एकीकृत ग्राहक प्रोफाइल को समृद्ध करें](enrichment-hub.md) या [पूर्वानुमानित मॉडल चलाएं](predictions-overview.md).
- ग्राहकों को समूहीकृत करने के लिए [सेगमेंट](segments.md) बनाएँ और [उपाय](measures.md) KPI की समीक्षा करें.
- अन्य एप्लिकेशनों में अपने डेटा के सबसेट को संसाधित करने के लिए [कनेक्शन](connections.md) और [निर्यात](export-destinations.md) सेट करें.
