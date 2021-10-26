---
title: रहस्यों को प्रबंधित करने के लिए अपनी स्वयं की Azure की वॉल्ट लाएं
description: अपनी स्वयं की Azure की वॉल्ट का इस्तेमाल करने के लिए Customer Insights को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: 6f521dfce3e0922238d16beee3be8e1bbcfc63a5
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606081"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>अपनी स्वयं की Azure की वॉल्ट लाएं (पूर्वावलोकन)

एक समर्पित [Azure की वॉल्ट](/azure/key-vault/general/basic-concepts) को ऑडिएंस इनसाइट परिवेश से जोड़ने से संगठनों को अनुपालन आवश्यकताओं को पूरा करने में मदद मिलती है.
समर्पित की वॉल्ट का इस्तेमाल किसी संगठन की अनुपालन सीमा में रहस्यों को स्टेज करने और उनका इस्तेमाल करने के लिए किया जा सकता है. ऑडिएंस इनसाइट तृतीय-पक्ष सिस्टम के लिए [कनेक्शन सेट अप](connections.md) करने के लिए Azure की वॉल्ट के रहस्यों का इस्तेमाल कर सकती है.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>ऑडिएंस इनसाइट परिवेश से की वॉल्ट को लिंक करें

### <a name="prerequisites"></a>पूर्वावश्यकताएँ

ऑडिएंस इनसाइट में की वॉल्ट को कॉन्फ़िगर करने के लिए, निम्नलिखित पूर्वापेक्षाएँ पूरी होनी चाहिए:

- आपके पास सक्रिय Azure सदस्यता है.

- ऑडियंस इनसाइट में आपकी [व्यवस्थापक](permissions.md#administrator) की भूमिका होती है. [ऑडिएंस इनसाइट में उपयोगकर्ता अनुमतियाँ](permissions.md#assign-roles-and-permissions) के बारे में और जानें.

- आपके पास की वॉल्ट या की वॉल्ट से संबंधित संसाधन समूह पर [योगदानकर्ता](/azure/role-based-access-control/built-in-roles#contributor) और [उपयोगकर्ता पहुँच व्यवस्थापक](/azure/role-based-access-control/built-in-roles#user-access-administrator) भूमिकाएँ हैं. अधिक जानकारी के लिए, [Azure पोर्टल का इस्तेमाल करके Azure भूमिका असाइनमेंट जोड़ें या निकालें](/azure/role-based-access-control/role-assignments-portal) पर जाएं. अगर आपके पास की वॉल्ट पर उपयोगकर्ता पहुँच व्यवस्थापक की भूमिका नहीं है, तो आपको Dynamics 365 Customer Insights के लिए Azure सेवा प्रिंसिपल के लिए भूमिका-आधारित पहुँच नियंत्रण अनुमतियाँ अलग से सेट करनी होंगी. लिंक की जाने वाली की वॉल्ट के लिए [Azure सेवा प्रिंसिपल का इस्तेमाल करें](connect-service-principal.md) चरणों का पालन करें.

- की वॉल्ट में की वॉल्ट फ़ायरवॉल **अक्षम** होना चाहिए.

- की वॉल्ट उसी [Azure स्थान](https://azure.microsoft.com/global-infrastructure/geographies/#overview) में होती है, जहां ऑडियंस इनसाइट परिवेश होता है. ऑडिएंस इनसाइट में परिवेश का क्षेत्र **व्यवस्थापक** > **सिस्टम** > **के बारे में** > **क्षेत्र** के अंतर्गत सूचीबद्ध है.

### <a name="link-a-key-vault-to-the-environment"></a>परिवेश के लिए एक 'की वॉल्ट' को लिंक करें

1. **व्यवस्थापक** > **सिस्टम** पर जाए, और फिर **सुरक्षा** टैब चुनें.
1. **की वॉल्ट** टाइल पर, **सेटअप** चुनें.
1. एक **सदस्यता** चुनें.
1. **की वॉल्ट** ड्रॉपडाउन सूची से एक की वॉल्ट चुनें. अगर बहुत ज़्यादा की वॉल्ट दिखाई दे रहे हैं, तो खोज परिणामों को सीमित करने के लिए संसाधन समूह का चयन करें.
1. **डेटा गोपनीयता और अनुपालन** कथन स्वीकार करें.
1. **सहेजें** चुनें.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="ऑडियंस इनसाइट्स में लिंक की गई की वॉल्ट सेट करने के चरण.":::

**की वॉल्ट** टाइल अब लिंक की गई की वॉल्ट का नाम, संसाधन समूह और सदस्यता दिखाती है. यह कनेक्शन सेटअप में उपयोग के लिए तैयार है.
ऑडिएंस इनसाइट को की वॉल्ट पर कौन-सी अनुमतियाँ दी गई हैं, इस बारे में विवरण के लिए इस आलेख में आगे, [ऑडिएंस इनसाइट्स के लिए की वॉल्ट पर दी गई अनुमतियाँ](#permissions-granted-on-the-key-vault-to-audience-insights) पर जाएं.

## <a name="use-the-key-vault-in-the-connection-setup"></a>कनेक्शन सेटअप में की वॉल्ट का इस्तेमाल करें

तृतीय-पक्ष सिस्टम में [कनेक्शन सेट अप](connections.md) करते समय, लिंक किए गए की वॉल्ट रहस्यों का इस्तेमाल कनेक्शन को कॉन्फ़िगर करने के लिए किया जा सकता है.

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.
1. **कनेक्शन जोड़ें** चुनें.
1. समर्थित कनेक्शन प्रकारों के लिए, अगर आपने कोई की वॉल्ट लिंक किया है, तो **की वॉल्ट का इस्तेमाल करें** टॉगल उपलब्ध है.
1. रहस्य को मैन्युअल रूप से दर्ज करने के बजाय, आप रहस्य नाम चुन सकते हैं जो की वॉल्ट में रहस्य मूल्य की ओर इशारा करता है.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="की वॉल्ट रहस्य का इस्तेमाल करने वाले SFTP कनेक्शन के साथ कनेक्शन फलक.":::

## <a name="supported-connection-types"></a>समर्थित कनेक्शन प्रकार

निम्नलिखित [निर्यात](export-destinations.md) कनेक्शन समर्थित हैं:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce मार्केटिंग क्लाउड](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>ऑडिएंस इनसाइट्स के लिए की वॉल्ट पर दी गई अनुमतियाँ

अगर या तो [की वॉल्ट पहुँच नीति](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) या [Azure भूमिका-आधारित पहुँच नियंत्रण](/azure/key-vault/general/rbac-guide?tabs=azure-cli) सक्षम है तो, लिंक की गई की वॉल्ट पर ऑडिएंस इनसाइट्स को निम्नलिखित अनुमतियाँ दी जाती हैं.

### <a name="key-vault-access-policy"></a>की वॉल्ट पहुँच नीति

| प्रकार        | अनुमतियाँ          |
| ----------- | -------------------- |
| अत्‍यंत महत्वपूर्ण         | [की प्राप्त करें](/rest/api/keyvault/get-keys), [की प्राप्त करें](/rest/api/keyvault/get-key)                                 |
| सीक्रेट      | [रहस्य प्राप्त करें](/rest/api/keyvault/get-secrets), [रहस्य प्राप्त करें](/rest/api/keyvault/get-secret)                     |
| प्रमाणपत्र | [प्रमाणपत्र प्राप्त करें](/rest/api/keyvault/get-certificates), [प्रमाणपत्र प्राप्त करें](/rest/api/keyvault/get-certificate) |

पूर्ववर्ती मान निष्पादन के दौरान सूचीबद्ध करने और पढ़ने के लिए न्यूनतम हैं.

### <a name="azure-role-based-access-control"></a>Azure भूमिका-आधारित पहुँच नियंत्रण

ऑडिएंस इनसाइट के लिए की वॉल्ट रीडर और की वॉल्ट रहस्य उपयोगकर्ता भूमिकाएं जोड़ी जाएंगी. इन भूमिकाओं के बारे में विवरण के लिए, [की वॉल्ट डेटा प्लेन ऑपरेशन के लिए Azure अंतर्निहित भूमिकाएं](/azure/key-vault/general/rbac-guide?tabs=azure-cli) पर जाएं.

## <a name="recommendations"></a>सुझाव

- एक अलग या समर्पित की वॉल्ट का इस्तेमाल करें जिसमें केवल ऑडिएंस इनसाइट्स के लिए आवश्यक रहस्य हों. इस बारे में और पढ़ें कि [अलग की वॉल्ट की सिफारिश क्यों की जाती है](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- नियंत्रण पहुँच, बैकअप, ऑडिट और पुनर्प्राप्ति विकल्पों के लिए [की वॉल्ट का इस्तेमाल करने के लिए सर्वोत्तम अभ्यास](/azure/key-vault/general/best-practices#turn-on-logging) का पालन करें.

## <a name="frequently-asked-questions"></a>अक्सर पूछे जाने वाले प्रश्न

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>क्या ऑडिएंस इनसाइट्स रहस्य लिख सकती है या रहस्यों को की वॉल्ट में ओवरराइट कर सकती है?

नहीं. ऑडिएंस इनसाइट को केवल [अनुमति दी गई](#permissions-granted-on-the-key-vault-to-audience-insights) अनुभाग में उल्लिखित पढ़ने और सूची बनाने की अनुमतियाँ दी गई हैं. सिस्टम की वॉल्ट में रहस्यों को जोड़, हटा या ओवरराइट नहीं कर सकता है. यही कारण है कि जब कोई कनेक्शन की वॉल्ट का इस्तेमाल करता है तो आप क्रेडेंशियल दर्ज नहीं कर सकते.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>क्या मैं किसी कनेक्शन को Key Vault रहस्य के इस्तेमाल से डिफ़ॉल्ट प्रमाणीकरण में बदल सकता हूं?

नहीं. लिंक किए गए की वॉल्ट से एक रहस्य का इस्तेमाल करके इसे कॉन्फ़िगर करने के बाद आप इसे डिफ़ॉल्ट कनेक्शन में वापस नहीं बदल सकते. एक अलग कनेक्शन बनाएँ और अगर आपको अब इसकी आवश्यकता नहीं है तो पुराने को हटा दें.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>मैं ऑडिएंस इनसाइट्स के लिए की वॉल्ट तक पहुँच कैसे निरस्त कर सकता हूं?

इस पर निर्भर करता है कि [की वॉल्ट पहुँच नीति](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) या [Azure भूमिका-आधारित पहुँच नियंत्रण](/azure/key-vault/general/rbac-guide?tabs=azure-cli) सक्षम है, तो आपको सेवा प्रिंसिपल `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` के लिए `Dynamics 365 AI for Customer Insights` नाम से अनुमतियाँ निकालने की आवश्यकता है. की वॉल्ट का इस्तेमाल करने वाले सभी कनेक्शन काम करना बंद कर देंगे.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>एक कनेक्शन में इस्तेमाल किया गया रहस्य की वॉल्ट से हटा दिया गया है. मैं क्या कर सकता हूँ?

ऑडिएंस इनसाइट्स में एक सूचना तब दिखाई देती है जब की वॉल्ट से कॉन्फ़िगर किया गया रहस्य अब पहुँच योग्य नहीं होता है. की वॉल्ट पर [सॉफ्ट-डिलीट](/azure/key-vault/general/soft-delete-overview) को सक्षम करें, ताकि अगर रहस्य गलती से हटा दिए गए हों तो उन्हें पुनर्स्थापित किया जा सके.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>एक कनेक्शन काम नहीं करता है, लेकिन मेरा रहस्य की वॉल्ट में है. क्या कारण हो सकता है?

ऑडिएंस इनसाइट में एक सूचना तब दिखाई देती है जब वह की वॉल्ट तक नहीं पहुँच पाती है. कारण ये हो सकते हैं:

- ऑडिएंस इनसाइट सेवा प्रिंसिपल की अनुमतियाँ हटा दी गईं हैं. उन्हें मैन्युअल रूप से पुनर्स्थापित करने की आवश्यकता है.

- की वॉल्ट पर फ़ायरवॉल सक्षम है. ऑडिएंस इनसाइट्स के लिए की वॉल्ट को फिर से पहुँच योग्य बनाने के लिए फ़ायरवॉल को अक्षम किया जाना चाहिए.
