---
title: थर्ड पार्टी के एनरिचमेंट के साथ HERE Technologies का एनरिचमेंट
description: HERE Technologies थर्ड पार्टी के एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597743"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>HERE Technologies (पूर्वावलोकन) के साथ ग्राहक प्रोफाइल का एनरिचमेंट

HERE Technologies एक लोकेशन प्लेटफ़ॉर्म कंपनी है जो स्थान-केंद्रित डेटा और सेवाएं प्रदान करती है. HERE टेक्नोलॉजीज की डेटा संवर्धन सेवाओं के साथ, आप अपने ग्राहकों के पते के सामान्यीकरण, अक्षांश और देशांतर निष्कर्षण आदि के साथ अधिक सटीक स्थान समझ बना सकते हैं.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

HERE Technologies के एनरिचमेंट को कॉन्फ़िगर करने के लिए, निम्नलिखित आवश्यकताओं को पूरा किया जाना चाहिए:

- आपके पास एक सक्रिय HERE Technologies सदस्यता है. सदस्यता प्राप्त करने के लिए, आप [यहां साइन-अप कर सकते हैं](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) या सीधे [HERE Technologies से संपर्क करें](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [HERE Technologies लोकेशन एनरिचमेंट के बारे में अधिक जानें.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- आपके पास HERE Technologies API कुंजी है.

- आपके पास [प्रशासक](permissions.md#administrator) की अनुमतियाँ है.

## <a name="configuration"></a>कॉन्फ़िगरेशन

1. **डेटा** > **संवर्धन** पर जाएँ.

1. HERE Technologies टाइल पर **मेरे डेटा को समृद्ध करें** का चयन करें.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies टाइल](media/HERE-tile.png "HERE Technologies टाइल")

1. एक सक्रिय **HERE Technologies API कुंजी** दर्ज करें. समीक्षा करें और **डेटा गोपनीयता और अनुपालन** के लिए **मैं सहमत हूं** चेकबॉक्स का चयन करके अपनी सहमति प्रदान करें. 

1. **HERE से कनेक्ट करें** चुनकर दोनों इनपुट्स की पुष्टि करें.

1.  **डेटा जोड़ें** का चयन करें और **ग्राहक डेटा सेट चुनें** जिनको आप HERE Technologies से स्थान डेटा के साथ समृद्ध करना चाहते हैं. आप अपनी सभी ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए **ग्राहक** निकाय का चयन कर सकते हैं या उस अनुभाग में निहित केवल ग्राहक प्रोफ़ाइल को बेहतर बनाने के लिए एक अनुभाग निकाय चुन सकते हैं.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="ग्राहक डेटा सेट चुनते समय का स्क्रीनशॉट.":::

1. चुनें कि क्या आप फ़ील्ड को प्राथमिक और/या द्वितीयक पते पर मैप करना चाहते हैं. आप दोनों पतों (उदाहरण के लिए, एक घर और एक व्यवसाय पता) के लिए एक फ़ील्ड मैपिंग निर्दिष्ट कर सकते हैं और दोनों पतों के लिए प्रोफाइल को अलग-अलग समृद्ध कर सकते हैं. **अगला** चुनें.

1. यह परिभाषित करें कि आपके एकीकृत प्रोफाइल से किन फ़ील्ड का उपयोग HERE Technologies से स्थान डेटा का मिलान करने के लिए किया जाना चाहिए. चयनित प्राइमरी और/या सेकेंडरी पते के लिए **स्ट्रीट 1** और **ज़िप/पोस्टल कोड** फ़ील्डों की आवश्यकता होती है. एक उच्च मिलान सटीकता के लिए, अधिक फ़ील्डों को जोड़ा जा सकता है.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies एनरिचमेंट कॉन्फ़िगरेशन पेज](media/enrichment-HERE-configuration.png "HERE Technologies एनरिचमेंट कॉन्फिगरेशन पेज")

1. फ़ील्ड मैपिंग को पूरा करने के लिए **लागू** चुनें.

## <a name="enrichment-results"></a>संवर्धन के परिणाम

संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें. आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं. प्रोसेस करने का समय आपके ग्राहक डेटा के आकार और HERE Technologies से API प्रतिक्रिया समय पर निर्भर करेगा.

संवर्धन प्रक्रिया पूरी होने के बाद, आप **मेरे संवर्धन** के तहत नए समृद्ध ग्राहक प्रोफ़ाइल डेटा की समीक्षा कर सकते हैं. इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.

आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.

## <a name="next-steps"></a>अगले चरण

अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं. अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [सेगमेंट](segments.md), [मापन](measures.md)बनाएं, और यहां तक कि [डेटा निर्यात करें](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को HERE Technologies पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं. Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि HERE Technologies आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.
आपका Dynamics 365 Customer Insights प्रशासक इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस एनरिचमेंट को हटा सकता है.


[!INCLUDE[footer-include](../includes/footer-banner.md)]