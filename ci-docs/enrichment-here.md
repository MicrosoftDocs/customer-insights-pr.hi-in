---
title: HERE टेक्नोलॉजीज के साथ ग्राहक प्रोफाइल को समृद्ध करें (पूर्वावलोकन)
description: HERE Technologies थर्ड पार्टी के एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237860"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>HERE टेक्नोलॉजीज के साथ ग्राहक प्रोफाइल को समृद्ध करें (पूर्वावलोकन)

HERE Technologies एक लोकेशन प्लेटफ़ॉर्म कंपनी है जो स्थान-केंद्रित डेटा और सेवाएं प्रदान करती है. HERE Technologies की डेटा संवर्धन सेवाएँ आपके ग्राहकों के बारे में स्थान जानकारी की सटीकता में सुधार करती हैं। यह पता सामान्यीकरण, अक्षांश और देशांतर निष्कर्षण, और बहुत कुछ प्रदान करता है।

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- एक सक्रिय HERE Technologies सदस्यता। सदस्यता प्राप्त करने के लिए, [पंजी यहॉ करे](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) या[यहां संपर्क करें टेक्नोलॉजीज](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) सीधे। [HERE Technologies लोकेशन एनरिचमेंट के बारे में अधिक जानें.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- एक यहाँ [संबंध](connections.md) है [कॉन्फ़िगर किया गया](#configure-the-connection-for-here-technologies) एक व्यवस्थापक द्वारा।

## <a name="configure-the-connection-for-here-technologies"></a>HERE Technologies के लिए कनेक्शन कॉन्फ़िगर करें

आप एक होना चाहिए [प्रशासक](permissions.md#admin) Customer Insights में और एक सक्रिय HERE Technologies API कुंजी है।

1. चुनना**कनेक्शन जोड़ें** किसी संवर्धन को कॉन्फ़िगर करते समय, या यहां जाएं **व्यवस्थापक** > **सम्बन्ध** और चुनें **स्थापित करना** HERE Technologies टाइल पर।

1. कनेक्शन के लिए एक नाम और एक मान्य HERE Technologies API कुंजी दर्ज करें।

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. चुनना**सत्यापित करना** कॉन्फ़िगरेशन को सत्यापित करने के लिए और फिर चुनें **बचाना**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE Technologies कनेक्शन कॉन्फ़िगरेशन पेज.":::

## <a name="configure-the-enrichment"></a>एनरिचमेंट को कॉन्फ़िगर करें

1. **डेटा** > **समृद्ध** पर जाएं और **खोजें** टैब का चयन करें.

1. चुनना**मेरा डेटा समृद्ध करें** पर **स्थान** HERE Technologies टाइल से।

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies टाइल.":::

1. ओवरव्यू की समीक्षा करें और फिर चुनें **अगला**.

1. कनेक्शन का चयन करें। यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. **अगला** चुनें.

1. को चुनिए **ग्राहक डेटा सेट** और वह प्रोफ़ाइल या खंड चुनें जिसे आप HERE Technologies के डेटा से समृद्ध करना चाहते हैं। *ग्राहक* इकाई आपके सभी ग्राहक प्रोफाइल को समृद्ध करती है जबकि एक सेगमेंट केवल उस सेगमेंट में निहित ग्राहक प्रोफाइल को समृद्ध करता है।

1. परिभाषित करें कि मिलान के लिए आपकी एकीकृत प्रोफ़ाइल से किस प्रकार के फ़ील्ड का उपयोग करना है: प्राथमिक और/या द्वितीयक पता। आप दोनों पतों के लिए एक फ़ील्ड मैपिंग निर्दिष्ट कर सकते हैं और दोनों पतों के लिए प्रोफ़ाइल को अलग-अलग समृद्ध कर सकते हैं. उदाहरण के लिए, घर के पते और व्यावसायिक पते के लिए। **अगला** चुनें.

1. अपने क्षेत्रों को HERE Technologies के डेटा से मैप करें। चयनित प्राइमरी और/या सेकेंडरी पते के लिए **स्ट्रीट 1** और **ज़िप/पोस्टल कोड** फ़ील्डों की आवश्यकता होती है. उच्च मिलान सटीकता के लिए, अधिक फ़ील्ड जोड़ें।

1. फील्ड मैपिंग को पूरा करने के लिए **अगला** चुनें.

1. प्रदान करें एक **नाम** संवर्धन के लिए और **आउटपुट इकाई का नाम**.

1. अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** चुनें.

1. चुनना**दौड़ना** संवर्धन प्रक्रिया शुरू करने के लिए या वापस लौटने के करीब **संवर्धन** पृष्ठ।

## <a name="view-enrichment-results"></a>संवर्धन परिणाम देखें

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**क्षेत्र द्वारा समृद्ध ग्राहकों की संख्या** प्रत्येक समृद्ध क्षेत्र के कवरेज में एक ड्रिल-डाउन प्रदान करता है।

## <a name="next-steps"></a>अगले कदम

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
