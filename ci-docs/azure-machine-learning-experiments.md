---
title: Azure मशीन लर्निंग-आधारित मॉडल का उपयोग करें
description: Dynamics 365 Customer Insights में Azure मशीन लर्निंग-आधारित मॉडल का उपयोग करें.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609827"
---
# <a name="use-azure-machine-learning-based-models"></a>Azure मशीन लर्निंग-आधारित मॉडल का उपयोग करें

Dynamics 365 Customer Insights में एकीकृत डेटा, मशीन लर्निंग मॉडल बनाने का स्रोत है, जो अतिरिक्त व्यावसायिक इनसाइट्स उत्पन्न कर सकता है. Customer Insights स्वयं के कस्टम मॉडल का उपयोग करने के लिए Azure मशीन लर्निंग के साथ एकीकृत करती है.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- Customer Insights तक पहुँच
- Azure एंटरप्राइज सदस्यता सक्रिय करें
- [एकीकृत ग्राहक प्रोफाइल](data-unification.md)
- [Azure ब्लॉब स्टोरेज में निकाय का निर्यात](export-azure-blob-storage.md) कॉन्फ़िगर किया गया है

## <a name="set-up-azure-machine-learning-workspace"></a>Azure मशीन लर्निंग कार्यक्षेत्र सेट करें

1. कार्यक्षेत्र बनाने के विभिन्न विकल्पों के लिए [Azure मशीन लर्निंग कार्यक्षेत्र बनाएं](/azure/machine-learning/concept-workspace#-create-a-workspace) देखें. सर्वश्रेष्ठ प्रदर्शन के लिए, एक Azure क्षेत्र में ऐसा कार्यक्षेत्र बनाएं जो भौगोलिक रूप से आपके Customer Insights परिवेश के सबसे करीब है.

1. अपने कार्यक्षेत्र तक [Azure मशीन लर्निंग स्टूडि](https://ml.azure.com/) के जरिए पहुंचें. आपके कार्यक्षेत्र के साथ कई [इंट्रेक्शन करने के तरीके](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) हैं.

## <a name="work-with-azure-machine-learning-designer"></a>Azure मशीन लर्निंग डिज़ाइनर के साथ काम करें

Azure मशीन लर्निंग डिज़ाइनर एक विज़ुअल कैनवास प्रदान करता है जहाँ आप डेटासेट और मॉड्यूल को ड्रैग और ड्रॉप कर सकते हैं। यदि डिज़ाइनर द्वारा बनाई गई बैच पाइपलाइन को तदनुसार कॉन्फ़िगर किया जाता है, तो उनको Customer Insights में एकीकृत किया जा सकता है. 

## <a name="working-with-azure-machine-learning-sdk"></a>Azure मशीन लर्निंग SDK के साथ काम करना

डेटा वैज्ञानिक और AI डेवलपर्स मशीन लर्निंग कार्यप्रवाह बनाने के लिए [Azure मशीन लर्निंग SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) का उपयोग करते हैं. फिलहाल, SDK का उपयोग करके प्रशिक्षित किए गए मॉडल को सीधे Customer Insights के साथ एकीकृत नहीं किया जा सकता. एक बैच निष्कर्ष पाइपलाइन जो उस मॉडल को इस्तेमाल करता है जो Customer Insights के साथ एकीकरण के लिए आवश्यक है.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Customer Insights के साथ एकीकृत करने के लिए बैच पाइपलाइन आवश्यकताएं

### <a name="dataset-configuration"></a>डेटासेट कॉन्फ़िगरेशन

अपने बैच अनुमान पाइपलाइन के लिए Customer Insights से निकाय डेटा का उपयोग करने के लिए डेटासेट बनाएं। इन डेटासेट को कार्यक्षेत्र में पंजीकृत करें। फिलहाल, हम .csv प्रारूप में केवल [सारणीबद्ध डेटासेट](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) का समर्थन करते हैं. एक पाइपलाइन पैरामीटर के रूप में निकाय डेटा के संगत डेटासेट को पैरामीटराइज़ करें।

- डिज़ाइनर में डेटासेट मापदंड

  डिज़ाइनर में, **डेटासेट में कॉलम का चयन करें** खोलें और **पाइपलाइन मापदंड के रूप में सेट करें** चुनें, जहां आप मापदंड के लिए एक नाम देते हैं.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="डिज़ाइनर में डेटासेट मापदंडीकरण.":::

- SDK (पायथन) में डेटासेट मापदंड

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>बैच निष्कर्ष पाइपलाइन
  
- डिज़ाइनर में, एक अनुमान पाइपलाइन बनाने या अपडेट करने के लिए एक प्रशिक्षण पाइपलाइन का उपयोग करें। फिलहाल, केवल बैच निष्कर्ष पाइपलाइनें समर्थित हैं.

- SDK का उपयोग करके, पाइपलाइन को एंडपॉइंट पर प्रकाशित करें। फिलहाल, Customer Insights मशीन लर्निंग कार्यक्षेत्र में बैच पाइपलाइन को समापन बिंदु में डिफ़ॉल्ट पाइपलाइन के साथ एकीकृत करता है.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Customer Insights में पाइपलाइन डेटा आयात करें

- डिज़ाइनर [डेटा मॉड्यूल निर्यात करें](/azure/machine-learning/algorithm-module-reference/export-data) प्रदान करता है, जो पाइपलाइन के आउटपुट को Azure स्टोरेज में निर्यात करने देता है. फिलहाल, मॉड्यूल को डेटास्टोर प्रकार **Azure ब्लॉब स्टोरेज** का उपयोग करना होगा और **डेटास्टोर** और सापेक्ष **पथ** का मापदंडीकरण करना चाहिए. Customer Insights पाइपलाइन निष्पादन के दौरान इन दोनों मापदंडों को एक डेटास्टोर और पथ के साथ ओवरराइड करती है जो उत्पाद के लिए पहुंच योग्य है.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="डेटा मॉड्यूल कॉन्फ़िगरेशन निर्यात करें.":::

- कोड का उपयोग करते हुए अनुमान आउटपुट लिखते समय, आउटपुट को एक पथ पर अपलोड करें a *पंजीकृत डेटास्टोर* कार्यक्षेत्र में। यदि पथ और डेटास्टोर को पाइपलाइन में मापदंडीकृत किया जाता है, तो Customer Insights निष्कर्ष आउटपुट को पढ़ और आयात कर सकेंगे. फिलहाल, एकल सारणीबद्ध आउटपुट csv प्रारूप में समर्थित है. पथ में निर्देशिका और फ़ाइल नाम शामिल होना चाहिए.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]