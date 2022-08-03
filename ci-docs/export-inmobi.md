---
title: InMobi में Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और इनमोबी को निर्यात करने का तरीका जानें।
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195890"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Customer Insights डेटा को InMobi में निर्यात करें (पूर्वावलोकन)

अपने Customer Insights इंस्टेंस से सेगमेंट सूचियों या अन्य डेटा को निर्यात करें [इनमोबी।](https://www.inmobi.com/)

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- एक [इनमोबी खाता](https://www.inmobi.com/) और व्यवस्थापक क्रेडेंशियल।
- एक [Azure ब्लॉब संग्रहण खाता](/azure/storage/blobs/create-data-lake-storage-account) नाम और खाता कुंजी। नाम और कुंजी खोजने के लिए, देखें [Azure पोर्टल में संग्रहण खाता सेटिंग प्रबंधित करें।](/azure/storage/common/storage-account-manage)
- एक [Azure ब्लॉब संग्रहण कंटेनर](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) को InMobi डेटा निर्यात करने के लिए।
- इनमोबी आपके ब्लॉब स्टोरेज से सीधा कनेक्शन बनाएगा, और आपके डेटा के स्वचालित आयात को इनमोबी में कॉन्फ़िगर करेगा। प्रक्रिया शुरू करने के लिए अपने इनमोबी प्रतिनिधि से संपर्क करें।

## <a name="known-limitations"></a>ज्ञात सीमाएँ

- Azure ब्लॉब संग्रहण के लिए, इनमें से चुनें [मानक प्रदर्शन और प्रीमियम प्रदर्शन स्तर।](/azure/storage/blobs/storage-blob-performance-tiers) अगर आप प्रीमियम प्रदर्शन स्तर चुनते हैं, तो [खाता प्रकार के रूप में प्रीमियम ब्लॉक ब्लॉब्स](/azure/storage/common/storage-account-overview#types-of-storage-accounts) चयन कर सकते है.

## <a name="set-up-connection-to-azure-blob-storage"></a>Azure ब्लॉब संग्रहण से कनेक्शन सेट करें

[अपने Azure ब्लॉब संग्रहण से कनेक्शन सेट करें](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[निर्यात कॉन्फ़िगर करें](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
