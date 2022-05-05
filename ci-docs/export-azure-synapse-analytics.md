---
title: Customer Insights डेटा निर्यात करें Azure Synapse Analytics
description: से कनेक्शन कॉन्फ़िगर करने का तरीका जानें Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e77227e1e353c02cfb13e26a8ecbe0768ba6c0fa
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642552"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>डेटा निर्यात करें Azure Synapse Analytics (पूर्वावलोकन)

Azure Synapse विश्लेषण सेवा है, जो डेटा वेयरहाउस और बड़े डेटा सिस्टम में इनसाइट के लिए समय की गति को बढ़ाती है. आप [Azure Synapse](/azure/synapse-analytics/overview-what-is) में अपने Customer Insights डेटा को अंतर्ग्रहित करके उसका उपयोग कर सकते हैं.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

Customer Insights से Azure Synapse में कनेक्शन कॉन्फ़िगर करने के लिए निम्नलिखित पूर्वापेक्षाएं पूरी होनी चाहिए.

> [!NOTE]
> सुनिश्चित करें कि वर्णित सभी **भूमिका असाइनमेंट** सेट किए जाएं.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights में पूर्वापेक्षाएं

* तुम्हारीAzure Active Directory (एडी) उपयोगकर्ता खाते में एक है **प्रशासक** ग्राहक अंतर्दृष्टि में भूमिका। के बारे में अधिक जानने [उपयोगकर्ता अनुमतियाँ सेट करना।](permissions.md#assign-roles-and-permissions)

Azure में: 

- एक सक्रिय Azure सदस्यता.

- यदि एक नया उपयोग कर रहे हैं Azure Data Lake Storage Gen2 खाता, *Insights के लिए सेवा प्रिंसिपल* ज़रूरत **संग्रहण ब्लॉब डेटा सहयोगी** अनुमतियाँ। [ऑडिएंस इनसाइट के लिए Azure सेवा प्रिंसिपल के साथ Azure Data Lake Storage Gen2 खाते से कनेक्ट करने](connect-service-principal.md) के बारे में और जानें. Data Lake Storage Gen2 में [पदानुक्रमिक नामस्थान](/azure/storage/blobs/data-lake-storage-namespace) **अवश्य** सक्षम होना चाहिए.

- संसाधन समूह पर जहां Azure Synapse कार्यक्षेत्र स्थित है, *सेवा प्रधान* और यह *Azure AD Customer Insights में व्यवस्थापक अनुमतियों वाला उपयोगकर्ता* कम से कम असाइन करने की आवश्यकता है **रीडर** अनुमतियाँ। अधिक जानकारी के लिए देखें, [Azure पोर्टल का उपयोग करके Azure भूमिकाएं असाइन करें](/azure/role-based-access-control/role-assignments-portal).

- *Azure AD Customer Insights में व्यवस्थापक अनुमतियों वाला उपयोगकर्ता* ज़रूरत **संग्रहण ब्लॉब डेटा सहयोगी** पर अनुमतियाँ Azure Data Lake Storage Gen2 खाता जहां डेटा स्थित है और से जुड़ा हुआ है Azure Synapse कार्यक्षेत्र। [ब्लॉब और क्यू डेटा तक पहुंचने हेतु एक Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना के बारे में](/azure/storage/common/storage-auth-aad-rbac-portal) और [संग्रहण ब्लॉब डेटा योगदानकर्ता अनुमतियां](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.

- *[Azure Synapse कार्यक्षेत्र प्रबंधित पहचान](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* को Azure Data Lake Storage Gen2 खाता पर जहां डेटा स्थित है और Azure Synapse कार्यक्षेत्र से जुड़ा हुआ है, वहां **स्टोरेज ब्लॉब डेटा योगदानकर्ता** अनुमतियां आवश्यक हैं. [ब्लॉब और क्यू डेटा तक पहुंच के लिए Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना](/azure/storage/common/storage-auth-aad-rbac-portal) और [ब्लॉब डेटा योगदानकर्ता अनुमतियां संग्रहण](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.

- पर Azure Synapse कार्यक्षेत्र, *Customer Insights के लिए सेवा प्रिंसिपल* ज़रूरत **सिनैप्स एडमिनिस्ट्रेटर** भूमिका सौंपी। अधिक जानकारी के लिए देखें, [अपने Synapse कार्यक्षेत्र के लिए पहुंच नियंत्रण कैसे सेट करें](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>कनेक्शन सेट करें और Azure Synapse में निर्यात करें

### <a name="configure-a-connection"></a>एक कनेक्शन कॉन्फ़िगर करें

कनेक्शन बनाने के लिए, Customer Insights में सेवा प्रिंसिपल और उपयोगकर्ता खाते की आवश्यकता होती है **रीडर** पर अनुमतियाँ *संसाधन समूह* जहां Synapse Analytics कार्यक्षेत्र स्थित है। इसके अतिरिक्त, सेवा प्रिंसिपल और Synapse Analytics कार्यस्थान पर उपयोगकर्ता की आवश्यकता है **सिनैप्स एडमिनिस्ट्रेटर** अनुमतियाँ। 

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **Azure Synapse Analytics** या चुनें **स्थापित करना** पर **Azure Synapse Analytics** कनेक्शन को कॉन्फ़िगर करने के लिए टाइल।

1. डिस्प्ले नाम फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. जिस सदस्यता में आप Customer Insights डेटा का उपयोग करना चाहते हैं, उसे चुनें और खोजें. सदस्यता के चयन के साथ ही आप **कार्यस्थान**, **संग्रहण खाता** और **कंटेनर** भी चुन सकते हैं.

1. कनेक्शन सहेजने के लिए **सहेजें** चुनें.

### <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं. एक साझा कनेक्शन के साथ निर्यात को कॉन्फ़िगर करने के लिए, आपको कम से कम चाहिए **सहयोगी** Customer Insights में अनुमतियाँ। अधिक जानकारी के लिए, देखें [निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).

1. **डेटा** > **निर्यात** पर जाएँ.

1. एक नया निर्यात बनाने के लिए, **निर्यात जोड़ें** का चयन करें.

1. में **निर्यात के लिए कनेक्शन** फ़ील्ड, से एक कनेक्शन चुनें **Azure Synapse Analytics** खंड। यदि आप इस अनुभाग का नाम नहीं देखते हैं, तो आपके लिए इस प्रकार का कोई [कनेक्शन](connections.md) उपलब्ध नहीं है.

1. अपने निर्यात के लिए एक पहचानने योग्य **प्रदर्शन नाम** और एक **डेटाबेस नाम** प्रदान करें.

1. चुनें कि आप किन इकाइयों को निर्यात करना चाहते हैं Azure Synapse Analytics.
   > [!NOTE]
   > [Common Data Model फ़ोल्डर](connect-common-data-model.md) पर आधारित डेटा स्रोत समर्थित नहीं हैं.

2. **सहेजें** चुनें.

निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.

निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है. आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.

Synapse Analytics को निर्यात किए गए डेटा को क्वेरी करने के लिए, आपको चाहिए **संग्रहण ब्लॉब डेटा रीडर** निर्यात के कार्यक्षेत्र पर गंतव्य भंडारण तक पहुंच। 

### <a name="update-an-export"></a>निर्यात अपडेट करें

1. **डेटा** > **निर्यात** पर जाएँ.

1. जिसे आप अपडेट करना चाहते हैं उस निर्यात पर **संपादित करें** चुनें.

   - चयन से निकायों को **जोड़ें** या **निकालें**. यदि निकायों को चयन से निकाल दिया जाता है, पर उन्हें Synapse Analytics डेटाबेस से नहीं हटाया जाता है. हालांकि, भविष्य में किए जाने वाले डेटा रीफ़्रेश में उस डेटाबेस में निकाले गए निकायों को अपडेट नहीं किया जाएगा.

   - **डेटाबेस का नाम बदलना** एक नया Synapse Analytics डेटाबेस बनाता है. उस नाम वाला डेटाबेस, जिसे पहले कॉन्फ़िगर किया गया था, भविष्य के रीफ़्रेश में उसे कोई अपडेट प्राप्त नहीं होगा.
