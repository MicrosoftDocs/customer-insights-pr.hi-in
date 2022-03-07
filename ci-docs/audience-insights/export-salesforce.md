---
title: Salesforce मार्केटिंग क्लाउड में Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Salesforce Marketing Cloud को निर्यात करने का तरीका जानें।
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b50539d6478a8fe196048f0fb421e5856f713a3ddc6577a637e593f90857ae8b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035555"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Salesforce Marketing Cloud में निर्यात अनुभाग और अन्य डेटा (पूर्वावलोकन)

Salesforce Marketing Cloud में अपने ग्राहक डेटा को सुरक्षित फ़ाइल स्थानांतरण प्रोटोकॉल (SFTP) स्थान के माध्यम से निर्यात करके उपयोग करें।

## <a name="prerequisites-for-connection"></a>कनेक्शन के लिए पहले से ज़रूरी चीजें

- एक SFTP होस्ट और संबंधित व्यवस्थापक क्रेडेंशियल की उपलब्धता। [Salesforce मार्केटिंग क्लाउड के लिए SFTP लोकेशन सेट करने का तरीका जानें](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Salesforce Marketing Cloud से कनेक्शन सेट करें

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. कनेक्शन को कॉन्फ़िगर करने के लिए **कनेक्शन जोड़ें** चुनें और **Salesforce मार्केटिंग क्लाउड** चुनें.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपने SFTP खाते के लिए **उपयोगकर्ता नाम**, **पासवर्ड**, **होस्टनाम** और **निर्यात फ़ोल्डर** प्रदान करें.

1. कनेक्शन का परीक्षण करने के लिए **सत्यापन करें** चुनें.

1. **डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** में, SFTP अनुभाग से एक कनेक्शन का चयन करें. यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.

1. अगर आप निर्यात की गई फ़ाइलों के लिए अपने डेटा **ज़िप** या **अनज़िप** और **फ़ील्ड डिलिमिटर** का निर्यात करना चाहते हैं तो चुनें.

1. निकायों का चयन करें, उदाहरण के लिए वे सेगमेंट जिनका आप निर्यात करना चाहते हैं.

   > [!NOTE]
   > प्रत्येक चयनित निकाय को निर्यात किए जाने पर पांच आउटपुट फाइलों में विभाजित किया जाएगा. 

1. **सहेजें** चुनें.

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है. आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं. 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Salesforce Marketing Cloud में SFTP स्थान से Customer Insights डेटा आयात करें

1. Customer Insights डेटा फ़ाइल को SFTP स्थान से आयात करने के लिए [Salesforce Marketing Cloud में डेटा एक्सटेंशन](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) बनाएँ।

2. Salesforce मार्केटिंग क्लाउड डेटा एक्सटेंशन में [SFTP स्थान से डेटा आयात करें](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)। 

3. डेटा एक्सटेंशन में डेटा आयात करने के लिए स्वचालन सेट करें। [फ़ाइल ड्रॉप ऑटोमेशन और शेड्यूल्ड ऑटोमेशन](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) के बारे में अधिक जानें।

   एक [ फ़ाइल ड्रॉप स्वचालन](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) या [ अनुसूचित स्वचालन ](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) को परिभाषित करें। 

[SFTP के साथ स्वचालन ](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) का यहाँ एक उदाहरण है।

## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को SFTP द्वारा डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं. Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि निर्यात गंतव्य आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.
आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
