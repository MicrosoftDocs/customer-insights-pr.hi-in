---
title: समर्थित पूर्वानुमान परिदृश्यों का अवलोकन
description: पूर्वानुमान परिदृश्य और विकल्प Dynamics 365 Customer Insights अनुप्रयोग द्वारा कवर किए गए हैं.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 57c61895d636273fc90a0ac5a942fd0c9abf583c687ae20621949554e581cdf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036011"
---
# <a name="predictions-overview"></a>पूर्वानुमानों का अवलोकन

Dynamics 365 Customer Insights, डेटा का पूर्वानुमान करने के लिए AI और मशीन लर्निंग का लाभ उठाने वाले विभिन्न विकल्पों के साथ आता है. 

## <a name="out-of-box-models"></a>आउट ऑफ बॉक्स मॉडल

डेटा का पूर्वानुमान शुरू करने का सबसे आसान तरीका पूर्वनिर्धारित मॉडल हैं, जिन्हें अक्सर आउट-ऑफ-बॉक्स मॉडल कहा जाता है. इनसाइट जनरेट करने के लिए उन्हें केवल कुछ डेटा और संरचना की आवश्यकता होती है. फिलहाल, निम्नलिखित मॉडल उपलब्ध हैं: 
- [ग्राहक जीवनकाल मान](predict-customer-lifetime-value.md): किसी व्यवसाय के साथ संपूर्ण सहभागिता के दौरान ग्राहक के संभावित राजस्व का का पूर्वानुमान लगाता है. 
- [उत्पाद अनुशंसा](predict-product-recommendation.md): खरीद व्यवहार और समान खरीद पैटर्न वाले ग्राहकों के आधार पर पूर्वानुमानित उत्पाद अनुशंसाओं के सेट का सुझाव देता है.
- [सदस्यता चर्न](predict-subscription-churn.md): पूर्वनुमान लगाता है कि कहीं ग्राहक द्वारा आपकी कंपनी के सदस्यता उत्पादों या सेवाओं का उपयोग बंद करने का खतरा तो नहीं है.
- [लेन-देन चर्न](predict-transactional-churn.md): पूर्वानुमान लगाता है कि क्या ग्राहक द्वारा आपके उत्पादों या सेवाओं को किसी निश्चित समयसीमा में नहीं खरीदेगा.

## <a name="azure-machine-learning-integration"></a>Azure मशीन लर्निंग एकीकरण

यदि कोई संगठन पहले से ही Azure मशीन लर्निंग प्रयोगों के आधार पर मशीन लर्निंग परिदृश्यों का उपयोग करता है, तो Customer Insights में कस्टम मॉडल सुविधा बिंदुओं को जोड़ने में मदद करती है. ऐसे कार्यप्रवाह बनाएं जो आपको वह डेटा चुनने में मदद करें जिससे आप इनसाइट जनरेट करना चाहते हैं और परिणामों को अपनी एकीकृत ग्राहक प्रोफ़ाइल में मैप करें. अधिक जानकारी के लिए, [कस्टम मशीन लर्निंग मॉडल](custom-models.md) देखें.

## <a name="ai-builder-prediction"></a>AI Builder पूर्वानुमान

कभी-कभी, डेटा सेट अधूरे होते हैं और कुछ मान गायब होते हैं. Customer Insights, ग्राहक निकाय और अनुभागों के लिए अनुपलब्ध मानों का पूर्वानुमान करने में मदद कर सकती हैं. अधिक जानकारी के लिए, [पूर्वानुमानों के साथ अपना आंशिक डेटा पूरा करें](predictions.md) देखें.