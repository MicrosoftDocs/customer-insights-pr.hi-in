---
title: InMobi में Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और इनमोबी को निर्यात करने का तरीका जानें।
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059609"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>सेगमेंट सूची और अन्य डेटा को इनमोबी में निर्यात करें (पूर्वावलोकन)

अपने Customer Insights इंस्टेंस से सेगमेंट सूचियों या अन्य डेटा को निर्यात करें [इनमोबी।](https://www.inmobi.com/)

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

1. आपके पास है [इनमोबी खाता](https://www.inmobi.com/) और व्यवस्थापक क्रेडेंशियल।
1. आपके पास Azure Blob संग्रहण खाता नाम और संबंधित खाता कुंजी है। अधिक जानकारी के लिए देखें [Azure पोर्टल में संग्रहण खाता सेटिंग प्रबंधित करें।](/azure/storage/common/storage-account-manage) इनमोबी डेटा को निर्यात करने के लिए स्टोरेज खाते में एक कंटेनर है। अधिक जानकारी के लिए देखें [एक कंटेनर बनाएं।](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)
1. इनमोबी आपके ब्लॉब स्टोरेज से सीधा कनेक्शन बनाएगा, और आपके डेटा के स्वचालित आयात को इनमोबी में कॉन्फ़िगर करेगा। प्रक्रिया शुरू करने के लिए अपने इनमोबी प्रतिनिधि से संपर्क करें।

## <a name="known-limitations"></a>ज्ञात सीमाएँ

1. Azure ब्लॉब संग्रहण के लिए, आप इनमें से चुन सकते हैं [मानक प्रदर्शन और प्रीमियम प्रदर्शन स्तर](/azure/storage/blobs/storage-blob-performance-tiers). अगर आप प्रीमियम प्रदर्शन स्तर चुनते हैं, तो [खाता प्रकार के रूप में प्रीमियम ब्लॉक ब्लॉब्स](/azure/storage/common/storage-account-overview#types-of-storage-accounts) चयन कर सकते है.

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Azure ब्लॉब संग्रहण से कनेक्शन सेट करें और एक निर्यात कॉन्फ़िगर करें

1. करने के लिए निर्देशों का पालन करें [अपने Azure ब्लॉब संग्रहण से एक कनेक्शन सेटअप करें](export-azure-blob-storage.md).
2. करने के लिए निर्देशों का पालन करें [एक निर्यात कॉन्फ़िगर करें](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
