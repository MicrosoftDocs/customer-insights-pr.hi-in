---
title: Microsoft Dataverse में Customer Insights डेटा
description: Microsoft Dataverse में Customer Insights निकायों का उपयोग तालिका के रूप में करें.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9855ff6908001dd18bc19a286fc56620d0a127e5
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645220"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse में Customer Insights डेटा के साथ कार्य करें

Customer Insights [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md) में आउटपुट निकायों को उपलब्ध कराने का विकल्प उपलब्ध कराता है. यह एकीकरण लो कोड / नो कोड दृष्टिकोण के माध्यम से डेटा साझाकरण को आसान और कस्टम विकास को सक्षम बनाता है. Dataverse में आउटपुट इकाइयाँ तालिका के रूप में उपलब्ध होंगी. ये तालिकाएं Power Apps के माध्यम से [Power Automate के माध्यम से स्वचालित कार्यप्रवाह](/power-automate/getting-started), [मॉडल-चालित अनुप्रयोग](/powerapps/maker/model-driven-apps/) और [कैनवास अनुप्रयोग](/powerapps/maker/canvas-apps/) जैसे परिदृश्यों को सक्षम करती हैं. आप किसी भी अन्य एप्लिकेशन के लिए डेटा का उपयोग कर सकते हैं जो Dataverse तालिका पर आधारित है. वर्तमान कार्यान्वयन मुख्य रूप से लुकअप का समर्थन करता है जहां उपलब्ध ऑडियंस इनसाइट निकाय से किसी दिए गए ग्राहक ID के लिए डेटा निकाला जा सकता है.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Customer Insights पर Dataverse परिवेश अटैच करें

**मौजूदा Dataverse परिवेश के साथ संगठन**

जो संगठन पहले से ही Dataverse का उपयोग करते हैं, वे जब कोई व्यवस्थापक ऑडियंस इनसाइट्स सेट करता है [अपने मौजूदा Dataverse परिवेशों में से एक का उपयोग कर सकते हैं](create-environment.md). Dataverse परिवेश को URL प्रदान करके, यह उनके नए ऑडियंस इनसाइट्स परिवेश से जोड़ रहा है. सर्वोत्तम संभव प्रदर्शन सुनिश्चित करने के लिए Customer Insights और Dataverse परिवेशों को एक ही क्षेत्र में होस्ट किया जाना चाहिए.

**नया संगठन**

यदि आप Customer Insights सेट करते समय एक नया संगठन बनाते हैं, तो आपको स्वचालित रूप से एक नया Dataverse परिवेश प्राप्त होगा.

> [!NOTE]
> यदि आपके संगठन पहले से ही अपने टैनेंट में Dataverse का उपयोग करते हैं, तो यह याद रखना आवश्यक है कि [Dataverse परिवेश निर्माण एक व्यवस्थापक द्वारा नियंत्रित किया जाता है](/power-platform/admin/control-environment-creation.md). उदाहरण के लिए, यदि आप अपने संगठनात्मक खाते के साथ एक नया ऑडियंस इनसाइट वातावरण स्थापित कर रहे हैं और व्यवस्थापक ने व्यवस्थापकों को छोड़कर बाकी सभी के लिए Dataverse परीक्षण परिवेश बनाना अक्षम कर दिया है, तो आप एक नया परीक्षण परिवेश नहीं बना सकते.
> 
> Customer Insights में बनाए गए Dataverse परीक्षण परिवेशों में 3 GB संग्रहण होता है, जिसकी गणना टैनेंट की कुल निर्दिष्ट क्षमता में नहीं की जाएगी. भुगतान सदस्यताओं को डेटाबेस के लिए 15 GB और फाइल स्टोरेज के लिए 20 GB की Dataverse पात्रता मिलती है.

## <a name="output-entities"></a>आउटपुट निकाय

Dataverse में ऑडिएंस इनसाइट्स से कुछ आउटपुट निकाय तालिका के रूप में उपलब्ध हैं. नीचे दिए गए खंड इन तालिकाओं के अपेक्षित स्कीमा का वर्णन करते हैं.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [संवर्द्धन](#enrichment)
- [पूर्वानुमान](#prediction)


### <a name="customerprofile"></a>CustomerProfile

इस तालिका में Customer Insights से एकीकृत ग्राहक प्रोफ़ाइल शामिल है. एकीकृत ग्राहक प्रोफ़ाइल के लिए स्कीमा मर्ज प्रक्रिया में उपयोग किए जाने वाले निकायों और विशेषताओं पर निर्भर करती है. एक ग्राहक प्रोफ़ाइल स्कीमा में आमतौर पर [CustomerProfile की कॉमन डेटा मॉडल परिभाषा](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) की विशेषताओं का एक सबसेट होता है.

### <a name="alternatekey"></a>AlternateKey

AlternateKey तालिका में उन निकायों की कुंजियाँ हैं, जिन्होंने एकीकृत प्रक्रिया में भाग लिया था.

|Column  |प्रकार  |विवरण  |
|---------|---------|---------|
|DataSourceName    |String         | डेटा स्रोत का नाम. उदाहरण के लिए: `datasource5`        |
|EntityName        | String        | ऑडिएंस इनसाइट में निकाय का नाम. उदाहरण के लिए: `contact1`        |
|AlternateValue    |String         |वैकल्पिक ID जिसे ग्राहक ID से मैप किया गया है. उदाहरण: `cntid_1078`         |
|KeyRing           | बहुरेखीय टेक्स्ट        | JSON मान  </br> नमूना: [{ "dataSourceName":" डेटासोर्स5 ",</br>"entityName": "संपर्क1",</br>"preferredKey":" cntid_1078",</br>"कीज़":[" cntid_1078"]}]       |
|CustomerId         | String        | एकीकृत ग्राहक प्रोफ़ाइल की ID.         |
|AlternateKeyId     | GUID         |  msdynci_identifier पर आधारित AlternateKey निर्धारणात्मक GUID       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> नमूना: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

इस तालिका में उन उपयोगकर्ताओं की गतिविधियाँ शामिल हैं जो Customer Insights में उपलब्ध हैं.

| Column            | प्रकार        | विवरण                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ग्राहक प्रोफ़ाइल ID                                                                      |
| ActivityId        | String      | ग्राहक गतिविधि की आंतरिक ID (प्राथमिक कुंजी)                                       |
| SourceEntityName  | String      | स्रोत निकाय का नाम                                                                |
| SourceActivityId  | String      | स्रोत निकाय से प्राथमिक कुंजी                                                       |
| ActivityType      | String      | कस्टम गतिविधि का सिमेंटिक गतिविधि प्रकार या नाम                                        |
| ActivityTimeStamp | DATETIME    | गतिविधि टाइम स्टैंप                                                                      |
| शीर्षक             | String      | गतिविधि का शीर्षक या नाम                                                               |
| विवरण       | String      | गतिविधि का विवरण                                                                     |
| URL               | String      | गतिविधि के लिए विशिष्ट एक बाहरी URL से लिंक करें                                         |
| SemanticData      | JSON स्ट्रिंग | गतिविधि के प्रकार के लिए विशिष्ट अर्थपूर्ण मानचित्रण क्षेत्रों के लिए कुंजी मान जोड़ियों की एक सूची शामिल है |
| RangeIndex        | String      | गतिविधि टाइमलाइन और प्रभावी श्रेणी प्रश्नों को छांटने के लिए उपयोग किया जाने वाला Unix टाइमस्टैम्प |
| mydynci_unifiedactivityid   | GUID | ग्राहक गतिविधि की आंतरिक ID (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

इस तालिका में ग्राहक एट्रिब्यूट-आधारित उपायों का आउटपुट डेटा है.

| Column             | प्रकार             | विवरण                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | ग्राहक प्रोफ़ाइल ID        |
| माप           | JSON स्ट्रिंग      | दिए गए ग्राहक के लिए माप नाम और मानों के लिए कुंजी मान जोड़े की एक सूची शामिल है | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ग्राहक प्रोफ़ाइल ID |


### <a name="enrichment"></a>संवर्द्धन

इस तालिका में संवर्धन प्रक्रिया का आउटपुट है.

| Column               | प्रकार             |  विवरण                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | ग्राहक प्रोफ़ाइल ID                                 |
| EnrichmentProvider   | String           | संवर्धन के लिए प्रदाता का नाम                                  |
| EnrichmentType       | String           | संवर्धन का प्रकार                                      |
| मान               | JSON स्ट्रिंग      | संवर्धन प्रक्रिया द्वारा निर्मित एट्रिब्यूट की सूची |
| msdynci_enrichmentid | GUID             | msdynci_identifier से जनरेट किया गया निर्धारणात्मक GUID |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>पूर्वानुमान

इस तालिका में मॉडल पूर्वानुमानों का आउटपुट है.

| Column               | प्रकार        | विवरण                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ग्राहक प्रोफ़ाइल ID                                  |
| ModelProvider        | String      | मॉडल के प्रदाता का नाम                                      |
| मॉडल                | String      | मॉडल का नाम                                                |
| मान               | JSON स्ट्रिंग | मॉडल द्वारा निर्मित एट्रिब्यूट की सूची |
| msdynci_predictionid | GUID        | msdynci_identifier से जनरेट किया गया निर्धारणात्मक GUID | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |
