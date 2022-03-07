---
title: Azure Data Lake Storage Gen2 के लिए Customer Insights डेटा निर्यात करें
description: Azure Data Lake Storage Gen2 के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596639"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage Gen2 के लिए कनेक्टर (पूर्वावलोकन)

अपने Customer Insights डेटा को Azure Data Lake Storage Gen2 में स्टोर करें या इसका इस्तेमाल अपने डेटा को दूसरे एप्लिकेशन में भेजने के लिए करें.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>कनेक्टर को Azure Data Lake Storage Gen2 के लिए कॉन्फ़िगर करें

1. ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.

1. **Azure Data Lake Storage Gen2** के अंतर्गत, **सेट अप** चुनें.

1. अपने गंतव्य-स्थल को **प्रदर्शन नाम** फील्ड में पहचान करने योग्य नाम दें.

1. अपने Azure Data Lake Storage Gen2 के लिए **अकाउंट नाम**, **अकाउंट कुंजी** और **कंटेनर** दर्ज करें.
    - Azure Data Lake Storage Gen2 के साथ उपयोग करने के लिए स्टोरेज अकाउंट बनाने का तरीका जानने के लिए, [स्टोरेज अकाउंट बनाएं](/azure/storage/blobs/create-data-lake-storage-account) देखें. 
    - Azure Data Lake Gen2 संग्रहण अकाउंट नाम और अकाउंट कुंजी को खोजने के तरीके के बारे में अधिक जानने के लिए, [Azure पोर्टल में संग्रहण अकाउंट सेटिंग प्रबंधित करें](/azure/storage/common/storage-account-manage) देखें.

1. **अगला** चुनें.

1. उस प्रत्येक निकाय के सामने दिए गए बॉक्स को चुनें जिसे आप इस गंतव्य-स्थल में एक्सपोर्ट करना चाहते हैं.

1. **सहेजें** चुनें.

## <a name="export-the-data"></a>डेटा निर्यात करें

आप [मांग पर डेटा निर्यात](export-destinations.md#export-data-on-demand) कर सकते हैं. निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).