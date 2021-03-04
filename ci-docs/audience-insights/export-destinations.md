---
title: एक्सपोर्ट गंतव्य
description: डेटा निर्यात करें और निर्यात स्थलों का प्रबंधन करें.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477135"
---
# <a name="export-destinations-preview-overview"></a>एक्सपोर्ट गंतव्य (पूर्वावलोकन) अवलोकन

**एक्सपोर्ट गंतव्य-स्थल** पेज आपको ऐसे सभी स्थल दिखाता है जिन्हें आपने डेटा एक्सपोर्ट करने के लिए तय किया है. आप निर्यात के लिए नए गंतव्य भी जोड़ सकते हैं. इसके अतिरिक्त, यह वर्तमान में निर्यात हुए उपलब्ध विकल्पों को दिखाता है. तुरंत अवलोकन, विवरण प्राप्त करें और पता करें कि आप प्रत्येक विस्तारण विकल्प के साथ क्या कर सकते हैं. एकीकृत प्रोफाइल, उपाय और खंडों को समर्थित ऐप में एक्सपोर्ट करें जो अपने कारोबार के लिए संगत हैं.

**व्यवस्थापक** > **निर्यात स्थलों** निम्नलिखित विस्तारणीयता विकल्प खोजने के लिए जाओ:

- [Dynamics 365 Customer कार्ड ऐड-इन](customer-card-add-in.md)
- [Facebook विज्ञापन प्रबंधक कनेक्टर](export-facebook.md)
- [Power Automate कनेक्टर](export-power-automate.md)
- [Power Apps कनेक्टर](export-power-apps.md)
- [Power BI कनेक्टर](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure ब्लॉब संग्रहण](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [LiveRamp&reg; कनेक्टर](export-liveramp.md)
- [Microsoft Teams के लिए Bot](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>नया एक्सपोर्ट गंतव्य-स्थल जोड़ें

निर्यात स्थलों को जोड़ने के लिए, आपके पास [प्रशासक अनुमतियां](permissions.md) हैं. यदि आप Microsoft सेवाओं को निर्यात करते हैं, तो हम मानते हैं कि दोनों सेवाएँ एक ही संगठन में हैं.

1. **व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.

1. **मेरे निर्यात गंतव्य** टैब पर स्विच करें.

1. एक नया निर्यात गंतव्य बनाने के लिए **गंतव्य जोड़ें** चुनें.

1. **गंतव्य जोड़ें** फलक में, ड्रॉप-डाउन में निर्यात गंतव्य के **प्रकार** का चयन करें.

1. आवश्यक विवरण प्रदान करें और निर्यात गंतव्य बनाने के लिए **अगला** चुनें.

आप भी **सेट अप** पर एक टाइल पर **डिस्कवर** टैब चुन सकते हैं.

## <a name="view-export-destinations"></a>एक्सपोर्ट गंतव्य-स्थल देखें

निर्यात गंतव्य बनाने के बाद, आप उन्हें **मेरा निर्यात गंतव्य** टैब पर एक तालिका में पाएंगे. इस तालिका में तीन कॉलम हैं:

- **प्रदर्शन नाम**: गंतव्य-स्थल बनाते समय आपके द्वारा दर्ज किया गया नाम.
- **प्रकार**: गंतव्य बनाते समय निर्यात गंतव्य प्रकार आप सेट करें.
- **सृजित**: गंतव्य-स्थल को बनाने की तारीख.

## <a name="edit-an-export-destination"></a>एक निर्यात गंतव्य संपादित करें

1. आप जिस एक्सपोर्ट गंतव्य-स्थल को सम्पादित करना चाहते हैं, उसके लिए वर्टिकल एलिप्सिस चुनें.

   > [!div class="mx-imgBorder"]
   > ![अनुलंब एलिप्सिस](media/export-destinations-page-ellipsis.png "ऊर्ध्वाधर दीर्घवृत्त")

1. ड्रॉपडाउन मेनू से **एडिट** का चयन करें.

1. उन मानों को बदलें जिन्हें अपडेट की आवश्यकता है और **सहेजें** चुनें.

## <a name="export-data-on-demand"></a>मांग पर डेटा निर्यात करें

निर्यात गंतव्य के लिए कनेक्टर को कॉन्फ़िगर करने के बाद, निर्यात हर [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).

निर्धारित किए गए रिफ्रेश का इंतजार किए बिना डेटा निर्यात करने के लिए, **मेरे निर्यात गंतव्य** टैब पर जाएं **एडमिन** > **निर्यात गंतव्य**.

> [!div class="mx-imgBorder"]
> ![अनुलंब एलिप्सिस](media/export-destinations-page-ellipsis.png "ऊर्ध्वाधर दीर्घवृत्त")

- सभी निर्यात गंतव्यों में साथ-साथ चलाने के लिए ऊपर दी गई सूची के ऊपर **निर्यात** को चुनें.
- एक सूची आइटम के बाद वृत्त (...) का चयन करें और फिर एकल निर्यात गंतव्य के लिए निर्यात चलाने के लिए **निर्यात** विकल्प चुनें.

## <a name="remove-an-export-destination"></a>एक्सपोर्ट गंतव्य-स्थल हटाना

एक्सपोर्ट गंतव्य-स्थल हटाने के लिए, मुख्य **एक्सपोर्ट गंतव्य-स्थल** पेज से शुरु करें.

1. आप जिस एक्सपोर्ट गंतव्य-स्थल को हटाना चाहते हैं, उसके लिए वर्टिकल एलिप्सिस चुनें.

   > [!div class="mx-imgBorder"]
   > ![अनुलंब एलिप्सिस](media/export-destinations-page-ellipsis.png "ऊर्ध्वाधर दीर्घवृत्त")

2. ड्रॉपडाउन मेनू से **हटाएं** चुनें.

3. पुष्टिकरण स्क्रीन पर **हटाएँ** चुनते हुए उसके हटाए जाने की पुष्टि करें.


[!INCLUDE[footer-include](../includes/footer-banner.md)]