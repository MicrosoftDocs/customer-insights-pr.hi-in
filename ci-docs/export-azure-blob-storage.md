---
title: एक Azure ब्लॉब स्टोरेज के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और ब्लॉब स्टोरेज विज्ञापन प्रबंधक को निर्यात करने का तरीका जानें.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3d573a6c83b7f0b0c33e656eb383e20a96856b0b
ms.sourcegitcommit: d45c00a5f6cb106714366af81e8070e7f53654b3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/15/2022
ms.locfileid: "8757388"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Azure ब्लॉब स्टोरेज (पूर्वावलोकन) के लिए सेगमेंट सूची और अन्य डेटा को निर्यात करें

अपने Customer Insights डेटा को ब्लॉब स्टोरेज में स्टोर करें या इसका इस्तेमाल अपने डेटा को दूसरे एप्लिकेशन में भेजने के लिए करें.

## <a name="known-limitations"></a>ज्ञात सीमाएँ

1. Azure Blob Storage के लिए आप [स्टैंडर्ड प्रदर्शन और प्रीमियम प्रदर्शन स्तर](/azure/storage/blobs/storage-blob-performance-tiers) के बीच चयन कर सकते हैं. अगर आप प्रीमियम प्रदर्शन स्तर चुनते हैं, तो [खाता प्रकार के रूप में प्रीमियम ब्लॉक ब्लॉब्स](/azure/storage/common/storage-account-overview#types-of-storage-accounts) चयन कर सकते है.

## <a name="set-up-the-connection-to-blob-storage"></a>ब्लॉब संग्रहण में कनेक्शन सेट अप करें

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. **कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Azure ब्लॉब संग्रहण** चुनें.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. अपने ब्लॉब स्टोरेज अकाउंट के लिए **अकाउंट का नाम**, **अकाउंट की कुंजी**, और **कंटेनर** दर्ज करें.
    - Blob संग्रहण खाते का नाम और खाता कुंजी खोजने के तरीके के बारे में अधिक जानने के लिए, [Azure पोर्टल में संग्रहण खाता सेटिंग्स का प्रबंधन करें](/azure/storage/common/storage-account-manage) देखें।
    - कंटेनर बनाने के बारे में जानने के लिए, [कंटेनर बनाएँ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) देखें.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें. 

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> यदि आपने Azure ब्लॉब स्टोरेज खाते के लिए सॉफ्ट डिलीट सेटिंग चालू की है, तो निर्यात विफल हो जाएगा. ब्लॉब में डेटा निर्यात करने के लिए सॉफ्ट डिलीट को बंद करें. अधिक जानकारी के लिए, [ब्लॉब सॉफ्ट डिलीट सक्षम करें](/azure/storage/blobs/soft-delete-blob-enable) देखें

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** में, Azure Blob Storage अनुभाग से एक कनेक्शन का चयन करें. यदि आपको यह अनुभाग नाम नहीं दिखता है, तो इस प्रकार का कोई भी कनेक्शन आपके लिए उपलब्ध नहीं है।

1. उस प्रत्येक निकाय के सामने दिए गए बॉक्स को चुनें जिसे आप इस गंतव्य-स्थल में एक्सपोर्ट करना चाहते हैं.

1. **सहेजें** चुनें.

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.     

आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं. 

निर्यात किया गया डेटा आपके द्वारा कॉन्फ़िगर किए गए ब्लॉब स्टोरेज कंटेनर में संग्रहीत किया जाता है. आपके कंटेनर में निम्नलिखित फोल्डर पथ अपने आप बनेंगे:

- स्रोत निकायों और सिस्टम द्वारा उत्पन्न स्रोत निकायों के लिए:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - उदाहरण: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- निर्यात किए गए निकायों के लिए model.json %ExportDestinationName% स्तर पर होगा.  
  - उदाहरण: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
