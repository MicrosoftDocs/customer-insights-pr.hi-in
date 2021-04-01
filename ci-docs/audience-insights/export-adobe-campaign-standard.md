---
title: Customer Insights डेटा को Adobe कैंपेन स्टैंडर्ड पर निर्यात करें
description: Adobe कैंपेन स्टैंडर्ड में ऑडियंस इनसाइट्स सेगमेंट का उपयोग करना सीखें.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596317"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="05062-103">Adobe कैंपेन स्टैंडर्ड (पूर्वावलोकन) में Customer Insights सेगमेंट का उपयोग करें</span><span class="sxs-lookup"><span data-stu-id="05062-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="05062-104">ऑडियंस Insights for Dynamics 365 Customer Insights के यूज़र के रूप में, आपने प्रासंगिक ऑडियंस को लक्षित करके अपने मार्केटिंग अभियानों को अधिक कुशल बनाने के लिए सेगमेंट बनाए होंगे.</span><span class="sxs-lookup"><span data-stu-id="05062-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="05062-105">Adobe एक्सपीरियंस प्लेटफ़ॉर्म में ऑडियंस इनसाइट्स से सेगमेंट उपयोग करने और Adobe Campaign स्टैंडर्ड जैसे अनुप्रयोगों के लिए, आपको इस आलेख में बताए गए कुछ चरणों का पालन करना होगा.</span><span class="sxs-lookup"><span data-stu-id="05062-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="इस आलेख में उल्लिखित चरणों का प्रक्रिया आरेख":::

## <a name="prerequisites"></a><span data-ttu-id="05062-107">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="05062-107">Prerequisites</span></span>

-   <span data-ttu-id="05062-108">Dynamics 365 Customer Insights लाइसेंस</span><span class="sxs-lookup"><span data-stu-id="05062-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="05062-109">Adobe अभियान स्टैंडर्ड लाइसेंस</span><span class="sxs-lookup"><span data-stu-id="05062-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="05062-110">Azure ब्लॉब स्टोरेज खाता</span><span class="sxs-lookup"><span data-stu-id="05062-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="05062-111">अभियान ओवरव्यू</span><span class="sxs-lookup"><span data-stu-id="05062-111">Campaign Overview</span></span>

<span data-ttu-id="05062-112">यह समझने के लिए कि आप Adobe एक्सपीरियंस प्लेटफ़ॉर्म में ऑडियंस इनसाइट्स के सेगमेंट का उपयोग कैसे कर सकते हैं, चलिए एक काल्पनिक नमूना अभियान पर नज़र डालें.</span><span class="sxs-lookup"><span data-stu-id="05062-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="05062-113">मान लें कि आपकी कंपनी अमेरिका में आपके ग्राहकों के लिए मासिक, सदस्यता-आधारित सेवा प्रदान करती है.</span><span class="sxs-lookup"><span data-stu-id="05062-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="05062-114">आप उन ग्राहकों की पहचान करना चाहते हैं जिनकी सदस्यता का अगले आठ दिनों में नवीनीकरण किया जाना है, लेकिन अभी तक उनकी सदस्यता का नवीनीकरण नहीं हुआ है.</span><span class="sxs-lookup"><span data-stu-id="05062-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="05062-115">इन ग्राहकों को बनाए रखने के लिए, आप उन्हें Adobe अभियान स्टैंडर्ड का उपयोग करके ईमेल के माध्यम से प्रचार प्रस्ताव भेजना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="05062-116">इस उदाहरण में, हम एक बार प्रचार ईमेल अभियान चलाना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="05062-117">यह आलेख अभियान को एक से अधिक बार चलाने के उपयोग के मामले को कवर नहीं करता है.</span><span class="sxs-lookup"><span data-stu-id="05062-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="05062-118">हालांकि, ऑडियंस इनसाइट्स और Adobe कैंपेन स्टैंडर्ड को बार-बार होने वाले अभियान परिदृश्य के लिए काम करने के लिए भी कॉन्फ़िगर किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="05062-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="05062-119">अपनी लक्षित ऑडियंस को पहचानें</span><span class="sxs-lookup"><span data-stu-id="05062-119">Identify your target audience</span></span>

<span data-ttu-id="05062-120">हमारे परिदृश्य में, हम मानते हैं कि ग्राहकों के ईमेल पते ऑडियंस इनसाइट्स में उपलब्ध हैं और सेगमेंट के सदस्यों की पहचान करने के लिए उनकी प्रचार संबंधी वरीयताओं का विश्लेषण किया गया था.</span><span class="sxs-lookup"><span data-stu-id="05062-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="05062-121">[आपके द्वारा ऑडियंस इनसाइट्स में परिभाषित किया गया सेगमेंट](segments.md) को **ChurnProneCustomers** कहा जाता है और आप इन ग्राहकों को ईमेल प्रमोशन भेजने की योजना बनाते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers सेगमेंट वाले सेगमेंट पेज का स्क्रीनशॉट बनाया गया है.":::

<span data-ttu-id="05062-123">आप जो ईमेल भेजना चाहते हैं, उसमें पहला नाम, उपनाम और ग्राहक की सदस्यता समाप्ति तिथि शामिल होगी.</span><span class="sxs-lookup"><span data-stu-id="05062-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="05062-124">यह ग्राहकों को उस छूट के बारे में सूचित करता है जिसे वे अपनी सदस्यता को समाप्त होने से पहले नवीनीकृत करने पर प्राप्त करते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="05062-125">अपनी लक्षित ऑडियंस निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="05062-125">Export your target audience</span></span>

<span data-ttu-id="05062-126">पहचानी गई हमारी लक्षित ऑडियंस के साथ, हम ऑडियंस इनसाइट्स से Azure ब्लॉब स्टोरेज खाते में निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="05062-127">ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="05062-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="05062-128">**Adobe अभियान** टाइल में, **सेट अप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="05062-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe कैंपेन स्टैंडर्ड के लिए कॉन्फ़िगरेशन टाइल.":::

1. <span data-ttu-id="05062-130">इस नए निर्यात डेस्टिनेशन के लिए एक **प्रदर्शन नाम** प्रदान करें और फिर **खाता नाम**, **खाता कुंजी**, और Azure ब्लॉब स्टोरेज खाते का **कंटेनर** दर्ज करें जहां आप सेगमेंट को निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="स्टोरेज खाता कॉन्फ़िगरेशन का स्क्रीनशॉट."::: 

   - <span data-ttu-id="05062-132">Azure Blob संग्रहण खाते का नाम और खाता कुंजी का पता लगाने के बारे में अधिक जानने के लिए, [Azure पोर्टल में संग्रहण खाता सेटिंग व्यवस्थित करें](/azure/storage/common/storage-account-manage) देखें.</span><span class="sxs-lookup"><span data-stu-id="05062-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="05062-133">कंटेनर बनाने के बारे में जानने के लिए, [कंटेनर बनाएँ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) देखें.</span><span class="sxs-lookup"><span data-stu-id="05062-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="05062-134">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="05062-134">Select **Next**.</span></span>

1. <span data-ttu-id="05062-135">वह सेगमेंट चुनें, जिसे आप निर्यात करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="05062-136">इस उदाहरण में, यह **ChurnProneCustomers** है.</span><span class="sxs-lookup"><span data-stu-id="05062-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers अनुभाग चयनित के साथ अनुभाग चयन उपयोगकर्ता इंटरफ़ेस का स्क्रीनशॉट.":::

1. <span data-ttu-id="05062-138">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="05062-138">Select **Next**.</span></span>

1. <span data-ttu-id="05062-139">अब हम Adobe कैंपेन स्टैंडर्ड प्रोफ़ाइल स्कीमा में ऑडियंस इनसाइट्स सेगमेंट से **स्रोत** फ़ील्ड को **लक्ष्य** फ़ील्ड नामों पर मैप करते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe कैंपेन स्टैंडर्ड कनेक्टर के लिए फ़ील्ड मैपिंग.":::

   <span data-ttu-id="05062-141">यदि आप अधिक विशेषताएं जोड़ना चाहते हैं, तो **विशेषता जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="05062-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="05062-142">यदि फ़ील्ड के दो सिस्टम में समान नाम नहीं है, तो लक्ष्य नाम स्रोत फ़ील्ड के नाम से अलग हो सकता है, ताकि आप तब भी सेगमेंट आउटपुट को ऑडियंस इनसाइट्स से Adobe कैंपेन स्टैंडर्ड पर मैप कर सकें.</span><span class="sxs-lookup"><span data-stu-id="05062-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="05062-143">ईमेल पते का उपयोग पहचान फ़ील्ड के रूप में किया जाता है, लेकिन आप अपनी ऑडियंस इनसाइट्स ग्राहक प्रोफ़ाइल से किसी भी अन्य पहचानकर्ता का उपयोग करके Adobe कैंपेन स्टैंडर्ड का डेटा मैप करने के लिए कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="05062-144">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="05062-144">Select **Save**.</span></span>

<span data-ttu-id="05062-145">निर्यात डेस्टिनेशन को सेव करने के बाद, आप इसे **व्यवस्थापक** > **निर्यात** > **मेरे निर्यात डेस्टिनेशन** पर पाते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="निर्यात और नमूना अनुभाग की सूची के साथ स्क्रीनशॉट पर प्रकाश डाला गया.":::

<span data-ttu-id="05062-147">अब आप [मांग पर सेगमेंट निर्यात कर सकते हैं](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="05062-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="05062-148">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md).</span><span class="sxs-lookup"><span data-stu-id="05062-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="05062-149">सुनिश्चित करें कि निर्यात किए गए सेगमेंट में रिकॉर्ड की संख्या आपके Adobe कैंपेन स्टैंडर्ड लाइसेंस की अनुमत सीमा के अंदर है.</span><span class="sxs-lookup"><span data-stu-id="05062-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="05062-150">निर्यात किए गए डेटा को ऊपर कॉन्फ़िगर किए गए Azure ब्लॉब स्टोरेज कंटेनर में स्टोर किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="05062-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="05062-151">निम्न फ़ोल्डर पाथ स्वचालित रूप से आपके कंटेनर में बनाया गया है:</span><span class="sxs-lookup"><span data-stu-id="05062-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="05062-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="05062-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="05062-153">उदाहरण: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="05062-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="05062-154">Adobe कैंपेन स्टैंडर्ड कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="05062-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="05062-155">जब ऑडियंस इनसाइट्स से सेगमेंट निर्यात किया जाता है, तो इसमें पिछले चरण में निर्यात डेस्टिनेशन को परिभाषित करते समय आपके द्वारा चुने गए कॉलम होते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="05062-156">इस डेटा का उपयोग [Adobe कैंपेन स्टैंडर्ड में प्रोफ़ाइल बनाने](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) के लिए किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="05062-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="05062-157">Adobe कैंपेन स्टैंडर्ड में सेगमेंट उपयोग करने के लिए, हमें दो अतिरिक्त फ़ील्ड को शामिल करने के लिए Adobe कैंपेन स्टैंडर्ड में प्रोफ़ाइल स्कीमा का विस्तार करना होगा.</span><span class="sxs-lookup"><span data-stu-id="05062-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="05062-158">जानें कि Adobe कैंपेन स्टैंडर्ड में नए फ़ील्ड के साथ [प्रोफ़ाइल संसाधन का विस्तार](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) कैसे करें.</span><span class="sxs-lookup"><span data-stu-id="05062-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="05062-159">हमारे उदाहरण में, ये फ़ील्ड *सेगमेंट नाम और सेगमेंट दिनांक (वैकल्पिक)* हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="05062-160">हम इन फ़ील्ड का उपयोग Adobe कैंपेन स्टैंडर्ड में प्रोफ़ाइल की पहचान करने के लिए करेंगे, जिसे हम इस अभियान के लिए लक्षित करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="05062-161">यदि आप जो आयात करने जा रहे हैं, उसके अलावा Adobe कैंपेन स्टैंडर्ड में कोई अन्य रिकॉर्ड नहीं हैं, तो आप इस चरण को छोड़ सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="05062-162">Adobe कैंपेन स्टैंडर्ड में डेटा आयात करें</span><span class="sxs-lookup"><span data-stu-id="05062-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="05062-163">अब जब सब कुछ अपनी जगह पर है, हमें प्रोफ़ाइल बनाने के लिए ऑडियंस इनसाइट्स से तैयार ऑडियंस डेटा को Adobe कैंपेन स्टैंडर्ड में आयात करने की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="05062-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="05062-164">किसी कार्यप्रवाह का उपयोग करके [Adobe कैंपेन स्टैंडर्ड में प्रोफ़ाइल कैसे आयात करें](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) जानें.</span><span class="sxs-lookup"><span data-stu-id="05062-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="05062-165">नीचे दी गई छवि में कार्यप्रवाह आयात को हर 8 घंटे में रन करने के लिए कॉन्फ़िगर किया गया है और निर्यात किए गए ऑडियंस इनसाइट्स सेगमेंट (Azure ब्लॉब स्टोरेज में .csv फ़ाइल) की तलाश करता है.</span><span class="sxs-lookup"><span data-stu-id="05062-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="05062-166">कार्यप्रवाह एक निर्दिष्ट कॉलम क्रम में .csv फ़ाइल की सामग्री निकालता है.</span><span class="sxs-lookup"><span data-stu-id="05062-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="05062-167">इस कार्यप्रवाह का निर्माण बुनियादी त्रुटि से निपटने के लिए किया गया है और यह सुनिश्चित करता है कि Adobe कैंपेन स्टैंडर्ड में डेटा हाइड्रेट करने से पहले प्रत्येक रिकॉर्ड का एक ईमेल पता हो.</span><span class="sxs-lookup"><span data-stu-id="05062-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="05062-168">कार्य प्रवाह भी ACS प्रोफ़ाइल डेटा में अपसर्टिंग से पहले फ़ाइल नाम से सेगमेंट नाम निकालता है.</span><span class="sxs-lookup"><span data-stu-id="05062-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe कैंपेन स्टैंडर्ड उपयोगकर्ता इंटरफ़ेस में एक आयात कार्यप्रवाह का स्क्रीनशॉट.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="05062-170">Adobe कैंपेन स्टैंडर्ड में ऑडियंस को पुनः प्राप्त करें</span><span class="sxs-lookup"><span data-stu-id="05062-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="05062-171">एक बार जब डेटा को Adobe कैंपेन स्टैंडर्ड में आयात कर दिया जाता है, तो आप हमारे नमूना अभियान के लिए पहचाने जाने वाले प्रोफ़ाइल का चयन करने के लिए *सेगमेंट नाम* और *सेगमेंट दिनांक* के आधार पर [एक कार्य प्रवाह बना सकते हैं](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) और ग्राहकों के लिए [क्वेरी](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) करते हैं.</span><span class="sxs-lookup"><span data-stu-id="05062-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="05062-172">Adobe कैंपेन स्टैंडर्ड का उपयोग करके ईमेल बनाएं और भेजें</span><span class="sxs-lookup"><span data-stu-id="05062-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="05062-173">ईमेल सामग्री बनाएं और फिर अपना ईमेल [परीक्षण करें और भेजें](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).</span><span class="sxs-lookup"><span data-stu-id="05062-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe कैंपेन स्टैंडर्ड से नवीकरण प्रस्ताव के साथ नमूना ईमेल.":::