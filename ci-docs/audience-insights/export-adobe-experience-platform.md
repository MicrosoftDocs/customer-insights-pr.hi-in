---
title: Customer Insights डेटा को Adobe एक्सपीरियंस प्लेटफ़ॉर्म में निर्यात करें
description: Adobe अनुभव प्लेटफ़ॉर्म में ऑडिएंस इनसाइट सेगमेंट का उपयोग करने का तरीका जानें।
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305526"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="2e23c-103">Adobe एक्सपीरियंस प्लेटफ़ॉर्म (पूर्वावलोकन) में Customer Insights सेगमेंट का उपयोग करें</span><span class="sxs-lookup"><span data-stu-id="2e23c-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="2e23c-104">Dynamics 365 Customer Insights में ऑडिएंस इनसाइट्स के उपयोगकर्ता के रूप में, आपने प्रासंगिक ऑडियंस को लक्षित करके अपने मार्केटिंग अभियानों को अधिक कुशल बनाने के लिए अनुभाग बनाए होंगे।</span><span class="sxs-lookup"><span data-stu-id="2e23c-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="2e23c-105">Adobe एक्सपीरियंस प्लेटफ़ॉर्म में ऑडियंस इनसाइट्स से सेगमेंट उपयोग करने और Adobe Campaign स्टैंडर्ड जैसे अनुप्रयोगों के लिए, आपको इस आलेख में बताए गए कुछ चरणों का पालन करना होगा.</span><span class="sxs-lookup"><span data-stu-id="2e23c-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="इस आलेख में उल्लिखित चरणों का प्रक्रिया आरेख.":::

## <a name="prerequisites"></a><span data-ttu-id="2e23c-107">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="2e23c-107">Prerequisites</span></span>

-   <span data-ttu-id="2e23c-108">Dynamics 365 Customer Insights लाइसेंस</span><span class="sxs-lookup"><span data-stu-id="2e23c-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="2e23c-109">Adobe एक्सपीरियंस प्लेटफ़ॉर्म लाइसेंस</span><span class="sxs-lookup"><span data-stu-id="2e23c-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="2e23c-110">Adobe अभियान स्टैंडर्ड लाइसेंस</span><span class="sxs-lookup"><span data-stu-id="2e23c-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="2e23c-111">Azure ब्लॉब स्टोरेज खाता</span><span class="sxs-lookup"><span data-stu-id="2e23c-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="2e23c-112">अभियान पूर्वावलोकन</span><span class="sxs-lookup"><span data-stu-id="2e23c-112">Campaign Overview</span></span>

<span data-ttu-id="2e23c-113">यह समझने के लिए कि आप Adobe एक्सपीरियंस प्लेटफ़ॉर्म में ऑडियंस इनसाइट्स के सेगमेंट का उपयोग कैसे कर सकते हैं, चलिए एक काल्पनिक नमूना अभियान पर नज़र डालें.</span><span class="sxs-lookup"><span data-stu-id="2e23c-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="2e23c-114">मान लें कि आपकी कंपनी अमेरिका में आपके ग्राहकों के लिए मासिक, सदस्यता-आधारित सेवा प्रदान करती है.</span><span class="sxs-lookup"><span data-stu-id="2e23c-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="2e23c-115">आप उन ग्राहकों की पहचान करना चाहते हैं जिनकी सदस्यता का अगले आठ दिनों में नवीनीकरण किया जाना है, लेकिन अभी तक उनकी सदस्यता का नवीनीकरण नहीं हुआ है.</span><span class="sxs-lookup"><span data-stu-id="2e23c-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="2e23c-116">इन ग्राहकों को रखने के लिए, आप उन्हें Adobe एक्सपीरियंस प्लेटफ़ॉर्म का उपयोग करके ईमेल के माध्यम से प्रचार प्रस्ताव भेजना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="2e23c-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="2e23c-117">इस उदाहरण में, हम एक बार प्रचार ईमेल अभियान चलाना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="2e23c-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="2e23c-118">यह आलेख अभियान को एक से अधिक बार चलाने के उपयोग के मामले को कवर नहीं करता है.</span><span class="sxs-lookup"><span data-stu-id="2e23c-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="2e23c-119">अपनी लक्षित ऑडियंस को पहचानें</span><span class="sxs-lookup"><span data-stu-id="2e23c-119">Identify your target audience</span></span>

<span data-ttu-id="2e23c-120">हमारे परिदृश्य में, हम मानते हैं कि ग्राहकों के ईमेल पते ऑडियंस इनसाइट्स में उपलब्ध हैं और सेगमेंट के सदस्यों की पहचान करने के लिए उनकी प्रचार संबंधी वरीयताओं का विश्लेषण किया गया था.</span><span class="sxs-lookup"><span data-stu-id="2e23c-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="2e23c-121">[आपके द्वारा ऑडियंस इनसाइट्स में परिभाषित किया गया सेगमेंट](segments.md) को **ChurnProneCustomers** कहा जाता है और आप इन ग्राहकों को ईमेल प्रमोशन भेजने की योजना बनाते हैं.</span><span class="sxs-lookup"><span data-stu-id="2e23c-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers सेगमेंट वाले सेगमेंट पेज का स्क्रीनशॉट बनाया गया है.":::

<span data-ttu-id="2e23c-123">आप जो ईमेल भेजना चाहते हैं, उसमें पहला नाम, उपनाम और ग्राहक की सदस्यता समाप्ति तिथि शामिल होगी.</span><span class="sxs-lookup"><span data-stu-id="2e23c-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="2e23c-124">यह ग्राहकों को उस छूट के बारे में सूचित करता है जिसे वे अपनी सदस्यता को समाप्त होने से पहले नवीनीकृत करने पर प्राप्त करते हैं.</span><span class="sxs-lookup"><span data-stu-id="2e23c-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="2e23c-125">अपनी लक्षित ऑडियंस निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="2e23c-125">Export your target audience</span></span>

<span data-ttu-id="2e23c-126">पहचानी गई हमारी लक्षित ऑडियंस के साथ, हम ऑडियंस इनसाइट्स से Azure ब्लॉब स्टोरेज खाते में निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="2e23c-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="2e23c-127">एक कनेक्शन कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="2e23c-127">Configure a connection</span></span>

1. <span data-ttu-id="2e23c-128">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="2e23c-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2e23c-129">कनेक्शन को कॉन्फ़िगर करने के लिए **कनेक्शन जोड़ें** का चयन करें और **Azure Blob संग्रहण** चुनें या **Azure Blob संग्रहण** टाइल में **सेट अप करें** का चयन करें।</span><span class="sxs-lookup"><span data-stu-id="2e23c-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure ब्लॉब स्टोरेज के लिए कॉन्फ़िगरेशन टाइल."::: 

1. <span data-ttu-id="2e23c-131">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="2e23c-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2e23c-132">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="2e23c-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2e23c-133">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="2e23c-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2e23c-134">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="2e23c-134">Choose who can use this connection.</span></span> <span data-ttu-id="2e23c-135">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="2e23c-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2e23c-136">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2e23c-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2e23c-137">जहां आप अनुभाग को निर्यात करना चाहते हैं वहां अपने Blob संग्रहण खाते के लिए **अकाउंट का नाम**, **अकाउंट कुंजी** और **कंटेनर** दर्ज करें।</span><span class="sxs-lookup"><span data-stu-id="2e23c-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="स्टोरेज खाता कॉन्फ़िगरेशन का स्क्रीनशॉट."::: 
   
    - <span data-ttu-id="2e23c-139">Blob संग्रहण खाते का नाम और खाता कुंजी खोजने के तरीके के बारे में अधिक जानने के लिए, [Azure पोर्टल में संग्रहण खाता सेटिंग्स का प्रबंधन करें](/azure/storage/common/storage-account-manage) देखें।</span><span class="sxs-lookup"><span data-stu-id="2e23c-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="2e23c-140">कंटेनर बनाने के बारे में जानने के लिए, [कंटेनर बनाएँ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) देखें.</span><span class="sxs-lookup"><span data-stu-id="2e23c-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="2e23c-141">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="2e23c-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="2e23c-142">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="2e23c-142">Configure an export</span></span>

<span data-ttu-id="2e23c-143">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="2e23c-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2e23c-144">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2e23c-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2e23c-145">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="2e23c-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2e23c-146">एक नया निर्यात बनाने के लिए, **निर्यात जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="2e23c-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="2e23c-147">**निर्यात के लिए कनेक्शन** में, Azure Blob Storage अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="2e23c-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="2e23c-148">यदि आपको यह अनुभाग नाम नहीं दिखता है, तो इस प्रकार का कोई भी कनेक्शन आपके लिए उपलब्ध नहीं है।</span><span class="sxs-lookup"><span data-stu-id="2e23c-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="2e23c-149">वह सेगमेंट चुनें, जिसे आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="2e23c-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="2e23c-150">इस उदाहरण में, यह **ChurnProneCustomers** है.</span><span class="sxs-lookup"><span data-stu-id="2e23c-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers अनुभाग चयनित के साथ अनुभाग चयन उपयोगकर्ता इंटरफ़ेस का स्क्रीनशॉट.":::

1. <span data-ttu-id="2e23c-152">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="2e23c-152">Select **Save**.</span></span>

<span data-ttu-id="2e23c-153">निर्यात डेस्टिनेशन को सहेजने के बाद, आप इसे **डेटा** > **निर्यात** पर पाते हैं.</span><span class="sxs-lookup"><span data-stu-id="2e23c-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="2e23c-154">अब आप [मांग पर सेगमेंट निर्यात कर सकते हैं](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2e23c-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="2e23c-155">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md).</span><span class="sxs-lookup"><span data-stu-id="2e23c-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2e23c-156">सुनिश्चित करें कि निर्यात किए गए सेगमेंट में रिकॉर्ड की संख्या आपके Adobe कैंपेन स्टैंडर्ड लाइसेंस की अनुमत सीमा के अंदर है.</span><span class="sxs-lookup"><span data-stu-id="2e23c-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="2e23c-157">निर्यात किए गए डेटा को ऊपर कॉन्फ़िगर किए गए Azure ब्लॉब स्टोरेज कंटेनर में स्टोर किया जाता है।</span><span class="sxs-lookup"><span data-stu-id="2e23c-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="2e23c-158">निम्न फ़ोल्डर पाथ स्वचालित रूप से आपके कंटेनर में बनाया गया है:</span><span class="sxs-lookup"><span data-stu-id="2e23c-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="2e23c-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="2e23c-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="2e23c-160">उदाहरण: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="2e23c-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="2e23c-161">*model.json* निर्यात किए गए निकायों के लिए *%ExportDestinationName%* स्तर पर रहता है.</span><span class="sxs-lookup"><span data-stu-id="2e23c-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="2e23c-162">उदाहरण: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="2e23c-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="2e23c-163">Adobe एक्सपीरियंस प्लेटफ़ॉर्म में एक्सपीरियंस डेटा मॉडल (XDM) को परिभाषित करें</span><span class="sxs-lookup"><span data-stu-id="2e23c-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="2e23c-164">Adobe एक्सपीरियंस प्लेटफ़ॉर्म में ऑडियंस इनसाइट्स से निर्यात किए गए डेटा का उपयोग करने से पहले हमें एक्सपीरियंस डेटा मॉडल स्कीमा को परिभाषित करने और [रियल टाइम ग्राहक प्रोफ़ाइल के लिए डेटा कॉन्फ़िगर करें](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="2e23c-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="2e23c-165">[XDM क्या है](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) जानें और [स्कीमा संरचना की मूल बातें](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) को समझें.</span><span class="sxs-lookup"><span data-stu-id="2e23c-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="2e23c-166">Adobe एक्सपीरियंस प्लेटफ़ॉर्म में डेटा आयात करें</span><span class="sxs-lookup"><span data-stu-id="2e23c-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="2e23c-167">अब जब सब कुछ अपनी जगह पर है, हमें ऑडियंस इनसाइट्स से तैयार ऑडियंस डेटा को Adobe एक्सपीरियंस प्लेटफ़ॉर्म में इंपोर्ट करने की जरूरत है.</span><span class="sxs-lookup"><span data-stu-id="2e23c-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="2e23c-168">सबसे पहले, [एक Azure ब्लॉब स्टोरेज स्रोत कनेक्शन बनाएं](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="2e23c-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="2e23c-169">स्रोत कनेक्शन को परिभाषित करने के बाद, क्लाउड स्टोरेज बैच कनेक्शन के लिए [डेटा प्रवाह कॉन्फ़िगर करें](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials), ताकि ऑडियंस से सेगमेंट आउटपुट को Adobe एक्सपीरियंस प्लेटफ़ॉर्म में आयात किया जा सके.</span><span class="sxs-lookup"><span data-stu-id="2e23c-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="2e23c-170">Adobe कैंपेन स्टैंडर्ड में एक ऑडियंस बनाएं</span><span class="sxs-lookup"><span data-stu-id="2e23c-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="2e23c-171">इस अभियान के लिए ईमेल भेजने हेतु, हम Adobe अभियान मानक का उपयोग करेंगे।</span><span class="sxs-lookup"><span data-stu-id="2e23c-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="2e23c-172">Adobe एक्सपीरियंस प्लेटफ़ॉर्म में डेटा आयात करने के बाद, हमें Adobe कैंपेन स्टैंडर्ड में Adobe एक्सपीरियंस प्लेटफ़ॉर्म में डेटा का उपयोग करते हुए [एक ऑडियंस बनाने](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="2e23c-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="2e23c-173">Adobe एक्सपीरियंस प्लेटफ़ॉर्म में डेटा पर आधारित ऑडियंस को परिभाषित करने के लिए Adobe कैंपेन स्टैंडर्ड में [सेगमेंट बिल्डर इस्तेमाल](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) करने के बारे में जानें.</span><span class="sxs-lookup"><span data-stu-id="2e23c-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="2e23c-174">Adobe कैंपेन स्टैंडर्ड का उपयोग करके ईमेल बनाएं और भेजें</span><span class="sxs-lookup"><span data-stu-id="2e23c-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="2e23c-175">ईमेल सामग्री बनाएं और फिर अपना ईमेल [परीक्षण करें और भेजें](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).</span><span class="sxs-lookup"><span data-stu-id="2e23c-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe कैंपेन स्टैंडर्ड से नवीकरण प्रस्ताव के साथ नमूना ईमेल.":::
