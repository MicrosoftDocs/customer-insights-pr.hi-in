---
title: डायनेमिक्स 365 मार्केटिंग में निर्यात खंड (पूर्वावलोकन)
description: कनेक्शन को कॉन्फ़िगर करने और Dynamics 365 Marketing को निर्यात करने का तरीका जानें.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196626"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>डायनेमिक्स 365 मार्केटिंग में निर्यात खंड (पूर्वावलोकन)

प्रयोग करना[खंडों](segments.md) अभियान बनाने और ग्राहकों के विशिष्ट समूहों से संपर्क करने के लिए [डायनेमिक्स 365 मार्केटिंग।](/dynamics365/marketing/customer-insights-segments)

यदि आप Dataverse संगठन में रीयल-टाइम ग्राहक यात्रा ऑर्केस्ट्रेशन के लिए Dynamics 365 Marketing की नई क्षमताओं का उपयोग कर रहे हैं, तो आपको Dynamics 365 Marketing के लिए मानक निर्यात बनाने की आवश्यकता नहीं है. Customer Insights के संपर्क और सेगमेंट मार्केटिंग और Customer Insights को जोड़ने के बाद सीधे Dynamics 365 Marketing में उपलब्ध हैं। मौजूदा निर्यात को हटाने से पहले, दस्तावेज़ीकरण की समीक्षा करें [Customer Insights और Dynamics 365 Marketing ग्राहक यात्रा ऑर्केस्ट्रेशन को कैसे कनेक्ट करें।](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="prerequisite"></a>पूर्वावश्यकता

इससे पहले कि आप Customer Insights से मार्केटिंग में एक सेगमेंट निर्यात करें, संपर्क रिकॉर्ड Dynamics 365 Marketing में मौजूद होने चाहिए. [Microsoft Dataverse का उपयोग करके Dynamics 365 Marketing](connect-dataverse-managed-lake.md) में संपर्कों को कैसे अंतर्ग्रहण करना है, पर अधिक पढ़ें.

> [!NOTE]
> Customer Insights से Marketing के लिए निर्यात खंड मार्केटिंग उदाहरणों में नए संपर्क रिकॉर्ड नहीं बनाएंगे। मार्केटिंग के संपर्क रिकॉर्ड Customer Insights में अंतर्ग्रहीत होने चाहिए और डेटा स्रोत के रूप में उपयोग किए जाने चाहिए। सेगमेंट को निर्यात करने से पहले ID से संपर्क करने के लिए ग्राहक ID को मैप करने के लिए उन्हें एकीकृत ग्राहक निकाय में शामिल करने की भी ज़रूरत है.

## <a name="set-up-connection-to-marketing"></a>मार्केटिंग में कनेक्शन सेट अप करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **डायनेमिक्स 365 मार्केटिंग**.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **सर्वर का पता** फ़ील्ड में अपने संगठन का मार्केटिंग URL दर्ज करें.

1. **सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Marketing खाता चुनें.

1. ग्राहक निकाय में संपर्क आईडी फ़ील्ड को Dynamics 365 संपर्क ID से मैप करें।

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** में, Dynamics 365 Marketing अनुभाग से एक कनेक्शन का चयन करें. यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. Dynamics 365 संपर्क ID से मेल खाने वाले ग्राहक निकाय में संपर्क ID फ़ील्ड का चयन करें।

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
