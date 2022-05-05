---
title: से डेटा निगलनाAzure Synapse Analytics
description: में एक डेटाबेस का प्रयोग करें Azure Synapse एक डेटा स्रोत के रूप में Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642652"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>कनेक्ट a Azure Synapse डेटा स्रोत (पूर्वावलोकन)

Azure Synapse Analytics एक उद्यम विश्लेषिकी सेवा है जो डेटा वेयरहाउस और बड़े डेटा सिस्टम में अंतर्दृष्टि के लिए समय को तेज करती है। Azure Synapse Analytics एंटरप्राइज़ डेटा वेयरहाउसिंग में उपयोग की जाने वाली सर्वोत्तम SQL तकनीकों को एक साथ लाता है, बड़े डेटा के लिए उपयोग की जाने वाली स्पार्क तकनीकें, लॉग और टाइम सीरीज़ एनालिटिक्स के लिए डेटा एक्सप्लोरर, डेटा एकीकरण और ETL/ELT के लिए पाइपलाइन, और अन्य Azure सेवाओं जैसे गहन एकीकरण के साथ।Power BI,Cosmos DB, और AzureML.

अधिक जानकारी के लिए देखें [Azure Synapse अवलोकन](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

से कनेक्शन को कॉन्फ़िगर करने के लिए निम्नलिखित पूर्वापेक्षाएँ पूरी होनी चाहिए Dynamics 365 Customer Insights कोAzure Synapse.

> [!IMPORTANT]
> सुनिश्चित करें कि वर्णित सभी **भूमिका असाइनमेंट** सेट किए जाएं.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights में पूर्वापेक्षाएं

* आपके पास है **प्रशासक** ग्राहक अंतर्दृष्टि में भूमिका। के बारे में अधिक जानने [Customer Insights में उपयोगकर्ता अनुमतियाँ](permissions.md#assign-roles-and-permissions).

Azure में: 

- एक सक्रिय Azure सदस्यता.

- यदि एक नया उपयोग कर रहे हैं Azure Data Lake Storage Gen2 खाता, *Insights के लिए सेवा प्रिंसिपल* ज़रूरत **संग्रहण ब्लॉब डेटा सहयोगी** अनुमतियाँ। के बारे में अधिक जानने [एक से जुड़नाAzure Data Lake Storage Customer Insights के लिए सेवा प्रिंसिपल के साथ](connect-service-principal.md). Data Lake Storage Gen2 में [पदानुक्रमिक नामस्थान](/azure/storage/blobs/data-lake-storage-namespace) **अवश्य** सक्षम होना चाहिए.

- संसाधन समूह पर Azure Synapse कार्यक्षेत्र स्थित है, *सेवा प्रधान* और यह *Customer Insights के लिए उपयोगकर्ता* कम से कम असाइन करने की आवश्यकता है **रीडर** अनुमतियाँ। अधिक जानकारी के लिए देखें, [Azure पोर्टल का उपयोग करके Azure भूमिकाएं असाइन करें](/azure/role-based-access-control/role-assignments-portal).

- *उपयोगकर्ता* को Azure Data Lake Storage Gen2 खाते पर **स्टोरेज ब्लॉब डेटा योगदानकर्ता** अनुमतियां आवश्यक होती हैं, जहां डेटा स्थित होता है और Azure Synapse कार्यक्षेत्र से जुड़ा होता है. [ब्लॉब और क्यू डेटा तक पहुंचने हेतु एक Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना के बारे में](/azure/storage/common/storage-auth-aad-rbac-portal) और [संग्रहण ब्लॉब डेटा योगदानकर्ता अनुमतियां](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.

- *[Azure Synapse कार्यक्षेत्र प्रबंधित पहचान](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* को Azure Data Lake Storage Gen2 खाता पर जहां डेटा स्थित है और Azure Synapse कार्यक्षेत्र से जुड़ा हुआ है, वहां **स्टोरेज ब्लॉब डेटा योगदानकर्ता** अनुमतियां आवश्यक हैं. [ब्लॉब और क्यू डेटा तक पहुंच के लिए Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना](/azure/storage/common/storage-auth-aad-rbac-portal) और [ब्लॉब डेटा योगदानकर्ता अनुमतियां संग्रहण](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.

- पर Azure Synapse कार्यक्षेत्र, *Customer Insights के लिए सेवा प्रिंसिपल* ज़रूरत **सिनैप्स एडमिनिस्ट्रेटर** भूमिका सौंपी। अधिक जानकारी के लिए देखें, [अपने Synapse कार्यक्षेत्र के लिए पहुंच नियंत्रण कैसे सेट करें](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>में डेटा लेक डेटाबेस से कनेक्ट करें Azure Synapse Analytics

1. **डेटा** > **डेटा स्रोत** पर जाएँ.

1. **डेटा स्रोत जोड़ें** को चुनें.

1. चुनें **Azure Synapse Analytics (पूर्वावलोकन)** तरीका।

1. डेटा स्रोत के लिए एक **नाम** प्रदान करें और डेटा स्रोत बनाने के लिए **अगला** चुनें. 

1. एक चुनें [उपलब्ध कनेक्शन](connections.md) कोAzure Synapse Analytics या एक नया बनाएँ।

1. एक विकल्प चुनें **झील डेटाबेस** चयनित में जुड़े कार्यक्षेत्र से Azure Synapse Analytics कनेक्शन और चुनें **अगला**.

1. कनेक्टेड डेटाबेस से अंतर्ग्रहण करने के लिए निकायों का चयन करें। 

1. वैकल्पिक रूप से, डेटा प्रोफ़ाइल चालू करने की अनुमति देने के लिए डेटा निकाय चुनें. 

1. चुनना**बचाना** अपने चयन को लागू करने के लिए और अपने नए बनाए गए डेटा स्रोत से डेटा का अंतर्ग्रहण शुरू करने के लिए झील डेटाबेस तालिकाओं से जुड़ा हुआ है Azure Synapse Analytics.
