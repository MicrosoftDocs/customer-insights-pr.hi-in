---
title: Customer Insights डेटा को LinkedIn Ads में निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और LinkedIn Ads को निर्यात करने का तरीका जानें.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2cfaa37fd0ac697f29665792bab27a925d8ea1eede0519d424524a7e5accbfeb
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034225"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>सेगमेंट LinkedIn Ads (पूर्वावलोकन) में निर्यात करें

Matched Audiences बनाने के लिए एकीकृत ग्राहक प्रोफ़ाइल के सेगमेंट को LinkedIn Ads में निर्यात करें. कंपनी लक्ष्यीकरण और संपर्क लक्ष्यीकरण के लिए matched audiences का उपयोग करें.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

-   आपके पास एक [LinkedIn Campaign Manager खाता](https://business.linkedin.com/marketing-solutions/ads) और संबंधित व्यवस्थापक क्रेडेंशियल्स हैं.
-   आपके पास ऑडियंस इनसाइट्स में [कॉन्फ़िगर सेगमेंट](segments.md) है.
-   निर्यात किए गए सेगमेंट में ग्राहक प्रोफ़ाइल में ईमेल पते वाली एक फ़ील्ड होती है.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- आप LinkedIn Ads को प्रति निर्यात में 100K प्रोफ़ाइल तक निर्यात कर सकते हैं.
- LinkedIn Ads को निर्यात करना सेगमेंट तक ही सीमित है.
- LinkedIn Ads को 100K प्रोफ़ाइल तक निर्यात पूरा करनें में 10 मिनट तक का समय लग सकता है. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>LinkedIn Ads में कनेक्शन सेट अप करें

1. ऑडियंस इनसाइट्स में, **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. **कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **LinkedIn विज्ञापन** चुनें.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होते हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपनी [LinkedIn Campaign Manager खाता ID](https://www.linkedin.com/help/lms/answer/a424270) प्रदान करें.

1. **डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.

1. Campaign Monitor से कनेक्शन शुरू करने के लिए **कनेक्ट करें** चुनें.

1. **LinkedIn के साथ प्रमाणित करें** चुनें और LinkedIn Campaign Manager के लिए अपने व्यवस्थापक क्रेडेंशियल्स प्रदान करें.

1. **अपने आप को निर्यात उपयोगकर्ता के रूप में जोड़ें** और अपने Customer Insights क्रेडेंशियल्स प्रदान करें .

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप किसी निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** फ़ील्ड में, LinkedIn Ads सेक्शन से एक कनेक्शन का चयन करें. यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.

1. चुनें कि आप LinkedIn पर [संपर्क लक्ष्य](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) के लिए डेटा निर्यात करना चाहते हैं या [कंपनी लक्ष्य](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) के लिए. 

1. **डेटा मिलान** सेक्शन में, अपनी एकीकृत ग्राहक प्रोफ़ाइल में उस फ़ील्ड का चयन करें जो ग्राहक के ईमेल पते का प्रतिनिधित्व करती है. LinkedIn विज्ञापन को खंडों को निर्यात करना आवश्यक है.

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं. LinkedIn Campaign Manager में matched audiences, निर्यात करने के लिए आपके द्वारा चुने गए सेगमेंट के नाम के साथ स्वचालित रूप से बन जाएगी. प्रत्येक सेगमेंट के परिणामस्वरूप एक अलग matched audience होगी. 

1. **सहेजें** चुनें.

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है. आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं. 


## <a name="data-privacy-and-compliance"></a>डेटा गोपनीयता और अनुपालन

जब आप Dynamics 365 Customer Insights को LinkedIn Ads में डेटा प्रसारित करने में सक्षम बनाते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के ट्रांसफ़र की अनुमति देते हैं, जिसमें व्यक्तिगत डेटा जैसे संभावित संवेदनशील डेटा शामिल हैं. Microsoft आपके निर्देश पर ऐसे डेटा को ट्रांसफ़र करेगा, लेकिन आप यह सुनिश्चित करने के लिए जिम्मेदार हैं कि LinkedIn Ads आपके पास किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करे. अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.

इस कार्यक्षमता का उपयोग बंद करने के लिए आपका Dynamics 365 Customer Insights व्यवस्थापक किसी भी समय इस निर्यात गंतव्य-स्थल को हटा सकता है.