---
title: Facebook विज्ञापन प्रबंधक के लिए Customer Insights डेटा निर्यात करें
description: Facebook विज्ञापन प्रबंधक तक कनेक्शन को कॉन्फ़िगर करना सीखें.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643685"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="b1f2b-103">Facebook विज्ञापन प्रबंधक के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="b1f2b-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="b1f2b-104">एकीकृत ग्राहक प्रोफाइल के सेगमेंट को Facebook विज्ञापन प्रबंधक पर निर्यात करें ताकि Facebook और Instagram पर अभियान बनाया जा सके.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b1f2b-105">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="b1f2b-105">Prerequisites</span></span>

- <span data-ttu-id="b1f2b-106">आपके पास ऐसा [**Facebook विज्ञापन खाता**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) होना चाहिए जिसमें एक [**Facebook व्यवसायिक खाता**](https://business.facebook.com/) शामिल हो.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="b1f2b-107">आपको [**Facebook विज्ञापन खाता**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) पर प्रशासक होना होगा.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="b1f2b-108">Facebook विज्ञापन प्रबंधक पर कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="b1f2b-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="b1f2b-109">**व्यवस्थापक** > **गंतव्य निर्यात करें** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b1f2b-110">**Facebook विज्ञापन प्रबंधक** के अंतर्गत, **सेट अप करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="b1f2b-111">अपने गंतव्य-स्थल को **प्रदर्शन नाम** में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b1f2b-112">अपने Facebook विज्ञापन खाता पर साइन इन करने के लिए **Facebook जारी रखें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="b1f2b-113">Facebook के साथ प्रमाणित करने के बाद **ads_management** अनुमति दें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="b1f2b-114">वह **Facebook विज्ञापन खाता** चुनें जिसके साथ आप कार्य करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="b1f2b-115">ड्रॉप-डाउन सूची से **मौजूदा कस्टम ऑडिएंस** का चयन करें या एक **नया कस्टम ऑडिएंस** बनाएँ.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="b1f2b-116">अधिक जानकारी के लिए, [**Facebook विज्ञापन प्रबंधक में ऑडिएंस**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) देखें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="b1f2b-117">**डेटा गोपनीयता और अनुपालन** की पुष्टि करने के लिए **मैं सहमत हूँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b1f2b-118">निर्यात कॉन्फ़िगर करने के लिए **अगला** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b1f2b-119">कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="b1f2b-119">Configure the connector</span></span>

1. <span data-ttu-id="b1f2b-120">Facebook विज्ञापन प्रबंधक पर भेजने के लिए **अपना प्रमुख पहचानकर्ता फ़ील्ड चुनें** में, **ईमेल**, **नाम और पता**, या **फ़ोन** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="b1f2b-121">चयनित मुख्य पहचानकर्ता के लिए अपने एकीकृत ग्राहक निकाय से संबंधित एट्रिब्यूट्स को मैप करें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="b1f2b-122">[युक्ति] यदि आप **ईमेल** को प्रमुख पहचानकर्ता के रूप में चयन करते हैं तो मिलान की संभावनाएँ सबसे अच्छी हो जाती हैं.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="b1f2b-123">अतिरिक्त पहचानकर्ताओं को जोड़ने से मिलान में सुधार हो सकता है.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="b1f2b-124">Facebook विज्ञापन प्रबंधक पर भेजने के लिए अतिरिक्त विशेषताएँ मैप करने के लिए **विशेषता जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="b1f2b-125">Facebook विज्ञापन प्रबंधक से विशेषताएँ निम्नलिखित उपयोगकर्ता अनुकूल नामों पर मैपिंग कर रही हैं: **FN** = **प्रथम नाम**, **LN** = **अंतिम नाम**, **FI** = **पहला आद्यक्षर**, **PHONE** = **फ़ोन**, **GEN** = **लिंग**, **DOB** = **जन्म तिथि**, **ST** = **राज्य**, **CT** = **शहर**, **ZIP** = **डाक कोड / ज़िप कोड**, **COUNTRY** = **देश / क्षेत्र**</span><span class="sxs-lookup"><span data-stu-id="b1f2b-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="b1f2b-126">उन अनुभागों का चयन करें जिन्हें आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="b1f2b-127">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b1f2b-128">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="b1f2b-128">Export the data</span></span>

<span data-ttu-id="b1f2b-129">आप [मांग पर डेटा निर्यात](export-destinations.md) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b1f2b-130">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b1f2b-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b1f2b-131">डेटा गोपनीयता और अनुपालन</span><span class="sxs-lookup"><span data-stu-id="b1f2b-131">Data privacy and compliance</span></span>

<span data-ttu-id="b1f2b-132">जब आप Dynamics 365 Customer Insights को Facebook विज्ञापन प्रबंधक पर डेटा संचारित करने के लिए सक्षम करते हैं, तो आप Dynamics 365 Customer Insights के लिए अनुपालन सीमा के बाहर डेटा के स्थानांतरित करने की अनुमति देते हैं, जिसमें संभावित संवेदनशील डेटा जैसे व्यक्तिगत डेटा शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b1f2b-133">Microsoft आपके निर्देश पर इस तरह के डेटा को स्थानांतरित करेगा, लेकिन आप यह सुनिश्चित करने के लिए उत्तरदायी हैं कि Facebook विज्ञापन आपके पास मौजूद किसी भी गोपनीयता या सुरक्षा दायित्वों को पूरा करता है.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b1f2b-134">अधिक जानकारी के लिए, [Microsoft गोपनीयता कथन](https://go.microsoft.com/fwlink/?linkid=396732) देखें.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b1f2b-135">आपका Dynamics 365 Customer Insights एडमिनिस्ट्रेटर इस कार्यक्षमता का उपयोग बंद करने के लिए किसी भी समय इस निर्यात गंतव्य को हटा सकता है.</span><span class="sxs-lookup"><span data-stu-id="b1f2b-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
