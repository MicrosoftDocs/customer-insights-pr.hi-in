---
title: Dynamics 365 Marketing के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Dynamics 365 Marketing को निर्यात करने का तरीका जानें.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642447"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing (पूर्वावलोकन) में सेगमेंट का उपयोग करें



अभियान उत्पन्न करने और Dynamics 365 Marketing वाले ग्राहकों के विशिष्ट समूहों से संपर्क करने के लिए [सेगमेंट](segments.md) का उपयोग करें. अधिक जानकारी के लिए, देखें [Dynamics 365 Customer Insights से Dynamics 365 Marketing का उपयोग करें](/dynamics365/marketing/customer-insights-segments).

यदि आप Dataverse संगठन में रीयल-टाइम ग्राहक यात्रा ऑर्केस्ट्रेशन के लिए Dynamics 365 Marketing की नई क्षमताओं का उपयोग कर रहे हैं, तो आपको Dynamics 365 Marketing के लिए मानक निर्यात बनाने की आवश्यकता नहीं है. Customer Insights के संपर्क और सेगमेंट मार्केटिंग और Customer Insights को जोड़ने के बाद सीधे Dynamics 365 Marketing में उपलब्ध हैं। मौजूदा निर्यात को हटाने से पहले, दस्तावेज़ीकरण की समीक्षा करें [Customer Insights और Dynamics 365 Marketing ग्राहक यात्रा ऑर्केस्ट्रेशन को कैसे कनेक्ट करें।](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="prerequisite-for-a-connection"></a>कनेक्शन के लिए पहले से ज़रूरी चीजें

- इससे पहले कि आप Customer Insights से मार्केटिंग में एक सेगमेंट निर्यात करें, संपर्क रिकॉर्ड Dynamics 365 Marketing में मौजूद होने चाहिए. [Microsoft Dataverse का उपयोग करके Dynamics 365 Marketing](connect-dataverse-managed-lake.md) में संपर्कों को कैसे अंतर्ग्रहण करना है, पर अधिक पढ़ें.

  > [!NOTE]
  > Customer Insights से Marketing के लिए निर्यात खंड मार्केटिंग उदाहरणों में नए संपर्क रिकॉर्ड नहीं बनाएंगे। मार्केटिंग के संपर्क रिकॉर्ड Customer Insights में अंतर्ग्रहीत होने चाहिए और डेटा स्रोत के रूप में उपयोग किए जाने चाहिए। सेगमेंट को निर्यात करने से पहले ID से संपर्क करने के लिए ग्राहक ID को मैप करने के लिए उन्हें एकीकृत ग्राहक निकाय में शामिल करने की भी ज़रूरत है.

## <a name="set-up-connection-to-marketing"></a>मार्केटिंग में कनेक्शन सेट अप करें

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. **कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Dynamics 365 Marketing** चुनें.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **सर्वर का पता** फ़ील्ड में अपने संगठन का मार्केटिंग URL दर्ज करें.

1. **सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Marketing खाता चुनें.

1. ग्राहक निकाय में संपर्क आईडी फ़ील्ड को Dynamics 365 संपर्क ID से मैप करें।

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें. 

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** में, Dynamics 365 Marketing अनुभाग से एक कनेक्शन का चयन करें. यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.

1. एक या अधिक सेगमेंट चुनें.

1. **सहेजें** चुनें.

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है. आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं. 

[!INCLUDE [footer-include](includes/footer-banner.md)]