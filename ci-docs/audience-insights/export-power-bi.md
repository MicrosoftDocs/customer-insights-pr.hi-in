---
title: Power BI कनेक्टर
description: Power BI में Dynamics 365 Customer Insights कनेक्टर का उपयोग करना सीखें.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596041"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="79b1f-103">Power BI के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="79b1f-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="79b1f-104">Power BI Desktop के साथ अपने डेटा के लिए विज़ुअलाइज़ेशन बनाएं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="79b1f-105">अतिरिक्त इनसाइट्स उत्पन्न करें और अपने एकीकृत ग्राहक डेटा के साथ रिपोर्ट बनाएं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="79b1f-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="79b1f-106">Prerequisites</span></span>

- <span data-ttu-id="79b1f-107">आपके पास एकीकृत ग्राहक प्रोफाइल हैं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="79b1f-108">आपके कंप्यूटर पर [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) का नवीनतम वर्जन इंस्टॉल है.</span><span class="sxs-lookup"><span data-stu-id="79b1f-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="79b1f-109">[Power BI Desktop के बारे में अधिक जानें](/power-bi/desktop-what-is-desktop)</span><span class="sxs-lookup"><span data-stu-id="79b1f-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="79b1f-110">Power BI के लिए कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="79b1f-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="79b1f-111">Power BI Desktop में, **फ़ाइल** > **डेटा प्राप्त करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="79b1f-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="79b1f-112">**अधिक देखें** चुनें और **Dynamics 365 Customer Insights** खोजें</span><span class="sxs-lookup"><span data-stu-id="79b1f-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="79b1f-113">**कनेक्ट करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="79b1f-113">Select **Connect**.</span></span>

1. <span data-ttu-id="79b1f-114">उसी संगठनात्मक खाते के साथ **साइन इन करें** जिसका उपयोग आप Customer Insights के लिए करते हैं और **कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="79b1f-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="79b1f-115">इस चरण में आपके द्वारा दर्शाए गए खाते का उपयोग Customer Insights से डेटा प्राप्त करने के लिए किया जाता है और आवश्यक नहीं कि यह आपके द्वारा Power BI में लॉग इन किए गए खाते के समान हो.</span><span class="sxs-lookup"><span data-stu-id="79b1f-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="79b1f-116">डेटा लाने के लिए उपयोग किए जाने वाले खाते को रीसेट करने के लिए, Power BI खोलें और **फ़ाइल** > **विकल्प** > **सेटिंग्स** > **डेटा स्रोत सेटिंग्स** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="79b1f-117">डेटा स्रोतों की सूची में, **Dynamics 365 Customer Insights लॉग इन** का चयन करें और **स्पष्ट अनुमतियां** चुनें.</span><span class="sxs-lookup"><span data-stu-id="79b1f-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="79b1f-118">**नेविगेटर** संवाद बॉक्स में.</span><span class="sxs-lookup"><span data-stu-id="79b1f-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="79b1f-119">आप उन सभी परिवेशों की सूची देखते हैं जिनके पास आपके पास पहुंच है.</span><span class="sxs-lookup"><span data-stu-id="79b1f-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="79b1f-120">एक परिवेश का विस्तार करें और किसी भी फ़ोल्डर (निकायों, साधनों, खंडों, एनरिचमेंट) को खोलें.</span><span class="sxs-lookup"><span data-stu-id="79b1f-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="79b1f-121">उदाहरण के लिए, **निकाय** फ़ोल्डर खोलें, उन सभी निकायओं को देखने के लिए जिन्हें आप आयात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="79b1f-122">![Power BI कनेक्टर नेविगेटर](media/power-bi-navigator.png "Power BI कनेक्टर नेविगेटर")</span><span class="sxs-lookup"><span data-stu-id="79b1f-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="79b1f-123">शामिल करने के लिए निकायों के बगल में स्थित चेक बॉक्स चुनें और **लोड करें**.</span><span class="sxs-lookup"><span data-stu-id="79b1f-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="79b1f-124">आप एकाधिक परिवेश से कई निकायों का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="79b1f-125">आपके निकाय लोड होने के दौरान आपको एक लोडिंग डायलॉग बॉक्स दिखाई देगा.</span><span class="sxs-lookup"><span data-stu-id="79b1f-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="79b1f-126">एक बार जब आपकी सभी चयनित निकायएं लोड हो जाती हैं, तो आप डेटा की कल्पना करने के लिए Power BI की क्षमताओं का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="79b1f-127">बड़े डेटा सेट</span><span class="sxs-lookup"><span data-stu-id="79b1f-127">Large data sets</span></span>

<span data-ttu-id="79b1f-128">Power BI के लिए Customer Insights कनेक्टर को उन डेटा सेटों के लिए काम करने के लिए डिज़ाइन किया गया है जिनमें 1 मिलियन तक ग्राहक प्रोफ़ाइल हैं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="79b1f-129">बड़े डेटा सेट को आयात करने से काम बन सकता है, लेकिन इसमें लंबा समय लगता है.</span><span class="sxs-lookup"><span data-stu-id="79b1f-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="79b1f-130">इसके अतिरिक्त, Power BI सीमाओं के कारण यह प्रक्रिया एक टाइम-आउट में चल सकती है.</span><span class="sxs-lookup"><span data-stu-id="79b1f-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="79b1f-131">अधिक जानकारी के लिए देखें [Power BI: बड़े डेटा सेट के लिए सिफारिशें।](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="79b1f-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="79b1f-132">डेटा के सबसेट के साथ काम करें</span><span class="sxs-lookup"><span data-stu-id="79b1f-132">Work with a subset of data</span></span>

<span data-ttu-id="79b1f-133">अपने डेटा के सबसेट के साथ काम करने पर विचार करें.</span><span class="sxs-lookup"><span data-stu-id="79b1f-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="79b1f-134">उदाहरण के लिए, आप Power BI को सभी ग्राहक रिकॉर्ड निर्यात करने के बजाय [सेगमेंट](segments.md) बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="79b1f-135">समस्या निवारण</span><span class="sxs-lookup"><span data-stu-id="79b1f-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="79b1f-136">Power BI में Customer Insights परिवेश नहीं दिखता है</span><span class="sxs-lookup"><span data-stu-id="79b1f-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="79b1f-137">ऑडियंस इनसाइट्स में दो समान निकायों के बीच परिभाषित एक से अधिक [संबंध](relationships.md) के लिए परिवेश Power BI कनेक्टर में उपलब्ध नहीं होगा.</span><span class="sxs-lookup"><span data-stu-id="79b1f-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="79b1f-138">आप डुप्लिकेट किए गए संबंधों को पहचान सकते हैं और निकाल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="79b1f-139">ऑडियंस इनसाइट्स में, Power BI में गायब हुए परिवेश पर आप **डेटा** > **संबंधों** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="79b1f-140">डुप्लिकेट संबंधों की पहचान करें:</span><span class="sxs-lookup"><span data-stu-id="79b1f-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="79b1f-141">जांचें कि क्या एक ही दो निकायों के बीच परिभाषित एक से अधिक संबंध हैं.</span><span class="sxs-lookup"><span data-stu-id="79b1f-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="79b1f-142">जांचें कि क्या दो निकायों के बीच एक संबंध बनाया गया है, जो दोनों एकीकरण प्रक्रिया में शामिल है.</span><span class="sxs-lookup"><span data-stu-id="79b1f-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="79b1f-143">एकीकरण प्रक्रिया में शामिल सभी निकायों के बीच एक अंतर्निहित संबंध परिभाषित है.</span><span class="sxs-lookup"><span data-stu-id="79b1f-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="79b1f-144">पहचाने गए किसी भी डुप्लिकेट संबंध को हटा दें.</span><span class="sxs-lookup"><span data-stu-id="79b1f-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="79b1f-145">डुप्लिकेट किए गए संबंधों को हटाने के बाद, Power BI कनेक्टर को फिर से कॉन्फ़िगर करने का प्रयास करें.</span><span class="sxs-lookup"><span data-stu-id="79b1f-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="79b1f-146">परिवेश अब उपलब्ध होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="79b1f-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]