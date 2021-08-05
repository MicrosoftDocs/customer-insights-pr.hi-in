---
title: सामान्य डेटा मॉडल में Customer Insights निकाय स्कीमा
description: सामान्य डेटा मॉडल में निकायों के साथ काम करें.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: e21f8a9422357fbc5c9425f91f3ba241c9dec9d8
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692307"
---
# <a name="entity-schemas-in-common-data-model"></a>सामान्य डेटा मॉडल में निकाय स्कीमा

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[सामान्य डेटा मॉडल](/common-data-model/) एक घोषणात्मक विनिर्देश है, और मानक निकायों की एक परिभाषा है जो व्यापार और उत्पादकता अनुप्रयोगों में आमतौर पर उपयोग की जाने वाली अवधारणाओं और गतिविधियों का प्रतिनिधित्व करती है. इस मॉडल को पर्यवेक्षीय और विश्लेषणात्मक डेटा के लिए भी विस्तारित किया जा रहा है. सामान्य डेटा मॉडल पूर्णतः स्पष्ट, मॉड्यूलर, और विस्तारणीय व्यापारिक निकाय—जैसे खाता, व्यवसाय इकाई, केस, संपर्क, लीड, अवसर और उत्पाद—साथ ही विक्रेताओं, श्रमिकों और ग्राहकों के साथ संवाद - जैसे गतिविधियाँ और सेवा स्तर के समझौते प्रदान करता है. कोई भी व्यक्ति व्यवसाय विशिष्ट अतिरिक्त विचार प्राप्त करने के लिए इस सामान्य डेटा मॉडल परिभाषाओं को बना सकते हैं और उन्हें विस्तारित कर सकते हैं.

यह साझा किया गया डेटा मॉडल, अनुप्रयोगों और डेटा एकीकरणों को डेटा की एकीकृत परिभाषा प्रदान करके ज़्यादा आसानी से सहयोग करने की अनुमति देता है. सामान्य डेटा मॉडल में मानक निकाय, संबंधों, पदानुक्रम, लक्षण और बहुत कुछ के साथ एक समृद्ध मेटाडेटा प्रणाली शामिल है. इसकी शुरुआत Dynamics 365 अनुप्रयोग से हुई है और यह 260 से अधिक मानक निकायों के साथ GitHub पर खुला स्रोत होता है. आंतरिक और बाहरी साझेदारों का एक बड़ा सिस्टम इस सामान्य डेटा मॉडल में उद्योग-विशिष्ट संकल्पनाएँ सृजित करता है.

आज Power BI डेटाप्रवाह और Azure डेटा सेवाएँ सहित अनेक प्रणालियों और प्लेटफार्म में सामान्य डेटा मॉडल को कार्यान्वित किया जाता है. यह पहले से ही [ओपन डेटा इनिशिएटिव](https://www.microsoft.com/open-data-initiative) के लिए सीधे मूल्य अर्जित करते हुए, Microsoft Dataverse, Dynamics 365, Power Apps, Power BI और आगामी Azure डेटा सेवाओं में समर्थित है.

## <a name="customer-insights-entity-schemas"></a>Customer Insights निकाय स्कीमा

ग्राहक के 360-डिग्री दृश्य को स्थापित करने और Customer Insights मॉडल को सामान्य डेटा मॉडल में विस्तारण उपलब्ध कराने के लिए, हमने निम्नलिखित निकाय स्कीमा प्रकाशित किए हैं:

| निकाय | वर्णन |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | प्रयोक्ता द्वारा किया गया कार्य जिसका व्यवसाय के लिए उल्लेखनीय मूल्य हो. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | कोई व्यक्ति या संगठन जिसने अच्छा कार्य-निष्पादन किया हो, या जिसमें व्यावसायिक कार्य करने की अच्छी संभावना हो. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | शून्य या इससे अधिक परिमापों द्वारा विभाजित KPI की परिभाषा (जैसे मासिक सक्रिय प्रयोक्ता, ग्राहक का कुल खर्च, ग्राहक की औसत अर्जन लागत) |
|[अनुभाग](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | सामान्य लक्षणों वाले सदस्यों के समूह को परिभाषित करता है. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | किसी दिए गए खंड में भाग लेने वाले सदस्य. |

अधिक जानकारी के लिए [सामान्य डेटा मॉडल में निकाय की योजना के बारे में Customer Insights](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview) संबंधी दस्तावेज देखें.

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>सामान्य डेटा मॉडल निकाय नेविगेटर का उपयोग करते हुए निकायों को देखें

आप [सामान्य डेटा मॉडल निकाय नेविगेटर](https://microsoft.github.io/CDM/) में निकायों को देख सकते हैं. **GitHub! से लोड करें** को चुनें बटन चुनें और उसे **foundationCommon** > **crmCommon** > **समाधान** > **customerInsights** में ले जाएँ जहाँ आपको निकायों के बारे में Customer Insights और उनकी परिभाषाएँ मिलेंगी.
> [!div class="mx-imgBorder"]
> ![निकाय CustomerActivity कार्य दिखाने वाला CDM निकाय नेविगेटर.](media/CDM-entity-navigator.png "निकाय CustomerActivity कार्य दिखाने वाला CDM निकाय नेविगेटर")


[!INCLUDE[footer-include](../includes/footer-banner.md)]