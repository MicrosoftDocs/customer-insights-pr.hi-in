---
title: सेगमेंट को Dynamics 365 Sales में निर्यात करें (पूर्वावलोकन)
description: कनेक्शन को कॉन्फ़िगर करने और Dynamics 365 Sales को निर्यात करने का तरीका जानें.
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
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195983"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>सेगमेंट को Dynamics 365 Sales में निर्यात करें (पूर्वावलोकन)

अपने ग्राहक डेटा को मार्केटिंग सूची बनाने, कार्यप्रवाह के फ़ॉलो अप और Dynamics 365 Sales के साथ प्रचार भेजने के लिए इस्तेमाल करें.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

इससे पहले कि आप Customer Insights से विक्रय में सेगमेंट निर्यात करें, संपर्क रिकॉर्ड Dynamics 365 Sales में मौजूद होने चाहिए. से संपर्कों को अंतर्ग्रहण करने के तरीके के बारे में और पढ़ें [डायनेमिक्स 365 सेल्स का उपयोग कर Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Customer Insights से Sales में सेगमेंट निर्यात करने से Sales इंस्टेंस में नए संपर्क रिकॉर्ड नहीं बनेंगे. Sales से संपर्क रिकॉर्ड Customer Insights में अंतर्ग्रहीत होने चाहिए और डेटा स्रोत के रूप में उपयोग किए जाने चाहिए। सेगमेंट को निर्यात करने से पहले ID से संपर्क करने के लिए ग्राहक ID को मैप करने के लिए उन्हें एकीकृत ग्राहक निकाय में शामिल करने की भी ज़रूरत है.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

Dynamics 365 Sales में निर्यात प्रति सेगमेंट 100,000 तक सीमित है, जिसे पूरा होने में 3 घंटे तक लग सकते हैं।

## <a name="set-up-connection-to-sales"></a>बिक्री के लिए कनेक्शन सेट करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **डायनेमिक्स 365 सेल्स।**

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **सर्वर का पता** फ़ील्ड में अपने संगठन का बिक्री URL दर्ज करें.

1. **सर्वर व्यवस्थापक खाता** अनुभाग में, **साइन इन** चुनें और एक Dynamics 365 Sales खाता चुनें.

1. Dynamics 365 कॉन्टैक्ट ID पर ग्राहक ID फ़ील्ड का मैप करें.

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** में, Dynamics 365 Sales अनुभाग से एक कनेक्शन का चयन करें. यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. Dynamics 365 संपर्क ID से मेल खाने वाले ग्राहक निकाय में संपर्क ID फ़ील्ड का चयन करें।

1. उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.

1. **सहेजें** चुनें

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
