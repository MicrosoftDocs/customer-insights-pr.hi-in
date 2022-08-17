---
title: अपनी स्वयं की Azure की वॉल्ट लाएं (पूर्वावलोकन)
description: रहस्यों को प्रबंधित करने के लिए अपने स्वयं के Azure कुंजी वॉल्ट का उपयोग करने के लिए Customer Insights को कॉन्फ़िगर करने का तरीका जानें।
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246157"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>अपनी स्वयं की Azure की वॉल्ट लाएं (पूर्वावलोकन)

एक समर्पित जोड़ना[Azure कुंजी तिजोरी](/azure/key-vault/general/basic-concepts) Customer Insights परिवेश से संगठनों को अनुपालन आवश्यकताओं को पूरा करने में मदद मिलती है।

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>मुख्य तिजोरी को Customer Insights परिवेश से लिंक करें

किसी संगठन की अनुपालन सीमा में रहस्यों को मंचित करने और उनका उपयोग करने के लिए समर्पित कुंजी वॉल्ट सेट करें।

### <a name="prerequisites"></a>पूर्वावश्यकताएँ

- एक सक्रिय Azure सदस्यता.

- एक [प्रशासक](permissions.md#admin) भूमिका[सौंपा गया](permissions.md#add-users) ग्राहक अंतर्दृष्टि में।

- [सहयोगी](/azure/role-based-access-control/built-in-roles#contributor) तथा[यूजर एक्सेस एडमिनिस्ट्रेटर](/azure/role-based-access-control/built-in-roles#user-access-administrator) कुंजी तिजोरी या संसाधन समूह पर भूमिकाएँ जो कुंजी तिजोरी से संबंधित हैं। अधिक जानकारी के लिए, [Azure पोर्टल का इस्तेमाल करके Azure भूमिका असाइनमेंट जोड़ें या निकालें](/azure/role-based-access-control/role-assignments-portal) पर जाएं. यदि आपके पास कुंजी तिजोरी पर उपयोगकर्ता पहुँच व्यवस्थापक भूमिका नहीं है, तो Azure सेवा प्रिंसिपल के लिए भूमिका-आधारित पहुँच नियंत्रण अनुमतियाँ सेट करें Dynamics 365 Customer Insights अलग से। लिंक की जाने वाली की वॉल्ट के लिए [Azure सेवा प्रिंसिपल का इस्तेमाल करें](connect-service-principal.md) चरणों का पालन करें.

- की वॉल्ट में की वॉल्ट फ़ायरवॉल होना चाहिए **अक्षम**.

- चाबी तिजोरी उसी में है [नीला स्थान](https://azure.microsoft.com/global-infrastructure/geographies/#overview) Customer Insights परिवेश के रूप में। Customer Insights में, यहाँ जाएँ **व्यवस्थापक** > **व्यवस्था** और यह **के बारे में** पर्यावरण के क्षेत्र को देखने के लिए टैब।

### <a name="recommendations"></a>सुझाव

- [एक अलग या समर्पित कुंजी वॉल्ट का उपयोग करें](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) जिसमें केवल Customer Insights के लिए आवश्यक रहस्य शामिल हैं।

- नियंत्रण पहुँच, बैकअप, ऑडिट और पुनर्प्राप्ति विकल्पों के लिए [की वॉल्ट का इस्तेमाल करने के लिए सर्वोत्तम अभ्यास](/azure/key-vault/general/best-practices#turn-on-logging) का पालन करें.

### <a name="link-a-key-vault-to-the-environment"></a>परिवेश के लिए एक 'की वॉल्ट' को लिंक करें

1. के लिए जाओ **व्यवस्थापक** > **सुरक्षा**, और फिर चुनें **कुंजी तिजोरी** टैब।
1. **की वॉल्ट** टाइल पर, **सेटअप** चुनें.
1. एक **सदस्यता** चुनें.
1. **की वॉल्ट** ड्रॉपडाउन सूची से एक की वॉल्ट चुनें. यदि बहुत अधिक कुंजी वाल्ट उपलब्ध हैं, तो खोज परिणामों को सीमित करने के लिए संसाधन समूह का चयन करें।
1. [डेटा गोपनीयता और अनुपालन](connections.md#data-privacy-and-compliance) की समीक्षा करें और **मैं सहमत हूं** का चयन करें.
1. **सहेजें** चुनें.

**कुंजी तिजोरी** टाइल लिंक की गई कुंजी वॉल्ट का नाम, सदस्यता और संसाधन समूह दिखाती है। यह कनेक्शन सेटअप में उपयोग के लिए तैयार है.
Customer Insights को मुख्य तिजोरी पर कौन-सी अनुमतियाँ दी गई हैं, इसके विवरण के लिए, यहाँ जाएँ [मुख्य तिजोरी पर दी गई अनुमतियां](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>कनेक्शन सेटअप में की वॉल्ट का इस्तेमाल करें

कब [कनेक्शन स्थापित करना](connections.md) प्रति[समर्थित तृतीय-पक्ष](#supported-connection-types) सिस्टम, कनेक्शन को विन्यस्त करने के लिए लिंक्ड की वॉल्ट के रहस्यों का उपयोग करें।

1. **व्यवस्थापक** > **कनेक्शन** पर जाएं.
1. **कनेक्शन जोड़ें** चुनें.
1. समर्थित कनेक्शन प्रकारों के लिए, अगर आपने कोई की वॉल्ट लिंक किया है, तो **की वॉल्ट का इस्तेमाल करें** टॉगल उपलब्ध है.
1. गुप्त को मैन्युअल रूप से दर्ज करने के बजाय, गुप्त नाम चुनें जो कुंजी तिजोरी में गुप्त मान की ओर इशारा करता है।

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="की वॉल्ट रहस्य का इस्तेमाल करने वाले SFTP कनेक्शन के साथ कनेक्शन फलक.":::

1. चुनना**बचाना** कनेक्शन बनाने के लिए।

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

## <a name="permissions-granted-on-the-key-vault"></a>मुख्य तिजोरी पर दी गई अनुमतियां

लिंक्ड की वॉल्ट पर Customer Insights को निम्नलिखित अनुमतियाँ दी जाती हैं, यदि या तो[कुंजी तिजोरी पहुंच नीति](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) या[Azure भूमिका-आधारित अभिगम नियंत्रण](/azure/key-vault/general/rbac-guide?tabs=azure-cli) सक्षम किया गया है।

### <a name="key-vault-access-policy"></a>की वॉल्ट पहुँच नीति

| प्रकार        | अनुमतियाँ          |
| ----------- | -------------------- |
| अत्‍यंत महत्वपूर्ण         | [की प्राप्त करें](/rest/api/keyvault/keys/get-keys/get-keys), [की प्राप्त करें](/rest/api/keyvault/keys/get-key/get-key)                                 |
| सीक्रेट      | [रहस्य प्राप्त करें](/rest/api/keyvault/secrets/get-secrets/get-secrets), [रहस्य प्राप्त करें](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| प्रमाणपत्र | [प्रमाणपत्र प्राप्त करें](/rest/api/keyvault/certificates/get-certificates/get-certificates), [प्रमाणपत्र प्राप्त करें](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

पूर्ववर्ती मान निष्पादन के दौरान सूचीबद्ध करने और पढ़ने के लिए न्यूनतम हैं.

### <a name="azure-role-based-access-control"></a>Azure भूमिका-आधारित पहुँच नियंत्रण

[कुंजी तिजोरी रीडर और कुंजी तिजोरी रहस्य उपयोगकर्ता भूमिकाएँ](/azure/key-vault/general/rbac-guide?tabs=azure-cli) Customer Insights के लिए जोड़ा जाएगा।

## <a name="frequently-asked-questions"></a>सामान्य प्रश्‍न

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>क्या Customer Insights रहस्य लिख सकता है या गुप्त को मुख्य तिजोरी में अधिलेखित कर सकता है?

नहीं. केवल पढ़ने और सूचीबद्ध करने की अनुमतियों में उल्लिखित है [दी गई अनुमति](#permissions-granted-on-the-key-vault) Customer Insights को प्रदान किए जाते हैं। सिस्टम की वॉल्ट में रहस्यों को जोड़, हटा या ओवरराइट नहीं कर सकता है. यही कारण है कि जब कोई कनेक्शन की वॉल्ट का इस्तेमाल करता है तो आप क्रेडेंशियल दर्ज नहीं कर सकते.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>क्या मैं किसी कनेक्शन को Key Vault रहस्य के इस्तेमाल से डिफ़ॉल्ट प्रमाणीकरण में बदल सकता हूं?

नहीं. लिंक किए गए की वॉल्ट से एक रहस्य का इस्तेमाल करके इसे कॉन्फ़िगर करने के बाद आप इसे डिफ़ॉल्ट कनेक्शन में वापस नहीं बदल सकते. एक अलग कनेक्शन बनाएँ और अगर आपको अब इसकी आवश्यकता नहीं है तो पुराने को हटा दें.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>मैं Customer Insights के लिए एक प्रमुख तिजोरी तक पहुंच कैसे रद्द कर सकता हूं?

अगर [कुंजी तिजोरी पहुंच नीति](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) या[Azure भूमिका-आधारित अभिगम नियंत्रण](/azure/key-vault/general/rbac-guide?tabs=azure-cli) सक्षम है, सेवा प्रिंसिपल के लिए अनुमतियों को हटा दें`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` नाम के साथ `Dynamics 365 AI for Customer Insights`. की वॉल्ट का इस्तेमाल करने वाले सभी कनेक्शन काम करना बंद कर देंगे.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>एक कनेक्शन में इस्तेमाल किया गया रहस्य की वॉल्ट से हटा दिया गया है. मैं क्या कर सकता हूँ?

Customer Insights में एक सूचना तब दिखाई देती है जब कुंजी तिजोरी से कॉन्फ़िगर किया गया रहस्य अब पहुंच योग्य नहीं होता है। की वॉल्ट पर [सॉफ्ट-डिलीट](/azure/key-vault/general/soft-delete-overview) को सक्षम करें, ताकि अगर रहस्य गलती से हटा दिए गए हों तो उन्हें पुनर्स्थापित किया जा सके.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>एक कनेक्शन काम नहीं करता है, लेकिन मेरा रहस्य की वॉल्ट में है. क्या कारण हो सकता है?

Customer Insights में एक सूचना तब दिखाई देती है जब वह की वॉल्ट तक नहीं पहुंच पाती है। कारण ये हो सकते हैं:

- Customer Insights सेवा प्रिंसिपल की अनुमतियाँ हटा दी गईं। उन्हें मैन्युअल रूप से पुनर्स्थापित करने की आवश्यकता है.

- की वॉल्ट पर फ़ायरवॉल सक्षम है. Customer Insights के लिए कुंजी वॉल्ट को फिर से एक्सेस करने योग्य बनाने के लिए फ़ायरवॉल को अक्षम किया जाना चाहिए।
