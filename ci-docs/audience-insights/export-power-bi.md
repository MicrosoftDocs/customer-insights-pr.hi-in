---
title: Power BI कनेक्टर
description: Power BI में Dynamics 365 Customer Insights कनेक्टर का उपयोग करना सीखें.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405926"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="615d8-103">Power BI के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="615d8-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="615d8-104">Power BI Desktop के साथ अपने डेटा के लिए विज़ुअलाइज़ेशन बनाएं.</span><span class="sxs-lookup"><span data-stu-id="615d8-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="615d8-105">अतिरिक्त इनसाइट्स उत्पन्न करें और अपने एकीकृत ग्राहक डेटा के साथ रिपोर्ट बनाएं.</span><span class="sxs-lookup"><span data-stu-id="615d8-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="615d8-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="615d8-106">Prerequisites</span></span>

- <span data-ttu-id="615d8-107">आपके पास एकीकृत ग्राहक प्रोफाइल हैं.</span><span class="sxs-lookup"><span data-stu-id="615d8-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="615d8-108">[Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) का नवीनतम संस्करण आपके कंप्यूटर पर स्थापित है.</span><span class="sxs-lookup"><span data-stu-id="615d8-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="615d8-109">[Power BI Desktop के बारे में अधिक जानें](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)</span><span class="sxs-lookup"><span data-stu-id="615d8-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="615d8-110">Power BI के लिए कनेक्टर कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="615d8-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="615d8-111">Power BI Desktop में, **फ़ाइल** > **डेटा प्राप्त करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="615d8-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="615d8-112">**अधिक देखें** चुनें और **Dynamics 365 Customer Insights** खोजें</span><span class="sxs-lookup"><span data-stu-id="615d8-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="615d8-113">परिणाम चुनें और **कनेक्ट करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="615d8-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="615d8-114">उसी संगठनात्मक खाते के साथ **साइन इन करें** जिसका उपयोग आप Customer Insights के लिए करते हैं और **कनेक्ट करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="615d8-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="615d8-115">इस चरण में आपके द्वारा दर्शाए गए खाते का उपयोग Customer Insights से डेटा प्राप्त करने के लिए किया जाता है और आवश्यक नहीं कि यह आपके द्वारा Power BI में लॉग इन किए गए खाते के समान हो.</span><span class="sxs-lookup"><span data-stu-id="615d8-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="615d8-116">डेटा लाने के लिए उपयोग किए जाने वाले खाते को रीसेट करने के लिए, Power BI खोलें और **फ़ाइल** > **विकल्प** > **सेटिंग्स** > **डेटा स्रोत सेटिंग्स** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="615d8-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="615d8-117">डेटा स्रोतों की सूची में, **Dynamics 365 Customer Insights लॉग इन** का चयन करें और **स्पष्ट अनुमतियां** चुनें.</span><span class="sxs-lookup"><span data-stu-id="615d8-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="615d8-118">**नेविगेटर** संवाद बॉक्स में.</span><span class="sxs-lookup"><span data-stu-id="615d8-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="615d8-119">आप उन सभी परिवेशों की सूची देखते हैं जिनके पास आपके पास पहुंच है.</span><span class="sxs-lookup"><span data-stu-id="615d8-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="615d8-120">एक परिवेश का विस्तार करें और किसी भी फ़ोल्डर (निकायों, साधनों, खंडों, एनरिचमेंट) को खोलें.</span><span class="sxs-lookup"><span data-stu-id="615d8-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="615d8-121">उदाहरण के लिए, **निकाय** फ़ोल्डर खोलें, उन सभी निकायओं को देखने के लिए जिन्हें आप आयात कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="615d8-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="615d8-122">![Power BI कनेक्टर नेविगेटर](media/power-bi-navigator.png "Power BI कनेक्टर नेविगेटर")</span><span class="sxs-lookup"><span data-stu-id="615d8-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="615d8-123">शामिल करने के लिए निकायों के बगल में स्थित चेक बॉक्स चुनें और **लोड करें**.</span><span class="sxs-lookup"><span data-stu-id="615d8-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="615d8-124">आप एकाधिक परिवेश से कई निकायों का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="615d8-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="615d8-125">आपके निकाय लोड होने के दौरान आपको एक लोडिंग डायलॉग बॉक्स दिखाई देगा.</span><span class="sxs-lookup"><span data-stu-id="615d8-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="615d8-126">एक बार जब आपकी सभी चयनित निकायएं लोड हो जाती हैं, तो आप डेटा की कल्पना करने के लिए Power BI की क्षमताओं का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="615d8-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="615d8-127">बड़े डेटा सेट</span><span class="sxs-lookup"><span data-stu-id="615d8-127">Large data sets</span></span>

<span data-ttu-id="615d8-128">Power BI के लिए Customer Insights कनेक्टर को उन डेटा सेटों के लिए काम करने के लिए डिज़ाइन किया गया है जिनमें 1 मिलियन तक ग्राहक प्रोफ़ाइल हैं.</span><span class="sxs-lookup"><span data-stu-id="615d8-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="615d8-129">बड़े डेटा सेट को आयात करने से काम बन सकता है, लेकिन इसमें लंबा समय लगता है.</span><span class="sxs-lookup"><span data-stu-id="615d8-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="615d8-130">इसके अतिरिक्त, Power BI सीमाओं के कारण यह प्रक्रिया एक टाइम-आउट में चल सकती है.</span><span class="sxs-lookup"><span data-stu-id="615d8-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="615d8-131">अधिक जानकारी के लिए देखें [Power BI: बड़े डेटा सेट के लिए सिफारिशें।](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="615d8-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="615d8-132">डेटा के सबसेट के साथ काम करें</span><span class="sxs-lookup"><span data-stu-id="615d8-132">Work with a subset of data</span></span>

<span data-ttu-id="615d8-133">अपने डेटा के सबसेट के साथ काम करने पर विचार करें.</span><span class="sxs-lookup"><span data-stu-id="615d8-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="615d8-134">उदाहरण के लिए, आप Power BI को सभी ग्राहक रिकॉर्ड निर्यात करने के बजाय [सेगमेंट](segments.md) बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="615d8-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
