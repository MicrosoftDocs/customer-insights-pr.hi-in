---
title: डेटा निर्यात करें Azure Data Lake Storage Gen2 (पूर्वावलोकन)
description: Azure Data Lake Storage Gen2 के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196442"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>डेटा निर्यात करें Azure Data Lake Storage Gen2 (पूर्वावलोकन)

अपने Customer Insights डेटा को Data Lake Storage Gen2 खाता में स्टोर करें या इसका इस्तेमाल अपने डेटा को दूसरे एप्लिकेशन में ट्रांसफ़र करने के लिए करें.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- ए [Azure Data Lake Gen2 के साथ उपयोग करने के लिए संग्रहण खाता।](/azure/storage/blobs/create-data-lake-storage-account) भंडारण खाते का नाम और कुंजी खोजने के लिए, देखें [Azure पोर्टल में संग्रहण खाता सेटिंग प्रबंधित करें।](/azure/storage/common/storage-account-manage)
- एक [Azure ब्लॉब संग्रहण कंटेनर](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- के लिये Azure Data Lake Storage Gen2, के बीच चुनें [मानक प्रदर्शन और प्रीमियम प्रदर्शन स्तर।](/azure/storage/blobs/create-data-lake-storage-account) अगर आप प्रीमियम प्रदर्शन स्तर चुनते हैं, तो [खाता प्रकार के रूप में प्रीमियम ब्लॉक ब्लॉब्स](/azure/storage/common/storage-account-overview#types-of-storage-accounts) चयन कर सकते है.

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>से कनेक्शन सेट करें Azure Data Lake Storage यूनिवर्सल Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **एज़्योर डेटा लेक जनरल 2**.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपने Azure Data Lake Storage Gen2 के लिए **अकाउंट नाम**, **अकाउंट कुंजी** और **कंटेनर** दर्ज करें.

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. में **निर्यात के लिए कनेक्शन** फ़ील्ड में, Azure डेटा लेक अनुभाग से एक कनेक्शन चुनें। यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. के लिए फ़ोल्डर का नाम दर्ज करें Azure Data Lake Storage Gen2 भंडारण।

1. उस प्रत्येक निकाय के सामने दिए गए बॉक्स को चुनें जिसे आप इस गंतव्य-स्थल में एक्सपोर्ट करना चाहते हैं.

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

निर्यात किया गया डेटा आपके द्वारा कॉन्फ़िगर किए गए Azure Data Lake Gen2 स्टोरेज कंटेनर में संग्रहीत किया जाता है.

> [!TIP]
> बड़ी मात्रा में डेटा वाले निकायों के निर्यात से प्रत्येक निर्यात के लिए एक ही फ़ोल्डर में एकाधिक CSV फ़ाइलें प्राप्त हो सकती हैं. निर्यात को पूरा करने में लगने वाले समय को कम करने के लिए प्रदर्शन कारणों से विभाजन निर्यात होता है।

[!INCLUDE [footer-include](includes/footer-banner.md)]
