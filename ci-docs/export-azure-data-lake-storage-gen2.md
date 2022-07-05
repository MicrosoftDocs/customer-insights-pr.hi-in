---
title: डेटा निर्यात करें Azure Data Lake Storage Gen2 (पूर्वावलोकन)
description: Azure Data Lake Storage Gen2 के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: c2446fba425203d2910b82134b73543a73c7ecf8
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082658"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>डेटा निर्यात करें Azure Data Lake Storage Gen2 (पूर्वावलोकन)

अपने Customer Insights डेटा को Data Lake Storage Gen2 खाता में स्टोर करें या इसका इस्तेमाल अपने डेटा को दूसरे एप्लिकेशन में ट्रांसफ़र करने के लिए करें.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

1. जब आप अपने डेटा लेक के लिए स्टोरेज अकाउंट बना रहे हों तो, Azure Data Lake Storage Gen2 के लिए आप [स्टैंडर्ड प्रदर्शन और प्रीमियम प्रदर्शन टियर](/azure/storage/blobs/create-data-lake-storage-account) में से किसी एक को चुन सकते हैं. अगर आप प्रीमियम प्रदर्शन स्तर चुनते हैं, तो खाता प्रकार के रूप में प्रीमियम ब्लॉक ब्लॉब चुनें.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>कनेक्शन सेट अप करें Azure Data Lake Storage Gen2

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. **कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Azure Data Lake Gen 2** चुनें.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपने Azure Data Lake Storage Gen2 के लिए **अकाउंट नाम**, **अकाउंट कुंजी** और **कंटेनर** दर्ज करें.
    - Azure Data Lake Storage Gen2 के साथ उपयोग करने के लिए स्टोरेज अकाउंट बनाने का तरीका जानने के लिए, [स्टोरेज अकाउंट बनाएं](/azure/storage/blobs/create-data-lake-storage-account) देखें. 
    - Azure Data Lake Gen2 स्टोरेज अकाउंट का नाम और अकाउंट कुंजी के बारे में अधिक जानने के लिए, देखें [Azure पोर्टल में स्टोरेज अकाउंट सेटिंग्स का प्रबंधन करें](/azure/storage/common/storage-account-manage).

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **निर्यात जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** में, **Azure Data Lake** अनुभाग से एक कनेक्शन का चयन करें. यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.

1. उस प्रत्येक निकाय के सामने दिए गए बॉक्स को चुनें जिसे आप इस गंतव्य-स्थल में एक्सपोर्ट करना चाहते हैं.

1. **सहेजें** चुनें.

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.
आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.

निर्यात किया गया डेटा आपके द्वारा कॉन्फ़िगर किए गए Azure Data Lake Gen2 स्टोरेज कंटेनर में संग्रहीत किया जाता है.

> [!TIP]
> बड़ी मात्रा में डेटा वाले निकायों के निर्यात से प्रत्येक निर्यात के लिए एक ही फ़ोल्डर में एकाधिक CSV फ़ाइलें प्राप्त हो सकती हैं. निर्यात को पूरा करने में लगने वाले समय को कम करने के लिए प्रदर्शन कारणों से विभाजन निर्यात होता है।

[!INCLUDE [footer-include](includes/footer-banner.md)]
