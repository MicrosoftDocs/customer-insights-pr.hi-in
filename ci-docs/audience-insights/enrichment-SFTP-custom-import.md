---
title: SFTP कस्टम आयात के साथ एनरिचमेंट
description: SFTP कस्टम आयात एनरिचमेंट के बारे में सामान्य जानकारी.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304652"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="63faa-103">कस्टम डेटा (पूर्वावलोकन) के साथ ग्राहक प्रोफाइल को समृद्ध करें</span><span class="sxs-lookup"><span data-stu-id="63faa-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="63faa-104">सेक्योर फ़ाइल ट्रांसफर प्रोटोकॉल (SFTP) कस्टम आयात आपको डेटा आयात करने में सक्षम बनाता है जिसे डेटा एकीकरण की प्रक्रिया से गुजरना नहीं पड़ता है.</span><span class="sxs-lookup"><span data-stu-id="63faa-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="63faa-105">यह आपके डेटा को लाने का एक लचीला, सुरक्षित और आसान तरीका है.</span><span class="sxs-lookup"><span data-stu-id="63faa-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="63faa-106">SFTP कस्टम आयात का उपयोग [SFTP निर्यात](export-sftp.md) के संयोजन में किया जा सकता है जो आपको समृद्धता के लिए आवश्यक ग्राहक प्रोफ़ाइल डेटा का निर्यात करने देता है.</span><span class="sxs-lookup"><span data-stu-id="63faa-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="63faa-107">फिर डेटा को संसाधित और समृद्ध किया जा सकता है, और समृद्ध डेटा को Dynamics 365 Customer Insights की ऑडिएंस इनसाइट्स क्षमता में वापस लाने के लिए SFTP कस्टम आयात का उपयोग किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="63faa-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="63faa-108">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="63faa-108">Prerequisites</span></span>

<span data-ttu-id="63faa-109">SFTP कस्टम आयात को कॉन्फ़िगर करने के लिए, निम्नलिखित आवश्यकताओं को पूरा किया जाना चाहिए:</span><span class="sxs-lookup"><span data-stu-id="63faa-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="63faa-110">आपके पास फ़ाइल का नाम और स्थान (पथ) है जिसे SFTP होस्ट पर आयात किया जाना है।</span><span class="sxs-lookup"><span data-stu-id="63faa-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="63faa-111">एक *model.json* फ़ाइल है जो आयात किए जाने वाले डेटा के लिए [सामान्य डेटा मॉडल स्कीमा](/common-data-model/) निर्दिष्ट करती है.</span><span class="sxs-lookup"><span data-stu-id="63faa-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="63faa-112">यह फाइल आयात करने के लिए फ़ाइल के रूप में एक ही निर्देशिका में होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="63faa-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="63faa-113">एक SFTP कनेक्शन पहले से ही एक व्यवस्थापक द्वारा कॉन्फ़िगर किया गया है *या* आपके पास [प्रशासक](permissions.md#administrator) अनुमतियां हैं.</span><span class="sxs-lookup"><span data-stu-id="63faa-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="63faa-114">आपको SFTP लोकेशन के लिए उपयोगकर्ता के क्रेडेंशियल्स, URL और पोर्ट नंबर की आवश्यकता होगी जहां से आप डेटा आयात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="63faa-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="63faa-115">आयात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="63faa-115">Configure the import</span></span>

1. <span data-ttu-id="63faa-116">**डेटा** > **समृद्ध** पर जाएं और **खोजें** टैब का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="63faa-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="63faa-117">**SFTP कस्टम आयात टाइल** पर, **मेरे डेटा को समृद्ध करें** चुनें और फिर **शुरू करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="63faa-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP कस्टम आयात टाइल.":::

1. <span data-ttu-id="63faa-119">ड्राप-डाउन सूची से [कनेक्शन](connections.md) चुनें।</span><span class="sxs-lookup"><span data-stu-id="63faa-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="63faa-120">यदि कोई कनेक्शन उपलब्ध नहीं है तो किसी व्यवस्थापक से संपर्क करें.</span><span class="sxs-lookup"><span data-stu-id="63faa-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="63faa-121">यदि आप एक व्यवस्थापक हैं, तो आप ड्रॉपडाउन सूची से **कनेक्शन जोड़ें** का चयन करके और **SFTP कस्टम आयात** चुनकर एक कनेक्शन बना सकते हैं ।</span><span class="sxs-lookup"><span data-stu-id="63faa-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="63faa-122">चयनित कनेक्शन की पुष्टि करने के लिए **कस्टम इम्पोर्ट से कनेक्ट करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="63faa-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="63faa-123">**अगला** चुनें और उस डेटा फ़ाइल का **पथ** तथा **फ़ाइल का नाम** दर्ज करें जिसे आप आयात करना चाहते हैं।</span><span class="sxs-lookup"><span data-stu-id="63faa-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="डेटा लोकेशन दर्ज करते समय का स्क्रीनशॉट.":::

1. <span data-ttu-id="63faa-125">**अगला** का चयन करें और संवर्धन और आउटपुट निकाय के लिए एक नाम दें.</span><span class="sxs-lookup"><span data-stu-id="63faa-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="63faa-126">अपने विकल्पों की समीक्षा करने के बाद **संवर्धन सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="63faa-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="63faa-127">SFTP कस्टम आयात के लिए कनेक्शन को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="63faa-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="63faa-128">आपको कनेक्शन को कॉन्फ़िगर करने के लिए एक व्यवस्थापक होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="63faa-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="63faa-129">किसी संवर्धन को कॉन्फ़िगर करते समय **कनेक्शन जोड़ें** का चयन करें *या* **व्यवस्थापक** > **कनेक्शन** पर जाएं और Custom Import टाइल पर **सेट करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="63faa-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="63faa-130">**डिस्प्ले नाम** बॉक्स में कनेक्शन के लिए एक नाम दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="63faa-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="63faa-131">SFTP सर्वर के लिए एक मान्य उपयोगकर्ता नाम, पासवर्ड और होस्ट URL दर्ज करें, जिस पर आयात किया जाने वाला डेटा रहता है।</span><span class="sxs-lookup"><span data-stu-id="63faa-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="63faa-132">समीक्षा करें और **डेटा गोपनीयता और अनुपालन** के लिए **मैं सहमत हूं** चेकबॉक्स का चयन करके अपनी सहमति प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="63faa-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="63faa-133">कॉन्फ़िगरेशन को मान्य करने के लिए **सत्यापित** चुनें.</span><span class="sxs-lookup"><span data-stu-id="63faa-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="63faa-134">एक बार सत्यापन पूरा हो जाने पर, **सहेजें** चुनकर कनेक्शन को सहेजा जा सकता है।</span><span class="sxs-lookup"><span data-stu-id="63faa-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63faa-135">![Experian कनेक्शन कॉन्फिगरेशन पृष्ठ](media/enrichment-SFTP-connection.png "Experian कनेक्शन कॉन्फिगरेशन पृष्ठ")</span><span class="sxs-lookup"><span data-stu-id="63faa-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="63faa-136">फील्ड मैपिंग को परिभाषित करना</span><span class="sxs-lookup"><span data-stu-id="63faa-136">Defining field mappings</span></span> 

<span data-ttu-id="63faa-137">SFTP सर्वर पर आयात की जाने वाली फ़ाइल को शामिल करने वाली निर्देशिका में एक *model.json* फ़ाइल भी होनी चाहिए.</span><span class="sxs-lookup"><span data-stu-id="63faa-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="63faa-138">यह फ़ाइल डेटा आयात करने के लिए उपयोग करने के लिए स्कीमा को परिभाषित करती है.</span><span class="sxs-lookup"><span data-stu-id="63faa-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="63faa-139">फ़ील्ड मैपिंग निर्दिष्ट करने के लिए स्कीमा को [ सामान्य डेटा मॉडल](/common-data-model/) का उपयोग करना होगा।</span><span class="sxs-lookup"><span data-stu-id="63faa-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="63faa-140">एक model.json फ़ाइल का एक सरल उदाहरण इस तरह दिखता है:</span><span class="sxs-lookup"><span data-stu-id="63faa-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="63faa-141">संवर्धन के परिणाम</span><span class="sxs-lookup"><span data-stu-id="63faa-141">Enrichment results</span></span>

<span data-ttu-id="63faa-142">संवर्धन प्रक्रिया शुरू करने के लिए, आदेश पट्टी से **रन** आदेश का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="63faa-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="63faa-143">आप सिस्टम को [शेड्यूल किया गया रीफ़्रेश](system.md#schedule-tab) के भाग के रूप में संवर्धन को स्वचालित रूप से चलाने दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="63faa-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="63faa-144">प्रोसेस करने के समय आयात किए जाने वाले डेटा के आकार और SFTP सर्वर से कनेक्शन पर निर्भर करेगा.</span><span class="sxs-lookup"><span data-stu-id="63faa-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="63faa-145">एनरिचमेंट प्रक्रिया पूरी होने के बाद, आप **मेरे एनरिचमेंट्स** के तहत अपने नए आयात किए गए कस्टम एनरिचमेंट डेटा की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="63faa-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="63faa-146">इसके अतिरिक्त, आपको अंतिम अद्यतन का समय और समृद्ध प्रोफ़ाइल की संख्या मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="63faa-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="63faa-147">आप **समृद्ध डेटा देखें** का चयन करके प्रत्येक समृद्ध प्रोफ़ाइल के विस्तृत व्यू का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="63faa-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="63faa-148">अगले चरण</span><span class="sxs-lookup"><span data-stu-id="63faa-148">Next steps</span></span>

<span data-ttu-id="63faa-149">अपने समृद्ध ग्राहक डेटा के ऊपर बनाएं.</span><span class="sxs-lookup"><span data-stu-id="63faa-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="63faa-150">[खंडों](segments.md) को बनाएं और [साधानों](measures.md) और अपने ग्राहकों को व्यक्तिगत अनुभव देने के लिए [डेटा निर्यात करें](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="63faa-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
