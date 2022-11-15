---
title: कनेक्ट a Azure Synapse डेटा स्रोत (पूर्वावलोकन)
description: में एक डेटाबेस का प्रयोग करें Azure Synapse एक डेटा स्रोत के रूप में Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738158"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>कनेक्ट a Azure Synapse Analytics डेटा स्रोत (पूर्वावलोकन)

Azure Synapse Analytics एक उद्यम विश्लेषिकी सेवा है जो डेटा वेयरहाउस और बड़े डेटा सिस्टम में अंतर्दृष्टि के लिए समय को तेज करती है। Azure Synapse Analytics एंटरप्राइज़ डेटा वेयरहाउसिंग में उपयोग की जाने वाली सर्वोत्तम SQL तकनीकों को एक साथ लाता है, बड़े डेटा के लिए उपयोग की जाने वाली स्पार्क तकनीकें, लॉग और टाइम सीरीज़ एनालिटिक्स के लिए डेटा एक्सप्लोरर, डेटा एकीकरण के लिए पाइपलाइन और ETL/ELT, और अन्य Azure सेवाओं के साथ गहन एकीकरण जैसे किPower BI,Cosmos DB, और AzureML.

अधिक जानकारी के लिए देखें [Azure Synapse अवलोकन](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

> [!NOTE]
> Synapse कार्यस्थान जिनके पास है [फ़ायरवॉल सक्षम](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) वर्तमान में समर्थित नहीं हैं।
> [!IMPORTANT]
> सुनिश्चित करें कि वर्णित सभी **भूमिका असाइनमेंट** सेट किए जाएं.  

**ग्राहक अंतर्दृष्टि में**:

* आपके पास है **प्रशासक** ग्राहक अंतर्दृष्टि में भूमिका। के बारे में अधिक जानने [Customer Insights में उपयोगकर्ता अनुमतियाँ](permissions.md#add-users).

**अज़ूर में**:

- एक सक्रिय Azure सदस्यता.

- यदि एक नया उपयोग कर रहे हैं Azure Data Lake Storage Gen2 खाता, *Insights के लिए सेवा प्रिंसिपल* जो "Dynamics 365 AI for Customer Insights" आवश्यकता है **संग्रहण ब्लॉब डेटा सहयोगी** अनुमतियाँ। के बारे में अधिक जानने [एक से जुड़नाAzure Data Lake Storage Customer Insights के लिए सेवा प्रिंसिपल के साथ](connect-service-principal.md). Data Lake Storage Gen2 में [पदानुक्रमिक नामस्थान](/azure/storage/blobs/data-lake-storage-namespace) **अवश्य** सक्षम होना चाहिए.

- संसाधन समूह पर Azure Synapse कार्यक्षेत्र स्थित है, *सेवा प्रधान* जो "Dynamics 365 AI for Customer Insights" है और *Customer Insights के लिए उपयोगकर्ता* कम से कम असाइन करने की आवश्यकता है **रीडर** अनुमतियाँ। अधिक जानकारी के लिए देखें, [Azure पोर्टल का उपयोग करके Azure भूमिकाएं असाइन करें](/azure/role-based-access-control/role-assignments-portal).

- *उपयोगकर्ता* को Azure Data Lake Storage Gen2 खाते पर **स्टोरेज ब्लॉब डेटा योगदानकर्ता** अनुमतियां आवश्यक होती हैं, जहां डेटा स्थित होता है और Azure Synapse कार्यक्षेत्र से जुड़ा होता है. [ब्लॉब और क्यू डेटा तक पहुंचने हेतु एक Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना के बारे में](/azure/storage/common/storage-auth-aad-rbac-portal) और [संग्रहण ब्लॉब डेटा योगदानकर्ता अनुमतियां](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.

- *[Azure Synapse कार्यक्षेत्र प्रबंधित पहचान](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* को Azure Data Lake Storage Gen2 खाता पर जहां डेटा स्थित है और Azure Synapse कार्यक्षेत्र से जुड़ा हुआ है, वहां **स्टोरेज ब्लॉब डेटा योगदानकर्ता** अनुमतियां आवश्यक हैं. [ब्लॉब और क्यू डेटा तक पहुंच के लिए Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना](/azure/storage/common/storage-auth-aad-rbac-portal) और [ब्लॉब डेटा योगदानकर्ता अनुमतियां संग्रहण](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.

- पर Azure Synapse कार्यक्षेत्र, *Customer Insights के लिए सेवा प्रिंसिपल* जो "Dynamics 365 AI for Customer Insights" आवश्यकता है **सिनैप्स एडमिनिस्ट्रेटर** भूमिका सौंपी। **उपयोगकर्ता** कम से कम एक की जरूरत है **सिनैप्स सहयोगी** कार्यक्षेत्र के लिए सौंपी गई भूमिका। अधिक जानकारी के लिए देखें, [अपने Synapse कार्यक्षेत्र के लिए पहुंच नियंत्रण कैसे सेट करें](/azure/synapse-analytics/security/how-to-set-up-access-control).

- यदि आपका Customer Insights परिवेश आपके डेटा को संग्रहीत करता है [अपनाAzure Data Lake Storage](own-data-lake-storage.md), उपयोगकर्ता जो कनेक्शन सेट करता है Azure Synapse Analytics कम से कम बिल्ट-इन की जरूरत है **रीडर** डेटा लेक स्टोरेज खाते पर भूमिका। अधिक जानकारी के लिए देखें, [Azure पोर्टल का उपयोग करके Azure भूमिकाएं असाइन करें](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>डेटा लेक डेटाबेस से कनेक्ट करें Azure Synapse Analytics

1. **डेटा** > **डेटा स्रोत** पर जाएँ.

1. **डेटा स्रोत जोड़ें** को चुनें.

1. चुनना**Azure Synapse Analytics (पूर्वावलोकन)** तरीका।

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Synapse Analytics डेटा से कनेक्ट करने के लिए डायलॉग बॉक्स":::
  
1. प्रवेश करें **नाम** डेटा स्रोत और एक वैकल्पिक के लिए **विवरण**.

1. एक चुनें [उपलब्ध कनेक्शन](connections.md) प्रतिAzure Synapse Analytics या[एक नया बनाएँ](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. चुनें **डेटाबेस** चयनित में जुड़े कार्यक्षेत्र से Azure Synapse Analytics कनेक्शन और चुनें **अगला**. वर्तमान में, हम केवल डेटाबेस प्रकार का समर्थन करते हैं *झील डेटाबेस*.

1. कनेक्टेड डेटाबेस से अंतर्ग्रहण करने के लिए निकायों का चयन करें और चुनें **अगला।**

1. वैकल्पिक रूप से, डेटा प्रोफ़ाइल चालू करने की अनुमति देने के लिए डेटा निकाय चुनें.

1. चुनना**बचाना** अपने चयन को लागू करने और अपने नए बनाए गए डेटा स्रोत से डेटा का अंतर्ग्रहण शुरू करने के लिए Azure Synapse Analytics. **डेटा स्रोत** पेज में नया डेटा स्रोत दिखा रहा है **रिफ्रेशिंग** दर्जा।

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

डेटा लोड होने में समय लग सकता है। एक सफल रीफ़्रेश के बाद, अंतर्ग्रहीत डेटा की समीक्षा की जा सकती है [**संस्थाओं**](entities.md) पृष्ठ।

[!INCLUDE [footer-include](includes/footer-banner.md)]
