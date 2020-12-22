---
title: Power BI कनेक्टर
description: Power BI में Dynamics 365 Customer Insights कनेक्टर का उपयोग करना सीखें.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405926"
---
# <a name="connector-for-power-bi-preview"></a>Power BI के लिए कनेक्टर (पूर्वावलोकन)

Power BI Desktop के साथ अपने डेटा के लिए विज़ुअलाइज़ेशन बनाएं. अतिरिक्त इनसाइट्स उत्पन्न करें और अपने एकीकृत ग्राहक डेटा के साथ रिपोर्ट बनाएं.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- आपके पास एकीकृत ग्राहक प्रोफाइल हैं.
- [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) का नवीनतम संस्करण आपके कंप्यूटर पर स्थापित है. [Power BI Desktop के बारे में अधिक जानें](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)

## <a name="configure-the-connector-for-power-bi"></a>Power BI के लिए कनेक्टर कॉन्फ़िगर करें

1. Power BI Desktop में, **फ़ाइल** > **डेटा प्राप्त करें** चुनें.

1. **अधिक देखें** चुनें और **Dynamics 365 Customer Insights** खोजें

1. परिणाम चुनें और **कनेक्ट करें** का चयन करें.

1. उसी संगठनात्मक खाते के साथ **साइन इन करें** जिसका उपयोग आप Customer Insights के लिए करते हैं और **कनेक्ट करें** चुनें.
   > [!NOTE]
   > इस चरण में आपके द्वारा दर्शाए गए खाते का उपयोग Customer Insights से डेटा प्राप्त करने के लिए किया जाता है और आवश्यक नहीं कि यह आपके द्वारा Power BI में लॉग इन किए गए खाते के समान हो. डेटा लाने के लिए उपयोग किए जाने वाले खाते को रीसेट करने के लिए, Power BI खोलें और **फ़ाइल** > **विकल्प** > **सेटिंग्स** > **डेटा स्रोत सेटिंग्स** पर जाएं. डेटा स्रोतों की सूची में, **Dynamics 365 Customer Insights लॉग इन** का चयन करें और **स्पष्ट अनुमतियां** चुनें.  

1. **नेविगेटर** संवाद बॉक्स में. आप उन सभी परिवेशों की सूची देखते हैं जिनके पास आपके पास पहुंच है. एक परिवेश का विस्तार करें और किसी भी फ़ोल्डर (निकायों, साधनों, खंडों, एनरिचमेंट) को खोलें. उदाहरण के लिए, **निकाय** फ़ोल्डर खोलें, उन सभी निकायओं को देखने के लिए जिन्हें आप आयात कर सकते हैं.

   ![Power BI कनेक्टर नेविगेटर](media/power-bi-navigator.png "Power BI कनेक्टर नेविगेटर")

1. शामिल करने के लिए निकायों के बगल में स्थित चेक बॉक्स चुनें और **लोड करें**. आप एकाधिक परिवेश से कई निकायों का चयन कर सकते हैं.

1. आपके निकाय लोड होने के दौरान आपको एक लोडिंग डायलॉग बॉक्स दिखाई देगा. एक बार जब आपकी सभी चयनित निकायएं लोड हो जाती हैं, तो आप डेटा की कल्पना करने के लिए Power BI की क्षमताओं का उपयोग कर सकते हैं.

## <a name="large-data-sets"></a>बड़े डेटा सेट

Power BI के लिए Customer Insights कनेक्टर को उन डेटा सेटों के लिए काम करने के लिए डिज़ाइन किया गया है जिनमें 1 मिलियन तक ग्राहक प्रोफ़ाइल हैं. बड़े डेटा सेट को आयात करने से काम बन सकता है, लेकिन इसमें लंबा समय लगता है. इसके अतिरिक्त, Power BI सीमाओं के कारण यह प्रक्रिया एक टाइम-आउट में चल सकती है. अधिक जानकारी के लिए देखें [Power BI: बड़े डेटा सेट के लिए सिफारिशें।](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>डेटा के सबसेट के साथ काम करें

अपने डेटा के सबसेट के साथ काम करने पर विचार करें. उदाहरण के लिए, आप Power BI को सभी ग्राहक रिकॉर्ड निर्यात करने के बजाय [सेगमेंट](segments.md) बना सकते हैं.
