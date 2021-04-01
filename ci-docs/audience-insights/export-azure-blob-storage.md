---
title: एक Azure ब्लॉब स्टोरेज के लिए Customer Insights डेटा निर्यात करें
description: Azure Blob स्टोरेज से कनेक्शन को कॉन्फ़िगर करना सीखें.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596179"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Azure ब्लॉब स्टोरेज के लिए कनेक्टर (पूर्वावलोकन)

अपने Customer Insights डेटा को Azure ब्लॉब स्टोरेज में संग्रहित करें या अपने डेटा को अन्य एप्लिकेशन में हस्तांतरित करने के लिए इसका उपयोग करें.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Azure ब्लॉब स्टोरेज के लिए कनेक्टर को कॉन्फ़िगर करें

1. ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.

1. **Azure ब्लॉब स्टोरेज** के अंतर्गत, **सेट करें** चुनें.

1. आपके Azure ब्लॉब स्टोरेज खाते के लिए **खाता नाम**, **खाता कुंजी**, और **कंटेनर** दर्ज करें.
    - Azure Blob संग्रहण खाते का नाम और खाता कुंजी का पता लगाने के बारे में अधिक जानने के लिए, [Azure पोर्टल में संग्रहण खाता सेटिंग व्यवस्थित करें](/azure/storage/common/storage-account-manage) देखें.
    - कंटेनर बनाने के बारे में जानने के लिए, [कंटेनर बनाएँ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) देखें.

1. अपने गंतव्य-स्थल को **प्रदर्शन नाम** फील्ड में पहचान करने योग्य नाम दें.

1. **अगला** चुनें.

1. उस प्रत्येक निकाय के सामने दिए गए बॉक्स को चुनें जिसे आप इस गंतव्य-स्थल में एक्सपोर्ट करना चाहते हैं.

1. **सहेजें** चुनें.

निर्यात किया गया डेटा आपके द्वारा कॉन्फ़िगर किए गए Azure ब्लॉब स्टोरेज कंटेनर में स्टोर किया गया है. आपके कंटेनर में निम्नलिखित फोल्डर पथ अपने आप बनेंगे:

- स्रोत निकायों और सिस्टम द्वारा उत्पन्न स्रोत निकायों के लिए: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - उदाहरण: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- model.json निर्यात किए गए निकायों के लिए %ExportDestinationName% स्तर पर रहेगा
  - उदाहरण: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>डेटा निर्यात करें

आप [मांग पर डेटा निर्यात](export-destinations.md#export-data-on-demand) कर सकते हैं. निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]