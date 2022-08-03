---
title: Azure ब्लॉब संग्रहण में डेटा निर्यात करें (पूर्वावलोकन)
description: कनेक्शन को कॉन्फ़िगर करने और ब्लॉब स्टोरेज विज्ञापन प्रबंधक को निर्यात करने का तरीका जानें.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195706"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Azure ब्लॉब संग्रहण में डेटा निर्यात करें (पूर्वावलोकन)

अपने Customer Insights डेटा को ब्लॉब स्टोरेज में स्टोर करें या इसका इस्तेमाल अपने डेटा को दूसरे एप्लिकेशन में भेजने के लिए करें.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- एक [Azure ब्लॉब संग्रहण खाता](/azure/storage/blobs/create-data-lake-storage-account) नाम और खाता कुंजी। नाम और कुंजी खोजने के लिए, देखें [Azure पोर्टल में संग्रहण खाता सेटिंग प्रबंधित करें।](/azure/storage/common/storage-account-manage)
- एक [Azure ब्लॉब संग्रहण कंटेनर](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- Azure ब्लॉब संग्रहण के लिए, इनमें से चुनें [मानक प्रदर्शन और प्रीमियम प्रदर्शन स्तर।](/azure/storage/blobs/storage-blob-performance-tiers) अगर आप प्रीमियम प्रदर्शन स्तर चुनते हैं, तो [खाता प्रकार के रूप में प्रीमियम ब्लॉक ब्लॉब्स](/azure/storage/common/storage-account-overview#types-of-storage-accounts) चयन कर सकते है.

## <a name="set-up-connection-to-blob-storage"></a>ब्लॉब स्टोरेज से कनेक्शन सेट करें

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **Azure ब्लॉब संग्रहण**.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपने ब्लॉब स्टोरेज अकाउंट के लिए **अकाउंट का नाम**, **अकाउंट की कुंजी**, और **कंटेनर** दर्ज करें.

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

इस निर्यात को कॉन्फ़िगर करने के लिए, आपके पास होना चाहिए [अनुमति](export-destinations.md#set-up-a-new-export) इस कनेक्शन प्रकार के लिए।

> [!IMPORTANT]
> यदि आपने चालू किया है [सॉफ्ट डिलीट सेटिंग](/azure/storage/blobs/soft-delete-blob-enable) Azure ब्लॉब संग्रहण खाते के लिए, निर्यात विफल हो जाएगा। ब्लॉब में डेटा निर्यात करने के लिए सॉफ्ट डिलीट को बंद करें.

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. **निर्यात के लिए कनेक्शन** में, Azure Blob Storage अनुभाग से एक कनेक्शन का चयन करें. यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. निर्यात के लिए एक नाम दर्ज करें।

1. ब्लॉब स्टोरेज के लिए फ़ोल्डर का नाम दर्ज करें।

1. उस प्रत्येक निकाय के सामने दिए गए बॉक्स को चुनें जिसे आप इस गंतव्य-स्थल में एक्सपोर्ट करना चाहते हैं.

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

निर्यात किया गया डेटा आपके द्वारा कॉन्फ़िगर किए गए ब्लॉब स्टोरेज कंटेनर में संग्रहीत किया जाता है. आपके कंटेनर में निम्नलिखित फोल्डर पथ अपने आप बनेंगे:

- स्रोत निकायों और सिस्टम द्वारा उत्पन्न स्रोत निकायों के लिए:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  उदाहरण: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > बड़ी मात्रा में डेटा वाले निकायों के निर्यात से प्रत्येक निर्यात के लिए एक ही फ़ोल्डर में एकाधिक CSV फ़ाइलें प्राप्त हो सकती हैं. निर्यात को पूरा करने में लगने वाले समय को कम करने के लिए प्रदर्शन कारणों से विभाजन निर्यात होता है।

- निर्यात की गई इकाइयों के लिए model.json यहां रहता है *%ExportDestinationName%* स्तर।  
  
  उदाहरण: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /ब्लॉबएक्सपोर्ट/मॉडल.जेसन

[!INCLUDE [footer-include](includes/footer-banner.md)]
