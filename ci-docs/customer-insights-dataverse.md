---
title: Microsoft Dataverse में Customer Insights डेटा के साथ कार्य करें
description: Customer Insights को जोड़ने का तरीका जानें और Microsoft Dataverse और उन आउटपुट संस्थाओं को समझें जिन्हें निर्यात किया जाता है।Dataverse
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 252723b8c174cb1ec488388c26fd2a1d398e9002
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011522"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse में Customer Insights डेटा के साथ कार्य करें

Customer Insights आउटपुट संस्थाओं को के रूप में उपलब्ध कराने का विकल्प प्रदान करता है।[Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) यह एकीकरण कम कोड/कोई कोड दृष्टिकोण के माध्यम से आसान डेटा साझाकरण और कस्टम विकास को सक्षम बनाता है। [आउटपुट संस्थाएं](#output-entities) तालिका के रूप में उपलब्ध हैं a Dataverse वातावरण। आप के आधार पर किसी अन्य एप्लिकेशन के लिए डेटा का उपयोग कर सकते हैं Dataverse टेबल। ये तालिकाएं . के माध्यम से स्वचालित कार्यप्रवाह जैसे परिदृश्यों को सक्षम करती हैं Power Automate याPower Apps.

अपने से जुड़ रहा है Dataverse पर्यावरण भी आपको सक्षम बनाता है [ऑन-प्रिमाइसेस डेटा स्रोतों का उपयोग करके डेटा निगलनाPower Platform डेटा प्रवाह और गेटवे](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- ग्राहक अंतर्दृष्टि और Dataverse परिवेशों को उसी क्षेत्र में होस्ट किया जाना चाहिए।
- इसमें आपकी वैश्विक व्यवस्थापक भूमिका होनी चाहिए Dataverse वातावरण। सत्यापित करें कि क्या यह [Dataverse पर्यावरण जुड़ा हुआ है](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) कुछ सुरक्षा समूहों के लिए और सुनिश्चित करें कि आपको उन सुरक्षा समूहों में जोड़ा गया है।
- कोई अन्य Customer Insights परिवेश पहले से इससे संबद्ध नहीं है Dataverse पर्यावरण जिसे आप कनेक्ट करना चाहते हैं। करना सीखें [a . से मौजूदा कनेक्शन को हटा दें Dataverse वातावरण](#remove-an-existing-connection-to-a-dataverse-environment).
- ए Microsoft Dataverse परिवेश केवल एक संग्रहण खाते से कनेक्ट हो सकता है। यह तभी लागू होता है जब आप परिवेश को इसमें कॉन्फ़िगर करते हैं [अपना उपयोग करें Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>कनेक्ट a Dataverse ग्राहक अंतर्दृष्टि के लिए पर्यावरण

**Microsoft Dataverse** चरण आपको Customer Insights को अपने से कनेक्ट करने देता है Dataverse पर्यावरण जबकि[Customer Insights वातावरण बनाना](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="के साथ डेटा साझा करनाMicrosoft Dataverse शुद्ध नए वातावरण के लिए स्वत: सक्षम।":::

व्यवस्थापक किसी मौजूदा को जोड़ने के लिए Customer Insights को कॉन्फ़िगर कर सकते हैं Dataverse वातावरण। को URL प्रदान करके Dataverse परिवेश, यह उनके नए Customer Insights परिवेश से जुड़ रहा है।

यदि आप किसी मौजूदा का उपयोग नहीं करना चाहते हैं Dataverse परिवेश में, सिस्टम आपके टैनेंट में Customer Insights डेटा के लिए एक नया परिवेश बनाता है। [Power Platform व्यवस्थापक नियंत्रित कर सकते हैं कि कौन वातावरण बना सकता है](/power-platform/admin/control-environment-creation). जब आप एक नया Customer Insights परिवेश सेट कर रहे हों और व्यवस्थापक ने के निर्माण को अक्षम कर दिया होDataverse व्यवस्थापकों को छोड़कर सभी के लिए परिवेश, आप एक नया परिवेश बनाने में सक्षम नहीं हो सकते हैं।

**डेटा साझाकरण सक्षम करें** साथ Dataverse डेटा साझाकरण चेकबॉक्स का चयन करके।

यदि आप अपने स्वयं के डेटा लेक संग्रहण खाते का उपयोग कर रहे हैं, तो आपको इसकी भी आवश्यकता होगी**अनुमतियाँ पहचानकर्ता**. अधिक जानकारी के लिए अनुमति पहचानकर्ता कैसे प्राप्त करें, निम्न अनुभाग की समीक्षा करें।

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>के साथ डेटा साझाकरण सक्षम करें Dataverse अपने से Azure Data Lake Storage (पूर्वावलोकन)

के साथ डेटा साझाकरण सक्षम करनाMicrosoft Dataverse जब आपका वातावरण [अपना उपयोग करता है Azure Data Lake Storage खाता](own-data-lake-storage.md) कुछ अतिरिक्त विन्यास की जरूरत है। Customer Insights परिवेश को सेट करने वाले उपयोगकर्ता के पास कम से कम **संग्रहण ब्लॉब डेटा रीडर** पर अनुमतियाँ *ग्राहकों की अंतर्दृष्टि* में कंटेनर Azure Data Lake Storage खाता।

1. अपनी Azure सदस्यता पर दो सुरक्षा समूह बनाएँ - एक **रीडर** सुरक्षा समूह और एक **सहयोगी** सुरक्षा समूह और सेट करें Microsoft Dataverse दोनों सुरक्षा समूहों के लिए स्वामी के रूप में सेवा।
2. इन सुरक्षा समूहों के माध्यम से अपने संग्रहण खाते में CustomerInsights कंटेनर पर एक्सेस कंट्रोल लिस्ट (ACL) प्रबंधित करें। जोड़ें Microsoft Dataverse सेवा और कोई भीDataverse -आधारित व्यावसायिक अनुप्रयोग जैसे Dynamics 365 Marketing to the **रीडर** के साथ सुरक्षा समूह **केवल पढ़ने के लिए** अनुमतियाँ। जोड़ें *केवल* के लिए Customers Insights आवेदन **सहयोगी** दोनों को अनुदान देने के लिए सुरक्षा समूह **पढ़ें और लिखें** प्रोफाइल और अंतर्दृष्टि लिखने की अनुमति।

### <a name="limitations"></a>सीमाएँ

उपयोग करते समय दो सीमाएँ हैं Dataverse अपनों के साथ Azure Data Lake Storage खाता:

- A . के बीच वन-टू-वन मैपिंग है Dataverse संगठन और एक Azure Data Lake Storage खाता। एक बार Dataverse संगठन किसी संग्रहण खाते से कनेक्ट है, यह किसी अन्य संग्रहण खाते से कनेक्ट नहीं हो सकता है। यह सीमा रोकता है कि a Dataverse एकाधिक संग्रहण खातों को पॉप्युलेट नहीं करता है।
- यदि आपकी पहुंच तक पहुंचने के लिए Azure निजी लिंक सेटअप की आवश्यकता है, तो डेटा साझाकरण कार्य नहीं करेगाAzure Data Lake Storage खाता क्योंकि यह फ़ायरवॉल के पीछे है। Dataverse वर्तमान में निजी लिंक के माध्यम से निजी समापन बिंदुओं से कनेक्शन का समर्थन नहीं करता है।

### <a name="set-up-powershell"></a>पावरशेल सेट करें

पावरशेल स्क्रिप्ट को निष्पादित करने के लिए, आपको सबसे पहले पावरशेल को तदनुसार सेट करना होगा।

1. का नवीनतम संस्करण स्थापित करें [Azure Active Directory ग्राफ के लिए पावरशेल](/powershell/azure/active-directory/install-adv2).
   1. अपने PC पर, अपने कीबोर्ड पर Windows बटन का चयन करें और **Windows PowerShell** खोजें और **व्यवस्थापक के रूप में चलाएं** चुनें.
   1. खुले PowerShell विंडो में, `Install-Module AzureAD` दर्ज करें.
2. तीन मॉड्यूल आयात करें।
    1. पावरशेल विंडो में, दर्ज करें`Install-Module -Name Az.Accounts` और चरणों का पालन करें।
    1. के लिए दोहराएँ`Install-Module -Name Az.Resources` तथा`Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>कॉन्फ़िगरेशन के चरण

1. हमारे इंजीनियर से चलाने के लिए आवश्यक दो पावरशेल स्क्रिप्ट डाउनलोड करें [गिटहब रेपो](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - आप की जरूरत है *किरायेदार व्यवस्थापक* इस पॉवरशेल स्क्रिप्ट को चलाने की अनुमति।
       - यह पॉवरशेल स्क्रिप्ट आपकी Azure सदस्यता पर दो सुरक्षा समूह बनाती है। एक रीडर समूह के लिए और दूसरा सहयोगी समूह के लिए और Microsoft Dataverse इन दोनों सुरक्षा समूहों के स्वामी के रूप में सेवा।
       - Azure सदस्यता आईडी प्रदान करके Windows PowerShell में इस PowerShell स्क्रिप्ट को निष्पादित करें जिसमें आपकाAzure Data Lake Storage. अतिरिक्त जानकारी और लागू किए गए तर्क की समीक्षा करने के लिए एक संपादक में पावरशेल स्क्रिप्ट खोलें।
       - इस स्क्रिप्ट द्वारा उत्पन्न दोनों सुरक्षा समूह आईडी मान सहेजें क्योंकि हम उनका उपयोग करेंगे`ByolSetup.ps1` लिखी हुई कहानी।

        > [!NOTE]
        > आपके टैनेंट पर सुरक्षा समूह निर्माण अक्षम किया जा सकता है। उस स्थिति में, एक मैन्युअल सेटअप की आवश्यकता होगी और आपकाAzure AD व्यवस्थापक को करना होगा[सुरक्षा समूह निर्माण सक्षम करें](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - आप की जरूरत है *संग्रहण ब्लॉब डेटा स्वामी* इस स्क्रिप्ट को चलाने के लिए स्टोरेज अकाउंट/कंटेनर स्तर पर अनुमतियां या यह स्क्रिप्ट आपके लिए एक बनाएगी। स्क्रिप्ट को सफलतापूर्वक चलाने के बाद आपका भूमिका असाइनमेंट मैन्युअल रूप से हटाया जा सकता है।
        - यह पॉवरशेल स्क्रिप्ट इसके लिए आवश्यक टोल-आधारित एक्सेस कंट्रोल (RBAC) जोड़ती है Microsoft Dataverse सेवा और कोई भीDataverse -आधारित व्यावसायिक अनुप्रयोग। यह इसके साथ बनाए गए सुरक्षा समूहों के लिए CustomerInsights कंटेनर पर एक्सेस कंट्रोल लिस्ट (ACL) को भी अपडेट करता है`CreateSecurityGroups.ps1` लिखी हुई कहानी। सहयोगी समूह के पास होगा*आरडब्ल्यूएक्स* अनुमति और पाठक समूह के पास होगा*आरएक्स* केवल अनुमति।
        - Azure सदस्यता आईडी प्रदान करके Windows PowerShell में इस PowerShell स्क्रिप्ट को निष्पादित करें जिसमें आपकाAzure Data Lake Storage, भंडारण खाता नाम, संसाधन समूह का नाम, और रीडर और सहयोगी सुरक्षा समूह आईडी मान। अतिरिक्त जानकारी और लागू किए गए तर्क की समीक्षा करने के लिए एक संपादक में पावरशेल स्क्रिप्ट खोलें।
        - स्क्रिप्ट को सफलतापूर्वक चलाने के बाद आउटपुट स्ट्रिंग को कॉपी करें। आउटपुट स्ट्रिंग इस तरह दिखती है:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. ऊपर से कॉपी की गई आउटपुट स्ट्रिंग को दर्ज करें **अनुमतियाँ पहचानकर्ता** पर्यावरण कॉन्फ़िगरेशन चरण का क्षेत्र Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="अपने स्वयं के डेटा साझाकरण को सक्षम करने के लिए कॉन्फ़िगरेशन विकल्प Azure Data Lake Storage साथ Microsoft Dataverse .":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>A . से मौजूदा कनेक्शन निकालें Dataverse वातावरण

A . से कनेक्ट करते समय Dataverse पर्यावरण, त्रुटि संदेश **यह CDS संगठन पहले से ही किसी अन्य Customer Insights उदाहरण से जुड़ा हुआ है** इसका मतलब है किDataverse पर्यावरण का पहले से ही Customer Insights परिवेश में उपयोग किया जा रहा है। आप मौजूदा कनेक्शन को वैश्विक व्यवस्थापक के रूप में हटा सकते हैं Dataverse वातावरण। परिवर्तनों को भरने में कुछ घंटे लग सकते हैं।

1. [Power Apps](https://make.powerapps.com) पर जाएँ.
1. पर्यावरण पिकर से पर्यावरण का चयन करें।
1. के लिए जाओ **समाधान**
1. नाम के समाधान को अनइंस्टॉल या डिलीट करें **Dynamics 365 Customer Insights ग्राहक कार्ड ऐड-इन (पूर्वावलोकन)**.

OR

1. अपनी खोलोDataverse वातावरण।
1. के लिए जाओ **एडवांस सेटिंग** > **समाधान**.
1. अनइंस्टॉल करें **CustomerInsightsCustomerCard** समाधान।

यदि निर्भरता के कारण कनेक्शन को हटाना विफल हो जाता है, तो आपको निर्भरता को भी हटाना होगा। अधिक जानकारी के लिए देखें [निर्भरता हटाना](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>आउटपुट निकाय

Customer Insights से कुछ आउटपुट निकाय तालिका के रूप में उपलब्ध हैं Dataverse. नीचे दिए गए खंड इन तालिकाओं के अपेक्षित स्कीमा का वर्णन करते हैं.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [संवर्द्धन](#enrichment)
- [पूर्वानुमान](#prediction)
- [खंड सदस्यता](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

इस तालिका में Customer Insights से एकीकृत ग्राहक प्रोफ़ाइल शामिल है. एकीकृत ग्राहक प्रोफ़ाइल के लिए स्कीमा डेटा एकीकरण प्रक्रिया में उपयोग की जाने वाली संस्थाओं और विशेषताओं पर निर्भर करती है। एक ग्राहक प्रोफ़ाइल स्कीमा में आमतौर पर [CustomerProfile की कॉमन डेटा मॉडल परिभाषा](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) की विशेषताओं का एक सबसेट होता है.

### <a name="alternatekey"></a>AlternateKey

AlternateKey तालिका में उन निकायों की कुंजियाँ हैं, जिन्होंने एकीकृत प्रक्रिया में भाग लिया था.

|Column  |प्रकार  |विवरण  |
|---------|---------|---------|
|DataSourceName    |String         | डेटा स्रोत का नाम. उदाहरण के लिए: `datasource5`        |
|EntityName        | String        | Customer Insights में निकाय का नाम. उदाहरण के लिए: `contact1`        |
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

### <a name="segment-membership"></a>खंड सदस्यता

इस तालिका में ग्राहक प्रोफाइल की खंड सदस्यता जानकारी है।

| Column        | प्रकार | विवरण                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ग्राहक प्रोफ़ाइल ID        |
| खंड प्रदाता      | String       | ऐप जो सेगमेंट प्रकाशित करता है।      |
| खंड सदस्यता प्रकार | String       | ग्राहक का प्रकार यह खंड सदस्यता रिकॉर्ड। ग्राहक, संपर्क, या खाते जैसे कई प्रकारों का समर्थन करता है। डिफ़ॉल्ट: ग्राहक  |
| सेगमेंट       | JSON स्ट्रिंग  | अद्वितीय खंडों की सूची जिसका ग्राहक प्रोफ़ाइल सदस्य है      |
| msdynci_identifier  | String   | खंड सदस्यता रिकॉर्ड का विशिष्ट पहचानकर्ता। `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | मार्गदर्शक      | से उत्पन्न नियतात्मक GUID`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
