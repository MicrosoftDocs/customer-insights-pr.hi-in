---
title: डेटा निर्यात करें Azure Synapse Analytics (पूर्व दर्शन)
description: से कनेक्शन कॉन्फ़िगर करने का तरीका जानें Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196396"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>डेटा निर्यात करें Azure Synapse Analytics (पूर्व दर्शन)

Azure Synapse विश्लेषण सेवा है, जो डेटा वेयरहाउस और बड़े डेटा सिस्टम में इनसाइट के लिए समय की गति को बढ़ाती है. आप [Azure Synapse](/azure/synapse-analytics/overview-what-is) में अपने Customer Insights डेटा को अंतर्ग्रहित करके उसका उपयोग कर सकते हैं.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

> [!NOTE]
> सुनिश्चित करें कि वर्णित सभी **भूमिका असाइनमेंट** सेट किए जाएं.

- Customer Insights में, आपकाAzure Active Directory (एडी) उपयोगकर्ता खाते में एक होना चाहिए [प्रशासक की भूमिका।](permissions.md#assign-roles-and-permissions)

Azure में:

- एक सक्रिय Azure सदस्यता.

- यदि एक नया उपयोग कर रहे हैं Azure Data Lake Storage Gen2 खाता,[Customer Insights के लिए सेवा प्रिंसिपल](connect-service-principal.md) है **संग्रहण ब्लॉब डेटा सहयोगी** अनुमतियाँ। Data Lake Storage Gen2 में [पदानुक्रमिक नामस्थान](/azure/storage/blobs/data-lake-storage-namespace) **अवश्य** सक्षम होना चाहिए.

- संसाधन समूह पर जहां Azure Synapse कार्यक्षेत्र स्थित है, *सेवा प्रधान* और यह *Azure AD Customer Insights में व्यवस्थापक अनुमतियों वाला उपयोगकर्ता* कम से कम असाइन किया जाना चाहिए **रीडर**[अनुमतियां](/azure/role-based-access-control/role-assignments-portal).

- *Azure AD Customer Insights में व्यवस्थापक अनुमतियों वाला उपयोगकर्ता* है **संग्रहण ब्लॉब डेटा सहयोगी** पर अनुमतियाँ Azure Data Lake Storage Gen2 खाता जहां डेटा स्थित है और से जुड़ा हुआ है Azure Synapse कार्यक्षेत्र। [ब्लॉब और क्यू डेटा तक पहुंचने हेतु एक Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना के बारे में](/azure/storage/common/storage-auth-aad-rbac-portal) और [संग्रहण ब्लॉब डेटा योगदानकर्ता अनुमतियां](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.

- *[Azure Synapse कार्यक्षेत्र प्रबंधित पहचान](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* है **संग्रहण ब्लॉब डेटा सहयोगी** पर अनुमतियाँ Azure Data Lake Storage Gen2 खाता जहां डेटा स्थित है और से जुड़ा हुआ है Azure Synapse कार्यक्षेत्र। [ब्लॉब और क्यू डेटा तक पहुंच के लिए Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना](/azure/storage/common/storage-auth-aad-rbac-portal) और [ब्लॉब डेटा योगदानकर्ता अनुमतियां संग्रहण](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.

- पर Azure Synapse कार्यक्षेत्र, *Customer Insights के लिए सेवा प्रिंसिपल* है **सिनैप्स एडमिनिस्ट्रेटर**[भूमिका सौंपी गई](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>से कनेक्शन सेट करें Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.

1. चुनना**कनेक्शन जोड़ें** और चुनें **Azure Synapse Analytics**.

1. **डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें. कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है. हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।

1. चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है. डिफ़ॉल्ट रूप से यह केवल व्यवस्थापक हैं. अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. जिस सदस्यता में आप Customer Insights डेटा का उपयोग करना चाहते हैं, उसे चुनें और खोजें. सदस्यता के चयन के साथ ही आप **कार्यस्थान**, **संग्रहण खाता** और **कंटेनर** भी चुन सकते हैं.

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं**.

1. कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.

## <a name="configure-an-export"></a>एक निर्यात कॉन्फ़िगर करें

[!INCLUDE [export-permission-include](includes/export-permission.md)] एक साझा कनेक्शन के साथ निर्यात को कॉन्फ़िगर करने के लिए, आपको कम से कम चाहिए **सहयोगी** Customer Insights में अनुमतियाँ।

1. **डेटा** > **निर्यात** पर जाएँ.

1. चुनना**निर्यात जोड़ें**.

1. में **निर्यात के लिए कनेक्शन** फ़ील्ड, से एक कनेक्शन चुनें Azure Synapse Analytics खंड। यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.

1. अपने निर्यात के लिए एक पहचानने योग्य **प्रदर्शन नाम** और एक **डेटाबेस नाम** प्रदान करें. निर्यात एक नया बना देगा[Azure Synapse झील डेटाबेस](/azure/synapse-analytics/database-designer/concepts-lake-database) कनेक्शन में परिभाषित कार्यक्षेत्र में।

1. चुनें कि आप किन इकाइयों को निर्यात करना चाहते हैं Azure Synapse Analytics.
   > [!NOTE]
   > [Common Data Model फ़ोल्डर](connect-common-data-model.md) पर आधारित डेटा स्रोत समर्थित नहीं हैं.

1. **सहेजें** चुनें.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Synapse Analytics को निर्यात किए गए डेटा को क्वेरी करने के लिए, आपको चाहिए **संग्रहण ब्लॉब डेटा रीडर** निर्यात के कार्यक्षेत्र पर गंतव्य भंडारण तक पहुंच।

## <a name="update-an-export"></a>निर्यात अपडेट करें

1. **डेटा** > **निर्यात** पर जाएँ.

1. जिसे आप अपडेट करना चाहते हैं उस निर्यात पर **संपादित करें** चुनें.

   - चयन से निकायों को **जोड़ें** या **निकालें**. यदि निकायों को चयन से निकाल दिया जाता है, पर उन्हें Synapse Analytics डेटाबेस से नहीं हटाया जाता है. हालांकि, भविष्य में किए जाने वाले डेटा रीफ़्रेश में उस डेटाबेस में निकाले गए निकायों को अपडेट नहीं किया जाएगा.

   - **डेटाबेस का नाम बदलना** एक नया Synapse Analytics डेटाबेस बनाता है. उस नाम वाला डेटाबेस, जिसे पहले कॉन्फ़िगर किया गया था, भविष्य के रीफ़्रेश में उसे कोई अपडेट प्राप्त नहीं होगा.

[!INCLUDE [footer-include](includes/footer-banner.md)]
