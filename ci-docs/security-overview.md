---
title: सुरक्षा सेटिंग्स Dynamics 365 Customer Insights
description: में सुरक्षा सेटिंग्स के बारे में जानें।Dynamics 365 Customer Insights
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653787"
---
# <a name="security-overview-page"></a>सुरक्षा अवलोकन पृष्ठ

**सुरक्षा** पृष्ठ उपयोगकर्ता अनुमतियों और सुविधाओं को कॉन्फ़िगर करने के विकल्पों को सूचीबद्ध करता है जो बनाने में मदद करते हैं Dynamics 365 Customer Insights अधिक सुरक्षित। केवल व्यवस्थापक ही इस पृष्ठ तक पहुंच सकते हैं। 

के लिए जाओ **व्यवस्थापक** > **सुरक्षा** सेटिंग्स को कॉन्फ़िगर करने के लिए।

**सुरक्षा** पृष्ठ में निम्नलिखित टैब शामिल हैं:
- [उपयोगकर्ता](#users-tab)
- [APIs](#apis-tab)
- [की वॉल्ट](#key-vault-tab)

## <a name="users-tab"></a>उपयोगकर्ता टैब

Customer Insights तक पहुंच आपके संगठन के उन उपयोगकर्ताओं तक सीमित है जिन्हें किसी व्यवस्थापक द्वारा एप्लिकेशन में जोड़ा गया था।**उपयोगकर्ताओं** टैब आपको उपयोगकर्ता पहुंच और उनकी अनुमतियों को प्रबंधित करने देता है। अधिक जानकारी के लिए देखें [उपयोगकर्ता अनुमतियाँ](permissions.md).

## <a name="apis-tab"></a>एपीआई टैब

उपयोग करने के लिए कुंजियों को देखें और प्रबंधित करें [Customer Insights API](apis.md) अपने पर्यावरण के डेटा के साथ।

आप चुनकर नई प्राथमिक और द्वितीयक कुंजियाँ बना सकते हैं **प्राथमिक पुन: उत्पन्न करें** या**माध्यमिक पुन: उत्पन्न करें**. 

पर्यावरण के लिए एपीआई एक्सेस को ब्लॉक करने के लिए, चुनें **अक्षम करना**. यदि एपीआई अक्षम हैं, तो आप चुन सकते हैं **सक्षम** फिर से पहुंच प्रदान करने के लिए।

## <a name="key-vault-tab"></a>कुंजी तिजोरी टैब

**कुंजी तिजोरी** टैब आपको स्वयं को लिंक और प्रबंधित करने देता है [Azure कुंजी तिजोरी](/azure/key-vault/general/basic-concepts) पर्यावरण को।
समर्पित की वॉल्ट का इस्तेमाल किसी संगठन की अनुपालन सीमा में रहस्यों को स्टेज करने और उनका इस्तेमाल करने के लिए किया जा सकता है. Customer Insights Azure Key Vault के रहस्यों का उपयोग करने के लिए कर सकती है [कनेक्शन स्थापित करें](connections.md) तृतीय-पक्ष प्रणालियों के लिए।

अधिक जानकारी के लिए, [अपना खुद का Azure कुंजी वॉल्ट लाएं](use-azure-key-vault.md) देखें.


[!INCLUDE [footer-include](includes/footer-banner.md)]
