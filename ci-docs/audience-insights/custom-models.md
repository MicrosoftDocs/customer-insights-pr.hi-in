---
title: कस्टम मशीन लर्निंग मॉडल | Microsoft Docs
description: Dynamics 365 Customer Insights में Azure मशीन लर्निंग से कस्टम मॉडल के साथ काम करें.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305636"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="71da7-103">कस्टम मशीन लर्निंग मॉडल</span><span class="sxs-lookup"><span data-stu-id="71da7-103">Custom machine learning models</span></span>

<span data-ttu-id="71da7-104">**इंटेलिजेंस** > **कस्टम मॉडल** आपको Azure मशीन लर्निंग मॉडल के आधार पर कार्यप्रवाह का प्रबंधन करने देता है.</span><span class="sxs-lookup"><span data-stu-id="71da7-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="71da7-105">कार्यप्रवाह आपको उस डेटा को चुनने में मदद करते हैं, जिनसे आप इन्साइट्स उत्पन्न करना चाहते हैं और परिणामों को अपने एकीकृत ग्राहक डेटा पर मैप करते हैं.</span><span class="sxs-lookup"><span data-stu-id="71da7-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="71da7-106">कस्टम ML मॉडल के निर्माण के बारे में अधिक जानकारी के लिए, [Azure मशीन लर्निंग-आधारित मॉडल का उपयोग करें](azure-machine-learning-experiments.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="71da7-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="71da7-107">जिम्मेदार AI</span><span class="sxs-lookup"><span data-stu-id="71da7-107">Responsible AI</span></span>

<span data-ttu-id="71da7-108">पूर्वानुमानें बेहतर ग्राहक अनुभव बनाने, व्यावसायिक क्षमताओं और राजस्व धाराओं में सुधार करने की क्षमताएं प्रदान करती हैं.</span><span class="sxs-lookup"><span data-stu-id="71da7-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="71da7-109">हम दृढ़ता से आपको सलाह देते हैं कि आप अपने पूर्वानुमान के मान को इसके प्रभाव और पूर्वाग्रहों के खिलाफ संतुलित करें जिसे नैतिक तरीके से पेश किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="71da7-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="71da7-110">Microsoft कैसा है [जिम्मेदार AI का संबोधन](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) के बारे में अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="71da7-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="71da7-111">आप [जिम्मेदार मशीन लर्निंग के लिए तकनीकों और प्रक्रियाओं](/azure/machine-learning/concept-responsible-ml) के बारे में भी जान सकते हैं जो Azure मशीन लर्निंग के लिए विशिष्ट है .</span><span class="sxs-lookup"><span data-stu-id="71da7-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="71da7-112">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="71da7-112">Prerequisites</span></span>

- <span data-ttu-id="71da7-113">वर्तमान में, यह सुविधा [मशीन लर्निंग स्टूडियो (क्लासिक)](https://studio.azureml.net) और [Azure मशीन लर्निंग बैच पाइपलाइन](/azure/machine-learning/concept-ml-pipelines) के माध्यम से प्रकाशित वेब सेवाओं का समर्थन करती है.</span><span class="sxs-lookup"><span data-stu-id="71da7-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="71da7-114">इस सुविधा का उपयोग करने के लिए आपको अपने Azure स्टूडियो उदाहरण से जुड़े एक Azure Data Lake Gen2 स्टोरेज खाते की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="71da7-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="71da7-115">अधिक जानकारी के लिए, [Azure Data Lake Storage जेन2 स्टोरेज खाता बनाएं](/azure/storage/blobs/data-lake-storage-quickstart-create-account) देखें.</span><span class="sxs-lookup"><span data-stu-id="71da7-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="71da7-116">पाइपलाइन्स के साथ Azure मशीन लर्निंग वर्कस्पेस के लिए, आपको Azure मशीन लर्निंग वर्कस्पेस के लिए स्वामी या यूज़र एक्सेस एडमिनिस्ट्रेटर की अनुमति चाहिए.</span><span class="sxs-lookup"><span data-stu-id="71da7-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="71da7-117">डेटा को आपके Customer Insights इंस्टेंस और कार्य प्रवाह में चयनित Azure वेब सेवाओं या पाइपलाइन्स के बीच ट्रांसफर किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="71da7-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="71da7-118">जब आप डेटा को किसी Azure सेवा में स्थानांतरित करते हैं, तो कृपया सुनिश्चित करें कि सेवा आपके संगठन के लिए उस डेटा के लिए किसी भी कानूनी या नियामक आवश्यकताओं का अनुपालन करने के लिए आवश्यक तरीके और स्थान में डेटा को संसाधित करने के लिए कॉन्फ़िगर की गई है.</span><span class="sxs-lookup"><span data-stu-id="71da7-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="71da7-119">नया कार्यप्रवाह जोड़ें</span><span class="sxs-lookup"><span data-stu-id="71da7-119">Add a new workflow</span></span>

1. <span data-ttu-id="71da7-120">**इंटेलिजेंस** > **कस्टम मॉडल्स** पर जाएं और **नया कार्यप्रवाह** चुनें.</span><span class="sxs-lookup"><span data-stu-id="71da7-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="71da7-121">अपने कस्टम मॉडल को **नाम** फ़ील्ड में एक पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="71da7-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="71da7-122">![नए कार्यप्रवाह फलक का स्क्रीनशॉट](media/new-workflowv2.png "नए कार्यप्रवाह फलक का स्क्रीनशॉट")</span><span class="sxs-lookup"><span data-stu-id="71da7-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="71da7-123">उस संगठन का चयन करें जिसमें **टैनेंट जिसमें आपकी वेब सेवा शामिल है** शामिल है.</span><span class="sxs-lookup"><span data-stu-id="71da7-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="71da7-124">यदि आपकी Azure मशीन लर्निंग सदस्यता Customer Insights से अलग टैनेंट में है, तो चयनित संगठन के लिए अपनी पहचान के साथ **साइन इन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="71da7-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="71da7-125">अपनी वेब सेवा से जुड़े **कार्यस्थानों** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="71da7-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="71da7-126">दो अनुभागें सूचीबद्ध हैं, एक Azure मशीन लर्निंग v1 (मशीन लर्निंग स्टूडियो (क्लासिक)) और Azure मशीन लर्निंग v2 (Azure मशीन लर्निंग) के लिए.</span><span class="sxs-lookup"><span data-stu-id="71da7-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="71da7-127">यदि आप पक्के तौर पर यह नहीं कह सकते हैं कि आपके मशीन लर्निंग स्टूडियो (क्लासिक) वेब सेवा के लिए कौन सा कार्यक्षेत्र सही है, तो **किसी भी** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="71da7-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="71da7-128">**आपके मॉडल को शामिल करने वाली वेब सेवा** ड्रॉपडाउन में मशीन लर्निंग स्टूडियो (क्लासिक) वेब सेवा या Azure मशीन लर्निंग पाइपलाइन चुनें.</span><span class="sxs-lookup"><span data-stu-id="71da7-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="71da7-129">उसके बाद, **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="71da7-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="71da7-130">[मशीन लर्निंग स्टूडियो (क्लासिक) में एक वेब सेवा का प्रकाशन](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) के बारे में अधिक जानें</span><span class="sxs-lookup"><span data-stu-id="71da7-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="71da7-131">[Azure मशीन लर्निंग में डिजाइनर का उपयोग करके एक पाइपलाइन का प्रकाशन](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) या [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) के बारे में अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="71da7-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="71da7-132">आपकी पाइपलाइन को [पाइपलाइन एंडपॉइंट](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) के तहत प्रकाशित किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="71da7-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="71da7-133">प्रत्येक **वेब सेवा इनपुट** के लिए, ऑडियंस इनसाइट्स से मिलते-जुलते **निकाय** का चयन करें और **अगला** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="71da7-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="71da7-134">कस्टम मॉडल कार्य प्रवाह, स्वतः शोध प्रणाली लागू करेगा, ताकि फ़ील्ड के नाम और डेटा प्रकार के आधार पर निकाय के एट्रिब्यूट के लिए वेब सेवा इनपुट फ़ील्ड को मैप किया जा सके.</span><span class="sxs-lookup"><span data-stu-id="71da7-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="71da7-135">अगर वेब सेवा फ़ील्ड को किसी निकाय में मैप नहीं किया जा सकता है तो आपको एक त्रुटि दिखाई देगी.</span><span class="sxs-lookup"><span data-stu-id="71da7-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="71da7-136">![कार्यप्रवाह कॉन्फ़िगर करें](media/intelligence-screen2-updated.png "कार्यप्रवाह कॉन्फ़िगर करें")</span><span class="sxs-lookup"><span data-stu-id="71da7-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="71da7-137">**मॉडल आउटपुट पैरामीटर** चरण में, निम्नलिखित गुणों को सेट करें:</span><span class="sxs-lookup"><span data-stu-id="71da7-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="71da7-138">मशीन लर्निंग स्टूडियो (क्लासिक)</span><span class="sxs-lookup"><span data-stu-id="71da7-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="71da7-139">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि वेब सेवा आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="71da7-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="71da7-140">Azure मशीन लर्निंग</span><span class="sxs-lookup"><span data-stu-id="71da7-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="71da7-141">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि पाइपलाइन आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="71da7-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="71da7-142">ड्रॉपडाउन से अपने बैच पाइपलाइन के **आउटपुट डेटा स्टोर पैरामीटर के नाम** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="71da7-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="71da7-143">ड्रॉपडाउन से अपने बैच पाइपलाइन के **आउटपुट पाथ पैरामीटर के नाम** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="71da7-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="71da7-144">![मॉडल आउटपुट पैरामीटर फलक](media/intelligence-screen3-outputparameters.png "मॉडल आउटपुट पैरामीटर फलक")</span><span class="sxs-lookup"><span data-stu-id="71da7-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="71da7-145">**परिणामों में ग्राहक ID** ड्रॉप-डाउन सूची से मेल खाने वाले एट्रिब्यूट का चयन करें जो ग्राहक को पहचानता है और **सहेजें** चुनें।</span><span class="sxs-lookup"><span data-stu-id="71da7-145">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="71da7-146">![ग्राहक डेटा फलक से परिणामों को संबंधित करें](media/intelligence-screen4-relatetocustomer.png "ग्राहक डेटा फलक से परिणामों को संबंधित करें")</span><span class="sxs-lookup"><span data-stu-id="71da7-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="71da7-147">आप कार्यप्रवाह के बारे में विवरण के साथ **सहेजे गये कार्यप्रवाह** स्क्रीन देखेंगे.</span><span class="sxs-lookup"><span data-stu-id="71da7-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="71da7-148">यदि आप एक Azure मशीन लर्निंग पाइपलाइन के लिए एक कार्यप्रवाह कॉन्फ़िगर करते हैं, तो ऑडियंस इनसाइट्स उस पाइपलाइन वाले कार्यक्षेत्र से जुड़ी होगी.</span><span class="sxs-lookup"><span data-stu-id="71da7-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="71da7-149">ऑडियंस इनसाइट्स को Azure कार्यक्षेत्र पर **योगदानकर्ता** भूमिका मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="71da7-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="71da7-150">**पूर्ण** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="71da7-150">Select **Done**.</span></span>

1. <span data-ttu-id="71da7-151">अब आप **कस्टम मॉडल** पेज से कार्यप्रवाह चला सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="71da7-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="71da7-152">कार्यप्रवाह संपादित करें</span><span class="sxs-lookup"><span data-stu-id="71da7-152">Edit a workflow</span></span>

1. <span data-ttu-id="71da7-153">**कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें और **संपादन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="71da7-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="71da7-154">आप **नाम प्रदर्शित करें** फ़ील्ड में अपने कार्यप्रवाह के पहचानने योग्य नाम को अपडेट कर सकते हैं, लेकिन आप कॉन्फ़िगर की गई वेब सेवा या पाइपलाइन को नहीं बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="71da7-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="71da7-155">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="71da7-155">Select **Next**.</span></span>

1. <span data-ttu-id="71da7-156">प्रत्येक **वेब सेवा इनपुट** के लिए, आप ऑडियंस इनसाइट्स से मिलते-जुलते **निकाय** अपडेट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="71da7-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="71da7-157">उसके बाद, **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="71da7-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="71da7-158">**मॉडल आउटपुट पैरामीटर** चरण में, निम्नलिखित गुणों को सेट करें:</span><span class="sxs-lookup"><span data-stu-id="71da7-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="71da7-159">मशीन लर्निंग स्टूडियो (क्लासिक)</span><span class="sxs-lookup"><span data-stu-id="71da7-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="71da7-160">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि वेब सेवा आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="71da7-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="71da7-161">Azure मशीन लर्निंग</span><span class="sxs-lookup"><span data-stu-id="71da7-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="71da7-162">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि पाइपलाइन आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="71da7-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="71da7-163">अपनी टेस्ट पाइपलाइन के लिए **आउटपुट डेटा स्टोर पैरामीटर का नाम** चुनें.</span><span class="sxs-lookup"><span data-stu-id="71da7-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="71da7-164">अपनी टेस्ट पाइपलाइन के लिए **आउटपुट पाथ पैरामीटर का नाम** चुनें.</span><span class="sxs-lookup"><span data-stu-id="71da7-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="71da7-165">**परिणामों में ग्राहक ID** ड्रॉप-डाउन सूची से मेल खाने वाले एट्रिब्यूट का चयन करें जो ग्राहक को पहचानता है और **सहेजें** चुनें।</span><span class="sxs-lookup"><span data-stu-id="71da7-165">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="71da7-166">ग्राहक निकाय के ग्राहक आईडी कॉलम के जैसे ही मानों वाले अनुमान आउटपुट से एट्रिब्यूट चुनें.</span><span class="sxs-lookup"><span data-stu-id="71da7-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="71da7-167">अगर आपके डेटा सेट में ऐसा कोई कॉलम नहीं है, तो ऐसी विशेषता चुनें जो पंक्ति को विशिष्ट रूप से पहचानती हो.</span><span class="sxs-lookup"><span data-stu-id="71da7-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="71da7-168">कार्यप्रवाह चलाएँ</span><span class="sxs-lookup"><span data-stu-id="71da7-168">Run a workflow</span></span>

1. <span data-ttu-id="71da7-169">**कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले में बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="71da7-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="71da7-170">**चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="71da7-170">Select **Run**.</span></span>

<span data-ttu-id="71da7-171">आपका कार्यप्रवाह भी हर शेड्यूल किए गए रिफ्रेश के साथ स्वत: चलता है.</span><span class="sxs-lookup"><span data-stu-id="71da7-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="71da7-172">[शेड्यूल रीफ्रेश सेट अप करना](system.md#schedule-tab) के बारे में और जानें.</span><span class="sxs-lookup"><span data-stu-id="71da7-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="71da7-173">कार्यप्रवाह हटाएँ</span><span class="sxs-lookup"><span data-stu-id="71da7-173">Delete a workflow</span></span>

1. <span data-ttu-id="71da7-174">**कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले में बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="71da7-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="71da7-175">**हटाएं** का चयन करें और अपने हटाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="71da7-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="71da7-176">आपका कार्यप्रवाह हटा दिया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="71da7-176">Your workflow will be deleted.</span></span> <span data-ttu-id="71da7-177">वह [निकाय](entities.md) जिसे आपके द्वारा कार्यप्रवाह बनाने के दौरान बनाया गया था, बना रहता है और उसे **निकाय** पेज से देखा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="71da7-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="71da7-178">परिणाम</span><span class="sxs-lookup"><span data-stu-id="71da7-178">Results</span></span>

<span data-ttu-id="71da7-179">कार्य प्रवाह के नतीजों को मॉडल आउटपुट पैरामीटर चरण के दौरान कॉन्फ़िगर किए गए निकाय में स्टोर किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="71da7-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="71da7-180">आप इस डेटा को [निकाय पेज](entities.md) या [API एक्सेस](apis.md) से एक्सेस कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="71da7-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="71da7-181">API एक्सेस</span><span class="sxs-lookup"><span data-stu-id="71da7-181">API Access</span></span>

<span data-ttu-id="71da7-182">विशिष्ट OData क्वेरी के लिए कस्टम मॉडल निकाय से डेटा प्राप्त करने के लिए, निम्न फॉर्मेट का उपयोग करें:</span><span class="sxs-lookup"><span data-stu-id="71da7-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="71da7-183">अपने Customer Insights परिवेश की ID के साथ `<your instance id>` बदलें, जिसे आप Customer Insights के एक्सेस के समय अपने ब्राउज़र के पता बार में पाते हैं.</span><span class="sxs-lookup"><span data-stu-id="71da7-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="71da7-184">`<custom model output entity>` को कस्टम मॉडल कॉन्फ़िगरेशन के मॉडल आउटपुट पैरामीटर चरण के दौरान आपके द्वारा प्रदान किए गए निकाय नाम के साथ बदलें.</span><span class="sxs-lookup"><span data-stu-id="71da7-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="71da7-185">`<guid value>` को उस ग्राहक की ग्राहक ID के साथ बदलें, जिसके लिए आप रिकॉर्ड एक्सेस करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="71da7-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="71da7-186">आप इस ID को आमतौर पर CustomerID फ़ील्ड में [ग्राहक प्रोफ़ाइल पेज](customer-profiles.md) पर पा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="71da7-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="71da7-187">सामान्य प्रश्‍न</span><span class="sxs-lookup"><span data-stu-id="71da7-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="71da7-188">कस्टम मॉडल कार्य प्रवाह सेट करते समय मैं अपनी पाइपलाइन क्यों नहीं देख सकता?</span><span class="sxs-lookup"><span data-stu-id="71da7-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="71da7-189">यह समस्या अक्सर पाइपलाइन में कॉन्फ़िगरेशन की समस्या के कारण होती है.</span><span class="sxs-lookup"><span data-stu-id="71da7-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="71da7-190">सुनिश्चित करें [इनपुट पैरामीटर कॉन्फ़िगर किया गया है](azure-machine-learning-experiments.md#dataset-configuration), और [आउटपुट डेटास्टोर और पाथ पैरामीटर](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) भी कॉन्फ़िगर किए गए हैं.</span><span class="sxs-lookup"><span data-stu-id="71da7-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="71da7-191">त्रुटि "इंटेलीजेंस कार्य प्रवाह को सेव नहीं कर सके" का क्या मतलब है?</span><span class="sxs-lookup"><span data-stu-id="71da7-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="71da7-192">यदि यूज़र के पास कार्यक्षेत्र पर मालिक या यूज़र एक्सेस एडमिनिस्ट्रेटर विशेषाधिकार नहीं होते तो वे आमतौर पर इस त्रुटि संदेश को देखते हैं.</span><span class="sxs-lookup"><span data-stu-id="71da7-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="71da7-193">यूज़र को कार्य प्रवाह के बाद के रन के लिए यूज़र क्रेडेंशियल्स उपयोग करने के बजाय कार्य प्रवाह को सेवा के रूप में प्रोसेस करने के लिए Customer Insights सक्षम करने में यूज़र की उच्च स्तरीय अनुमति चाहिए होती है.</span><span class="sxs-lookup"><span data-stu-id="71da7-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
