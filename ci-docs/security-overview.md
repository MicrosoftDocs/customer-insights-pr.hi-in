---
title: सुरक्षा सेटिंग्स कॉन्फ़िगर करें
description: में सुरक्षा सेटिंग्स के बारे में जानें।Dynamics 365 Customer Insights
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387251"
---
# <a name="configure-security-settings"></a>सुरक्षा सेटिंग्स कॉन्फ़िगर करें

API कुंजियाँ प्रबंधित करें, ग्राहक डेटा तक पहुँचें, और Azure Private Link सेट करें।

## <a name="manage-api-keys"></a>एपीआई कुंजी प्रबंधित करें

उपयोग करने के लिए कुंजियों को देखें और प्रबंधित करें [Customer Insights API](apis.md) अपने परिवेश में डेटा के साथ।

1. के लिए जाओ **व्यवस्थापक** > **सुरक्षा** और चुनें **शहद की मक्खी** टैब।

1. यदि पर्यावरण के लिए एपीआई एक्सेस सेट नहीं किया गया है, तो चुनें **सक्षम करना**. या, पर्यावरण के लिए एपीआई एक्सेस को ब्लॉक करने के लिए, चुनें **बंद करना** और पुष्टि करें।

1. प्राथमिक और द्वितीयक API कुंजियाँ प्रबंधित करें:

   1. प्राथमिक या द्वितीयक API कुंजी दिखाने के लिए, चुनें **प्रदर्शन** चिन्ह, प्रतीक।

   1. प्राथमिक या द्वितीयक API कुंजी को कॉपी करने के लिए, चुनें **प्रतिलिपि** चिन्ह, प्रतीक।

   1. नई प्राथमिक या द्वितीयक API कुंजियाँ बनाने के लिए, चुनें **प्राथमिक पुन: उत्पन्न करें** या**माध्यमिक पुन: उत्पन्न करें**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>ग्राहक लॉकबॉक्स (पूर्वावलोकन) के साथ ग्राहक डेटा को सुरक्षित रूप से एक्सेस करें

Customer Insights का उपयोग करता है Power Platform ग्राहक लॉकबॉक्स क्षमता। ग्राहक लॉकबॉक्स डेटा एक्सेस अनुरोधों की समीक्षा और अनुमोदन (या अस्वीकार) करने के लिए एक इंटरफ़ेस प्रदान करता है। ये अनुरोध तब होते हैं जब किसी समर्थन मामले को हल करने के लिए ग्राहक डेटा तक डेटा पहुंच की आवश्यकता होती है। इस सुविधा का उपयोग करने के लिए, Customer Insights के पास a . के साथ एक मौजूदा कनेक्शन होना चाहिए Microsoft Dataverse आपके किरायेदार में पर्यावरण।

ग्राहक लॉकबॉक्स के बारे में अधिक जानकारी के लिए, देखें [सारांश](/power-platform/admin/about-lockbox#summary) काPower Platform ग्राहक लॉकबॉक्स। लेख भी वर्णन करता है [कार्यप्रवाह](/power-platform/admin/about-lockbox#workflow) और आवश्यक [स्थापित करना](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) ग्राहक लॉकबॉक्स को सक्षम करने के लिए।

> [!IMPORTANT]
> के लिए वैश्विक प्रशासक Power Platform याPower Platform व्यवस्थापक Customer Insights के लिए जारी Customer Lockbox अनुरोधों को स्वीकृत कर सकते हैं।

## <a name="set-up-an-azure-private-link"></a>एक Azure निजी लिंक सेट करें

[Azure निजी लिंक](/azure/private-link/private-link-overview) आइए Customer Insights को आपसे कनेक्ट करें Azure Data Lake Storage अपने वर्चुअल नेटवर्क में एक निजी एंडपॉइंट पर खाता। भंडारण खाते में डेटा के लिए, जो सार्वजनिक इंटरनेट के संपर्क में नहीं है, निजी लिंक उस प्रतिबंधित नेटवर्क से कनेक्शन को सक्षम बनाता है।

> [!IMPORTANT]
> निजी लिंक कनेक्शन स्थापित करने के लिए न्यूनतम भूमिका आवश्यकता:
>
> - ग्राहक अंतर्दृष्टि: व्यवस्थापक
> - Azure अंतर्निहित भूमिका:[संग्रहण खाता सहयोगी](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - कस्टम Azure भूमिका के लिए अनुमतियाँ: [Microsoft.Storage/storageAccounts/read और Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsस्वीकृति/क्रिया](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Customer Insights में, यहाँ जाएँ **व्यवस्थापक** > **सुरक्षा** और चुनें **निजी लिंक** टैब।

1. चुनना**निजी लिंक जोड़ें**.

   **निजी लिंक जोड़ें** फलक आपके टैनेंट के उन संग्रहण खातों को सूचीबद्ध करता है जिन्हें देखने की आपको अनुमतियाँ प्राप्त हैं।

1. सदस्यता, संसाधन समूह और संग्रहण खाते का चयन करें।

1. की समीक्षा करें [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) और चुनें **मैं सहमत हूं** .

1. **सहेजें** चुनें.

1. अपने डेटा लेक स्टोरेज खाते में जाएं और स्क्रीन पर प्रस्तुत लिंक को खोलें।

1. निजी लिंक को स्वीकृति दें।


[!INCLUDE [footer-include](includes/footer-banner.md)]
