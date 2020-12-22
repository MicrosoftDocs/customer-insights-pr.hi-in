---
title: एक Azure Data Lake खाते में सामान्य डेटा मॉडल डेटा कनेक्ट करें
description: Azure Data Lake Storage का उपयोग कर सामान्य डेटा मॉडल डेटा के साथ काम करें.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643460"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="a4c4e-103">किसी Azure Data Lake खाते का उपयोग करके कॉमन डेटा मॉडल फ़ोल्डर से जोड़ें</span><span class="sxs-lookup"><span data-stu-id="a4c4e-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="a4c4e-104">यह आलेख आपके Azure Data Lake Storage Gen2 खाते का उपयोग करके एक सामान्य डेटा मॉडल फ़ोल्डर से डेटा को इन्जेस्ट करने के बारे में जानकारी प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="a4c4e-105">महत्वपूर्ण विचार</span><span class="sxs-lookup"><span data-stu-id="a4c4e-105">Important considerations</span></span>

- <span data-ttu-id="a4c4e-106">आपके Azure Data Lake के डेटा को Common Data Model के मानक का पालन करने की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="a4c4e-107">अन्य प्रारूप फिलहाल समर्थित नहीं हैं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="a4c4e-108">डेटा इन्जेस्चन विशेष रूप से Azure Data Lake *Gen2* स्टोरेज खातों का समर्थन करता है.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="a4c4e-109">आप डेटा इन्जेस्ट करने के लिए Azure Data Lake Gen1 स्टोरेज खातों का उपयोग नहीं कर सकते.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="a4c4e-110">एक Azure service principal के साथ प्रमाणित करने के लिए, सुनिश्चित करें कि यह आपके टेनेंट में कॉन्फ़िगर किया गया है.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="a4c4e-111">अधिक जानकारी के लिए, देखें [एक Azure Data Lake Storage Gen2 खाते के लिए एक Azure service principal के साथ ऑडियंस इन्साइट्स को कनेक्ट करें](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a4c4e-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="a4c4e-112">जिस Azure Data Lake को आप कनेक्ट करना चाहते हैं और डेटा को इन्जेस्ट करना चाहते हैं, वो Dynamics 365 Customer Insights परिवेश के रूप में एक ही Azure क्षेत्र में होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="a4c4e-113">एक अलग Azure क्षेत्र में एक Data Lake से एक सामान्य डेटा मॉडल फ़ोल्डर के लिए कनेक्शंस समर्थित नहीं हैं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="a4c4e-114">परिवेश के Azure क्षेत्र को जानने के लिए, ऑडियंस इन्साइट्स में **व्यवस्थापक** > **सिस्टम** > **के बारे में** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="a4c4e-115">ऑनलाइन सेवाओं में संग्रहीत डेटा को किसी अलग स्थान पर संग्रहीत किया जा सकता है जहां डेटा को Dynamics 365 Customer Insights में प्रोसेस किया जाता है या संग्रहीत किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="a4c4e-116"> ऑनलाइन सेवाओं में संग्रहित डेटा को आयात या कनेक्ट करके, आप सहमत होते हैं कि डेटा को Dynamics 365 Customer Insights के साथ स्थानांतरित और संग्रहित किया जा सकता है. [Microsoft ट्रस्ट सेंटर में और जानें.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="a4c4e-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="a4c4e-117">Common Data Model फ़ोल्डर से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="a4c4e-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="a4c4e-118">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="a4c4e-119">**डेटा स्रोत जोड़ें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="a4c4e-120">**एक सामान्य डेटा मॉडल फ़ोल्डर से कनेक्ट करें** का चयन करें, डेटा स्रोत के लिए एक **नाम** दर्ज करें, और **अगला** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="a4c4e-121">आप प्रमाणीकरण के लिए संसाधन-आधारित विकल्प और सदस्यता-आधारित विकल्प का उपयोग करके बीच में चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="a4c4e-122">अधिक जानकारी के लिए, देखें [एक Azure Data Lake Storage Gen2 खाते के लिए एक Azure service principal के साथ ऑडियंस इन्साइट्स को कनेक्ट करें](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a4c4e-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="a4c4e-123">**कंटेनर** जानकारी दर्ज करें और **अगला** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4c4e-124">![Azure Data Lake के लिए कनेक्कशन विवरण दर्ज करने हेतु संवाद बॉक्स](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="a4c4e-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="a4c4e-125">**एक सामान्य डेटा मॉडल फ़ोल्डर का चयन करें** संवाद में, उसी से डेटा आयात करने के लिए model.json फ़ाइल का चयन करें, और **अगला** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a4c4e-126">परिवेश में किसी अन्य डेटा स्रोत से जुड़ी कोई भी model.json फाइल सूची में नहीं दिखाई देगी.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="a4c4e-127">आपको चयनित model.json फ़ाइल में उपलब्ध निकायों की सूची मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="a4c4e-128">आप उपलब्ध निकायों की सूची की समीक्षा कर सकते हैं और उनमें से चुयन करके **सहेजें** चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="a4c4e-129">सभी चयनित निकाय नए डेटा स्रोत से इन्जेस्ट किए जायेंगे.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4c4e-130">![model.json फ़ाइल से निकायों की सूची प्रदर्शित करने वाला संवाद बॉक्स](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="a4c4e-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="a4c4e-131">आप डेटा प्रोफाइलिंग को सक्षम करने के लिए कौन सी डेटा निकायों को इंगित करना चाहते हैं और **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="a4c4e-132">डेटा प्रोफाइलिंग विश्लेषण और अन्य क्षमताओं को सक्षम बनाता है.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="a4c4e-133">आप पूरी निकाय का चयन कर सकते हैं, जो निकाय से सभी विशेषताओं का चयन करता है, या अपनी पसंद के कुछ विशेषताओं का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="a4c4e-134">डिफ़ॉल्ट रूप से, डेटा प्रोफाइलिंग के लिए कोई निकाय सक्षम नहीं है.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4c4e-135">![डेटा प्रोफाइलिंग दिखाता एक संवाद बॉक्स](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="a4c4e-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="a4c4e-136">आपके चयन को सहेजने के बाद, **डेटा स्रोत** पृष्ठ खुलता है.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="a4c4e-137">अब आपको डेटा स्रोत के रूप में Common Data Model फ़ोल्डर कनेक्शन देखना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="a4c4e-138">एक model.json फ़ाइल उसी परिवेश में केवल एक ही डेटा स्रोत के साथ संबद्ध हो सकता है.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="a4c4e-139">हालांकि, एक ही model.json फ़ाइल कई परिवेश में डेटा स्रोतों के लिए इस्तेमाल किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="a4c4e-140">एक Common Data Model फ़ोल्डर डेटा स्रोत संपादित करें</span><span class="sxs-lookup"><span data-stu-id="a4c4e-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="a4c4e-141">आप सामान्य डेटा मॉडल फ़ोल्डर वाले स्टोरेज खाते के लिए एक्सेस कुंजी को अपडेट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="a4c4e-142">आप model.json फ़ाइल भी बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-142">You may also change the model.json file.</span></span> <span data-ttu-id="a4c4e-143">अपने संग्रहण खाते से एक अलग कंटेनर से कनेक्ट करने के लिए, या खाता नाम बदलने के लिए, [एक नया डेटा स्रोत कनेक्शन बनाएं](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="a4c4e-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="a4c4e-144">ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a4c4e-145">आप जिस डेटा स्रोत को अपडेट करना चाहते हैं, उसके आगे दीर्घवृत्त का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="a4c4e-146">सूची से **संपादन करें** विकल्प चुनें.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="a4c4e-147">वैकल्पिक रूप से, **एक्सेस कुंजी** को अपडेट करें और **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![किसी विद्यमान डेटा स्रोत के लिए एक्सेस कुंजी को संपादित करने और अद्यतन करने के लिए संवाद बॉक्स](media/edit-access-key.png)

5. <span data-ttu-id="a4c4e-149">वैकल्पिक रूप से, आप खाते की कुंजी कनेक्शन से संसाधन-आधारित या सदस्यता-आधारित कनेक्शन में अपडेट कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="a4c4e-150">अधिक जानकारी के लिए, देखें [एक Azure Data Lake Storage Gen2 खाते के लिए एक Azure service principal के साथ ऑडियंस इन्साइट्स को कनेक्ट करें](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a4c4e-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="a4c4e-151">कनेक्शन अपडेट करते समय आप **कंटेनर** जानकारी नहीं बदल सकते.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4c4e-152">![Azure Data Lake के लिए कनेक्कशन विवरण दर्ज करने हेतु संवाद बॉक्स](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="a4c4e-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="a4c4e-153">वैकल्पिक रूप से, निकायों के एक भिन्न सेट के साथ भिन्न model.json फ़ाइल को चुनें.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="a4c4e-154">वैकल्पिक रूप से, आप इन्जेस्ट करने के लिए अतिरिक्त निकायों का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="a4c4e-155">निर्भरता न होने पर आप पहले से ही चयनित निकायों को हटा भी सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a4c4e-156">यदि विद्यमान model.json फ़ाइल और संस्थाओं के सेट पर निर्भरताएं हैं, तो आपको एक त्रुटि संदेश दिखाई देगा और एक भिन्न model.json फ़ाइल को चुना नहीं जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="a4c4e-157">Model.json फ़ाइल को बदलने से पहले उन निर्भरताओं को हटाएं अथवा model.json फ़ाइल के साथ एक नया डेटा स्रोत बनाएँ जिसका उपयोग आप निर्भरताओं को हटाने से बचने के लिए करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="a4c4e-158">वैकल्पिक रूप से, आप डेटा प्रोफाइलिंग को चालू करने के लिए या पहले से चुने गए को अक्षम करने के लिए अतिरिक्त विशेषताओं या निकायों का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="a4c4e-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
