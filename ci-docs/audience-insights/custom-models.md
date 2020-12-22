---
title: कस्टम मशीन लर्निंग मॉडल | Microsoft Docs
description: Dynamics 365 Customer Insights में Azure मशीन लर्निंग से कस्टम मॉडल के साथ काम करें.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668905"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="29f54-103">कस्टम मशीन लर्निंग मॉडल</span><span class="sxs-lookup"><span data-stu-id="29f54-103">Custom machine learning models</span></span>

<span data-ttu-id="29f54-104">**इंटेलिजेंस** > **कस्टम मॉडल** आपको Azure मशीन लर्निंग मॉडल के आधार पर कार्यप्रवाह का प्रबंधन करने देता है.</span><span class="sxs-lookup"><span data-stu-id="29f54-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="29f54-105">कार्यप्रवाह आपको उस डेटा को चुनने में मदद करते हैं, जिनसे आप इन्साइट्स उत्पन्न करना चाहते हैं और परिणामों को अपने एकीकृत ग्राहक डेटा पर मैप करते हैं.</span><span class="sxs-lookup"><span data-stu-id="29f54-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="29f54-106">कस्टम ML मॉडल के निर्माण के बारे में अधिक जानकारी के लिए, [Azure मशीन लर्निंग-आधारित मॉडल का उपयोग करें](azure-machine-learning-experiments.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="29f54-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="29f54-107">जिम्मेदार AI</span><span class="sxs-lookup"><span data-stu-id="29f54-107">Responsible AI</span></span>

<span data-ttu-id="29f54-108">पूर्वानुमानें बेहतर ग्राहक अनुभव बनाने, व्यावसायिक क्षमताओं और राजस्व धाराओं में सुधार करने की क्षमताएं प्रदान करती हैं.</span><span class="sxs-lookup"><span data-stu-id="29f54-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="29f54-109">हम दृढ़ता से आपको सलाह देते हैं कि आप अपने पूर्वानुमान के मान को इसके प्रभाव और पूर्वाग्रहों के खिलाफ संतुलित करें जिसे नैतिक तरीके से पेश किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="29f54-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="29f54-110">Microsoft कैसा है [जिम्मेदार AI का संबोधन](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) के बारे में अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="29f54-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="29f54-111">आप [जिम्मेदार मशीन लर्निंग के लिए तकनीकों और प्रक्रियाओं](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) के बारे में भी जान सकते हैं जो Azure मशीन लर्निंग के लिए विशिष्ट है .</span><span class="sxs-lookup"><span data-stu-id="29f54-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="29f54-112">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="29f54-112">Prerequisites</span></span>

- <span data-ttu-id="29f54-113">वर्तमान में, यह सुविधा [मशीन लर्निंग स्टूडियो (क्लासिक)](https://studio.azureml.net) और [Azure मशीन लर्निंग बैच पाइपलाइन](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) के माध्यम से प्रकाशित वेब सेवाओं का समर्थन करती है.</span><span class="sxs-lookup"><span data-stu-id="29f54-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="29f54-114">इस सुविधा का उपयोग करने के लिए आपको अपने Azure स्टूडियो उदाहरण से जुड़े एक Azure Data Lake Gen2 स्टोरेज खाते की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="29f54-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="29f54-115">अधिक जानकारी के लिए देखें [Azure Data Lake Storage Gen2 संग्रहण खाता बनाएँ](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="29f54-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="29f54-116">नया कार्यप्रवाह जोड़ें</span><span class="sxs-lookup"><span data-stu-id="29f54-116">Add a new workflow</span></span>

1. <span data-ttu-id="29f54-117">**इंटेलिजेंस** > **कस्टम मॉडल्स** पर जाएं और **नया कार्यप्रवाह** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29f54-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="29f54-118">अपने कस्टम मॉडल को **नाम** फ़ील्ड में एक पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="29f54-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="29f54-119">![नए कार्यप्रवाह फलक का स्क्रीनशॉट](media/new-workflowv2.png "नए कार्यप्रवाह फलक का स्क्रीनशॉट")</span><span class="sxs-lookup"><span data-stu-id="29f54-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="29f54-120">उस संगठन का चयन करें जिसमें **टैनेंट जिसमें आपकी वेब सेवा शामिल है** शामिल है.</span><span class="sxs-lookup"><span data-stu-id="29f54-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="29f54-121">यदि आपकी Azure मशीन लर्निंग सदस्यता Customer Insights से अलग टैनेंट में है, तो चयनित संगठन के लिए अपनी पहचान के साथ **साइन इन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29f54-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="29f54-122">अपनी वेब सेवा से जुड़े **कार्यस्थानों** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29f54-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="29f54-123">दो अनुभागें सूचीबद्ध हैं, एक Azure मशीन लर्निंग v1 (मशीन लर्निंग स्टूडियो (क्लासिक)) और Azure मशीन लर्निंग v2 (Azure मशीन लर्निंग) के लिए.</span><span class="sxs-lookup"><span data-stu-id="29f54-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="29f54-124">यदि आप पक्के तौर पर यह नहीं कह सकते हैं कि आपके मशीन लर्निंग स्टूडियो (क्लासिक) वेब सेवा के लिए कौन सा कार्यक्षेत्र सही है, तो **किसी भी** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29f54-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="29f54-125">**आपके मॉडल को शामिल करने वाली वेब सेवा** ड्रॉपडाउन में मशीन लर्निंग स्टूडियो (क्लासिक) वेब सेवा या Azure मशीन लर्निंग पाइपलाइन चुनें.</span><span class="sxs-lookup"><span data-stu-id="29f54-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="29f54-126">उसके बाद, **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29f54-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="29f54-127">[मशीन लर्निंग स्टूडियो (क्लासिक) में एक वेब सेवा का प्रकाशन](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) के बारे में अधिक जानें</span><span class="sxs-lookup"><span data-stu-id="29f54-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="29f54-128">[Azure मशीन लर्निंग में डिजाइनर का उपयोग करके एक पाइपलाइन का प्रकाशन](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) या [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) के बारे में अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="29f54-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="29f54-129">आपकी पाइपलाइन को [पाइपलाइन एंडपॉइंट](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) के तहत प्रकाशित किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="29f54-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="29f54-130">प्रत्येक **वेब सेवा इनपुट** के लिए, ऑडियंस इनसाइट्स से मिलते-जुलते **निकाय** का चयन करें और **अगला** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29f54-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="29f54-131">![कार्यप्रवाह कॉन्फ़िगर करें](media/intelligence-screen2-updated.png "कार्यप्रवाह कॉन्फ़िगर करें")</span><span class="sxs-lookup"><span data-stu-id="29f54-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="29f54-132">**मॉडल आउटपुट पैरामीटर** चरण में, निम्नलिखित गुणों को सेट करें:</span><span class="sxs-lookup"><span data-stu-id="29f54-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="29f54-133">मशीन लर्निंग स्टूडियो (क्लासिक)</span><span class="sxs-lookup"><span data-stu-id="29f54-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="29f54-134">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि वेब सेवा आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="29f54-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="29f54-135">Azure मशीन लर्निंग</span><span class="sxs-lookup"><span data-stu-id="29f54-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="29f54-136">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि पाइपलाइन आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="29f54-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="29f54-137">ड्रॉपडाउन से अपने बैच पाइपलाइन के **आउटपुट डेटा स्टोर पैरामीटर के नाम** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29f54-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="29f54-138">ड्रॉपडाउन से अपने बैच पाइपलाइन के **आउटपुट पाथ पैरामीटर के नाम** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29f54-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="29f54-139">![मॉडल आउटपुट पैरामीटर फलक](media/intelligence-screen3-outputparameters.png "मॉडल आउटपुट पैरामीटर फलक")</span><span class="sxs-lookup"><span data-stu-id="29f54-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="29f54-140">**परिणामों में ग्राहक ID** ड्रॉप-डाउन सूची से मिलते-जुलते विशेषता का चयन करें जो ग्राहकों की पहचान करती है और **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29f54-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="29f54-141">![ग्राहक डेटा फलक से परिणामों को संबंधित करें](media/intelligence-screen4-relatetocustomer.png "ग्राहक डेटा फलक से परिणामों को संबंधित करें")</span><span class="sxs-lookup"><span data-stu-id="29f54-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="29f54-142">आप कार्यप्रवाह के बारे में विवरण के साथ **सहेजे गये कार्यप्रवाह** स्क्रीन देखेंगे.</span><span class="sxs-lookup"><span data-stu-id="29f54-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="29f54-143">यदि आप एक Azure मशीन लर्निंग पाइपलाइन के लिए एक कार्यप्रवाह कॉन्फ़िगर करते हैं, तो ऑडियंस इनसाइट्स उस पाइपलाइन वाले कार्यक्षेत्र से जुड़ी होगी.</span><span class="sxs-lookup"><span data-stu-id="29f54-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="29f54-144">ऑडियंस इनसाइट्स को Azure कार्यक्षेत्र पर **योगदानकर्ता** भूमिका मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="29f54-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="29f54-145">**पूर्ण** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29f54-145">Select **Done**.</span></span>

1. <span data-ttu-id="29f54-146">अब आप **कस्टम मॉडल** पेज से कार्यप्रवाह चला सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="29f54-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="29f54-147">कार्यप्रवाह संपादित करें</span><span class="sxs-lookup"><span data-stu-id="29f54-147">Edit a workflow</span></span>

1. <span data-ttu-id="29f54-148">**कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें और **संपादन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29f54-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="29f54-149">आप **नाम प्रदर्शित करें** फ़ील्ड में अपने कार्यप्रवाह के पहचानने योग्य नाम को अपडेट कर सकते हैं, लेकिन आप कॉन्फ़िगर की गई वेब सेवा या पाइपलाइन को नहीं बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="29f54-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="29f54-150">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29f54-150">Select **Next**.</span></span>

1. <span data-ttu-id="29f54-151">प्रत्येक **वेब सेवा इनपुट** के लिए, आप ऑडियंस इनसाइट्स से मिलते-जुलते **निकाय** अपडेट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="29f54-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="29f54-152">उसके बाद, **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29f54-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="29f54-153">**मॉडल आउटपुट पैरामीटर** चरण में, निम्नलिखित गुणों को सेट करें:</span><span class="sxs-lookup"><span data-stu-id="29f54-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="29f54-154">मशीन लर्निंग स्टूडियो (क्लासिक)</span><span class="sxs-lookup"><span data-stu-id="29f54-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="29f54-155">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि वेब सेवा आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="29f54-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="29f54-156">Azure मशीन लर्निंग</span><span class="sxs-lookup"><span data-stu-id="29f54-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="29f54-157">उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि पाइपलाइन आउटपुट परिणाम प्रवाहित हो.</span><span class="sxs-lookup"><span data-stu-id="29f54-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="29f54-158">अपनी टेस्ट पाइपलाइन के लिए **आउटपुट डेटा स्टोर पैरामीटर का नाम** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29f54-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="29f54-159">अपनी टेस्ट पाइपलाइन के लिए **आउटपुट पाथ पैरामीटर का नाम** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29f54-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="29f54-160">**परिणामों में ग्राहक ID** ड्रॉप-डाउन सूची से मिलते-जुलते विशेषता का चयन करें जो ग्राहकों की पहचान करती है और **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29f54-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="29f54-161">आपको ग्राहक निकाय के ग्राहक ID कॉलम के समान मानों के साथ अनुमान आउटपुट से एक विशेषता का चयन करना होगा.</span><span class="sxs-lookup"><span data-stu-id="29f54-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="29f54-162">अगर आपके डेटा सेट में ऐसा कोई कॉलम नहीं है, तो ऐसी विशेषता चुनें जो पंक्ति को विशिष्ट रूप से पहचानती हो.</span><span class="sxs-lookup"><span data-stu-id="29f54-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="29f54-163">कार्यप्रवाह चलाएँ</span><span class="sxs-lookup"><span data-stu-id="29f54-163">Run a workflow</span></span>

1. <span data-ttu-id="29f54-164">**कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले में बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29f54-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="29f54-165">**चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="29f54-165">Select **Run**.</span></span>

<span data-ttu-id="29f54-166">आपका कार्यप्रवाह भी हर शेड्यूल किए गए रिफ्रेश के साथ स्वत: चलता है.</span><span class="sxs-lookup"><span data-stu-id="29f54-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="29f54-167">[शेड्यूल रीफ्रेश सेट अप करना](system.md#schedule-tab) के बारे में और जानें.</span><span class="sxs-lookup"><span data-stu-id="29f54-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="29f54-168">कार्यप्रवाह हटाएँ</span><span class="sxs-lookup"><span data-stu-id="29f54-168">Delete a workflow</span></span>

1. <span data-ttu-id="29f54-169">**कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले में बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="29f54-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="29f54-170">**हटाएं** का चयन करें और अपने हटाने की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="29f54-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="29f54-171">आपका कार्यप्रवाह हटा दिया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="29f54-171">Your workflow will be deleted.</span></span> <span data-ttu-id="29f54-172">वह [निकाय](entities.md) जिसे आपके द्वारा कार्यप्रवाह बनाने के दौरान बनाया गया था, बना रहता है और उसे **निकाय** पेज से देखा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="29f54-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
