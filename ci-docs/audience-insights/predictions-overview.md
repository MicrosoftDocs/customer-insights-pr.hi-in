---
title: समर्थित पूर्वानुमान परिदृश्यों का अवलोकन
description: पूर्वानुमान परिदृश्य और विकल्प Dynamics 365 Customer Insights अनुप्रयोग द्वारा कवर किए गए हैं.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095715"
---
# <a name="predictions-overview"></a><span data-ttu-id="e7472-103">पूर्वानुमानों का अवलोकन</span><span class="sxs-lookup"><span data-stu-id="e7472-103">Predictions overview</span></span>

<span data-ttu-id="e7472-104">Dynamics 365 Customer Insights, डेटा का पूर्वानुमान करने के लिए AI और मशीन लर्निंग का लाभ उठाने वाले विभिन्न विकल्पों के साथ आता है.</span><span class="sxs-lookup"><span data-stu-id="e7472-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="e7472-105">आउट ऑफ बॉक्स मॉडल</span><span class="sxs-lookup"><span data-stu-id="e7472-105">Out-of-box models</span></span>

<span data-ttu-id="e7472-106">डेटा का पूर्वानुमान शुरू करने का सबसे आसान तरीका पूर्वनिर्धारित मॉडल हैं, जिन्हें अक्सर आउट-ऑफ-बॉक्स मॉडल कहा जाता है.</span><span class="sxs-lookup"><span data-stu-id="e7472-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="e7472-107">इनसाइट जनरेट करने के लिए उन्हें केवल कुछ डेटा और संरचना की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="e7472-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="e7472-108">फिलहाल, निम्नलिखित मॉडल उपलब्ध हैं:</span><span class="sxs-lookup"><span data-stu-id="e7472-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="e7472-109">[ग्राहक जीवनकाल मान](predict-customer-lifetime-value.md): किसी व्यवसाय के साथ संपूर्ण सहभागिता के दौरान ग्राहक के संभावित राजस्व का का पूर्वानुमान लगाता है.</span><span class="sxs-lookup"><span data-stu-id="e7472-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="e7472-110">[उत्पाद अनुशंसा](predict-product-recommendation.md): खरीद व्यवहार और समान खरीद पैटर्न वाले ग्राहकों के आधार पर पूर्वानुमानित उत्पाद अनुशंसाओं के सेट का सुझाव देता है.</span><span class="sxs-lookup"><span data-stu-id="e7472-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="e7472-111">[सदस्यता चर्न](predict-subscription-churn.md): पूर्वनुमान लगाता है कि कहीं ग्राहक द्वारा आपकी कंपनी के सदस्यता उत्पादों या सेवाओं का उपयोग बंद करने का खतरा तो नहीं है.</span><span class="sxs-lookup"><span data-stu-id="e7472-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="e7472-112">[लेन-देन चर्न](predict-transactional-churn.md): पूर्वानुमान लगाता है कि क्या ग्राहक द्वारा आपके उत्पादों या सेवाओं को किसी निश्चित समयसीमा में नहीं खरीदेगा.</span><span class="sxs-lookup"><span data-stu-id="e7472-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="e7472-113">Azure मशीन लर्निंग एकीकरण</span><span class="sxs-lookup"><span data-stu-id="e7472-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="e7472-114">यदि कोई संगठन पहले से ही Azure मशीन लर्निंग प्रयोगों के आधार पर मशीन लर्निंग परिदृश्यों का उपयोग करता है, तो Customer Insights में कस्टम मॉडल सुविधा बिंदुओं को जोड़ने में मदद करती है.</span><span class="sxs-lookup"><span data-stu-id="e7472-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="e7472-115">ऐसे कार्यप्रवाह बनाएं जो आपको वह डेटा चुनने में मदद करें जिससे आप इनसाइट जनरेट करना चाहते हैं और परिणामों को अपनी एकीकृत ग्राहक प्रोफ़ाइल में मैप करें.</span><span class="sxs-lookup"><span data-stu-id="e7472-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="e7472-116">अधिक जानकारी के लिए, [कस्टम मशीन लर्निंग मॉडल](custom-models.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="e7472-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="e7472-117">AI Builder पूर्वानुमान</span><span class="sxs-lookup"><span data-stu-id="e7472-117">AI Builder prediction</span></span>

<span data-ttu-id="e7472-118">कभी-कभी, डेटा सेट अधूरे होते हैं और कुछ मान गायब होते हैं.</span><span class="sxs-lookup"><span data-stu-id="e7472-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="e7472-119">Customer Insights, ग्राहक निकाय और अनुभागों के लिए अनुपलब्ध मानों का पूर्वानुमान करने में मदद कर सकती हैं.</span><span class="sxs-lookup"><span data-stu-id="e7472-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="e7472-120">अधिक जानकारी के लिए, [पूर्वानुमानों के साथ अपना आंशिक डेटा पूरा करें](predictions.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="e7472-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
