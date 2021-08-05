---
title: Customer Insights डेटा Azure Synapse Analytics में निर्यात करें
description: Azure Synapse Analytics से कनेक्शन को कॉन्फ़िगर करने की विधि जानें.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7ee57aa9e86ebf9bd1989d88750642f0b01bd4bf
ms.sourcegitcommit: f18635c29bb25d9e424a3f5825dc2696278450cf
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/30/2021
ms.locfileid: "6327366"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Azure Synapse Analytics में डेटा निर्यात करें (पूर्वावलोकन)

Azure Synapse विश्लेषण सेवा है, जो डेटा वेयरहाउस और बड़े डेटा सिस्टम में इनसाइट के लिए समय की गति को बढ़ाती है. आप [Azure Synapse](/azure/synapse-analytics/overview-what-is) में अपने Customer Insights डेटा को अंतर्ग्रहित करके उसका उपयोग कर सकते हैं.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

Customer Insights से Azure Synapse में कनेक्शन कॉन्फ़िगर करने के लिए निम्नलिखित पूर्वापेक्षाएं पूरी होनी चाहिए.

> [!NOTE]
> सुनिश्चित करें कि वर्णित सभी **भूमिका असाइनमेंट** सेट किए जाएं.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights में पूर्वापेक्षाएं

* ऑडियंस इनसाइट में आपकी **व्यवस्थापक** की भूमिका होती है. [ऑडिएंस इनसाइट्स में उपयोगकर्ता अनुमतियां सेटिंग्स](permissions.md#assign-roles-and-permissions) के बारे में और अधिक जानें

Azure में: 

- एक सक्रिय Azure सदस्यता.

- यदि एक नए Azure Data Lake Storage Gen2 खाते का उपयोग कर रहे हैं, तो *ऑडिएंस इनसाइट के लिए सेवा प्रिंसिपल* को **स्टोरेज ब्लॉब डेटा योगदानकर्ता** अनुमतियों की आवश्यकता होती है. [ऑडिएंस इनसाइट के लिए Azure सेवा प्रिंसिपल के साथ Azure Data Lake Storage Gen2 खाते से कनेक्ट करने](connect-service-principal.md) के बारे में और जानें. Data Lake Storage Gen2 में [पदानुक्रमिक नामस्थान](/azure/storage/blobs/data-lake-storage-namespace) **अवश्य** सक्षम होना चाहिए.

- संसाधन समूह पर Azure Synapse कार्यस्थान स्थित है, *सर्विस प्रिंसिपल* और *ऑडियंस इनसाइट के लिए उपयोगकर्ता* को कम से कम **रीडर** अनुमतियां असाइन करना आवश्यक है. अधिक जानकारी के लिए देखें, [Azure पोर्टल का उपयोग करके Azure भूमिकाएं असाइन करें](/azure/role-based-access-control/role-assignments-portal).

- *उपयोगकर्ता* को Azure Data Lake Storage Gen2 खाते पर **स्टोरेज ब्लॉब डेटा योगदानकर्ता** अनुमतियां आवश्यक होती हैं, जहां डेटा स्थित होता है और Azure Synapse कार्यक्षेत्र से जुड़ा होता है. [ब्लॉब और क्यू डेटा तक पहुंचने हेतु एक Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना के बारे में](/azure/storage/common/storage-auth-aad-rbac-portal) और [संग्रहण ब्लॉब डेटा योगदानकर्ता अनुमतियां](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.

- *[Azure Synapse कार्यक्षेत्र प्रबंधित पहचान](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* को Azure Data Lake Storage Gen2 खाता पर जहां डेटा स्थित है और Azure Synapse कार्यक्षेत्र से जुड़ा हुआ है, वहां **स्टोरेज ब्लॉब डेटा योगदानकर्ता** अनुमतियां आवश्यक हैं. [ब्लॉब और क्यू डेटा तक पहुंच के लिए Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना](/azure/storage/common/storage-auth-aad-rbac-portal) और [ब्लॉब डेटा योगदानकर्ता अनुमतियां संग्रहण](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.

- Azure Synapse कार्यस्थान पर, *ऑडिएंस इनसाइट के लिए सेवा प्रिंसिपल* को **Synapse व्यवस्थापक** भूमिका असाइन की जानी चाहिए. अधिक जानकारी के लिए देखें, [अपने Synapse कार्यक्षेत्र के लिए पहुंच नियंत्रण कैसे सेट करें](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>कनेक्शन सेट करें और Azure Synapse में निर्यात करें

### <a name="configure-a-connection"></a>एक कनेक्शन कॉन्फ़िगर करें

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. **कनेक्शन जोड़ें** चुनें और **Azure Synapse विश्लेषण** चुनें या कनेक्शन कॉन्फ़िगर करने के लिए **Azure Synapse विश्लेषण** टाइल पर **सेट अप करें** चुनें.

1. डिस्प्ले नाम फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. जिस सदस्यता में आप Customer Insights डेटा का उपयोग करना चाहते हैं, उसे चुनें और खोजें. सदस्यता के चयन के साथ ही आप **कार्यस्थान**, **संग्रहण खाता** और **कंटेनर** भी चुन सकते हैं.

1. कनेक्शन सहेजने के लिए **सहेजें** चुनें.

### <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. अधिक जानकारी के लिए, देखें [निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **निर्यात जोड़ें** का चयन करें.

1. **निर्यात के लिए कनेक्शन** फ़ील्ड में, **Azure Synapse विश्लेषण** अनुभाग से एक कनेक्शन चुनें. यदि आप इस अनुभाग का नाम नहीं देखते हैं, तो आपके लिए इस प्रकार का कोई [कनेक्शन](connections.md) उपलब्ध नहीं है.

1. अपने निर्यात के लिए एक पहचानने योग्य **प्रदर्शन नाम** और एक **डेटाबेस नाम** प्रदान करें.

1. आप किन निकायों को Azure Synapse Analytics में निर्यात करना चाहते हैं उनका चयन करें.
   > [!NOTE]
   > [Common Data Model फ़ोल्डर](connect-common-data-model.md) पर आधारित डेटा स्रोत समर्थित नहीं हैं.

2. **सहेजें** चुनें.

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है. आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.

### <a name="update-an-export"></a>निर्यात अपडेट करें

1. **डेटा** > **निर्यात** पर जाएँ.

1. जिसे आप अपडेट करना चाहते हैं उस निर्यात पर **संपादित करें** चुनें.

   - चयन से निकायों को **जोड़ें** या **निकालें**. यदि निकायों को चयन से निकाल दिया जाता है, पर उन्हें Synapse Analytics डेटाबेस से नहीं हटाया जाता है. हालांकि, भविष्य में किए जाने वाले डेटा रीफ़्रेश में उस डेटाबेस में निकाले गए निकायों को अपडेट नहीं किया जाएगा.

   - **डेटाबेस का नाम बदलना** एक नया Synapse Analytics डेटाबेस बनाता है. उस नाम वाला डेटाबेस, जिसे पहले कॉन्फ़िगर किया गया था, भविष्य के रीफ़्रेश में उसे कोई अपडेट प्राप्त नहीं होगा.
