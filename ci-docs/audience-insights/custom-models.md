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
# <a name="custom-machine-learning-models"></a>कस्टम मशीन लर्निंग मॉडल

**इंटेलिजेंस** > **कस्टम मॉडल** आपको Azure मशीन लर्निंग मॉडल के आधार पर कार्यप्रवाह का प्रबंधन करने देता है. कार्यप्रवाह आपको उस डेटा को चुनने में मदद करते हैं, जिनसे आप इन्साइट्स उत्पन्न करना चाहते हैं और परिणामों को अपने एकीकृत ग्राहक डेटा पर मैप करते हैं. कस्टम ML मॉडल के निर्माण के बारे में अधिक जानकारी के लिए, [Azure मशीन लर्निंग-आधारित मॉडल का उपयोग करें](azure-machine-learning-experiments.md) देखें.

## <a name="responsible-ai"></a>जिम्मेदार AI

पूर्वानुमानें बेहतर ग्राहक अनुभव बनाने, व्यावसायिक क्षमताओं और राजस्व धाराओं में सुधार करने की क्षमताएं प्रदान करती हैं. हम दृढ़ता से आपको सलाह देते हैं कि आप अपने पूर्वानुमान के मान को इसके प्रभाव और पूर्वाग्रहों के खिलाफ संतुलित करें जिसे नैतिक तरीके से पेश किया जा सकता है. Microsoft कैसा है [जिम्मेदार AI का संबोधन](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) के बारे में अधिक जानें. आप [जिम्मेदार मशीन लर्निंग के लिए तकनीकों और प्रक्रियाओं](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) के बारे में भी जान सकते हैं जो Azure मशीन लर्निंग के लिए विशिष्ट है .

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- वर्तमान में, यह सुविधा [मशीन लर्निंग स्टूडियो (क्लासिक)](https://studio.azureml.net) और [Azure मशीन लर्निंग बैच पाइपलाइन](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) के माध्यम से प्रकाशित वेब सेवाओं का समर्थन करती है.

- इस सुविधा का उपयोग करने के लिए आपको अपने Azure स्टूडियो उदाहरण से जुड़े एक Azure Data Lake Gen2 स्टोरेज खाते की आवश्यकता है. अधिक जानकारी के लिए देखें [Azure Data Lake Storage Gen2 संग्रहण खाता बनाएँ](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>नया कार्यप्रवाह जोड़ें

1. **इंटेलिजेंस** > **कस्टम मॉडल्स** पर जाएं और **नया कार्यप्रवाह** चुनें.

1. अपने कस्टम मॉडल को **नाम** फ़ील्ड में एक पहचानने योग्य नाम दें.

   > [!div class="mx-imgBorder"]
   > ![नए कार्यप्रवाह फलक का स्क्रीनशॉट](media/new-workflowv2.png "नए कार्यप्रवाह फलक का स्क्रीनशॉट")

1. उस संगठन का चयन करें जिसमें **टैनेंट जिसमें आपकी वेब सेवा शामिल है** शामिल है.

1. यदि आपकी Azure मशीन लर्निंग सदस्यता Customer Insights से अलग टैनेंट में है, तो चयनित संगठन के लिए अपनी पहचान के साथ **साइन इन** चुनें.

1. अपनी वेब सेवा से जुड़े **कार्यस्थानों** का चयन करें. दो अनुभागें सूचीबद्ध हैं, एक Azure मशीन लर्निंग v1 (मशीन लर्निंग स्टूडियो (क्लासिक)) और Azure मशीन लर्निंग v2 (Azure मशीन लर्निंग) के लिए. यदि आप पक्के तौर पर यह नहीं कह सकते हैं कि आपके मशीन लर्निंग स्टूडियो (क्लासिक) वेब सेवा के लिए कौन सा कार्यक्षेत्र सही है, तो **किसी भी** का चयन करें.

1. **आपके मॉडल को शामिल करने वाली वेब सेवा** ड्रॉपडाउन में मशीन लर्निंग स्टूडियो (क्लासिक) वेब सेवा या Azure मशीन लर्निंग पाइपलाइन चुनें. उसके बाद, **अगला** चुनें.
   - [मशीन लर्निंग स्टूडियो (क्लासिक) में एक वेब सेवा का प्रकाशन](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) के बारे में अधिक जानें
   - [Azure मशीन लर्निंग में डिजाइनर का उपयोग करके एक पाइपलाइन का प्रकाशन](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) या [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) के बारे में अधिक जानें. आपकी पाइपलाइन को [पाइपलाइन एंडपॉइंट](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) के तहत प्रकाशित किया जाना चाहिए.

1. प्रत्येक **वेब सेवा इनपुट** के लिए, ऑडियंस इनसाइट्स से मिलते-जुलते **निकाय** का चयन करें और **अगला** का चयन करें.
   > [!NOTE]
   > कस्टम मॉडल कार्य प्रवाह, स्वतः शोध प्रणाली लागू करेगा, ताकि फ़ील्ड के नाम और डेटा प्रकार के आधार पर निकाय के एट्रिब्यूट के लिए वेब सेवा इनपुट फ़ील्ड को मैप किया जा सके. अगर वेब सेवा फ़ील्ड को किसी निकाय में मैप नहीं किया जा सकता है तो आपको एक त्रुटि दिखाई देगी.

   > [!div class="mx-imgBorder"]
   > ![कार्यप्रवाह कॉन्फ़िगर करें](media/intelligence-screen2-updated.png "कार्यप्रवाह कॉन्फ़िगर करें")
   
1. **मॉडल आउटपुट पैरामीटर** चरण में, निम्नलिखित गुणों को सेट करें:
   - मशीन लर्निंग स्टूडियो (क्लासिक)
      1. उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि वेब सेवा आउटपुट परिणाम प्रवाहित हो.
   - Azure मशीन लर्निंग
      1. उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि पाइपलाइन आउटपुट परिणाम प्रवाहित हो.
      1. ड्रॉपडाउन से अपने बैच पाइपलाइन के **आउटपुट डेटा स्टोर पैरामीटर के नाम** का चयन करें.
      1. ड्रॉपडाउन से अपने बैच पाइपलाइन के **आउटपुट पाथ पैरामीटर के नाम** का चयन करें.
      
      > [!div class="mx-imgBorder"]
      > ![मॉडल आउटपुट पैरामीटर फलक](media/intelligence-screen3-outputparameters.png "मॉडल आउटपुट पैरामीटर फलक")

1. **परिणामों में ग्राहक ID** ड्रॉप-डाउन सूची से मिलते-जुलते विशेषता का चयन करें जो ग्राहकों की पहचान करती है और **सहेजें** का चयन करें.
   
   > [!div class="mx-imgBorder"]
   > ![ग्राहक डेटा फलक से परिणामों को संबंधित करें](media/intelligence-screen4-relatetocustomer.png "ग्राहक डेटा फलक से परिणामों को संबंधित करें")

1. आप कार्यप्रवाह के बारे में विवरण के साथ **सहेजे गये कार्यप्रवाह** स्क्रीन देखेंगे.    
   यदि आप एक Azure मशीन लर्निंग पाइपलाइन के लिए एक कार्यप्रवाह कॉन्फ़िगर करते हैं, तो ऑडियंस इनसाइट्स उस पाइपलाइन वाले कार्यक्षेत्र से जुड़ी होगी. ऑडियंस इनसाइट्स को Azure कार्यक्षेत्र पर **योगदानकर्ता** भूमिका मिलेगी.

1. **पूर्ण** चयन करें.

1. अब आप **कस्टम मॉडल** पेज से कार्यप्रवाह चला सकते हैं.

## <a name="edit-a-workflow"></a>कार्यप्रवाह संपादित करें

1. **कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें और **संपादन** चुनें.

1. आप **नाम प्रदर्शित करें** फ़ील्ड में अपने कार्यप्रवाह के पहचानने योग्य नाम को अपडेट कर सकते हैं, लेकिन आप कॉन्फ़िगर की गई वेब सेवा या पाइपलाइन को नहीं बदल सकते हैं. **अगला** चुनें.

1. प्रत्येक **वेब सेवा इनपुट** के लिए, आप ऑडियंस इनसाइट्स से मिलते-जुलते **निकाय** अपडेट कर सकते हैं. उसके बाद, **अगला** चुनें.

1. **मॉडल आउटपुट पैरामीटर** चरण में, निम्नलिखित गुणों को सेट करें:
   - मशीन लर्निंग स्टूडियो (क्लासिक)
      1. उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि वेब सेवा आउटपुट परिणाम प्रवाहित हो.
   - Azure मशीन लर्निंग
      1. उस आउटपुट **निकाय का नाम** दर्ज करें जिसमें आप चाहते हैं कि पाइपलाइन आउटपुट परिणाम प्रवाहित हो.
      1. अपनी टेस्ट पाइपलाइन के लिए **आउटपुट डेटा स्टोर पैरामीटर का नाम** चुनें.
      1. अपनी टेस्ट पाइपलाइन के लिए **आउटपुट पाथ पैरामीटर का नाम** चुनें.

1. **परिणामों में ग्राहक ID** ड्रॉप-डाउन सूची से मिलते-जुलते विशेषता का चयन करें जो ग्राहकों की पहचान करती है और **सहेजें** का चयन करें.
   आपको ग्राहक निकाय के ग्राहक ID कॉलम के समान मानों के साथ अनुमान आउटपुट से एक विशेषता का चयन करना होगा. अगर आपके डेटा सेट में ऐसा कोई कॉलम नहीं है, तो ऐसी विशेषता चुनें जो पंक्ति को विशिष्ट रूप से पहचानती हो.

## <a name="run-a-workflow"></a>कार्यप्रवाह चलाएँ

1. **कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले में बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें.

1. **चलाएं** चुनें.

आपका कार्यप्रवाह भी हर शेड्यूल किए गए रिफ्रेश के साथ स्वत: चलता है. [शेड्यूल रीफ्रेश सेट अप करना](system.md#schedule-tab) के बारे में और जानें.

## <a name="delete-a-workflow"></a>कार्यप्रवाह हटाएँ

1. **कस्टम मॉडल** पृष्ठ पर, आपके द्वारा पहले में बनाए गए कार्यप्रवाह के बाजू में **कार्यकलाप** कॉलम में वर्टिकल एलिप्सिस का चयन करें.

1. **हटाएं** का चयन करें और अपने हटाने की पुष्टि करें.

आपका कार्यप्रवाह हटा दिया जाएगा. वह [निकाय](entities.md) जिसे आपके द्वारा कार्यप्रवाह बनाने के दौरान बनाया गया था, बना रहता है और उसे **निकाय** पेज से देखा जा सकता है.


[!INCLUDE[footer-include](../includes/footer-banner.md)]