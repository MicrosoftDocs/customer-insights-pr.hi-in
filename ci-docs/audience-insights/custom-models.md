---
title: कस्टम मशीन लर्निंग मॉडल | Microsoft Docs
description: Dynamics 365 Customer Insights में Azure मशीन लर्निंग से कस्टम मॉडल के साथ काम करें.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267236"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="1ad86-103">कस्टम मशीन लर्निंग मॉडल</span><span class="sxs-lookup"><span data-stu-id="1ad86-103">Custom machine learning models</span></span>

<span data-ttu-id="1ad86-104">**इंटेलिजेंस** > **कस्टम मॉडल** आपको Azure मशीन लर्निंग मॉडल के आधार पर कार्यप्रवाह का प्रबंधन करने देता है.</span><span class="sxs-lookup"><span data-stu-id="1ad86-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="1ad86-105">कार्यप्रवाह आपको उस डेटा को चुनने में मदद करते हैं, जिनसे आप इन्साइट्स उत्पन्न करना चाहते हैं और परिणामों को अपने एकीकृत ग्राहक डेटा पर मैप करते हैं.</span><span class="sxs-lookup"><span data-stu-id="1ad86-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="1ad86-106">कस्टम ML मॉडल के निर्माण के बारे में अधिक जानकारी के लिए, [Azure मशीन लर्निंग-आधारित मॉडल का उपयोग करें](azure-machine-learning-experiments.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="1ad86-107">जिम्मेदार AI</span><span class="sxs-lookup"><span data-stu-id="1ad86-107">Responsible AI</span></span>

<span data-ttu-id="1ad86-108">पूर्वानुमानें बेहतर ग्राहक अनुभव बनाने, व्यावसायिक क्षमताओं और राजस्व धाराओं में सुधार करने की क्षमताएं प्रदान करती हैं.</span><span class="sxs-lookup"><span data-stu-id="1ad86-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="1ad86-109">हम दृढ़ता से आपको सलाह देते हैं कि आप अपने पूर्वानुमान के मान को इसके प्रभाव और पूर्वाग्रहों के खिलाफ संतुलित करें जिसे नैतिक तरीके से पेश किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="1ad86-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="1ad86-110">Microsoft कैसा है [जिम्मेदार AI का संबोधन](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) के बारे में अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="1ad86-111">आप [जिम्मेदार मशीन लर्निंग के लिए तकनीकों और प्रक्रियाओं](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) के बारे में भी जान सकते हैं जो Azure मशीन लर्निंग के लिए विशिष्ट है .</span><span class="sxs-lookup"><span data-stu-id="1ad86-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ad86-112">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="1ad86-112">Prerequisites</span></span>

- <span data-ttu-id="1ad86-113">वर्तमान में, यह सुविधा [मशीन लर्निंग स्टूडियो (क्लासिक)](https://studio.azureml.net) और [Azure मशीन लर्निंग बैच पाइपलाइन](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) के माध्यम से प्रकाशित वेब सेवाओं का समर्थन करती है.</span><span class="sxs-lookup"><span data-stu-id="1ad86-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="1ad86-114">इस सुविधा का उपयोग करने के लिए आपको अपने Azure स्टूडियो उदाहरण से जुड़े एक Azure Data Lake Gen2 स्टोरेज खाते की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="1ad86-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="1ad86-115">अधिक जानकारी के लिए देखें [Azure Data Lake Storage Gen2 संग्रहण खाता बनाएँ](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="1ad86-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="1ad86-116">नया कार्यप्रवाह जोड़ें</span><span class="sxs-lookup"><span data-stu-id="1ad86-116">Add a new workflow</span></span>

1. <span data-ttu-id="1ad86-117">**इंटेलिजेंस** > **कस्टम मॉडल्स** पर जाएं और **नया कार्यप्रवाह** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="1ad86-118">अपने कस्टम मॉडल को **नाम** फ़ील्ड में एक पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ad86-119">![नए कार्यप्रवाह फलक का स्क्रीनशॉट](media/new-workflowv2.png "नए कार्यप्रवाह फलक का स्क्रीनशॉट")</span><span class="sxs-lookup"><span data-stu-id="1ad86-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="1ad86-120">उस संगठन का चयन करें जिसमें **टैनेंट जिसमें आपकी वेब सेवा शामिल है** शामिल है.</span><span class="sxs-lookup"><span data-stu-id="1ad86-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="1ad86-121">यदि आपकी Azure मशीन लर्निंग सदस्यता Customer Insights से अलग टैनेंट में है, तो चयनित संगठन के लिए अपनी पहचान के साथ **साइन इन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="1ad86-122">अपनी वेब सेवा से जुड़े **कार्यस्थानों** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="1ad86-123">दो अनुभागें सूचीबद्ध हैं, एक Azure मशीन लर्निंग v1 (मशीन लर्निंग स्टूडियो (क्लासिक)) और Azure मशीन लर्निंग v2 (Azure मशीन लर्निंग) के लिए.</span><span class="sxs-lookup"><span data-stu-id="1ad86-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="1ad86-124">यदि आप पक्के तौर पर यह नहीं कह सकते हैं कि आपके मशीन लर्निंग स्टूडियो (क्लासिक) वेब सेवा के लिए कौन सा कार्यक्षेत्र सही है, तो **किसी भी** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="1ad86-125">**आपके मॉडल को शामिल करने वाली वेब सेवा** ड्रॉपडाउन में मशीन लर्निंग स्टूडियो (क्लासिक) वेब सेवा या Azure मशीन लर्निंग पाइपलाइन चुनें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="1ad86-126">उसके बाद, **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="1ad86-127">[मशीन लर्निंग स्टूडियो (क्लासिक) में एक वेब सेवा का प्रकाशन](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) के बारे में अधिक जानें</span><span class="sxs-lookup"><span data-stu-id="1ad86-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="1ad86-128">[Azure मशीन लर्निंग में डिजाइनर का उपयोग करके एक पाइपलाइन का प्रकाशन](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) या [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) के बारे में अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="1ad86-129">आपकी पाइपलाइन को [पाइपलाइन एंडपॉइंट](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) के तहत प्रकाशित किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="1ad86-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="1ad86-130">प्रत्येक **वेब सेवा इनपुट** के लिए, ऑडियंस इनसाइट्स से मिलते-जुलते **निकाय** का चयन करें और **अगला** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1ad86-131">कस्टम मॉडल कार्य प्रवाह, स्वतः शोध प्रणाली लागू करेगा, ताकि फ़ील्ड के नाम और डेटा प्रकार के आधार पर निकाय के एट्रिब्यूट के लिए वेब सेवा इनपुट फ़ील्ड को मैप किया जा सके.</span><span class="sxs-lookup"><span data-stu-id="1ad86-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="1ad86-132">अगर वेब सेवा फ़ील्ड को किसी निकाय में मैप नहीं किया जा सकता है तो आपको एक त्रुटि दिखाई देगी.</span><span class="sxs-lookup"><span data-stu-id="1ad86-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ad86-133">![कार्यप्रवाह कॉन्फ़िगर करें](media/intelligence-screen2-updated.png "कार्यप्रवाह कॉन्फ़िगर करें")</span><span class="sxs-lookup"><span data-stu-id="1ad86-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="1ad86-134">**मॉडल आउटपुट पैरामीटर** चरण में, निम्नलिखित गुणों को सेट करें:</span><span class="sxs-lookup"><span data-stu-id="1ad86-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1ad86-135">मशीन लर्निंग स्टूडियो (क्लासिक)</span><span class="sxs-lookup"><span data-stu-id="1ad86-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1ad86-136">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि वेब सेवा आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="1ad86-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1ad86-137">Azure मशीन लर्निंग</span><span class="sxs-lookup"><span data-stu-id="1ad86-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1ad86-138">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि पाइपलाइन आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="1ad86-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1ad86-139">ड्रॉपडाउन से अपने बैच पाइपलाइन के **आउटपुट डेटा स्टोर पैरामीटर के नाम** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="1ad86-140">ड्रॉपडाउन से अपने बैच पाइपलाइन के **आउटपुट पाथ पैरामीटर के नाम** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="1ad86-141">![मॉडल आउटपुट पैरामीटर फलक](media/intelligence-screen3-outputparameters.png "मॉडल आउटपुट पैरामीटर फलक")</span><span class="sxs-lookup"><span data-stu-id="1ad86-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="1ad86-142">**परिणामों में ग्राहक ID** ड्रॉप-डाउन सूची से मिलते-जुलते विशेषता का चयन करें जो ग्राहकों की पहचान करती है और **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ad86-143">![ग्राहक डेटा फलक से परिणामों को संबंधित करें](media/intelligence-screen4-relatetocustomer.png "ग्राहक डेटा फलक से परिणामों को संबंधित करें")</span><span class="sxs-lookup"><span data-stu-id="1ad86-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="1ad86-144">आप कार्यप्रवाह के बारे में विवरण के साथ **सहेजे गये कार्यप्रवाह** स्क्रीन देखेंगे.</span><span class="sxs-lookup"><span data-stu-id="1ad86-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="1ad86-145">यदि आप एक Azure मशीन लर्निंग पाइपलाइन के लिए एक कार्यप्रवाह कॉन्फ़िगर करते हैं, तो ऑडियंस इनसाइट्स उस पाइपलाइन वाले कार्यक्षेत्र से जुड़ी होगी.</span><span class="sxs-lookup"><span data-stu-id="1ad86-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="1ad86-146">ऑडियंस इनसाइट्स को Azure कार्यक्षेत्र पर **योगदानकर्ता** भूमिका मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="1ad86-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="1ad86-147">**पूर्ण** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-147">Select **Done**.</span></span>

1. <span data-ttu-id="1ad86-148">अब आप **कस्टम मॉडल** पेज से कार्यप्रवाह चला सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1ad86-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="1ad86-149">कार्यप्रवाह संपादित करें</span><span class="sxs-lookup"><span data-stu-id="1ad86-149">Edit a workflow</span></span>

1. <span data-ttu-id="1ad86-150">**कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें और **संपादन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="1ad86-151">आप **नाम प्रदर्शित करें** फ़ील्ड में अपने कार्यप्रवाह के पहचानने योग्य नाम को अपडेट कर सकते हैं, लेकिन आप कॉन्फ़िगर की गई वेब सेवा या पाइपलाइन को नहीं बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1ad86-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="1ad86-152">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-152">Select **Next**.</span></span>

1. <span data-ttu-id="1ad86-153">प्रत्येक **वेब सेवा इनपुट** के लिए, आप ऑडियंस इनसाइट्स से मिलते-जुलते **निकाय** अपडेट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="1ad86-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="1ad86-154">उसके बाद, **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="1ad86-155">**मॉडल आउटपुट पैरामीटर** चरण में, निम्नलिखित गुणों को सेट करें:</span><span class="sxs-lookup"><span data-stu-id="1ad86-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1ad86-156">मशीन लर्निंग स्टूडियो (क्लासिक)</span><span class="sxs-lookup"><span data-stu-id="1ad86-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1ad86-157">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि वेब सेवा आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="1ad86-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1ad86-158">Azure मशीन लर्निंग</span><span class="sxs-lookup"><span data-stu-id="1ad86-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1ad86-159">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि पाइपलाइन आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="1ad86-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1ad86-160">अपनी टेस्ट पाइपलाइन के लिए **आउटपुट डेटा स्टोर पैरामीटर का नाम** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="1ad86-161">अपनी टेस्ट पाइपलाइन के लिए **आउटपुट पाथ पैरामीटर का नाम** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="1ad86-162">**परिणामों में ग्राहक ID** ड्रॉप-डाउन सूची से मिलते-जुलते विशेषता का चयन करें जो ग्राहकों की पहचान करती है और **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="1ad86-163">आपको ग्राहक निकाय के ग्राहक ID कॉलम के समान मानों के साथ अनुमान आउटपुट से एक विशेषता का चयन करना होगा.</span><span class="sxs-lookup"><span data-stu-id="1ad86-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="1ad86-164">अगर आपके डेटा सेट में ऐसा कोई कॉलम नहीं है, तो ऐसी विशेषता चुनें जो पंक्ति को विशिष्ट रूप से पहचानती हो.</span><span class="sxs-lookup"><span data-stu-id="1ad86-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="1ad86-165">कार्यप्रवाह चलाएँ</span><span class="sxs-lookup"><span data-stu-id="1ad86-165">Run a workflow</span></span>

1. <span data-ttu-id="1ad86-166">**कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले में बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1ad86-167">**चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-167">Select **Run**.</span></span>

<span data-ttu-id="1ad86-168">आपका कार्यप्रवाह भी हर शेड्यूल किए गए रिफ्रेश के साथ स्वत: चलता है.</span><span class="sxs-lookup"><span data-stu-id="1ad86-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="1ad86-169">[शेड्यूल रीफ्रेश सेट अप करना](system.md#schedule-tab) के बारे में और जानें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="1ad86-170">कार्यप्रवाह हटाएँ</span><span class="sxs-lookup"><span data-stu-id="1ad86-170">Delete a workflow</span></span>

1. <span data-ttu-id="1ad86-171">**कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले में बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1ad86-172">**हटाएं** का चयन करें और अपने हटाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="1ad86-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="1ad86-173">आपका कार्यप्रवाह हटा दिया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="1ad86-173">Your workflow will be deleted.</span></span> <span data-ttu-id="1ad86-174">वह [निकाय](entities.md) जिसे आपके द्वारा कार्यप्रवाह बनाने के दौरान बनाया गया था, बना रहता है और उसे **निकाय** पेज से देखा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="1ad86-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]