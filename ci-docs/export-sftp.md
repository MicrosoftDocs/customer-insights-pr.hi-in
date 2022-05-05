---
title: Customer Insights डेटा को SFTP होस्ट में निर्यात करें (इसमें वीडियो शामिल है)
description: कनेक्शन को कॉन्फ़िगर करने और SFTP स्थान को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5170ec4ca35ad2a94f02e9d696c44a32da888120
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642592"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>अनुभागों और अन्य डेटा को SFTP (पूर्वावलोकन) में निर्यात करें

अपने ग्राहक डेटा का उपयोग तीसरे पक्ष के अनुप्रयोगों में सुरक्षित फ़ाइल ट्रांसफर प्रोटोकॉल (SFTP) लोकेशन पर निर्यात करके करें.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>कनेक्शन के लिए पहले से ज़रूरी चीजें

- एक SFTP होस्ट और संबंधित क्रेडेंशियल्स की उपलब्धता.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- फायरवॉल के पीछे एसएफ़टीपी गंतव्य वर्तमान में समर्थित नहीं हैं। 
- निर्यात का रनटाइम आपके सिस्टम के प्रदर्शन पर निर्भर करता है. हम आपके सर्वर के न्यूनतम कॉन्फ़िगरेशन के रूप में दो CPU कोर और 1 Gb मेमोरी की सलाह देते हैं. 
- दो CPU कोर और मेमोरी के 1 Gb के अनुशंसित न्यूनतम कॉन्फ़िगरेशन का उपयोग करके 100 मिलियन ग्राहक प्रोफ़ाइल के साथ निर्यात करने वाले निकायों को 90 मिनट लग सकते हैं. 

## <a name="set-up-connection-to-sftp"></a>SFTP में कनेक्शन सेट अप करें

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. **कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **SFTP** चुनें.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपने SFTP खाते के लिए **उपयोगकर्ता नाम**, **पासवर्ड**, **होस्टनाम** और **निर्यात फ़ोल्डर** प्रदान करें.

1. कनेक्शन का परीक्षण करने के लिए **सत्यापन करें** चुनें.

1. अगर आप निर्यात की गई फ़ाइलों के लिए अपने डेटा **ज़िप** या **अनज़िप** और **फ़ील्ड डिलिमिटर** का निर्यात करना चाहते हैं तो चुनें.

1. **डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** में, SFTP अनुभाग से एक कनेक्शन का चयन करें. यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.

1. निकायों का चयन करें, उदाहरण के लिए वे सेगमेंट जिनका आप निर्यात करना चाहते हैं.

   > [!NOTE]
   > प्रत्येक चयनित निकाय को निर्यात किए जाने पर पांच आउटपुट फाइलों में विभाजित किया जाएगा. 

1. **सहेजें** चुनें.

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है. आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं. 

## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को SFTP द्वारा डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं. Microsoft आपके निर्देश पर ऐसे डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि निर्यात गंतव्य आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.
आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.

[!INCLUDE [footer-include](includes/footer-banner.md)]