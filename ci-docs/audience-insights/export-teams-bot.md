---
title: Microsoft Teams के लिए बॉट
description: एक बॉट की मदद से Microsoft Teams में एकीकृत ग्राहक प्रोफाइल देखें.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d6b016c1ec35e26ce6449333234edfd218bc9354
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232104"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insights के लिए Teams बॉट (पूर्वावलोकन)

एक बॉट को टीम चैनलों में एकीकृत ग्राहक प्रोफाइल देखने देने के लिए Microsoft Teams के साथ जुड़ें.

> [!div class="mx-imgBorder"]
> ![Teams बॉट एक ग्राहक रिकॉर्ड दिखाती हैं.](media/teams-bot.png "Teams बॉट एक ग्राहक रिकॉर्ड दिखाती हैं")

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

बॉट को सेट और कॉन्फ़िगर करने के लिए, निम्नलिखित पूर्वअपेक्षाएँ पूरी की जानी चाहिए:

- कम से कम एक है [डेटा स्रोत जोड़ा गया](data-sources.md).
- [एकीकरण प्रक्रिया](data-unification.md) पूरी हो गयी है.
- फ़ील्ड [खोज और फ़िल्टर इंडेक्स](search-filter-index.md) में जोड़े जाते हैं.
- Customer Insights और टीम एक ही संगठन में हैं.
- आपके परिवेश में प्राथमिक लक्षित ऑडिएंस हैं जो अलग-अलग ग्राहकों पर सेट हैं. व्यावसायिक खाते समर्थित नहीं हैं.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]
## <a name="configure-the-bot"></a>बॉट कॉन्फ़िगर करें

1. ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.
1. Microsoft Teams टाइल पर, **सेट अप** का चयन करें.
1. आप टीम में **अनुप्रयोग** क्षेत्र में वापस भेजे गए हैं. आप टीम भी खोल सकते हैं और नीचे-बाएँ कोने में **अनुप्रयोग** का चयन करें या सीधे [AppSource से प्राप्त करें](https://go.microsoft.com/fwlink/?linkid=2124104).
1. **Customer Insights** को खोजें और ऐप चुनें.
1. **जोड़ें** चुनें.
1. Teams में Customer Insights में साइन इन करने के बाद, आप एक स्वागत संदेश देखेंगे और शुरू कर सकते हैं.

## <a name="things-you-can-do-with-the-bot"></a>चीज़ें जो आप बॉट के साथ कर सकते हैं

बॉट एकीकृत ग्राहक प्रोफाइल के लिए लुकअप क्षमताएं प्रदान करता है.

- खोज और फ़िल्टर इंडेक्स में जोड़े गए एकीकृत ग्राहक प्रोफ़ाइल पर नाम, ईमेल पता, या किसी अन्य क्षेत्र के बाद **खोज**  दर्ज करें.

  आपको परिणामी ग्राहक प्रोफ़ाइल से अधिकतम 15 फ़ील्ड के साथ एक कार्ड मिलेगा. एकाधिक मिलान परिणामों की एक सूची देते हैं जहां आप एक प्रोफ़ाइल का चयन कर सकते हैं. सटीक मिलान देखने के लिए आप खोज शब्द को दोहरे उद्धरण में जोड़ सकते हैं.

- यदि आपका संगठन एक ही संगठन में कई Customer Insights परिवेश रखता है, तो आप यह चुनने के लिए **switchinstance** दर्ज कर सकते हैं कि आप बॉट को किस परिवेश से जोड़ना चाहते हैं.

- बॉट के लिए उपलब्ध आदेशों की एक सूची देखने के लिए **मदद** दर्ज करें.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]