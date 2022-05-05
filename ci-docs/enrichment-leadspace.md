---
title: थर्ड पार्टी एनरिचमेंट Leadspace के साथ कंपनी प्रोफाइल का एनरिचमेंट
description: Leadspace थर्ड पार्टी एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 08a4c56eb1c387015fd9e985a0c9484a13236fcf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642722"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Leadspace के साथ कंपनी प्रोफाइल का समृद्धि (पूर्वावलोकन)

लीडस्पेस एक डेटा साइंस कंपनी है, जो B-से-B ग्राहक डेटा प्लेटफ़ॉर्म प्रदान करती है. यह खातों के अनुसार उनके डेटा को समृद्ध करने के लिए एकीकृत ग्राहक प्रोफ़ाइल वाले परिवेश को समर्थ बनाता है. कंपनी साइज़, स्थान या उद्योग जैसे एट्रिब्यूट्स से *ग्राहक प्रोफ़ाइल* को समृद्ध करें. शीर्षक, पर्सोना या ईमेल सत्यापन जैसे एट्रिब्यूट्स से *संपर्क प्रोफ़ाइल* समृद्ध करें.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

Leadspace को कॉन्फ़िगर करने के लिए, निम्नलिखित आवश्यक शर्तें पूरी की जानी चाहिए:

- आपके पास एक सक्रिय लीडस्पेस लाइसेंस है.
- आपके पास खातों के अनुसार [एकीकृत ग्राहक प्रोफ़ाइल](customer-profiles.md) है.
- एक लीडस्पेस कनेक्शन को पहले ही किसी व्यवस्थापक द्वारा कॉन्फ़िगर किया जा चुका है या आपके पास [व्यवस्थापक](permissions.md#admin) अनुमतियां और "सतत कुंजी" (जिसे **लीडस्पेस टोकन**) कहा जाता है है. अपने प्रोडक्ट के बारे में विवरण के लिए [लीडस्पेस](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) से सीधे संपर्क करें.

## <a name="configure-the-enrichment"></a>एनरिचमेंट को कॉन्फ़िगर करें

1. **डेटा** > **संवर्धन** पर जाएँ.

1. लीडस्पेस टाइल पर **मेरे डेटा को समृद्ध करें** को चुनें और **शुरू करें** का चयन करें.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace टाइल का स्क्रीनशॉट.":::

1. ड्राप-डाउन सूची से [कनेक्शन](connections.md) चुनें। यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें. यदि आप एक व्यवस्थापक हैं, तो आप **कनेक्शन जोड़ें** का चयन करके और **लीडस्पेस** का चयन करके एक कनेक्शन बना सकते हैं. 

1. कनेक्शन की पुष्टि करने के लिए **लीडस्पेस से कनेक्ट करें** चुनें.

1. **अगला** चुनें और उस **ग्राहक डेटा सेट** को चुनें जिसे आप लीडस्पेस से कंपनी डेटा के साथ समृद्ध करना चाहते हैं. आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए **ग्राहक** निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="ग्राहक डेटा सेट चुनते समय का स्क्रीनशॉट.":::

1. **अगला** चुनें और परिभाषित करें कि आपके एकीकृत प्रोफ़ाइल से किन फ़ील्ड का उपयोग लीडस्पेस से कंपनी डेटा का मिलान करने के लिए किया जाता है. **कंपनी का नाम** फ़ील्ड की आवश्यकता है. एक उच्च मिलान सटीकता के लिए, दो अन्य फ़ील्डों तक, **कंपनी की वेबसाइट** और **कंपनी का स्थान**, जोड़ा जा सकता है.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace फील्ड-मैपिंग फलक.":::

1. फील्ड मैपिंग को पूरा करने के लिए **अगला** चुनें.

1. अगर अपनी *संपर्क प्रोफ़ाइल* समृद्ध करना चाहते हैं, तो चेकबॉक्स का चयन करें. Customer Insights आवश्यक फ़ील्ड को स्वचालित रूप से मैप कर देगा।

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="लीडस्पेस संपर्क रिकॉर्ड संवर्धन.":::
 
1. संवर्धन के लिए एक नाम प्रदान करें और अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** का चयन करें.


## <a name="configure-the-connection-for-leadspace"></a>Leadspace के लिए कनेक्शन को कॉन्फ़िगर करें 

आपको कनेक्शन को कॉन्फ़िगर करने के लिए एक व्यवस्थापक होना चाहिए. किसी संवर्धन को कॉन्फ़िगर करते समय **कनेक्शन जोड़ें** का चयन करें *या* **व्यवस्थापक** > **कनेक्शन** पर जाएं और Leadspace टाइल पर **सेट करें** का चयन करें.

1. **आरंभ करें** चुनें. 

1. **डिस्प्ले नाम** बॉक्स में कनेक्शन के लिए एक नाम दर्ज करें.

1. अपना Leadspace टोकन प्रदान करें.

1. **मैं सहमत हूं** चयन करके **डेटा गोपनीयता और अनुपालन** की समीक्षा करें और इसके लिए अपनी सहमति प्रदान करें।

1. कॉन्फ़िगरेशन को मान्य करने के लिए **सत्यापित** चुनें.

1. सत्यापन पूरा करने के बाद, **सहेजें** चुनें.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace कनेक्शन कॉन्फ़िगरेशन पृष्ठ.":::

## <a name="enrichment-results"></a>संवर्धन के परिणाम

संवर्धन को रिफ्रेश करने के बाद, आप [मेरे संवर्धन](enrichment-hub.md) के तहत नया संवर्धित कंपनी डेटा की समीक्षा कर सकते हैं. आप अंतिम अपडेट का समय और समृद्ध प्रोफाइल की संख्या पा सकते हैं.

आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.

अधिक जानकारी के लिए, [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API) देखें.

## <a name="next-steps"></a>अगले कदम


[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को Leadspace पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं. Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Leadspace आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.
आपका Dynamics 365 Customer Insights व्यवस्थापक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस संवर्धन को हटा सकता है.


[!INCLUDE [footer-include](includes/footer-banner.md)]