---
title: Dynamics 365 Customer Insights के लिए Teams बॉट (पूर्वावलोकन)
description: एक बॉट की मदद से Microsoft Teams में एकीकृत ग्राहक प्रोफाइल देखें.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195844"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insights के लिए Teams बॉट (पूर्वावलोकन)

एक बॉट को टीम चैनलों में एकीकृत ग्राहक प्रोफाइल देखने देने के लिए Microsoft Teams के साथ जुड़ें.

:::image type="content" source="media/teams-bot.png" alt-text="Teams बॉट एक ग्राहक रिकॉर्ड दिखाती हैं":::

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- कम से कम एक [डेटा स्रोत जोड़ा गया।](data-sources.md)
- [एकीकरण प्रक्रिया](data-unification.md) पूरी हो गयी है.
- फ़ील्ड्स को इसमें जोड़ा जाता है [खोज और फ़िल्टर अनुक्रमणिका।](search-filter-index.md)
- Customer Insights और टीम एक ही संगठन में हैं.
- आपके परिवेश में प्राथमिक लक्षित ऑडिएंस हैं जो अलग-अलग ग्राहकों पर सेट हैं. व्यावसायिक खाते समर्थित नहीं हैं.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>बॉट कॉन्फ़िगर करें

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.
1. Microsoft Teams टाइल पर, **सेट अप** का चयन करें.
1. आप टीम में **अनुप्रयोग** क्षेत्र में वापस भेजे गए हैं. आप टीम भी खोल सकते हैं और नीचे-बाएँ कोने में **अनुप्रयोग** का चयन करें या सीधे [AppSource से प्राप्त करें](https://go.microsoft.com/fwlink/?linkid=2124104).
1. **Customer Insights** को खोजें और ऐप चुनें.
1. **जोड़ें** चुनें.
1. Teams में Customer Insights में लॉग इन करें। एक स्वागत संदेश प्रदर्शित होता है।

## <a name="things-you-can-do-with-the-bot"></a>चीज़ें जो आप बॉट के साथ कर सकते हैं

बॉट एकीकृत ग्राहक प्रोफाइल के लिए लुकअप क्षमताएं प्रदान करता है.

- प्रवेश करना**तलाशी** एक नाम, ईमेल पता, या एकीकृत ग्राहक प्रोफ़ाइल पर कोई अन्य फ़ील्ड जो खोज और फ़िल्टर अनुक्रमणिका में जोड़ा जाता है।

  आपको परिणामी ग्राहक प्रोफ़ाइल से अधिकतम 15 फ़ील्ड के साथ एक कार्ड मिलेगा. एकाधिक मिलान परिणामों की एक सूची देते हैं जहां आप एक प्रोफ़ाइल का चयन कर सकते हैं. सटीक मिलान देखने के लिए, शब्द खोजें को दोहरे उद्धरण चिह्नों में जोड़ें।

- यदि आपका संगठन एक ही संगठन में एकाधिक Customer Insights वातावरण बनाए रखता है, तो दर्ज करें **स्विचइंस्टेंस** यह चुनने के लिए कि आप बॉट को किस परिवेश से कनेक्ट करना चाहते हैं।

- बॉट के लिए उपलब्ध आदेशों की एक सूची देखने के लिए **मदद** दर्ज करें.  

[!INCLUDE [footer-include](includes/footer-banner.md)]