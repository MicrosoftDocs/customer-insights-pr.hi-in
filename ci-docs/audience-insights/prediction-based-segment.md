---
title: पूर्वानुमान आउटपुट के आधार पर सेगमेंट
description: पूर्वानुमान मॉडल के आउटपुट निकाय के आधार पर सेगमेंट बनाएं.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741431"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="c3180-103">पूर्वानुमान मॉडल (पूर्वावलोकन) के आधार पर एक सेगमेंट बनाएं</span><span class="sxs-lookup"><span data-stu-id="c3180-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="c3180-104">पूर्वानुमानों के परिणाम कभी-कभी केवल आपके ग्राहकों के सबसेट पर लागू होते हैं.</span><span class="sxs-lookup"><span data-stu-id="c3180-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="c3180-105">पूर्वानुमान मॉडल के परिणामों से सेगमेंट बनाकर अनुशंसाओं के व्यक्तिकरण को बढ़ाएं.</span><span class="sxs-lookup"><span data-stu-id="c3180-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="c3180-106">उदाहरण के लिए, आप उन ग्राहकों को विशिष्ट अनुशंसाएं दे सकते हैं जो एक निश्चित प्रकार की सेवा को वरीयता देते हैं.</span><span class="sxs-lookup"><span data-stu-id="c3180-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c3180-107">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="c3180-107">Prerequisites</span></span>

- <span data-ttu-id="c3180-108">Customer Insights में कम से कम [योगदानकर्ता की अनुमतियां](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c3180-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="c3180-109">एक प्रोडक्ट की अनुशंसा, ट्रांज़ैक्शनल चर्ण, सब्स्क्रिप्शन चर्ण या ग्राहक के लिए लाइफटाइम वैल्यू मॉडल Customer Insights में कॉन्फ़िगर किया गया है.</span><span class="sxs-lookup"><span data-stu-id="c3180-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="c3180-110">विभिन्न मॉडल को सेट करने के लिए आवश्यकताओं की समीक्षा करें:</span><span class="sxs-lookup"><span data-stu-id="c3180-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="c3180-111">उत्पाद सुझाव मॉडल</span><span class="sxs-lookup"><span data-stu-id="c3180-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="c3180-112">सब्स्क्रिप्शन चर्ण मॉडल</span><span class="sxs-lookup"><span data-stu-id="c3180-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="c3180-113">ट्रांज़ैक्शनल चर्ण मॉडल</span><span class="sxs-lookup"><span data-stu-id="c3180-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="c3180-114">ग्राहक के लिए लाइफटाइम वैल्यू मॉडल</span><span class="sxs-lookup"><span data-stu-id="c3180-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="c3180-115">पूर्वानुमानों के आधार पर ग्राहक के सेगमेंट बनाएं</span><span class="sxs-lookup"><span data-stu-id="c3180-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="c3180-116">**इंटेलिजेंस** > **पूर्वानुमानों** पर जाएं और **मेरे पूर्वानुमान** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="c3180-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c3180-117">आप जिस मॉडल की समीक्षा करना चाहते हैं उसके बगल में वर्टिकल एलिप्सिस का चयन करें और **देखें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="c3180-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="c3180-118">परिणाम पृष्ठ पर, **सेगमेंट बनाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="c3180-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="c3180-119">परिणाम पृष्ठ के बारे में अधिक जानकारी के लिए, मॉडल से जुड़े लेख की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="c3180-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="सेगमेंट बनाएं कार्रवाई को उजागर करते हुए पूर्वानुमान के परिणाम पृष्ठ का स्क्रीनशॉट.":::

1. <span data-ttu-id="c3180-121">चयनित मॉडल की आउटपुट निकाय के आधार पर एक नया सेगमेंट बनाएं.</span><span class="sxs-lookup"><span data-stu-id="c3180-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="c3180-122">अधिक जानकारी के लिए, [अनुभाग बनाएँ और प्रबंधित करें](segments.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="c3180-122">For more information, see [Create and manage segments](segments.md).</span></span>