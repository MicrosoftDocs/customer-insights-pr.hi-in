---
title: Customer Insights में सुरक्षा सेटिंग्स
description: में सुरक्षा सेटिंग्स के बारे में जानें।Dynamics 365 Customer Insights
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947417"
---
# <a name="security-settings-in-customer-insights"></a>Customer Insights में सुरक्षा सेटिंग्स

**सुरक्षा** पृष्ठ उपयोगकर्ता अनुमतियों और सुविधाओं को कॉन्फ़िगर करने के विकल्पों को सूचीबद्ध करता है जो बनाने में मदद करते हैं Dynamics 365 Customer Insights ज्यादा सुरक्षित। केवल व्यवस्थापक ही इस पृष्ठ तक पहुंच सकते हैं।

के लिए जाओ **व्यवस्थापक** > **सुरक्षा** सेटिंग्स को कॉन्फ़िगर करने के लिए।

**सुरक्षा** पृष्ठ में निम्नलिखित टैब शामिल हैं:

- [उपयोगकर्ता](#users-tab)
- [APIs](#apis-tab)
- [निजी लिंक](#private-links-tab)
- [की वॉल्ट](#key-vault-tab)
- [ग्राहक लॉकबॉक्स (पूर्वावलोकन) के साथ ग्राहक डेटा को सुरक्षित रूप से एक्सेस करें](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>उपयोगकर्ता टैब

Customer Insights तक पहुंच आपके संगठन के उन उपयोगकर्ताओं तक सीमित है जिन्हें किसी व्यवस्थापक द्वारा एप्लिकेशन में जोड़ा गया था।**उपयोगकर्ताओं** टैब आपको उपयोगकर्ता पहुंच और उनकी अनुमतियों को प्रबंधित करने देता है। अधिक जानकारी के लिए देखें [उपयोगकर्ता अनुमतियाँ](permissions.md).

## <a name="apis-tab"></a>एपीआई टैब

उपयोग करने के लिए कुंजियों को देखें और प्रबंधित करें [Customer Insights API](apis.md) अपने पर्यावरण के डेटा के साथ।

आप चुनकर नई प्राथमिक और द्वितीयक कुंजियाँ बना सकते हैं **प्राथमिक पुन: उत्पन्न करें** या**माध्यमिक पुन: उत्पन्न करें**. 

पर्यावरण के लिए एपीआई एक्सेस को ब्लॉक करने के लिए, चुनें **बंद करना**. यदि एपीआई अक्षम हैं, तो आप चुन सकते हैं **सक्षम करना** फिर से पहुंच प्रदान करने के लिए।

## <a name="private-links-tab"></a>निजी लिंक टैब

[Azure निजी लिंक](/azure/private-link/private-link-overview) आइए Customer Insights को आपसे कनेक्ट करें Azure Data Lake Storage अपने वर्चुअल नेटवर्क में एक निजी एंडपॉइंट पर खाता। एक भंडारण खाते में डेटा के लिए, जो सार्वजनिक इंटरनेट के संपर्क में नहीं है, निजी लिंक उस प्रतिबंधित नेटवर्क से कनेक्शन को सक्षम करता है।

> [!IMPORTANT]
> निजी लिंक कनेक्शन स्थापित करने के लिए न्यूनतम भूमिका आवश्यकता:
>
> - ग्राहक अंतर्दृष्टि: व्यवस्थापक
> - Azure अंतर्निहित भूमिका:[संग्रहण खाता सहयोगी](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - कस्टम Azure भूमिका के लिए अनुमतियाँ: [Microsoft.Storage/storageAccounts/read और Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsस्वीकृति/क्रिया](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Customer Insights में Private Link सेट करना दो चरणों वाली प्रक्रिया है। सबसे पहले, आप से एक निजी लिंक बनाने की पहल करें **व्यवस्थापक** > **सुरक्षा** > **निजी लिंक** ग्राहक अंतर्दृष्टि में। **निजी लिंक जोड़ें** फलक आपके टैनेंट के उन संग्रहण खातों को सूचीबद्ध करता है जिन्हें देखने की आपको अनुमतियाँ प्राप्त हैं। भंडारण खाते का चयन करें और निजी लिंक बनाने के लिए सहमति प्रदान करें।

इसके बाद, आपको डेटा लेक स्टोरेज अकाउंट साइड पर प्राइवेट लिंक को मंजूरी देनी होगी। नए निजी लिंक को स्वीकृत करने के लिए स्क्रीन पर प्रस्तुत लिंक को खोलें।

## <a name="key-vault-tab"></a>कुंजी तिजोरी टैब

**कुंजी तिजोरी** टैब आपको स्वयं को लिंक और प्रबंधित करने देता है [Azure कुंजी तिजोरी](/azure/key-vault/general/basic-concepts) पर्यावरण को।
समर्पित की वॉल्ट का इस्तेमाल किसी संगठन की अनुपालन सीमा में रहस्यों को स्टेज करने और उनका इस्तेमाल करने के लिए किया जा सकता है. Customer Insights Azure Key Vault के रहस्यों का उपयोग करने के लिए कर सकती है [कनेक्शन स्थापित करें](connections.md) तृतीय-पक्ष प्रणालियों के लिए।

अधिक जानकारी के लिए, [अपना खुद का Azure कुंजी वॉल्ट लाएं](use-azure-key-vault.md) देखें.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>ग्राहक लॉकबॉक्स (पूर्वावलोकन) के साथ ग्राहक डेटा को सुरक्षित रूप से एक्सेस करें

Customer Insights इसका उपयोग कर रहा है Power Platform ग्राहक लॉकबॉक्स क्षमता। ग्राहक लॉकबॉक्स डेटा एक्सेस अनुरोधों की समीक्षा और अनुमोदन (या अस्वीकार) करने के लिए एक इंटरफ़ेस प्रदान करता है। ये अनुरोध तब होते हैं जब किसी समर्थन मामले को हल करने के लिए ग्राहक डेटा तक डेटा पहुंच की आवश्यकता होती है। इस सुविधा का उपयोग करने के लिए, Customer Insights के पास a . के साथ एक मौजूदा कनेक्शन होना चाहिए Microsoft Dataverse आपके किरायेदार में पर्यावरण।

ग्राहक लॉकबॉक्स के बारे में अधिक जानकारी के लिए, देखें [सारांश](/power-platform/admin/about-lockbox#summary) काPower Platform ग्राहक लॉकबॉक्स। लेख भी वर्णन करता है [कार्यप्रवाह](/power-platform/admin/about-lockbox#workflow) और आवश्यक [स्थापित करना](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) ग्राहक लॉकबॉक्स को सक्षम करने के लिए।

> [!IMPORTANT]
> के लिए वैश्विक प्रशासक Power Platform याPower Platform व्यवस्थापक Customer Insights के लिए जारी Customer Lockbox अनुरोधों को स्वीकृत कर सकते हैं।

[!INCLUDE [footer-include](includes/footer-banner.md)]
