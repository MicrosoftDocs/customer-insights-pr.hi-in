---
title: Azure मशीन लर्निंग के प्रयोग
description: Dynamics 365 Customer Insights में Azure मशीन लर्निंग-आधारित मॉडल का उपयोग करें.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267908"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="c0e84-103">Azure मशीन लर्निंग-आधारित मॉडल का उपयोग करें</span><span class="sxs-lookup"><span data-stu-id="c0e84-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="c0e84-104">Dynamics 365 Customer Insights में एकीकृत डेटा, मशीन लर्निंग मॉडल बनाने का स्रोत है, जो अतिरिक्त व्यावसायिक इनसाइट्स उत्पन्न कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="c0e84-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="c0e84-105">Customer Insights अपना खुद का कस्टम मॉडल उपयोग करने के लिए मशीन लर्निंग स्टूडियो (क्लासिक) और Azure मशीन लर्निंग के साथ एकीकृत करती है.</span><span class="sxs-lookup"><span data-stu-id="c0e84-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="c0e84-106">मशीन लर्निंग स्टूडियो (क्लासिक) पर बनाए गए प्रयोगों के उदाहरणों के लिए [मशीन लर्निंग स्टूडियो (क्लासिक) प्रयोग](machine-learning-studio-experiments.md) को देखें.</span><span class="sxs-lookup"><span data-stu-id="c0e84-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c0e84-107">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="c0e84-107">Prerequisites</span></span>

- <span data-ttu-id="c0e84-108">Customer Insights तक पहुँच</span><span class="sxs-lookup"><span data-stu-id="c0e84-108">Access to Customer Insights</span></span>
- <span data-ttu-id="c0e84-109">Azure एंटरप्राइज सदस्यता सक्रिय करें</span><span class="sxs-lookup"><span data-stu-id="c0e84-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="c0e84-110">एकीकृत ग्राहक प्रोफाइल</span><span class="sxs-lookup"><span data-stu-id="c0e84-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="c0e84-111">[Azure ब्लॉब स्टोरेज में निकाय का निर्यात](export-azure-blob-storage.md) कॉन्फ़िगर किया गया है</span><span class="sxs-lookup"><span data-stu-id="c0e84-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="c0e84-112">Azure मशीन लर्निंग कार्यक्षेत्र सेट करें</span><span class="sxs-lookup"><span data-stu-id="c0e84-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="c0e84-113">कार्यक्षेत्र बनाने के विभिन्न विकल्पों के लिए [Azure मशीन लर्निंग कार्यक्षेत्र बनाएं](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) देखें.</span><span class="sxs-lookup"><span data-stu-id="c0e84-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="c0e84-114">सर्वश्रेष्ठ प्रदर्शन के लिए, एक Azure क्षेत्र में ऐसा कार्यक्षेत्र बनाएं जो भौगोलिक रूप से आपके Customer Insights परिवेश के सबसे करीब है.</span><span class="sxs-lookup"><span data-stu-id="c0e84-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="c0e84-115">अपने कार्यक्षेत्र तक [Azure मशीन लर्निंग स्टूडि](https://ml.azure.com/) के जरिए पहुंचें.</span><span class="sxs-lookup"><span data-stu-id="c0e84-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="c0e84-116">आपके कार्यक्षेत्र के साथ कई [इंट्रेक्शन करने के तरीके](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) हैं.</span><span class="sxs-lookup"><span data-stu-id="c0e84-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="c0e84-117">Azure मशीन लर्निंग डिज़ाइनर के साथ काम करें</span><span class="sxs-lookup"><span data-stu-id="c0e84-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="c0e84-118">Azure मशीन लर्निंग डिज़ाइनर एक विज़ुअल कैनवास प्रदान करता है, जहां आप मशीन लर्निंग स्टूडियो (क्लासिक) की तरह ही डेटासेट और मॉड्यूल को खींच और छोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c0e84-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="c0e84-119">यदि डिज़ाइनर द्वारा बनाई गई बैच पाइपलाइन को तदनुसार कॉन्फ़िगर किया जाता है, तो उनको Customer Insights में एकीकृत किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="c0e84-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="c0e84-120">Azure मशीन लर्निंग SDK के साथ काम करना</span><span class="sxs-lookup"><span data-stu-id="c0e84-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="c0e84-121">डेटा वैज्ञानिक और AI डेवलपर्स मशीन लर्निंग कार्यप्रवाह बनाने के लिए [Azure मशीन लर्निंग SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) का उपयोग करते हैं.</span><span class="sxs-lookup"><span data-stu-id="c0e84-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="c0e84-122">फिलहाल, SDK का उपयोग करके प्रशिक्षित किए गए मॉडल को सीधे Customer Insights के साथ एकीकृत नहीं किया जा सकता.</span><span class="sxs-lookup"><span data-stu-id="c0e84-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="c0e84-123">एक बैच निष्कर्ष पाइपलाइन जो उस मॉडल को इस्तेमाल करता है जो Customer Insights के साथ एकीकरण के लिए आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="c0e84-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="c0e84-124">Customer Insights के साथ एकीकृत करने के लिए बैच पाइपलाइन आवश्यकताएं</span><span class="sxs-lookup"><span data-stu-id="c0e84-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="c0e84-125">डेटासेट कॉन्फ़िगरेशन</span><span class="sxs-lookup"><span data-stu-id="c0e84-125">Dataset Configuration</span></span>

<span data-ttu-id="c0e84-126">आपको डेटासेट बनाने की आवश्यकता है, ताकि Customer Insights से निकाय डेटा को अपने निष्कर्ष पाइपलाइन के लिए उपयोग कर सकें.</span><span class="sxs-lookup"><span data-stu-id="c0e84-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="c0e84-127">इन डेटासेट को कार्यक्षेत्र में पंजीकृत करने की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="c0e84-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="c0e84-128">फिलहाल, हम .csv प्रारूप में केवल [सारणीबद्ध डेटासेट](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) का समर्थन करते हैं.</span><span class="sxs-lookup"><span data-stu-id="c0e84-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="c0e84-129">जो डेटासेट निकाय डेटा के अनुरूप होते हैं, उन्हें पाइपलाइन मापदंड के रूप में मापदंडीकृत किया जाना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="c0e84-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="c0e84-130">डिज़ाइनर में डेटासेट मापदंड</span><span class="sxs-lookup"><span data-stu-id="c0e84-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="c0e84-131">डिज़ाइनर में, **डेटासेट में कॉलम का चयन करें** खोलें और **पाइपलाइन मापदंड के रूप में सेट करें** चुनें, जहां आप मापदंड के लिए एक नाम देते हैं.</span><span class="sxs-lookup"><span data-stu-id="c0e84-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="c0e84-132">![डिज़ाइनर में डेटासेट मापदंडीकरण](media/intelligence-designer-dataset-parameters.png "डिज़ाइनर में डेटासेट मापदंडीकरण")</span><span class="sxs-lookup"><span data-stu-id="c0e84-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="c0e84-133">SDK (पायथन) में डेटासेट मापदंड</span><span class="sxs-lookup"><span data-stu-id="c0e84-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="c0e84-134">बैच निष्कर्ष पाइपलाइन</span><span class="sxs-lookup"><span data-stu-id="c0e84-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="c0e84-135">डिज़ाइनर में, एक प्रशिक्षण पाइपलाइन का उपयोग एक निष्कर्ष पाइपलाइन बनाने या उसे अद्यतन करने के लिए किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="c0e84-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="c0e84-136">फिलहाल, केवल बैच निष्कर्ष पाइपलाइनें समर्थित हैं.</span><span class="sxs-lookup"><span data-stu-id="c0e84-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="c0e84-137">SDK का उपयोग करके, आप पाइपलाइन को समापन बिंदु पर प्रकाशित कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c0e84-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="c0e84-138">फिलहाल, Customer Insights मशीन लर्निंग कार्यक्षेत्र में बैच पाइपलाइन को समापन बिंदु में डिफ़ॉल्ट पाइपलाइन के साथ एकीकृत करता है.</span><span class="sxs-lookup"><span data-stu-id="c0e84-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="c0e84-139">Customer Insights में पाइपलाइन डेटा आयात करें</span><span class="sxs-lookup"><span data-stu-id="c0e84-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="c0e84-140">डिज़ाइनर [डेटा मॉड्यूल निर्यात करें](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) प्रदान करता है, जो पाइपलाइन के आउटपुट को Azure स्टोरेज में निर्यात करने देता है.</span><span class="sxs-lookup"><span data-stu-id="c0e84-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="c0e84-141">फिलहाल, मॉड्यूल को डेटास्टोर प्रकार **Azure ब्लॉब स्टोरेज** का उपयोग करना होगा और **डेटास्टोर** और सापेक्ष **पथ** का मापदंडीकरण करना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="c0e84-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="c0e84-142">Customer Insights पाइपलाइन निष्पादन के दौरान इन दोनों मापदंडों को एक डेटास्टोर और पथ के साथ ओवरराइड करती है जो उत्पाद के लिए पहुंच योग्य है.</span><span class="sxs-lookup"><span data-stu-id="c0e84-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c0e84-143">![डेटा मॉड्यूल कॉन्फ़िगरेशन निर्यात करें](media/intelligence-designer-importdata.png "डेटा मॉड्यूल कॉन्फ़िगरेशन निर्यात करें")</span><span class="sxs-lookup"><span data-stu-id="c0e84-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="c0e84-144">कोड का उपयोग करके निष्कर्ष आउटपुट लिखते समय आप कार्यक्षेत्र में *पंजीकृत डेटास्टोर* के पथ पर आउटपुट अपलोड कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="c0e84-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="c0e84-145">यदि पथ और डेटास्टोर को पाइपलाइन में मापदंडीकृत किया जाता है, तो Customer Insights निष्कर्ष आउटपुट को पढ़ और आयात कर सकेंगे.</span><span class="sxs-lookup"><span data-stu-id="c0e84-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="c0e84-146">फिलहाल, एकल सारणीबद्ध आउटपुट csv प्रारूप में समर्थित है.</span><span class="sxs-lookup"><span data-stu-id="c0e84-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="c0e84-147">पथ में निर्देशिका और फ़ाइल नाम शामिल होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="c0e84-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]