---
title: Customer Insights API के लिए OData क्वेरी उदाहरण
description: डेटा की समीक्षा करने के लिए Customer Insights API को क्वेरी करने के लिए ओपन डेटा प्रोटोकॉल (OData) के लिए आमतौर पर उपयोग किए जाने वाले उदाहरण।
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8843fc04e4e6eaba0019d932c54f62561ffbdb92
ms.sourcegitcommit: f3c12ad445d5f91a88f91a7bbc40790ebcfaa826
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/06/2022
ms.locfileid: "9121564"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Customer Insights API के लिए OData क्वेरी उदाहरण

ओपन डेटा प्रोटोकॉल (ओडाटा) एक डेटा एक्सेस प्रोटोकॉल है जो HTTP जैसे कोर प्रोटोकॉल पर बनाया गया है। यह वेब के लिए आरईएसटी जैसी सामान्य रूप से स्वीकृत पद्धतियों का उपयोग करता है। विभिन्न प्रकार के पुस्तकालय और उपकरण हैं जिनका उपयोग ओडाटा सेवाओं का उपभोग करने के लिए किया जा सकता है।

इस लेख में कुछ अक्सर अनुरोध किए गए उदाहरण प्रश्नों को सूचीबद्ध किया गया है जो आपको निम्नलिखित के आधार पर अपने स्वयं के कार्यान्वयन के निर्माण में मदद करेंगे [Customer Insights API](apis.md).

लक्षित परिवेशों पर काम करने के लिए आपको क्वेरी नमूनों को संशोधित करना होगा: 

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` कहाँ पे{instanceId} Customer Insights परिवेश का GUID है जिसे आप क्वेरी करना चाहते हैं। [ListAllInstances ऑपरेशन](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) आपको खोजने देता है{InstanceId} आपके पास पहुंच है।
- {CID}: एकीकृत ग्राहक रिकॉर्ड का GUID। उदाहरण: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: डेटा स्रोत में ग्राहक रिकॉर्ड की प्राथमिक कुंजी का पहचानकर्ता। उदाहरण: `CNTID_1002`
- {DSname}: डेटा स्रोत के निकाय नाम वाली स्ट्रिंग जो Customer Insights में समा जाती है। उदाहरण: `Website_contacts`.
- {SegmentName}: Customer Insights में किसी सेगमेंट के आउटपुट निकाय नाम के साथ स्ट्रिंग। उदाहरण: `Male_under_40`.

## <a name="customer"></a>ग्राहक

निम्न तालिका में निम्न के लिए नमूना प्रश्नों का एक सेट है *ग्राहक* कंपनी।

|क्वेरी प्रकार |उदाहरण  | नोट  |
|---------|---------|---------|
|एकल ग्राहक आईडी     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|वैकल्पिक कुंजी    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  एकीकृत ग्राहक इकाई में वैकल्पिक कुंजियाँ बनी रहती हैं       |
|चुनें   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|इसमें    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|वैकल्पिक कुंजी + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|खोज करें  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   खोज स्ट्रिंग के लिए शीर्ष 10 परिणाम देता है      |
|खंड सदस्यता  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | विभाजन निकाय से पंक्तियों की एक पूर्व निर्धारित संख्या देता है।      |
|ग्राहक के लिए खंड सदस्यता | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | ग्राहक प्रोफ़ाइल लौटाता है यदि वे दिए गए सेगमेंट के सदस्य हैं     |

## <a name="unified-activity"></a>एकीकृत गतिविधि

निम्न तालिका में निम्न के लिए नमूना प्रश्नों का एक सेट है *एकीकृत गतिविधि* कंपनी।

|क्वेरी प्रकार |उदाहरण  | नोट  |
|---------|---------|---------|
|सीआईडी की गतिविधि     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | एक विशिष्ट ग्राहक प्रोफ़ाइल की गतिविधियों को सूचीबद्ध करता है |
|गतिविधि अवधि    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  अवधि . में ग्राहक प्रोफ़ाइल की गतिविधियां       |
|गतिविधि का प्रकार    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|प्रदर्शन नाम . द्वारा गतिविधि     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|गतिविधि छँटाई    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  आरोही या अवरोही गतिविधियों को क्रमबद्ध करें       |
|खंड सदस्यता से गतिविधि का विस्तार  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>अन्य उदाहरण

निम्न तालिका में अन्य निकायों के लिए नमूना प्रश्नों का एक सेट है।

|क्वेरी प्रकार |उदाहरण  | नोट  |
|---------|---------|---------|
|सीआईडी के उपाय    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|सीआईडी के समृद्ध ब्रांड    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|सीआईडी के समृद्ध हित    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|इन-क्लॉज + विस्तृत करें     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>समर्थित नहीं OData क्वेरी

निम्न क्वेरी Customer Insights द्वारा समर्थित नहीं हैं:

- `$filter` अंतर्ग्रहण स्रोत संस्थाओं पर। आप $filter क्वेरीज़ केवल उन सिस्टम निकायों पर चला सकते हैं, जिन्हें Customer Insights बनाता है।
- `$expand` एक से`$search` सवाल। उदाहरण: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` से`$select` यदि केवल विशेषताओं का एक सबसेट चुना गया है। उदाहरण: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` किसी दिए गए ग्राहक के लिए समृद्ध ब्रांड या रुचि समानताएं। उदाहरण: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- वैकल्पिक कुंजी के माध्यम से पूर्वानुमान मॉडल आउटपुट इकाइयों को क्वेरी करें। उदाहरण: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
