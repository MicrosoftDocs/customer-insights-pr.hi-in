---
title: Dynamics 365 Sales के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और Dynamics 365 Sales को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 987690283090ec83ca75f50bf8f3cd8da9295887
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642637"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Dynamics 365 Sales (पूर्वावलोकन) में सेगमेंटों का उपयोग करें



अपने ग्राहक डेटा को मार्केटिंग सूची बनाने, कार्यप्रवाह के फ़ॉलो अप और Dynamics 365 Sales के साथ प्रचार भेजने के लिए इस्तेमाल करें.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- Dynamics 365 Sales में निर्यात प्रति सेगमेंट 100'000 सदस्यों तक सीमित है।
- Dynamics 365 Sales में सेगमेंट निर्यात को पूरा होने में 3 घंटे तक लग सकते हैं. 

## <a name="prerequisite-for-connection"></a>कनेक्शन के लिए पूर्वावश्यकताएँ

1. इससे पहले कि आप Customer Insights से विक्रय में सेगमेंट निर्यात करें, संपर्क रिकॉर्ड Dynamics 365 Sales में मौजूद होने चाहिए. से संपर्कों को अंतर्ग्रहण करने के तरीके के बारे में और पढ़ें [डायनेमिक्स 365 सेल्स का उपयोग कर Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Customer Insights से Sales में सेगमेंट निर्यात करने से Sales इंस्टेंस में नए संपर्क रिकॉर्ड नहीं बनेंगे. Sales से संपर्क रिकॉर्ड Customer Insights में अंतर्ग्रहीत होने चाहिए और डेटा स्रोत के रूप में उपयोग किए जाने चाहिए। सेगमेंट को निर्यात करने से पहले ID से संपर्क करने के लिए ग्राहक ID को मैप करने के लिए उन्हें एकीकृत ग्राहक निकाय में शामिल करने की भी ज़रूरत है.

## <a name="set-up-the-connection-to-sales"></a>विक्रय के लिए कनेक्शन सेट करें

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. **कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Dynamics 365 Sales** चुनें.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **सर्वर का पता** फ़ील्ड में अपने संगठन का बिक्री URL दर्ज करें.

1. **सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Sales खाता चुनें.

1. Dynamics 365 कॉन्टैक्ट ID पर ग्राहक ID फ़ील्ड का मैप करें.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें. 

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** में, Dynamics 365 Sales अनुभाग से एक कनेक्शन का चयन करें. यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.

1. एक या अधिक सेगमेंट चुनें.

1. **सहेजें** चुनें

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है. आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं. 

[!INCLUDE [footer-include](includes/footer-banner.md)]