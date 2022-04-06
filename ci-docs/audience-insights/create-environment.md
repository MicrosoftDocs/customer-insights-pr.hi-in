---
title: Customer Insights में परिवेश बनाएँ
description: Dynamics 365 Customer Insights के लिए लाइसेंस प्राप्त सदस्यता के साथ परिवेश बनाने के चरण.
ms.date: 03/28/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: a538237322615f69f0a5cb43d394275bf79af00b
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491915"
---
# <a name="create-an-environment-in-audience-insights"></a>ऑडियंस इनसाइट में एक वातावरण बनाएं

यह आलेख बताता है कि आपके संगठन द्वारा Dynamics 365 Customer Insights सदस्यता खरीदने के बाद एक नया परिवेश कैसे बनाया जाए. 

संगठन हर Customer Insights लाइसेंस के लिए *दो* परिवेश बना सकते हैं. यदि आपका संगठन एक से अधिक लाइसेंस खरीदता है, तो उपलब्ध परिवेशों की संख्या बढ़ाने के लिए [हमारी सहायता टीम से संपर्क करें](https://go.microsoft.com/fwlink/?linkid=2079641). क्षमता और ऐड-ऑन क्षमता के बारे में अधिक जानकारी के लिए, [Dynamics 365 लाइसेंसिंग मार्गदर्शिका](https://go.microsoft.com/fwlink/?LinkId=866544) डाउनलोड करें.

> [!NOTE]
> यदि आप सेवा को आज़माना चाहते हैं, तो [एक ट्रायल परिवेश सेट करें](../trial-signup.md) देखें.

## <a name="create-a-new-environment"></a>कोई नया परिवेश बनाएँ

Customer Insights के लिए सदस्यता लाइसेंस खरीदने के बाद, के वैश्विक व्यवस्थापक Microsoft 365 टैनेंट को एक ईमेल प्राप्त होता है जो उन्हें परिवेश बनाने के लिए आमंत्रित करता है। शुरू करने के लिए [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) पर जाएँ. 

एक निर्देशित अनुभव आपको नए परिवेश के लिए सभी आवश्यक जानकारी एकत्र करने के चरणों में मदद करता है. परिवेश बनाने या प्रबंधित करने के लिए आपको ऑडियंस इनसाइट्स में [व्यवस्थापक अनुमतियां](permissions.md) की आवश्यकता होती है.

1. ऑडियंस इनसाइट्स में, परिवेश पिकर खोलें और **+ नया** चुनें.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="पर्यावरण पिकर का चयन करें.":::

1. निम्नलिखित सेक्सन में उल्लिखित निर्देशित अनुभव का पालन करें.

### <a name="step-1-provide-environment-information"></a>चरण 1: पर्यावरण की जानकारी प्रदान करें

**मूल जानकारी** चरण में, चुनें कि आप शुरुआत से एक परिवेश बनाना चाहते हैं या [किसी अन्य परिवेश से डेटा कॉपी करें](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="नया Customer Insights परिवेश बनाने के लिए संवाद.":::

निम्न विवरण प्रदान करें:
   - **नाम**: इस वातावरण का नाम है. यदि आपने मौजूदा परिवेश को कॉपी किया है, तो यह फ़ील्ड पहले से ही भरी हुई होती है, लेकिन आप इसे बदल सकते हैं.
   - **अपना व्यवसाय चुनें**: नए परिवेश के लिए प्राइमरी ऑडिएंस को चुनें. आप अलग-अलग उपभोक्ताओं (B-से-C) या [व्यवसाय खातों](work-with-business-accounts.md) के साथ काम कर सकते हैं.
   - **प्रकार**: चुनें कि क्या आप प्रोडक्शन परिवेश बनाना चाहते हैं या सैंडबॉक्स. सैंडबॉक्स परिवेश शेड्यूल किए गए डेटा को रीफ़्रेश करने की अनुमति नहीं देते हैं और पूर्व-कार्यान्वयन और परीक्षण के लिए अभिप्रेत हैं. सैंडबॉक्स परिवेश उन्हीं प्राइमरी ऑडियंस का उपयोग करते हैं जो वर्तमान में चयनित प्रोडक्शन परिवेश के रूप में हैं.
   - **क्षेत्र**: वह क्षेत्र जिसमें सेवा को तैनात और होस्ट किया गया है.

### <a name="step-2-configure-data-storage"></a>चरण 2: डेटा संग्रहण कॉन्फ़िगर करें

**डेटा संग्रहण** चरण में, ऑडियंस इनसाइट्स से डेटा संग्रहीत करने का स्थान चुनें.

आपके पास दो विकल्प होंगे: **Customer Insights संग्रहण** (एक Azure डेटा लेक जिसे Customer Insights टीम द्वारा प्रबंधित किया जाता है) और **Azure Data Lake Storage** (अपना खुद का Azure Data Lake Storage). डिफ़ॉल्ट रूप से, Customer Insights संग्रहण विकल्प चुना जाता है.

:::image type="content" source="media/data-storage-environment.png" alt-text="अपने ऑडियंस इनसाइट्स डेटा को संग्रहण करने के लिए Azure Data Lake Storage चुनें.":::

डेटा को Azure Data Lake Storage में सहेज कर, आप सहमति देते हैं कि डेटा उस Azure स्टोरेज खाते के लिए उपयुक्त ज्योग्राफिक स्थान पर स्थानांतरित और संग्रहीत किया जाएगा. यह स्थान उस स्थान से भिन्न हो सकता है जहां डेटा को Dynamics 365 Customer Insights में संग्रहीत किया जाता है. [Microsoft विश्वास केन्द्र](https://www.microsoft.com/trust-center) पर अधिक जानें.

> [!NOTE]
> Customer Insights वर्तमान में निम्नलिखित का समर्थन करती है:
> - ऐसे इंजेस्टेड निकाय जो Power BI डेटाफ़्लो से है और Microsoft Dataverse-प्रबंधित Data Lake में संग्रहीत हैं.  
> - Azure Data Lake Storage खाते उसी Azure क्षेत्र से हैं जिसे आपने परिवेश बनाते समय चुना था.
> - Azure Data Lake Storage ऐसे खाते जो Gen2 हैं और जिनके पास है *पदानुक्रमित नाम स्थान* सक्षम। Azure Data Lake Gen1 संग्रहण खाते समर्थित नहीं हैं।

Azure Data Lake Storage विकल्प के लिए, आप प्रमाणीकरण के लिए संसाधन-आधारित विकल्प और सदस्यता-आधारित विकल्प के बीच चयन कर सकते हैं। अधिक जानकारी के लिए, [Azure सर्विस प्रिंसिपल का उपयोग करके एक Azure Data Lake Storage खाते से कनेक्ट करें](connect-service-principal.md) देखें. **कंटेनर** का नाम `customerinsights` होगा और इसे बदला नहीं जा सकता.

जब सिस्टम प्रक्रिया जैसे डेटा इन्जेस्चन पूरा हो जाता है, तो सिस्टम आपके द्वारा निर्दिष्ट संग्रहण खाते में संगत फ़ोल्डर बनाता है. डेटा फ़ाइलें और *model.json* फ़ाइलें प्रक्रिया नाम के आधार पर बनाई और फ़ोल्डर में जोड़ी जाती हैं.

यदि आप Customer Insights के अनेक परिवेश बनाते हैं और उन परिवेशों से आउटपुट निकायों को अपने संग्रहण खाते में सहेजना चुनते हैं, तो Customer Insights कंटेनर में `ci_environmentID` के साथ प्रत्येक परिवेश के लिए अलग फ़ोल्डर बनाता है.

### <a name="step-3-connect-to-microsoft-dataverse"></a>चरण 3: Microsoft Dataverse से कनेक्ट करें
   
**Microsoft Dataverse** चरण से आप Customer Insights को अपने Dataverse परिवेश से जोड़ सकते हैं.

अपना प्रदान करें Microsoft Dataverse पर आधारित व्यावसायिक अनुप्रयोगों के साथ डेटा (प्रोफाइल और अंतर्दृष्टि) साझा करने के लिए पर्यावरण Dataverse, जैसे Dynamics 365 Marketing या मॉडल-चालित अनुप्रयोग Power Apps. यदि आपके पास अपना नहीं है तो इस फ़ील्ड को खाली छोड़ दें Dataverse पर्यावरण और हम आपके लिए एक प्रावधान करेंगे।

अपने से जुड़ रहा है Dataverse पर्यावरण भी आपको सक्षम बनाता है [ऑन-प्रिमाइसेस डेटा स्रोतों का उपयोग करके डेटा निगलनाPower Platform डेटा प्रवाह और गेटवे।](data-sources.md#add-data-from-on-premises-data-sources) आप भी उपयोग कर सकते हैं [आउट-ऑफ़-बॉक्स पूर्वानुमान मॉडल](predictions-overview.md?tabs=b2c#out-of-box-models) a . से जुड़कर Dataverse वातावरण।

> [!IMPORTANT]
> 1. ग्राहक अंतर्दृष्टि और Dataverse डेटा साझाकरण को सक्षम करने के लिए एक ही क्षेत्र में होना चाहिए।
> 1. इसमें आपकी वैश्विक व्यवस्थापक भूमिका होनी चाहिए Dataverse वातावरण। सत्यापित करें कि क्या यह [Dataverse पर्यावरण जुड़ा हुआ है](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) कुछ सुरक्षा समूहों के लिए और सुनिश्चित करें कि आप उन सुरक्षा समूहों में जोड़े गए हैं।
> 1. कोई मौजूदा Customer Insights परिवेश पहले से उससे संबद्ध नहीं है Dataverse वातावरण। करना सीखें [a . से मौजूदा कनेक्शन को हटा दें Dataverse वातावरण](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="के साथ डेटा साझा करनाMicrosoft Dataverse शुद्ध नए उदाहरणों के लिए स्वतः सक्षम।":::

के साथ डेटा साझाकरण सक्षम करने के बारे में अधिक जानकारी के लिए Microsoft Dataverse अपने से Azure Data Lake Storage, देखो[से कनेक्ट Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights निम्नलिखित डेटा साझाकरण परिदृश्यों का समर्थन नहीं करता है:
- अगर आप Dataverse के साथ डेटा साझाकरण सक्षम करते हैं, तो आप [किसी निकाय में अनुमानित या अनुपलब्ध मान बना सकते हैं](predictions.md) नहीं कर पाएंगे.

### <a name="step-4-finalize-the-settings"></a>चरण 4: सेटिंग्स को अंतिम रूप दें

**समीक्षा** चरण में, सभी निर्दिष्ट सेटिंग्स पर जाएं. जब सब कुछ पूरा दिखे, तो परिवेश सेट करने के लिए **बनाएं** चुनें. 

आप अधिकांश सेटिंग्स को बाद में भी बदल सकते हैं. अधिक जानकारी के लिए, [परिवेश प्रबंधित करें](manage-environments.md) देखें.

## <a name="work-with-your-new-environment"></a>अपने नए परिवेश के साथ काम करें

Customer Insights की कॉन्फ़िगरेशन शुरू करने में आपकी मदद के लिए निम्नलिखित आर्टिकल की समीक्षा करें: 

- [अधिक उपयोगकर्ता जोड़ें और अनुमतियां असाइन करें](permissions.md).
- [अपने डेटा स्रोतों को अंतर्ग्रहण करना](data-sources.md) और [एकीकृत ग्राहक प्रोफ़ाइल](data-unification.md) प्राप्त करने के लिए उन्हें [डेटा एकीकरण प्रक्रिया](customer-profiles.md) में से चलाएं.
- [एकीकृत ग्राहक प्रोफाइल को समृद्ध करें](enrichment-hub.md) या [पूर्वानुमानित मॉडल चलाएं](predictions-overview.md).
- ग्राहकों को समूहीकृत करने के लिए [सेगमेंट बनाएँ](segments.md) और KPI की समीक्षा करने के लिए [माप](measures.md) बनाएँ.
- अन्य एप्लिकेशनों में अपने डेटा के सबसेट को संसाधित करने के लिए [कनेक्शन सेट करें](connections.md) और [निर्यात](export-destinations.md) करें.
