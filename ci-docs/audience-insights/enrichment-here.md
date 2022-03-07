---
title: तृतीय-पक्ष संवर्धन HERE Technologies के साथ संवर्धन
description: HERE Technologies थर्ड पार्टी के एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1b46e8913c6d288b93cdf32e195b5e9387916e70
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230384"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>HERE Technologies (पूर्वावलोकन) के साथ ग्राहक प्रोफाइल का एनरिचमेंट

HERE Technologies एक लोकेशन प्लेटफ़ॉर्म कंपनी है जो स्थान-केंद्रित डेटा और सेवाएं प्रदान करती है. HERE टेक्नोलॉजीज की डेटा संवर्धन सेवाओं के साथ, आप अपने ग्राहकों के पते के सामान्यीकरण, अक्षांश और देशांतर निष्कर्षण आदि के साथ अधिक सटीक स्थान समझ बना सकते हैं.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

HERE Technologies के एनरिचमेंट को कॉन्फ़िगर करने के लिए, निम्नलिखित आवश्यकताओं को पूरा किया जाना चाहिए:

- आपके पास एक सक्रिय HERE Technologies सदस्यता है. सदस्यता प्राप्त करने के लिए, आप [यहां साइन-अप](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) या सीधे [HERE Technologies से संपर्क](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) कर सकते हैं। [HERE Technologies लोकेशन एनरिचमेंट के बारे में अधिक जानें.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [कनेक्शन](connections.md) उपलब्ध है *या* आपके पास [व्यवस्थापक](permissions.md#administrator) अनुमतियाँ और HERE Technologies API कुंजी हैं।

## <a name="configure-the-enrichment"></a>एनरिचमेंट को कॉन्फ़िगर करें

1. **डेटा** > **संवर्धन** पर जाएँ. 

1. HERE Technologies टाइल पर **मेरे डेटा को समृद्ध करें** और **शुरू करें** का चयन करें.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies टाइल.](media/HERE-tile.png "HERE Technologies टाइल")

1. ड्राप-डाउन सूची से [कनेक्शन](connections.md) चुनें। यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें. यदि आप एक व्यवस्थापक हैं, तो आप **कनेक्शन जोड़ें** का चयन करके एक कनेक्शन बना सकते हैं. ड्रॉपडाउन सूची से **HERE Technologies** चुनें। 

1. चयन की पुष्टि करने के लिए **HERE Technologies से कनेक्ट करें** चुनें.

1.  **अगला** चुनें और उन **ग्राहक डेटा सेट** का चयन करें जिसे आप HERE Technologies के लोकेशन डेटा के साथ समृद्ध करना चाहते हैं. आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए **ग्राहक** निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="ग्राहक डेटा सेट चुनते समय का स्क्रीनशॉट.":::

1. चुनें कि क्या आप फ़ील्ड को प्राथमिक और/या द्वितीयक पते पर मैप करना चाहते हैं. आप दोनों पतों के लिए एक फ़ील्ड मैपिंग निर्दिष्ट कर सकते हैं और दोनों पतों के लिए प्रोफ़ाइल को अलग-अलग समृद्ध कर सकते हैं. उदाहरण के लिए, यदि कोई घर और व्यवसाय का पता हो. **अगला** चुनें.

1. यह परिभाषित करें कि आपके एकीकृत प्रोफाइल से किन फ़ील्ड का उपयोग HERE Technologies से स्थान डेटा का मिलान करने के लिए किया जाना चाहिए. चयनित प्राइमरी और/या सेकेंडरी पते के लिए **स्ट्रीट 1** और **ज़िप/पोस्टल कोड** फ़ील्डों की आवश्यकता होती है. एक उच्च मिलान सटीकता के लिए, अधिक फ़ील्डों को जोड़ा जा सकता है.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies एनरिचमेंट कॉन्फ़िगरेशन पेज.](media/enrichment-HERE-configuration.png "HERE Technologies एनरिचमेंट कॉन्फिगरेशन पेज")

1. फील्ड मैपिंग को पूरा करने के लिए **अगला** चुनें.

1. संवर्धन के लिए एक नाम प्रदान करें. 

1. अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** चुनें.

## <a name="configure-the-connection-for-here-technologies"></a>HERE Technologies के लिए कनेक्शन कॉन्फ़िगर करें 

आपको कनेक्शन को कॉन्फ़िगर करने के लिए एक व्यवस्थापक होना चाहिए. किसी संवर्धन को कॉन्फ़िगर करते समय **कनेक्शन जोड़ें** का चयन करें *या* **व्यवस्थापक** > **कनेक्शन** पर जाएं और HERE Technologies टाइल पर **सेट करें** का चयन करें.

1. **डिस्प्ले नाम** बॉक्स में कनेक्शन के लिए एक नाम दर्ज करें.

1. एक वैध HERE Technologies API कुंजी प्रदान करें.

1. **मैं सहमत हूं** चयन करके **डेटा गोपनीयता और अनुपालन** की समीक्षा करें और इसके लिए अपनी सहमति प्रदान करें।

1. कॉन्फ़िगरेशन को मान्य करने के लिए **सत्यापित** चुनें.

1. सत्यापन पूरा करने के बाद, **सहेजें** चुनें.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies कनेक्शन कॉन्फ़िगरेशन पेज.](media/enrichment-HERE-connection.png "HERE Technologies कनेक्शन कॉन्फ़िगरेशन पेज")

## <a name="enrichment-results"></a>संवर्धन के परिणाम

संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें. आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं. प्रोसेस करने का समय आपके ग्राहक डेटा के आकार और HERE Technologies से API प्रतिक्रिया समय पर निर्भर करेगा.

संवर्धन प्रक्रिया पूरी होने के बाद, आप **मेरे संवर्धन** के तहत नए समृद्ध ग्राहक प्रोफ़ाइल डेटा की समीक्षा कर सकते हैं. इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.

आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.

## <a name="next-steps"></a>अगले कदम

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को HERE Technologies पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं. Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि HERE Technologies आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.
आपका Dynamics 365 Customer Insights व्यवस्थापक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस संवर्धन को हटा सकता है.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
