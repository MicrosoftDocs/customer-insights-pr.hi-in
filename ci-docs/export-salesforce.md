---
title: Salesforce मार्केटिंग क्लाउड में डेटा निर्यात करें (पूर्वावलोकन)
description: कनेक्शन को कॉन्फ़िगर करने और Salesforce Marketing Cloud को निर्यात करने का तरीका जानें।
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197040"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Salesforce मार्केटिंग क्लाउड में डेटा निर्यात करें (पूर्वावलोकन)

Salesforce Marketing Cloud में अपने ग्राहक डेटा को सुरक्षित फ़ाइल स्थानांतरण प्रोटोकॉल (SFTP) स्थान के माध्यम से निर्यात करके उपयोग करें।

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- एक [Salesforce मार्केटिंग क्लाउड के लिए SFTP होस्ट](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) और संबंधित व्यवस्थापक क्रेडेंशियल।

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>सेल्सफोर्स मार्केटिंग क्लाउड से कनेक्शन सेट करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **सेल्सफोर्स मार्केटिंग क्लाउड।**

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपने SFTP खाते के लिए **उपयोगकर्ता नाम**, **पासवर्ड**, **होस्टनाम** और **निर्यात फ़ोल्डर** प्रदान करें.

1. कनेक्शन का परीक्षण करने के लिए **सत्यापन करें** चुनें.

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** में, SFTP अनुभाग से एक कनेक्शन का चयन करें. यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. अगर आप निर्यात की गई फ़ाइलों के लिए अपने डेटा **ज़िप** या **अनज़िप** और **फ़ील्ड डिलिमिटर** का निर्यात करना चाहते हैं तो चुनें.

1. इकाइयों का चयन करें, उदाहरण के लिए सेगमेंट, जिन्हें आप निर्यात करना चाहते हैं।

   > [!NOTE]
   > निर्यात किए जाने पर प्रत्येक चयनित निकाय को अधिकतम पांच आउटपुट फ़ाइलों में विभाजित किया जाएगा।

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Salesforce Marketing Cloud में SFTP स्थान से Customer Insights डेटा आयात करें

1. Customer Insights डेटा फ़ाइल को SFTP स्थान से आयात करने के लिए [Salesforce Marketing Cloud में डेटा एक्सटेंशन](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) बनाएँ।

2. Salesforce मार्केटिंग क्लाउड डेटा एक्सटेंशन में [SFTP स्थान से डेटा आयात करें](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)।

3. डेटा एक्सटेंशन में डेटा आयात करने के लिए स्वचालन सेट करें। [फ़ाइल ड्रॉप ऑटोमेशन और शेड्यूल्ड ऑटोमेशन](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) के बारे में अधिक जानें।

   एक [ फ़ाइल ड्रॉप स्वचालन](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) या [ अनुसूचित स्वचालन ](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) को परिभाषित करें।

[SFTP के साथ स्वचालन ](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) का यहाँ एक उदाहरण है।

[!INCLUDE [footer-include](includes/footer-banner.md)]
