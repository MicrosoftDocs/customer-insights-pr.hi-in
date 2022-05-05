---
title: समर्थित पूर्वानुमान परिदृश्यों का अवलोकन
description: पूर्वानुमान परिदृश्य और विकल्प Dynamics 365 Customer Insights अनुप्रयोग द्वारा कवर किए गए हैं.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642934"
---
# <a name="predictions-overview"></a>पूर्वानुमानों का अवलोकन

Dynamics 365 Customer Insights, डेटा का पूर्वानुमान करने के लिए AI और मशीन लर्निंग का लाभ उठाने वाले विभिन्न विकल्पों के साथ आता है. 

## <a name="out-of-box-models"></a>आउट ऑफ बॉक्स मॉडल

डेटा का पूर्वानुमान शुरू करने का सबसे आसान तरीका पूर्वनिर्धारित मॉडल हैं, जिन्हें अक्सर आउट-ऑफ-बॉक्स मॉडल कहा जाता है. इनसाइट जनरेट करने के लिए उन्हें केवल कुछ डेटा और संरचना की आवश्यकता होती है. फिलहाल, निम्नलिखित मॉडल उपलब्ध हैं: 

# <a name="individual-consumers-b-to-c"></a>[व्यक्तिगत उपभोक्ता (B-टू-C)](#tab/b2c)

- [ग्राहक जीवनकाल मान](predict-customer-lifetime-value.md): किसी व्यवसाय के साथ संपूर्ण सहभागिता के दौरान ग्राहक के संभावित राजस्व का का पूर्वानुमान लगाता है.
- [उत्पाद अनुशंसा](predict-product-recommendation.md): खरीद व्यवहार और समान खरीद पैटर्न वाले ग्राहकों के आधार पर पूर्वानुमानित उत्पाद अनुशंसाओं के सेट का सुझाव देता है.
- [सदस्यता चर्न](predict-subscription-churn.md): पूर्वनुमान लगाता है कि कहीं ग्राहक द्वारा आपकी कंपनी के सदस्यता उत्पादों या सेवाओं का उपयोग बंद करने का खतरा तो नहीं है.
- [लेन-देन चर्न](predict-transactional-churn.md): पूर्वानुमान लगाता है कि क्या ग्राहक द्वारा आपके उत्पादों या सेवाओं को किसी निश्चित समयसीमा में नहीं खरीदेगा.
- [भावनाओं का विश्लेषण](sentiment-analysis.md) : ग्राहक प्रतिक्रिया की भावना का विश्लेषण करें और उन व्यावसायिक पहलुओं की पहचान करें जिनका अक्सर उल्लेख किया जाता है।

# <a name="business-accounts-b-to-b"></a>[व्यावसायिक खाते (B-टू-B)](#tab/b2b)

- [लेन-देन चर्न](predict-transactional-churn.md): पूर्वानुमान लगाता है कि क्या ग्राहक द्वारा आपके उत्पादों या सेवाओं को किसी निश्चित समयसीमा में नहीं खरीदेगा.

---

> [!TIP]
> हम अनुशंसा करते हैं कि आप अद्यतन डेटा के साथ आउट-ऑफ़-द-बॉक्स मॉडल को नियमित रूप से रीफ़्रेश करें ताकि यह सुनिश्चित हो सके कि वे आपके व्यावसायिक उपयोग के मामले की सही-सही जानकारी देते हैं। जब सिस्टम नए या अपडेट किए गए डेटा स्रोतों को अंतर्ग्रहीत करता है तो डेटा को एड-हॉक रीफ़्रेश किया जाता है। हालांकि, मॉडल केवल इस मामले में फिर से स्कोर करेंगे और मौजूदा प्रशिक्षण डेटा का उपयोग करना जारी रखेंगे।
> 
> आप एक कॉन्फ़िगर कर सकते हैं **शेड्यूल अपडेट करें** कॉन्फ़िगरेशन अनुभव में मॉडल रीट्रेनिंग शेड्यूल सेट करके। मॉडल इस शेड्यूल पर फिर से प्रशिक्षित और पुन: स्कोर करेगा, जिसे आप किसी भी समय बदल सकते हैं।


## <a name="azure-machine-learning-integration"></a>Azure मशीन लर्निंग एकीकरण

यदि कोई संगठन पहले से ही Azure मशीन लर्निंग प्रयोगों के आधार पर मशीन लर्निंग परिदृश्यों का उपयोग करता है, तो Customer Insights में कस्टम मॉडल सुविधा बिंदुओं को जोड़ने में मदद करती है. ऐसे कार्यप्रवाह बनाएं जो आपको वह डेटा चुनने में मदद करें जिससे आप इनसाइट जनरेट करना चाहते हैं और परिणामों को अपनी एकीकृत ग्राहक प्रोफ़ाइल में मैप करें. अधिक जानकारी के लिए, [कस्टम मशीन लर्निंग मॉडल](custom-models.md) देखें.

## <a name="ai-builder-prediction"></a>AI Builder पूर्वानुमान

कभी-कभी, डेटा सेट अधूरे होते हैं और कुछ मान गायब होते हैं. Customer Insights, ग्राहक निकाय और अनुभागों के लिए अनुपलब्ध मानों का पूर्वानुमान करने में मदद कर सकती हैं. अधिक जानकारी के लिए, [पूर्वानुमानों के साथ अपना आंशिक डेटा पूरा करें](predictions.md) देखें.