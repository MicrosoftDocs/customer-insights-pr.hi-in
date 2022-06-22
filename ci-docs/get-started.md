---
title: Dynamics 365 Customer Insights के साथ प्रारंभ करें
description: Customer Insights का अवलोकन संसाधनों को शीघ्रता से आरंभ करने में सहायता करता है।
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011981"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights के साथ प्रारंभ करें

Customer Insights आपको अपने ग्राहकों की गहरी समझ बनाने में मदद कर सकती है। 360 डिग्री ग्राहक दृष्टि तैयार करने के लिए विभिन्न लेनदेन, व्यवहारात्मक और प्रेक्षण करने योग्य स्रोतों से डेटा प्राप्त करें. ग्राहक-केंद्रित अनुभव और प्रक्रियाओं को समझने के लिए इन सूचनाओं का उपयोग करें. ग्राहक डेटा को एकीकृत करें और समझें और बुद्धिमान इन्साइट्स और कार्यों के लिए इसका उपयोग करें.

## <a name="step-1-create-an-environment"></a>चरण 1: परिवेश बनाएँ

सबसे पहले, काम करने के लिए एक माहौल बनाएं। यदि आपके संगठन ने पहले ही लाइसेंस खरीद लिया है, तो [परिवेश बनाएं](create-environment.md) देखें. Customer Insights का परीक्षण शुरू करने के लिए, देखें [एक परीक्षण वातावरण स्थापित करें।](trial-signup.md)

## <a name="step-2-explore-customer-insights"></a>चरण 2: ग्राहक अंतर्दृष्टि का अन्वेषण करें

जब आप पहली बार Customer Insights में लॉग इन करते हैं, तो सेटिंग्स कॉन्फ़िगर करें और उत्पाद को एक्सप्लोर करें।

1. [Customer Insights में लॉग इन करें](https://home.ci.ai.dynamics.com) अपने Microsoft . का उपयोग करनाAzure Active Directory (एएडी) उपयोगकर्ता खाता।

1. डेमो डेटा देखने के लिए परिवेश बदलें और [ग्राहक अंतर्दृष्टि का अन्वेषण करें।](home.md)

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>चरण 3: इंजेस्ट करें, एकीकृत करें और अपने डेटा के लिए संबंध स्थापित करें

एकीकृत प्रोफ़ाइल इनसाइट्स प्राप्त करने और डेटा पर कार्रवाई करने का आधार हैं. विभिन्न स्रोतों से डेटा लेना और एकीकृत प्रोफ़ाइल को जोड़ने के लिए डेटा एकीकरण प्रक्रिया को चलाना. अंतर्ग्रहण निकायों के बीच संबंध निर्दिष्ट करें और प्रोफ़ाइल में जानकारी जोड़ने के लिए संवर्धन सुविधाओं का उपयोग करें।

1. अनेक विकल्पों से डेटा स्रोत बनाकर डेटा अंतर्ग्रहण करें. बीच चयन [Azure Data Lake Storage, सामान्य डेटा मॉडल सहित](connect-common-data-model.md),[Azure Synapse Analytics](connect-synapse.md),[Microsoft Dataverse](connect-dataverse-managed-lake.md), या[Power Query कनेक्टर्स](connect-power-query.md).

1. चलाएँ [डेटा एकीकरण प्रक्रिया](data-unification.md) की पहचान करके [स्रोत फ़ील्ड](map-entities.md), हटाना[डुप्लिकेट](remove-duplicates.md),[मिलान की शर्तें](match-entities.md), तथा[एकीकृत क्षेत्र](merge-entities.md).

1. [वे निकाय जिनको सिस्टम बनाता है](entities.md) से परिचित हों और [अंतर्ग्रहित निकायों के बीच संबंध](relationships.md) बनाएँ.

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>चरण 4: पूर्वानुमानों, गतिविधियों और उपायों के साथ एकीकृत प्रोफ़ाइल को बेहतर बनाएँ

एकीकृत प्रोफ़ाइल सेट अप के साथ, अपना डेटा बढ़ाएं और उनके द्वारा प्रदान की जाने वाली जानकारी को और बढ़ाएं।

1. [अपने ग्राहक डेटा को समृद्ध करें](enrichment-hub.md) के लिए समृद्ध प्रदाताओं की विस्तारित लाइब्रेरी में से चुनें.

1. मंथन की संभावना या अपेक्षित राजस्व का पूर्वानुमान करने के लिए [सबसे अलग मॉडल](predictions-overview.md) का उपयोग करें.

1. अंतर्ग्रहण डेटा के आधार पर [गतिविधियों को कॉन्फ़िगर करें](activities.md) और कालानुक्रमिक टाइमलाइन में अपने ग्राहकों के साथ सहभागिता की विज़ुअलाइज़ करें.

1. अपने व्यावसायिक लक्ष्यों और KPI का आंकलन करने के लिए [उपाय बनाएँ](measures.md).

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>चरण 5: विभिन्न निर्यात विकल्पों के माध्यम से अनुभाग बनाएँ और डेटा सक्रिय करें

अब जब आपका डेटा पूरा हो गया है और इसमें आपके ग्राहकों के बारे में विस्तृत जानकारी है, तो उस डेटा पर कार्रवाई करने के तरीकों की तलाश करें।

1. [अनुभाग बनाएँ](segments.md), आपके ग्राहक आधार के सबसेट, ताकि यह सुनिश्चित किया जा सके कि आपकी कार्रवाई लक्षित ग्राहकों के लिए प्रासंगिक हैं.

1. [निर्यात विकल्प](export-destinations.md) का विस्तृत कैटलॉग ब्राउज़ करें जहां आप ग्राहक डेटा का उपयोग कर सकते हैं. उदाहरण के लिए, आप प्रचार को प्रबंधित करने और डिजिटल मार्केटिंग तक पहुंचने के लिए डेटा का उपयोग कर सकते हैं.

1. एकीकरण विकल्पों की समीक्षा करें, उदाहरण के लिए अन्य Dynamics 365 ऐप के साथ [ग्राहक कार्ड ऐड-इन](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
