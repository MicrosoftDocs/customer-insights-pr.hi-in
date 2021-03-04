---
title: SFTP कस्टम आयात के साथ एनरिचमेंट
description: SFTP कस्टम आयात एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269608"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="e2070-103">कस्टम डेटा (पूर्वावलोकन) के साथ ग्राहक प्रोफाइल को समृद्ध करें</span><span class="sxs-lookup"><span data-stu-id="e2070-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="e2070-104">सेक्योर फ़ाइल ट्रांसफर प्रोटोकॉल (SFTP) कस्टम आयात आपको डेटा आयात करने में सक्षम बनाता है जिसे डेटा एकीकरण की प्रक्रिया से गुजरना नहीं पड़ता है.</span><span class="sxs-lookup"><span data-stu-id="e2070-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="e2070-105">यह आपके डेटा को लाने का एक लचीला, सुरक्षित और आसान तरीका है.</span><span class="sxs-lookup"><span data-stu-id="e2070-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="e2070-106">SFTP कस्टम आयात का उपयोग [SFTP निर्यात](export-sftp.md) के संयोजन में किया जा सकता है जो आपको समृद्धता के लिए आवश्यक ग्राहक प्रोफ़ाइल डेटा का निर्यात करने देता है.</span><span class="sxs-lookup"><span data-stu-id="e2070-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="e2070-107">डेटा तो संसाधित किया जा सकता है, समृद्ध, और SFTP कस्टम आयात Dynamics 365 Customer Insights की ऑडियंस इनसाइट्स क्षमता को वापस लाने के लिए समृद्ध डेटा लाने के लिए इस्तेमाल किया जा सकता है .</span><span class="sxs-lookup"><span data-stu-id="e2070-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2070-108">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="e2070-108">Prerequisites</span></span>

<span data-ttu-id="e2070-109">SFTP कस्टम आयात को कॉन्फ़िगर करने के लिए, निम्नलिखित आवश्यकताओं को पूरा किया जाना चाहिए:</span><span class="sxs-lookup"><span data-stu-id="e2070-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e2070-110">आपके पास SFTP स्थान के लिए उपयोगकर्ता क्रेडेंशियल्स (उपयोगकर्ता नाम और पासवर्ड) है जहां से डेटा आयात किया जा रहा है.</span><span class="sxs-lookup"><span data-stu-id="e2070-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="e2070-111">आपके पास SFTP होस्ट के लिए URL और पोर्ट नंबर (सामान्य तौर पर 22) है.</span><span class="sxs-lookup"><span data-stu-id="e2070-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="e2070-112">आपके पास SFTP होस्ट पर आयात की जाने वाली फ़ाइल का नाम और स्थान है.</span><span class="sxs-lookup"><span data-stu-id="e2070-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="e2070-113">एक *model.json* फ़ाइल है जो आयात किए जाने वाले डेटा के लिए स्कीमा निर्दिष्ट करती है.</span><span class="sxs-lookup"><span data-stu-id="e2070-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="e2070-114">यह फाइल आयात करने के लिए फ़ाइल के रूप में एक ही निर्देशिका में होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="e2070-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="e2070-115">आपके पास [प्रशासक](permissions.md#administrator) की अनुमति है.</span><span class="sxs-lookup"><span data-stu-id="e2070-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="e2070-116">कॉन्फ़िगरेशन</span><span class="sxs-lookup"><span data-stu-id="e2070-116">Configuration</span></span>

1. <span data-ttu-id="e2070-117">**डेटा** > **समृद्ध** पर जाएं और **खोजें** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e2070-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e2070-118">**SFTP कस्टम आयात टाइल** पर, **मेरे डेटा को समृद्ध करें**.</span><span class="sxs-lookup"><span data-stu-id="e2070-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2070-119">![SFTP कस्टम आयात टाइल](media/SFTP_Custom_Import_tile.png "SFTP कस्टम आयात टाइल")</span><span class="sxs-lookup"><span data-stu-id="e2070-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="e2070-120">**शुरू करें** चुनें और SFTP सर्वर के लिए क्रेडेंशियल्स और पता प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="e2070-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="e2070-121">उदाहरण के लिए, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="e2070-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="e2070-122">यदि यह रूट फ़ोल्डर में नहीं है तो SFTP सर्वर पर फ़ाइल के लिए डेटा और पाथ शामिल फ़ाइल का नाम दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="e2070-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="e2070-123">**कस्टम आयात से कनेक्ट करें** का चयन करके सभी इनपुटों की पुष्टि करें.</span><span class="sxs-lookup"><span data-stu-id="e2070-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2070-124">![SFTP कस्टम आयात कॉन्फ़िगरेशन फ्लाईआउट](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP कस्टम आयात कॉन्फ़िगरेशन फ्लाईआउट")</span><span class="sxs-lookup"><span data-stu-id="e2070-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="e2070-125">फील्ड मैपिंग को परिभाषित करना</span><span class="sxs-lookup"><span data-stu-id="e2070-125">Defining field mappings</span></span> 

<span data-ttu-id="e2070-126">SFTP सर्वर पर आयात की जाने वाली फ़ाइल को शामिल करने वाली निर्देशिका में एक *model.json* फ़ाइल भी होनी चाहिए.</span><span class="sxs-lookup"><span data-stu-id="e2070-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="e2070-127">यह फ़ाइल डेटा आयात करने के लिए उपयोग करने के लिए स्कीमा को परिभाषित करती है.</span><span class="sxs-lookup"><span data-stu-id="e2070-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="e2070-128">स्कीमा को फील्ड मैपिंग को निर्दिष्ट करने के लिए [सामान्य डेटा मॉडल](https://docs.microsoft.com/common-data-model/) का उपयोग करना होता है .</span><span class="sxs-lookup"><span data-stu-id="e2070-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="e2070-129">एक model.json फ़ाइल का एक सरल उदाहरण इस तरह दिखता है:</span><span class="sxs-lookup"><span data-stu-id="e2070-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="e2070-130">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="e2070-130">Enrichment results</span></span>

<span data-ttu-id="e2070-131">संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e2070-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e2070-132">आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e2070-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e2070-133">प्रोसेस करने के समय आयात किए जाने वाले डेटा के आकार और SFTP सर्वर से कनेक्शन पर निर्भर करेगा.</span><span class="sxs-lookup"><span data-stu-id="e2070-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="e2070-134">एनरिचमेंट प्रक्रिया पूरी होने के बाद, आप **मेरे एनरिचमेंट्स** के तहत अपने नए आयात किए गए कस्टम एनरिचमेंट डेटा की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e2070-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="e2070-135">इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="e2070-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e2070-136">आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e2070-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2070-137">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="e2070-137">Next steps</span></span>

<span data-ttu-id="e2070-138">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="e2070-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e2070-139">अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [सेगमेंट](segments.md), [साधन](measures.md), और [डेटा निर्यात](export-destinations.md) बनाएं .</span><span class="sxs-lookup"><span data-stu-id="e2070-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]