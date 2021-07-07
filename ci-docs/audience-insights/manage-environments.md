---
title: परिवेश बनाएं और प्रबंधित करें
description: जानें कि सेवा के लिए साइन अप कैसे करें और परिवेश का प्रबंधन कैसे करें.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304882"
---
# <a name="manage-environments"></a><span data-ttu-id="96fe4-103">परिवेश प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="96fe4-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="96fe4-104">इस लेख में बताया गया है कि कैसे एक नया संगठन बनाने के लिए और कैसे एक परिवेश प्रावधान करने के लिए.</span><span class="sxs-lookup"><span data-stu-id="96fe4-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="96fe4-105">साइन अप करें और एक संगठन बनाएं</span><span class="sxs-lookup"><span data-stu-id="96fe4-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="96fe4-106">[Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) वेबसाइट पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="96fe4-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="96fe4-107">**आरंभ करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="96fe4-108">अपना पसंदीदा साइन-अप परिदृश्य चुनें और संबंधित लिंक को चुनें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="96fe4-109">नियम और शर्तें स्वीकार करें और संगठन बनाना शुरू के लिए **जारी रखें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="96fe4-110">परिवेश बनने के बाद, आपको [Customer Insights](https://home.ci.ai.dynamics.com) पर रीडायरेक्ट किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="96fe4-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="96fe4-111">अनुप्रयोग को एक्सप्लोर करने के लिए डेमो परिवेश का उपयोग करें, या अगले खंड में दिये चरणों का पालन करके एक नया परिवेश बनाएं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="96fe4-112">परिवेश सेटिंग्स निर्दिष्ट करने के बाद, **बनाएं** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="96fe4-113">परिवेश को सफलतापूर्वक बनाने के बाद आपको साइन इन किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="96fe4-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="96fe4-114">किसी मौजूदा संगठन में एक परिवेश बनाएँ</span><span class="sxs-lookup"><span data-stu-id="96fe4-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="96fe4-115">नया परिवेश बनाने के दो तरीके हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="96fe4-116">आप या तो पूरी तरह से नया कॉन्फ़िगरेशन निर्दिष्ट कर सकते हैं, या आप मौजूदा परिवेश से कुछ कॉन्फ़िगरेशन सेटिंग्स कॉपी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="96fe4-117">संगठन हर Customer Insights लाइसेंस के लिए *दो* परिवेश बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="96fe4-118">यदि आपका संगठन एक से अधिक बार लाइसेंस खरीदता है, तो कृपया उपलब्ध परिवेश की संख्या बढ़ाने के लिए [हमारी सहायता टीम](https://go.microsoft.com/fwlink/?linkid=2079641) से संपर्क करें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="96fe4-119">क्षमता और ऐड-ऑन क्षमता के बारे में अधिक जानकारी के लिए, [Dynamics 365 लाइसेंसिंग गाइड](https://go.microsoft.com/fwlink/?LinkId=866544) डाउनलोड करें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="96fe4-120">एक परिवेश बनाएँ:</span><span class="sxs-lookup"><span data-stu-id="96fe4-120">To create an environment:</span></span>

1. <span data-ttu-id="96fe4-121">ऐप के हेडर में **परिवेश** पिकर का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="96fe4-122">**नया** चुनें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="96fe4-123">![परिवेश सेटिंग्स।](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="96fe4-123">![Environment settings.](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="96fe4-124">**एक परिवेश बनाएं** संवाद में, **नया परिवेश** चुनें।</span><span class="sxs-lookup"><span data-stu-id="96fe4-124">In the **Create an environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="96fe4-125">यदि आप [वर्तमान परिवेश से डेटा की प्रतिलिपि बनाना चाहते हैं](#considerations-for-copy-configuration-preview), तो **मौजूदा परिवेश से प्रतिलिपि बनाएँ** चुनें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="96fe4-126">आपको अपने संगठन के सभी उपलब्ध परिवेशों की एक सूची दिखाई देगी जहां से आप डेटा कॉपी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="96fe4-127">निम्न विवरण प्रदान करें:</span><span class="sxs-lookup"><span data-stu-id="96fe4-127">Provide the following details:</span></span>
   - <span data-ttu-id="96fe4-128">**नाम**: इस वातावरण का नाम है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="96fe4-129">यदि आपने मौजूदा परिवेश को कॉपी किया है, तो यह फ़ील्ड पहले से ही भरी हुई होती है, लेकिन आप इसे बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="96fe4-130">**प्रकार**: चुनें कि क्या आप प्रोडक्शन परिवेश बनाना चाहते हैं या सैंडबॉक्स.</span><span class="sxs-lookup"><span data-stu-id="96fe4-130">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>
   - <span data-ttu-id="96fe4-131">**क्षेत्र**: वह क्षेत्र जिसमें सेवा को तैनात और होस्ट किया गया है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-131">**Region**: The region into which the service is deployed and hosted.</span></span>
   
1. <span data-ttu-id="96fe4-132">वैकल्पिक रूप से, आप **उन्नत सेटिंग** चुन सकते हैं:</span><span class="sxs-lookup"><span data-stu-id="96fe4-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="96fe4-133">**सभी डेटा को सहेजें**: यह निर्दिष्ट करता है कि आप Customer Insights से जनित आउटपुट डेटा को कहां संग्रहीत करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="96fe4-134">आपके पास दो विकल्प होंगे: **Customer Insights संग्रहण** (एक Azure Data Lake जिसे Customer Insights टीम द्वारा प्रबंधित किया जाता है) और **Azure Data Lake Storage** (अपना खुद का Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="96fe4-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="96fe4-135">डिफ़ॉल्ट रूप से, Customer Insights संग्रहण विकल्प चुना जाता है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-135">By default, the Customer Insights storage option is selected.</span></span>

     > [!NOTE]
     > <span data-ttu-id="96fe4-136">Azure Data Lake Storage में डेटा को सहेजकर, आप सहमत होते हैं कि डेटा उस Azure संग्रहण खाते के लिए उपयुक्त भौगोलिक स्थान पर स्थानांतरित और संग्रहित किया जाएगा, जो कि Dynamics 365 Customer Insights में डेटा संग्रहित करने से भिन्न हो सकता है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="96fe4-137">Microsoft विश्वास केन्द्र पर अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
     >
     > <span data-ttu-id="96fe4-138">वर्तमान में, अंतर्ग्रहीय निकायों को हमेशा Customer Insights द्वारा प्रबंधित Data Lake में संग्रहित किया जाता है।</span><span class="sxs-lookup"><span data-stu-id="96fe4-138">Currently, ingested entities are always stored in the Customer Insights Managed Data Lake.</span></span> 
     > 
     > <span data-ttu-id="96fe4-139">हम केवल उसी Azure क्षेत्र के Azure Data Lake Storage खातों का समर्थन करते हैं, जिसे आपने परिवेश बनाते समय चुना था।</span><span class="sxs-lookup"><span data-stu-id="96fe4-139">We support only Azure Data Lake Storage accounts from the same Azure region you selected when creating the environment.</span></span> 
     > 
     > <span data-ttu-id="96fe4-140">हम केवल उन Azure Data Lake Storage खातों का समर्थन करते हैं जिनमें पदानुक्रमित नाम स्थान सक्षम है।</span><span class="sxs-lookup"><span data-stu-id="96fe4-140">We support only Azure Data Lake Storage accounts that have hierarchical namespace enabled.</span></span>


   - <span data-ttu-id="96fe4-141">Azure Data Lake Storage विकल्प के लिए, आप प्रमाणीकरण के लिए संसाधन-आधारित विकल्प और सदस्यता-आधारित विकल्प के बीच चयन कर सकते हैं।</span><span class="sxs-lookup"><span data-stu-id="96fe4-141">For the Azure Data Lake Storage option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="96fe4-142">अधिक जानकारी के लिए, देखें [एक Azure Data Lake Storage Gen2 खाते के लिए एक Azure service principal के साथ ऑडियंस इन्साइट्स को कनेक्ट करें](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="96fe4-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="96fe4-143">**कंटेनर** का नाम बदला नहीं जा सकता है और यह `customerinsights` रहेगा.</span><span class="sxs-lookup"><span data-stu-id="96fe4-143">The **Container** name can't be changed and will be `customerinsights`.</span></span>
   
   - <span data-ttu-id="96fe4-144">अगर आप [पूर्वानुमानों](predictions.md) का उपयोग करना चाहते हैं, तो Microsoft Dataverse के साथ डेटा साझा करना कॉन्फ़िगर करें या ऑन-प्रीमाइसेस डेटा स्रोतों से डेटा अंतर्ग्रहण सक्षम करें, **Microsoft Dataverse डेटा साझा करना कॉन्फ़िगर करें और अतिरिक्त क्षमताओं को सक्षम करें** के तहत Microsoft Dataverse परिवेश URL प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-144">If you want to use [predictions](predictions.md), configure data sharing with Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="96fe4-145">**डेटा साझाकरण सक्षम करें** को चुनें, ताकि Microsoft Dataverse प्रबंधित Data Lake के साथ Customer Insights आउटपुट डेटा साझा किया जा सके.</span><span class="sxs-lookup"><span data-stu-id="96fe4-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="96fe4-146">जब आप सभी डेटा को अपने Azure Data Lake Storage में सहेजते हैं, Microsoft Dataverse प्रबंधित डेटा लेक के साथ डेटा साझाकरण वर्तमान में समर्थित नहीं है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="96fe4-147">जब आप Microsoft Dataverse प्रबंधित Data Lake के साथ डेटा साझा करने को सक्षम करते हैं, तो [एक निकाय में लापता मानों का पूर्वानुमान](predictions.md) वर्तमान में समर्थित नहीं है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="96fe4-148">![ Microsoft Dataverse के साथ डेटा साझा करने में सक्षम करने का कॉन्फ़िगरेशन विकल्प.](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="96fe4-148">![Configuration options to enable data sharing with Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="96fe4-149">जब आप प्रक्रियाएं चलाते हैं, जैसे डेटा इन्जेस्चन या सेगमेंट निर्माण, संबंधित फ़ोल्डर आपके ऊपर निर्दिष्ट स्टोरेज खाते में बनाए जाएंगे.</span><span class="sxs-lookup"><span data-stu-id="96fe4-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="96fe4-150">प्रक्रिया नाम के आधार पर डेटा फ़ाइलें और model.json फाइलें संबंधित फ़ोल्डर्स में बनाई जाएंगी और जोड़ी जाएंगी.</span><span class="sxs-lookup"><span data-stu-id="96fe4-150">Data files and model.json files will be created and added to folders based on the process name.</span></span>

   <span data-ttu-id="96fe4-151">यदि आप Customer Insights के कई परिवेश बनाते हैं और अपने स्टोरेज खाते में उन परिवेशों से आउटपुट निकायों को सहेजना चुनते हैं, तो कंटेनर में ci_<environmentid> के साथ प्रत्येक परिवेश के लिए अलग-अलग फ़ोल्डर बनाए जाएंगे.</span><span class="sxs-lookup"><span data-stu-id="96fe4-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="96fe4-152">कॉन्फ़िगरेशन कॉपी करने के लिए विचार (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="96fe4-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="96fe4-153">निम्नलिखित कॉन्फ़िगरेशन सेटिंग्स को कॉपी किया जाता है:</span><span class="sxs-lookup"><span data-stu-id="96fe4-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="96fe4-154">फ़ीचर कॉन्‍फ़िगरेशन</span><span class="sxs-lookup"><span data-stu-id="96fe4-154">Feature configurations</span></span>
- <span data-ttu-id="96fe4-155">अंतर्ग्रहण किया गया/आयातित डेटा स्रोत</span><span class="sxs-lookup"><span data-stu-id="96fe4-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="96fe4-156">डेटा एकीकरण (मानचित्र, मिलान, मर्ज) कॉन्फ़िगरेशन</span><span class="sxs-lookup"><span data-stu-id="96fe4-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="96fe4-157">खंड</span><span class="sxs-lookup"><span data-stu-id="96fe4-157">Segments</span></span>
- <span data-ttu-id="96fe4-158">माप</span><span class="sxs-lookup"><span data-stu-id="96fe4-158">Measures</span></span>
- <span data-ttu-id="96fe4-159">संबंध</span><span class="sxs-lookup"><span data-stu-id="96fe4-159">Relationships</span></span>
- <span data-ttu-id="96fe4-160">गतिविधियाँ</span><span class="sxs-lookup"><span data-stu-id="96fe4-160">Activities</span></span>
- <span data-ttu-id="96fe4-161">इंडेक्स खोजें और फ़ि‍ल्‍टर करें</span><span class="sxs-lookup"><span data-stu-id="96fe4-161">Search & filter Index</span></span>
- <span data-ttu-id="96fe4-162">निर्यात गंतव्य</span><span class="sxs-lookup"><span data-stu-id="96fe4-162">Export destinations</span></span>
- <span data-ttu-id="96fe4-163">शेड्यूल किया गया रीफ़्रेश</span><span class="sxs-lookup"><span data-stu-id="96fe4-163">Scheduled refresh</span></span>
- <span data-ttu-id="96fe4-164">संवर्धन</span><span class="sxs-lookup"><span data-stu-id="96fe4-164">Enrichments</span></span>
- <span data-ttu-id="96fe4-165">मॉडल प्रबंधन</span><span class="sxs-lookup"><span data-stu-id="96fe4-165">Model management</span></span>
- <span data-ttu-id="96fe4-166">भूमिका असाइनमेंट</span><span class="sxs-lookup"><span data-stu-id="96fe4-166">Role assignments</span></span>

<span data-ttu-id="96fe4-167">निम्नलिखित सेटिंग्स को कॉपी *नहीं* किया जाता है:</span><span class="sxs-lookup"><span data-stu-id="96fe4-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="96fe4-168">ग्राहक के प्रोफाइल.</span><span class="sxs-lookup"><span data-stu-id="96fe4-168">Customer profiles.</span></span>
- <span data-ttu-id="96fe4-169">डेटा स्रोत क्रेडेंशियल.</span><span class="sxs-lookup"><span data-stu-id="96fe4-169">Data source credentials.</span></span> <span data-ttu-id="96fe4-170">आपको प्रत्येक डेटा स्रोत के लिए क्रेडेंशियल्स प्रदान करना होगा और डेटा स्रोतों को मैन्युअल रूप से रिफ़ेश करना होगा.</span><span class="sxs-lookup"><span data-stu-id="96fe4-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="96fe4-171">सामान्य डेटा मॉडल फ़ोल्डर और Dataverse प्रबंधित Data Lake से डेटा स्रोत.</span><span class="sxs-lookup"><span data-stu-id="96fe4-171">Data sources from Common Data Model folder and Dataverse managed Data Lake.</span></span> <span data-ttu-id="96fe4-172">आपको उन डेटा स्रोतों को मैन्युअल रूप से उसी नाम से बनाना होगा जैसा कि स्रोत परिवेश में है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="96fe4-173">जब आप किसी परिवेश को कॉपी करते हैं, तो आपको एक पुष्टिकरण संदेश दिखाई देगा कि नया परिवेश बनाया गया है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="96fe4-174">डेटा स्रोतों की सूची देखने हेतु **डेटा स्रोतों पर जाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="96fe4-175">सभी डेटा स्रोत एक **क्रेडेंशियल अपेक्षित** वस्तु स्थिति दिखाएंगे.</span><span class="sxs-lookup"><span data-stu-id="96fe4-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="96fe4-176">डेटा स्रोतों को संपादित करें और उन्हें रिफ़्रेश करने हेतु क्रेडेंशियल दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96fe4-177">![डेटा स्रोतों को कॉपी किया गया।](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="96fe4-177">![Data sources copied.](media/data-sources-copied.png)</span></span>

<span data-ttu-id="96fe4-178">डेटा स्रोतों को रिफ्रेश करने के बाद, **डेटा** > **एकीकृत करें** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="96fe4-179">यहां आपको स्रोत परिवेश से सेटिंग्स मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="96fe4-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="96fe4-180">उन्हें आवश्यकतानुसार संपादित करें या डेटा एकीकरण प्रक्रिया आरंभ करने और एकीकृत ग्राहक निकाय बनाने हेतु **चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="96fe4-181">जब डेटा एकीकरण पूरा हो जाता है, तो उन्हें भी रिफ़्रेश करने हेतु **उपाय** और **खंड** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="96fe4-182">एक विद्यमान परिवेश संपादित करें</span><span class="sxs-lookup"><span data-stu-id="96fe4-182">Edit an existing environment</span></span>

<span data-ttu-id="96fe4-183">आप विद्यमान परिवेश के कुछेक विवरणों को संपादित कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="96fe4-184">ऐप के हेडर में **परिवेश** पिकर का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="96fe4-185">**संपादन** आइकन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="96fe4-186">**परिवेश संपादित करें** बॉक्स में, आप परिवेश के **प्रदर्शन नाम** को अपडेट कर सकते हैं, लेकिन आप **क्षेत्र** या **प्रकार** को नहीं बदल सकते.</span><span class="sxs-lookup"><span data-stu-id="96fe4-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="96fe4-187">यदि किसी परिवेश को Azure Data Lake Storage में डेटा संग्रहीत करने के लिए कॉन्फ़िगर किया गया है, तो आप **खाता कुंजी** अपडेट कर सकते हैं।</span><span class="sxs-lookup"><span data-stu-id="96fe4-187">If an environment is configured to store data in Azure Data Lake Storage, you can update the **Account key**.</span></span> <span data-ttu-id="96fe4-188">लेकिन, आप **खाते का नाम** या **कंटेनर** नाम नहीं बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="96fe4-189">वैकल्पिक रूप से, आप खाता कुंजी-आधारित कनेक्शन से संसाधन-आधारित या सदस्यता-आधारित कनेक्शन में अपडेट कर सकते हैं।</span><span class="sxs-lookup"><span data-stu-id="96fe4-189">Optionally, you can update from an account key-based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="96fe4-190">एक बार अपग्रेड होने के बाद, आप अपडेट के बाद खाता कुंजी पर वापस नहीं लौट सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="96fe4-191">अधिक जानकारी के लिए, देखें [एक Azure Data Lake Storage Gen2 खाते के लिए एक Azure service principal के साथ ऑडियंस इन्साइट्स को कनेक्ट करें](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="96fe4-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="96fe4-192">कनेक्शन अपडेट करते समय आप **कंटेनर** जानकारी नहीं बदल सकते.</span><span class="sxs-lookup"><span data-stu-id="96fe4-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="96fe4-193">वैकल्पिक रूप से, आप Microsoft Dataverse के साथ डेटा साझा करना कॉन्फ़िगर करें और अतिरिक्त क्षमताओं को सक्षम करें **के तहत Microsoft Dataverse परिवेश का URL प्रदान कर सकते हैं**.</span><span class="sxs-lookup"><span data-stu-id="96fe4-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="96fe4-194">ये क्षमताएं Microsoft Dataverse के आधार पर अनुप्रयोगों और समाधानों के साथ डेटा साझा करने, ऑन-प्रीमाइसेस डेटा स्रोतों से डेटा अंतर्ग्रहण करने या [पूर्वानुमानों](predictions.md) का उपयोग शामिल करती हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-194">These capabilities include data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="96fe4-195">**डेटा साझाकरण सक्षम करें** को चुनें, ताकि Microsoft Dataverse प्रबंधित Data Lake के साथ Customer Insights आउटपुट डेटा साझा किया जा सके.</span><span class="sxs-lookup"><span data-stu-id="96fe4-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="96fe4-196">जब आप सभी डेटा को अपने Azure Data Lake Storage में सहेजते हैं, Microsoft Dataverse प्रबंधित डेटा लेक के साथ डेटा साझाकरण वर्तमान में समर्थित नहीं है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="96fe4-197">जब आप Microsoft Dataverse प्रबंधित Data Lake के साथ डेटा साझा करना सक्षम करते हैं तो ऐसे में [एक निकाय में लापता मानों का पूर्वानुमान](predictions.md) वर्तमान में समर्थित नहीं है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="96fe4-198">Microsoft Dataverse के साथ डेटा साझा करना सक्षम करने के बाद, आपके डेटा स्रोतों और अन्य प्रक्रियाओं का पूरा रिफ़्रेश शुरू होता है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-198">After enabling data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes starts.</span></span> <span data-ttu-id="96fe4-199">यदि प्रक्रियाएं वर्तमान में चल रही हैं, तो आपको Microsoft Dataverse के साथ डेटा साझा करने में सक्षम करने का विकल्प नहीं दिखाई देता है.</span><span class="sxs-lookup"><span data-stu-id="96fe4-199">If processes are currently running, you don't see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="96fe4-200">डेटा साझा करने को सक्षम करने के लिए उन प्रक्रियाओं के पूरा होने तक प्रतीक्षा करें या रद्द करें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-200">Wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text=" Microsoft Dataverse के साथ डेटा साझा करने में सक्षम करने का कॉन्फ़िगरेशन विकल्प.":::
   
   <span data-ttu-id="96fe4-202">जब आप प्रक्रियाएं चलाते हैं, जैसे डेटा इन्जेस्चन या सेगमेंट निर्माण, संबंधित फ़ोल्डर आपके ऊपर निर्दिष्ट स्टोरेज खाते में बनाए जाएंगे.</span><span class="sxs-lookup"><span data-stu-id="96fe4-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="96fe4-203">आपके द्वारा चलाई जाने वाली प्रक्रिया के आधार पर डेटा फ़ाइलें और model.json फाइलें संबंधित सबफोल्डर्स में बनाई जाएंगी और जोड़ी जाएंगी.</span><span class="sxs-lookup"><span data-stu-id="96fe4-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="96fe4-204">मौजूदा परिवेश को रीसेट करना</span><span class="sxs-lookup"><span data-stu-id="96fe4-204">Reset an existing environment</span></span>

<span data-ttu-id="96fe4-205">एडमिनिस्ट्रेटर के रूप में, यदि आप सभी कॉन्फ़िगरेशन हटाना चाहते हैं और अंतर्ग्रहण किए गए डेटा को हटाना चाहते हैं, तो आप एक परिवेश को खाली स्थिति में रीसेट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="96fe4-206">ऐप के हेडर में **परिवेश** पिकर का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="96fe4-207">उस परिवेश का चयन करें जिसे आप रीसेट करना चाहते हैं और एलिप्सिस (**...**) का चयन करें।</span><span class="sxs-lookup"><span data-stu-id="96fe4-207">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="96fe4-208">**रीसेट** विकल्प चुनें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="96fe4-209">हटाने की पुष्टि करने के लिए, परिवेश का नाम दर्ज करें और **रीसेट** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment"></a><span data-ttu-id="96fe4-210">मौजूदा परिवेश हटाएँ</span><span class="sxs-lookup"><span data-stu-id="96fe4-210">Delete an existing environment</span></span>

<span data-ttu-id="96fe4-211">एडमिनिस्ट्रेटर के रूप में, आप अपने द्वारा प्रबंधित किए गए परिवेश को हटा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="96fe4-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="96fe4-212">ऐप के हेडर में **परिवेश** पिकर का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="96fe4-213">उस परिवेश का चयन करें जिसे आप रीसेट करना चाहते हैं और एलिप्सिस (**...**) का चयन करें।</span><span class="sxs-lookup"><span data-stu-id="96fe4-213">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="96fe4-214">**हटाएं** विकल्प चुनें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="96fe4-215">हटाने की पुष्टि करने हेतु, परिवेश का नाम दर्ज करें और **हटाने** चुनें.</span><span class="sxs-lookup"><span data-stu-id="96fe4-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
