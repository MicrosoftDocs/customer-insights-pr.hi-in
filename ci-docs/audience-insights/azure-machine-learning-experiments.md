---
title: Azure मशीन लर्निंग के प्रयोग
description: Dynamics 365 Customer Insights में Azure मशीन लर्निंग-आधारित मॉडल का उपयोग करें.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3f97e22687ae4f5536d492bac83bdf9c711e2c94
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554437"
---
# <a name="use-azure-machine-learning-based-models"></a>Azure मशीन लर्निंग-आधारित मॉडल का उपयोग करें

Dynamics 365 Customer Insights में एकीकृत डेटा, मशीन लर्निंग मॉडल बनाने का स्रोत है, जो अतिरिक्त व्यावसायिक इनसाइट्स उत्पन्न कर सकता है. Customer Insights अपना खुद का कस्टम मॉडल उपयोग करने के लिए मशीन लर्निंग स्टूडियो (क्लासिक) और Azure मशीन लर्निंग के साथ एकीकृत करती है. मशीन लर्निंग स्टूडियो (क्लासिक) पर बनाए गए प्रयोगों के उदाहरणों के लिए [मशीन लर्निंग स्टूडियो (क्लासिक) प्रयोग](machine-learning-studio-experiments.md) को देखें. 

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- Customer Insights तक पहुँच
- Azure एंटरप्राइज सदस्यता सक्रिय करें
- [एकीकृत ग्राहक प्रोफाइल](data-unification.md)
- [Azure ब्लॉब स्टोरेज में निकाय का निर्यात](export-azure-blob-storage.md) कॉन्फ़िगर किया गया है

## <a name="set-up-azure-machine-learning-workspace"></a>Azure मशीन लर्निंग कार्यक्षेत्र सेट करें

1. कार्यक्षेत्र बनाने के विभिन्न विकल्पों के लिए [Azure मशीन लर्निंग कार्यक्षेत्र बनाएं](/azure/machine-learning/concept-workspace#-create-a-workspace) देखें. सर्वश्रेष्ठ प्रदर्शन के लिए, एक Azure क्षेत्र में ऐसा कार्यक्षेत्र बनाएं जो भौगोलिक रूप से आपके Customer Insights परिवेश के सबसे करीब है.

1. अपने कार्यक्षेत्र तक [Azure मशीन लर्निंग स्टूडि](https://ml.azure.com/) के जरिए पहुंचें. आपके कार्यक्षेत्र के साथ कई [इंट्रेक्शन करने के तरीके](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) हैं.

## <a name="work-with-azure-machine-learning-designer"></a>Azure मशीन लर्निंग डिज़ाइनर के साथ काम करें

Azure मशीन लर्निंग डिज़ाइनर एक विज़ुअल कैनवास प्रदान करता है, जहां आप मशीन लर्निंग स्टूडियो (क्लासिक) की तरह ही डेटासेट और मॉड्यूल को खींच और छोड़ सकते हैं. यदि डिज़ाइनर द्वारा बनाई गई बैच पाइपलाइन को तदनुसार कॉन्फ़िगर किया जाता है, तो उनको Customer Insights में एकीकृत किया जा सकता है. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Azure मशीन लर्निंग SDK के साथ काम करना

डेटा वैज्ञानिक और AI डेवलपर्स मशीन लर्निंग कार्यप्रवाह बनाने के लिए [Azure मशीन लर्निंग SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) का उपयोग करते हैं. फिलहाल, SDK का उपयोग करके प्रशिक्षित किए गए मॉडल को सीधे Customer Insights के साथ एकीकृत नहीं किया जा सकता. एक बैच निष्कर्ष पाइपलाइन जो उस मॉडल को इस्तेमाल करता है जो Customer Insights के साथ एकीकरण के लिए आवश्यक है.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Customer Insights के साथ एकीकृत करने के लिए बैच पाइपलाइन आवश्यकताएं

### <a name="dataset-configuration"></a>डेटासेट कॉन्फ़िगरेशन

आपको डेटासेट बनाने की आवश्यकता है, ताकि Customer Insights से निकाय डेटा को अपने निष्कर्ष पाइपलाइन के लिए उपयोग कर सकें. इन डेटासेट को कार्यक्षेत्र में पंजीकृत करने की आवश्यकता है. फिलहाल, हम .csv प्रारूप में केवल [सारणीबद्ध डेटासेट](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) का समर्थन करते हैं. जो डेटासेट निकाय डेटा के अनुरूप होते हैं, उन्हें पाइपलाइन मापदंड के रूप में मापदंडीकृत किया जाना चाहिए.
   
* डिज़ाइनर में डेटासेट मापदंड
   
     डिज़ाइनर में, **डेटासेट में कॉलम का चयन करें** खोलें और **पाइपलाइन मापदंड के रूप में सेट करें** चुनें, जहां आप मापदंड के लिए एक नाम देते हैं.

     > [!div class="mx-imgBorder"]
     > ![डिज़ाइनर में डेटासेट मापदंडीकरण.](media/intelligence-designer-dataset-parameters.png "डिज़ाइनर में डेटासेट मापदंडीकरण")
   
* SDK (पायथन) में डेटासेट मापदंड
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>बैच निष्कर्ष पाइपलाइन
  
* डिज़ाइनर में, एक प्रशिक्षण पाइपलाइन का उपयोग एक निष्कर्ष पाइपलाइन बनाने या उसे अद्यतन करने के लिए किया जा सकता है. फिलहाल, केवल बैच निष्कर्ष पाइपलाइनें समर्थित हैं.

* SDK का उपयोग करके, आप पाइपलाइन को समापन बिंदु पर प्रकाशित कर सकते हैं. फिलहाल, Customer Insights मशीन लर्निंग कार्यक्षेत्र में बैच पाइपलाइन को समापन बिंदु में डिफ़ॉल्ट पाइपलाइन के साथ एकीकृत करता है.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Customer Insights में पाइपलाइन डेटा आयात करें

* डिज़ाइनर [डेटा मॉड्यूल निर्यात करें](/azure/machine-learning/algorithm-module-reference/export-data) प्रदान करता है, जो पाइपलाइन के आउटपुट को Azure स्टोरेज में निर्यात करने देता है. फिलहाल, मॉड्यूल को डेटास्टोर प्रकार **Azure ब्लॉब स्टोरेज** का उपयोग करना होगा और **डेटास्टोर** और सापेक्ष **पथ** का मापदंडीकरण करना चाहिए. Customer Insights पाइपलाइन निष्पादन के दौरान इन दोनों मापदंडों को एक डेटास्टोर और पथ के साथ ओवरराइड करती है जो उत्पाद के लिए पहुंच योग्य है.
   > [!div class="mx-imgBorder"]
   > ![डेटा मॉड्यूल कॉन्फ़िगरेशन निर्यात करें.](media/intelligence-designer-importdata.png "डेटा मॉड्यूल कॉन्फ़िगरेशन निर्यात करें")
   
* कोड का उपयोग करके निष्कर्ष आउटपुट लिखते समय आप कार्यक्षेत्र में *पंजीकृत डेटास्टोर* के पथ पर आउटपुट अपलोड कर सकते हैं. यदि पथ और डेटास्टोर को पाइपलाइन में मापदंडीकृत किया जाता है, तो Customer Insights निष्कर्ष आउटपुट को पढ़ और आयात कर सकेंगे. फिलहाल, एकल सारणीबद्ध आउटपुट csv प्रारूप में समर्थित है. पथ में निर्देशिका और फ़ाइल नाम शामिल होना चाहिए.

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