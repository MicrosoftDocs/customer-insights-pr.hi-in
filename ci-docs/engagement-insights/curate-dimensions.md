---
title: व्यवहार संबंधी डेटा को विभाजित करने के लिए जनसांख्यिकीय आयामों का उपयोग करें (क्यूरेटेड आयाम)
description: ऑडिएंस इनसाइट्स ग्राहक प्रोफ़ाइल गुणों को सक्षम करने के लिए एकीकृत प्रोफ़ाइल क्यूरेटेड आयामों का उपयोग करें.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466350"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>व्यवहार संबंधी डेटा को विभाजित करने के लिए जनसांख्यिकीय आयामों का उपयोग करें

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

एकीकृत प्रोफ़ाइल जनसांख्यिकीय आयामों का उपयोग करके, सहभागिता इनसाइट्स उपयोगकर्ता ऑडिएंस इनसाइट्स प्रोफ़ाइल गुणों तक पहुंच सकते हैं. फिर आप इन गुणों का उपयोग व्यवहार संबंधी डेटा के इंटरैक्टिव विश्लेषणों में कर सकते हैं, जिसमें आपकी वेबसाइट या मोबाइल ऐप पर सहभागिता इनसाइट्स द्वारा कैप्चर किया गया डेटा भी शामिल है.

>[!NOTE]
> सहभागिता इनसाइट में ईवेंट गुण के लिए आउट-ऑफ़-द-बॉक्स आयाम शामिल हैं. और जानकारी: [आयाम बनाएँ और देखें](dimensions.md)

## <a name="prerequisite"></a>पूर्वावश्यकता

- वह सहभागिता इनसाइट्स परिवेश जिसमें आपके पास ग्राहक प्रोफ़ाइल डेटा ऑडिएंस इनसाइट्स परिवेश से जुड़ा होता है जहां ग्राहक प्रोफ़ाइल बनाई जाती है. अधिक जानकारी: [ऑडियंस इनसाइट्स और सहभागिता इनसाइट्स के बीच लिंक बनाएँ](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> ऑडिएंस इनसाइट्स और सहभागिता इनसाइट्स परिवेशों के बीच लिंक बनाने के बाद, आप केवल ग्राहक प्रोफ़ाइल गुणों के लिए विशिष्ट डेटा चाह सकते हैं, जो सहभागिता इनसाइट्स में आयामों के रूप में उपयोगी हो सकता है. अधिक जानकारी के लिए, [ऑडियंस इनसाइट्स एकीकृत प्रोफ़ाइल विशेषताओं और खंडों को सक्षम करें](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments) पर जाएँ.

## <a name="create-a-new-custom-report"></a>एक नई कस्टम रिपोर्ट बनाएँ.

1. बाएँ फलक पर, **कस्टम** > **नई रिपोर्ट** चुनें और फिर अपनी इच्छित मीट्रिक चुनें. (इस उदाहरण के लिए, हमने **घंटे के अनुसार से पेज व्यू** चुना है.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="कोई मीट्रिक चुनें.":::

2. विज़ुअलाइज़ेशन संपादक में, **आयाम** चुनें और फिर **आयाम प्रकार** ड्रॉपडाउन मेनू में **जनसांख्यिकीय** चुनें.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="जनसांख्यिकीय चुनें.":::

3. एक **Signal.Customer.*xxx*** आयाम चुनें. (यह उदाहरण Signal.Customer.Country दिखाता है.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="एक आयाम चुनें.":::
  
## <a name="limitations"></a>सीमाएँ

वर्तमान में आप व्यवहार संबंधी डेटा को विभाजित करने के लिए केवल जनसांख्यिकीय आयामों का उपयोग कर सकते हैं.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
