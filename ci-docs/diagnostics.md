---
title: लॉग इन अग्रेषण Dynamics 365 Customer Insights Azure मॉनिटर के साथ (पूर्वावलोकन)
description: यहां लॉग भेजने का तरीका जानें Microsoft Azure निगरानी करना।
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8c72df7054a682244215bbee54968d6aef4bbf59
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052655"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>लॉग इन अग्रेषण Dynamics 365 Customer Insights Azure मॉनिटर के साथ (पूर्वावलोकन)

Dynamics 365 Customer Insights Azure मॉनिटर के साथ एक सीधा एकीकरण प्रदान करता है। Azure मॉनिटर संसाधन लॉग आपको मॉनिटर करने और लॉग भेजने की सुविधा देता है [एज़्योर स्टोरेज](https://azure.microsoft.com/services/storage/),[Azure लॉग एनालिटिक्स](/azure/azure-monitor/logs/log-analytics-overview), या उन्हें स्ट्रीम करें [अज़ूर इवेंट हब](https://azure.microsoft.com/services/event-hubs/).

Customer Insights निम्न इवेंट लॉग भेजता है:

- **लेखापरीक्षा कार्यक्रम**
  - **एपीआईइवेंट** - के माध्यम से किए गए परिवर्तन ट्रैकिंग को सक्षम बनाता है Dynamics 365 Customer Insights यूआई।
- **ऑपरेशनल इवेंट्स**
  - **कार्यप्रवाह घटना** - वर्कफ़्लो आपको सेट करने देता है [डेटा स्रोत](data-sources.md),[यूनिफाई](data-unification.md),[समृद्ध](enrichment-hub.md), और अंत में [निर्यात करना](export-destinations.md) अन्य प्रणालियों में डेटा। उन सभी चरणों को व्यक्तिगत रूप से किया जा सकता है (उदाहरण के लिए, एकल निर्यात को ट्रिगर करें)। ऑर्केस्ट्रेटेड भी चलाया जा सकता है (उदाहरण के लिए, डेटा स्रोतों से डेटा रीफ्रेश जो एकीकरण प्रक्रिया को ट्रिगर करता है, जो संवर्धन में खींचेगा और एक बार डेटा को किसी अन्य सिस्टम में निर्यात करेगा)। अधिक जानकारी के लिए देखें [वर्कफ़्लोइवेंट स्कीमा](#workflow-event-schema).
  - **एपीआईइवेंट** - ग्राहकों को सभी एपीआई कॉल करने के लिए उदाहरण Dynamics 365 Customer Insights. अधिक जानकारी के लिए देखें [एपीआईइवेंट स्कीमा](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>नैदानिक सेटिंग सेट करें

### <a name="prerequisites"></a>पूर्वावश्यकताएँ

Customer Insights में निदान को कॉन्फ़िगर करने के लिए, निम्नलिखित पूर्वापेक्षाएँ पूरी होनी चाहिए:

- आपके पास एक सक्रिय है [Azure सदस्यता](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- आपके पास [प्रशासक](permissions.md#admin) Customer Insights में अनुमतियाँ।
- आपके पास है **सहयोगी** तथा**यूजर एक्सेस एडमिनिस्ट्रेटर** Azure पर गंतव्य संसाधन पर भूमिका। संसाधन एक हो सकता है Azure Data Lake Storage खाता, Azure ईवेंट हब या Azure लॉग एनालिटिक्स कार्यस्थान। अधिक जानकारी के लिए देखें [Azure पोर्टल का उपयोग करके Azure भूमिका असाइनमेंट जोड़ें या निकालें](/azure/role-based-access-control/role-assignments-portal). Customer Insights में नैदानिक सेटिंग्स को कॉन्फ़िगर करते समय यह अनुमति आवश्यक है, इसे सफल सेटअप के बाद बदला जा सकता है।
- [गंतव्य आवश्यकताएं](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) Azure संग्रहण के लिए, Azure Event Hub, या Azure Log Analytics मिले।
- आपके पास कम से कम **रीडर** उस संसाधन समूह पर भूमिका जिससे संसाधन संबंधित है।

### <a name="set-up-diagnostics-with-azure-monitor"></a>Azure मॉनिटर के साथ निदान सेट करें

1. Customer Insights में, चुनें **व्यवस्था** > **निदान** इस उदाहरण को कॉन्फ़िगर किए गए निदान स्थलों को देखने के लिए।

1. चुनना**गंतव्य जोड़ें**.

   > [!div class="mx-imgBorder"]
   > ![निदान कनेक्शन](media/diagnostics-pane.png "निदान कनेक्शन")

1. में एक नाम प्रदान करें **निदान गंतव्य के लिए नाम** खेत।

1. चुनना**किरायेदार** गंतव्य संसाधन के साथ Azure सदस्यता का चयन करें और **लॉग इन करें**.

1. को चुनिए **संसाधन प्रकार** (स्टोरेज अकाउंट, इवेंट हब या लॉग एनालिटिक्स)।

1. को चुनिए **अंशदान** गंतव्य संसाधन के लिए।

1. को चुनिए **संसाधन समूह** गंतव्य संसाधन के लिए।

1. को चुनिए **संसाधन**.

1. पुष्टि**डेटा गोपनीयता और अनुपालन** बयान।

1. चुनना**सिस्टम से कनेक्ट करें** गंतव्य संसाधन से कनेक्ट करने के लिए। यदि एपीआई उपयोग में है और ईवेंट उत्पन्न करता है, तो लॉग 15 मिनट के बाद गंतव्य में दिखाई देने लगते हैं।

### <a name="remove-a-destination"></a>एक गंतव्य निकालें

1. के लिए जाओ **व्यवस्था** > **निदान**.

1. सूची में निदान गंतव्य का चयन करें।

1. में **कार्रवाई** कॉलम, चुनें **मिटाना** चिह्न।

1. लॉग अग्रेषण को रोकने के लिए हटाने की पुष्टि करें। Azure सदस्यता पर संसाधन हटाया नहीं जाएगा। आप में लिंक का चयन कर सकते हैं **कार्रवाई** चयनित संसाधन के लिए Azure पोर्टल खोलने और उसे वहां हटाने के लिए कॉलम।

## <a name="log-categories-and-event-schemas"></a>लॉग श्रेणियां और घटना स्कीमा

वर्तमान में [एपीआई इवेंट](apis.md) और वर्कफ़्लो ईवेंट समर्थित हैं और निम्न श्रेणियां और स्कीमा लागू होते हैं।
लॉग स्कीमा इस प्रकार है [Azure मॉनिटर सामान्य स्कीमा।](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema)

### <a name="categories"></a>श्रेणियाँ

Customer Insights दो श्रेणियां प्रदान करता है:

- **ऑडिट इवेंट्स** :[एपीआई इवेंट](#api-event-schema) सेवा पर कॉन्फ़िगरेशन परिवर्तनों को ट्रैक करने के लिए। `POST|PUT|DELETE|PATCH` संचालन इस श्रेणी में जाते हैं।
- **परिचालन कार्यक्रम** :[एपीआई इवेंट](#api-event-schema) या[वर्कफ़्लो इवेंट](#workflow-event-schema) सेवा का उपयोग करते समय उत्पन्न।  उदाहरण के लिए,`GET` अनुरोध या वर्कफ़्लो के निष्पादन ईवेंट।

## <a name="configuration-on-the-destination-resource"></a>गंतव्य संसाधन पर विन्यास

संसाधन प्रकार पर आपकी पसंद के आधार पर निम्नलिखित चरण स्वचालित रूप से लागू होंगे:

### <a name="storage-account"></a>संग्रहण खाता

Customer Insights सेवा प्रिंसिपल को मिलता है **संग्रहण खाता सहयोगी** चयनित संसाधन पर अनुमति देता है और चयनित नाम स्थान के अंतर्गत दो कंटेनर बनाता है:

- `insight-logs-audit` युक्त **ऑडिट इवेंट्स**
- `insight-logs-operational` युक्त **परिचालन कार्यक्रम**

### <a name="event-hub"></a>इवेंट हब

Customer Insights सेवा प्रिंसिपल को मिलता है **Azure इवेंट हब डेटा स्वामी** संसाधन पर अनुमति और चयनित नाम स्थान के तहत दो इवेंट हब बनाएगा:

- `insight-logs-audit` युक्त **ऑडिट इवेंट्स**
- `insight-logs-operational` युक्त **परिचालन कार्यक्रम**

### <a name="log-analytics"></a>लॉग एनालिटिक्स

Customer Insights सेवा प्रिंसिपल को मिलता है **लॉग एनालिटिक्स सहयोगी** संसाधन पर अनुमति। लॉग के तहत उपलब्ध होंगे **लॉग्स** > **टेबल** > **लॉग प्रबंधन** चयनित लॉग एनालिटिक्स कार्यस्थान पर। इसका विस्तार करें **लॉग प्रबंधन** समाधान और पता लगाएँ`CIEventsAudit` तथा`CIEventsOperational` टेबल।

- `CIEventsAudit` युक्त **ऑडिट इवेंट्स**
- `CIEventsOperational` युक्त **परिचालन कार्यक्रम**

नीचे **प्रश्नों** विंडो, विस्तृत करें **अंकेक्षण** समाधान और खोज के द्वारा प्रदान किए गए उदाहरण प्रश्नों का पता लगाएं`CIEvents`.

## <a name="event-schemas"></a>घटना स्कीमा

API ईवेंट और वर्कफ़्लो ईवेंट में एक समान संरचना और विवरण होते हैं जहाँ वे भिन्न होते हैं, देखें [एपीआई घटना स्कीमा](#api-event-schema) या[वर्कफ़्लो इवेंट स्कीमा](#workflow-event-schema).

### <a name="api-event-schema"></a>एपीआई घटना स्कीमा

| क्षेत्र             | डेटा प्रकार  | आवश्यक/वैकल्पिक | विवरण       | उदाहरण        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | टाइमस्टैंप | आवश्य          | इवेंट का टाइमस्टैम्प (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | आवश्य          | घटना का उत्सर्जन करने वाले उदाहरण का संसाधन आईडी         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | आवश्य          | इस घटना द्वारा दर्शाए गए ऑपरेशन का नाम।                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | आवश्य          | घटना की लॉग श्रेणी। या`Operational` या`Audit`. सभी पोस्ट/पुट/पैच/हटाएं HTTP अनुरोध के साथ टैग किए गए हैं`Audit`, बाकी सब कुछ के साथ`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | आवश्य          | घटना की स्थिति। `Success`,`ClientError`,`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | वैकल्पिक          | घटना के परिणाम की स्थिति। यदि कार्रवाई REST API कॉल से मेल खाती है, तो यह HTTP स्थिति कोड है।        | `200`             |
| `durationMs`      | लंबा      | वैकल्पिक          | मिलीसेकंड में ऑपरेशन की अवधि।     | `133`     |
| `callerIpAddress` | String    | वैकल्पिक          | कॉलर आईपी पता, यदि ऑपरेशन एक एपीआई कॉल से मेल खाता है जो सार्वजनिक रूप से उपलब्ध आईपी पते से आता है।                                                 | `144.318.99.233`         |
| `identity`        | String    | वैकल्पिक          | JSON ऑब्जेक्ट उस उपयोगकर्ता या एप्लिकेशन की पहचान का वर्णन करता है जिसने ऑपरेशन किया था।       | देखना[पहचान](#identity-schema) खंड।     |  
| `properties`      | String    | वैकल्पिक          | घटनाओं की विशेष श्रेणी के लिए अधिक गुणों के साथ JSON ऑब्जेक्ट।      | देखना[गुण](#api-properties-schema) खंड।    |
| `level`           | String    | आवश्य          | घटना की गंभीरता का स्तर।    | `Informational`,`Warning`,`Error`, या`Critical`.           |
| `uri`             | String    | वैकल्पिक          | पूर्ण अनुरोध यूआरआई।    |               |

#### <a name="identity-schema"></a>पहचान स्कीमा

`identity` JSON ऑब्जेक्ट में निम्न संरचना है

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| क्षेत्र                         | विवरण                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | उपयोगकर्ता या ऐप्लिकेशन के लिए असाइन की गई भूमिका. अधिक जानकारी के लिए देखें [उपयोगकर्ता अनुमतियाँ](permissions.md).                                     |
| `Authorization.RequiredRoles` | ऑपरेशन करने के लिए आवश्यक भूमिकाएँ। `Admin` भूमिका सभी कार्यों को करने की अनुमति है।                                                    |
| `Claims`                      | उपयोगकर्ता या ऐप JSON वेब टोकन (JWT) के दावे। दावा गुण प्रति संगठन अलग-अलग होते हैं और Azure Active Directory विन्यास। |

#### <a name="api-properties-schema"></a>एपीआई गुण स्कीमा

[एपीआई इवेंट](apis.md) निम्नलिखित गुण हैं।

| क्षेत्र                        | विवरण                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | हमेशा`ApiEvent`, लॉग इवेंट को API ईवेंट के रूप में चिह्नित करना।                                                                 |
| `properties.userAgent`       | ब्राउज़र एजेंट अनुरोध भेज रहा है या`unknown`.                                                                        |
| `properties.method`          | HTTP विधि:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | अनुरोध का सापेक्ष पथ।                                                                                          |
| `properties.origin`          | URI इंगित करता है कि फ़ेच कहाँ से आता है or `unknown`.                                                                  |
| `properties.operationStatus` | `Success` HTTP स्थिति कोड के लिए <400 <br> `ClientError` HTTP स्थिति कोड के लिए <500 <br> `Error` HTTP स्थिति के लिए>= 500 |
| `properties.tenantId`        | संगठन ID                                                                                                        |
| `properties.tenantName`      | संगठन का नाम।                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory कॉल करने वाले का ऑब्जेक्ट आईडी।                                                                         |
| `properties.instanceId`      | ग्राहकों की अंतर्दृष्टि`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>वर्कफ़्लो इवेंट स्कीमा

वर्कफ़्लो में कई चरण होते हैं। [डेटा स्रोत निगलना](data-sources.md),[यूनिफाई](data-unification.md),[समृद्ध](enrichment-hub.md), तथा[निर्यात करना](export-destinations.md) जानकारी। उन सभी चरणों को व्यक्तिगत रूप से चलाया जा सकता है या निम्नलिखित प्रक्रियाओं के साथ व्यवस्थित किया जा सकता है।

#### <a name="operation-types"></a>ऑपरेशन के प्रकार

| OperationType     | समूह                                     |
| ----------------- | ----------------------------------------- |
| घूस         | [डेटा स्रोत](data-sources.md)           |
| डेटा तैयारी   | [डेटा स्रोत](data-sources.md)           |
| मैप               | [डेटा एकीकरण](data-unification.md)   |
| मिलान             | [डेटा एकीकरण](data-unification.md)   |
| मर्ज करें             | [डेटा एकीकरण](data-unification.md)   |
| प्रोफाइल स्टोर      | [ग्राहक के प्रोफाइल](customer-profiles.md) |
| खोज करें            | [ग्राहक के प्रोफाइल](customer-profiles.md) |
| गतिविधि          | [गतिविधियाँ](activities.md)                  |
| गुण उपाय | [खंड और उपाय](segments.md)      |
| इकाई उपाय    | [खंड और उपाय](segments.md)      |
| माप          | [खंड और उपाय](segments.md)      |
| सेगमेंटेशन      | [खंड और उपाय](segments.md)      |
| संवर्द्धन        | [संवर्द्धन](enrichment-hub.md)                                          |
| इंटेलिजेंस      | [पूर्वानुमान](predictions-overview.md)                                          |
| ऐबिल्डर         | [पूर्वानुमान](predictions-overview.md)                                          |
| इनसाइट्स          | [पूर्वानुमान](predictions-overview.md)                                          |
| Export            | [निर्यात](export-destinations.md)                                          |
| मॉडल प्रबंधन   | [पूर्वानुमान](custom-models.md)                                           |
| संबंध       | [डेटा एकीकरण](relationships.md)                                           |

#### <a name="field-description"></a>क्षेत्र विवरण

| क्षेत्र           | डेटा प्रकार  | आवश्यक/वैकल्पिक | विवरण                                                                                                                                                   | उदाहरण                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | टाइमस्टैंप | आवश्य          | इवेंट का टाइमस्टैम्प (UTC)।                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | आवश्य          | उस घटना का संसाधन आईडी जिसने घटना को उत्सर्जित किया।                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | आवश्य          | इस घटना द्वारा दर्शाए गए ऑपरेशन का नाम। `{OperationType}.[WorkFlow|Task][Started|Completed]`. देखना[ऑपरेशन के प्रकार](#operation-types) संदर्भ के लिए। | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | आवश्य          | घटना की लॉग श्रेणी। हमेशा`Operational` कार्यप्रवाह घटनाओं के लिए                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | आवश्य          | घटना की स्थिति। `Running`,`Skipped`,`Successful`,`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | लंबा      | वैकल्पिक          | मिलीसेकंड में ऑपरेशन की अवधि।                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | वैकल्पिक          | घटनाओं की विशेष श्रेणी के लिए अधिक गुणों के साथ JSON ऑब्जेक्ट।                                                                                        | उप अनुभाग देखें [कार्यप्रवाह गुण](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | आवश्य          | घटना की गंभीरता का स्तर।                                                                                                                                  | `Informational`, `Warning`, या `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>वर्कफ़्लो गुण स्कीमा

वर्कफ़्लो इवेंट में निम्नलिखित गुण होते हैं।

| क्षेत्र              | Workflow | कार्य | विवरण            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | हां      | हां  | हमेशा`WorkflowEvent`, ईवेंट को वर्कफ़्लो ईवेंट के रूप में चिह्नित करना।                                                                                                                                                                                                |
| `properties.workflowJobId`                   | हां      | हां  | कार्यप्रवाह चलाने का पहचानकर्ता। वर्कफ़्लो निष्पादन के भीतर सभी वर्कफ़्लो और कार्य ईवेंट समान हैं`workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | हां      | हां  | ऑपरेशन के पहचानकर्ता, देखें [ऑपरेशन के प्रकार](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | हां      | No   | केवल वर्कफ़्लो। कार्यप्रवाह ट्रिगर करने वाले कार्यों की संख्या।                                                                                                                                                                                                       |
| `properties.submittedBy`                     | हां      | No   | ऑप्शनल. केवल वर्कफ़्लो ईवेंट। Azure Active Directory [उपयोगकर्ता का ऑब्जेक्ट आईडी](/azure/marketplace/find-tenant-object-id#find-user-object-id) वर्कफ़्लो किसने ट्रिगर किया, यह भी देखें`properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | हां      | No   | `full` या`incremental` ताज़ा करें।                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | हां      | No   | `OnDemand` या `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | हां      | No   | `Running` या`Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | हां      | हां  | यूटीसी टाइमस्टैम्प`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | हां      | हां  | यूटीसी टाइमस्टैम्प`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | हां      | हां  | यूटीसी टाइमस्टैम्प`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | हां      | हां  | ग्राहकों की अंतर्दृष्टि`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | हां  | - ऑपरेशन टाइप के लिए =`Export`, पहचानकर्ता निर्यात कॉन्फ़िगरेशन का मार्गदर्शक है। <br> - ऑपरेशन टाइप के लिए =`Enrichment`, यह संवर्धन की मार्गदर्शिका है <br> - ऑपरेशन टाइप के लिए`Measures` तथा`Segmentation`, पहचानकर्ता इकाई का नाम है। |
| `properties.friendlyName`                    | No       | हां  | निर्यात या संसाधित की जाने वाली इकाई का उपयोगकर्ता के अनुकूल नाम।                                                                                                                                                                                           |
| `properties.error`                           | No       | हां  | ऑप्शनल. अधिक विवरण के साथ त्रुटि संदेश।                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | हां  | ऑप्शनल. ऑपरेशन टाइप के लिए`Export` केवल। निर्यात के प्रकार की पहचान करता है। अधिक जानकारी के लिए देखें [निर्यात स्थलों का अवलोकन](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | हां  | ऑप्शनल. ऑपरेशन टाइप के लिए`Export` केवल। निर्यात में कॉन्फ़िगर की गई संस्थाओं की एक सूची शामिल है।                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | हां  | ऑप्शनल. ऑपरेशन टाइप के लिए`Export` केवल। निर्यात के लिए विस्तृत संदेश।                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | हां  | ऑप्शनल. ऑपरेशन टाइप के लिए`Segmentation` केवल। खंड के सदस्यों की कुल संख्या को इंगित करता है।                                                                                                                                                    |
