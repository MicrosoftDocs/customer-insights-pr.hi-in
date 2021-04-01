---
title: उत्पाद सुझाव पूर्वानुमान का सैंपल गाइड
description: आउट ऑफ़ द बॉक्स उत्पाद सुझाव पूर्वानुमान मॉडल आज़माने के लिए इस सैंपल गाइड का उपयोग करें.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595275"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="9a5a7-103">उत्पाद सुझाव का पूर्वानुमान (पूर्वावलोकन) सैंपल गाइड</span><span class="sxs-lookup"><span data-stu-id="9a5a7-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="9a5a7-104">हम आपको नीचे दिए गए सैंपल डेटा का उपयोग करके उत्पाद सुझाव के पूर्वानुमान का पूरा उदाहरण समझाएंगे.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="9a5a7-105">परिदृश्य</span><span class="sxs-lookup"><span data-stu-id="9a5a7-105">Scenario</span></span>

<span data-ttu-id="9a5a7-106">Contoso एक कंपनी है जो उच्च गुणवत्ता वाली कॉफी और कॉफी मशीन का उत्पादन करती है, जिसे वे अपने Contoso कॉफी वेबसाइट के जरिए बेचते हैं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="9a5a7-107">उनका लक्ष्य यह समझना है कि उन्हें बार-बार आने वाले अपने ग्राहकों को कौन से उत्पाद का सुझाव देना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="9a5a7-108">यह जानना कि ग्राहक ज़्यादा **खरीद की संभावना** रखते हैं, विशिष्ट वस्तुओं पर ध्यान केंद्रित करके मार्केटिंग प्रयासों को बचाने में उनकी मदद कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9a5a7-109">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="9a5a7-109">Prerequisites</span></span>

- <span data-ttu-id="9a5a7-110">Customer Insights में कम से कम [योगदानकर्ता की अनुमतियां](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9a5a7-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="9a5a7-111">हम सिफारिश करते हैं कि आप [नए परिवेश में](manage-environments.md) निम्नलिखित चरणों को लागू करें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="9a5a7-112">कार्य 1 - इन्जेस्ट डेटा</span><span class="sxs-lookup"><span data-stu-id="9a5a7-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="9a5a7-113">विशेष रूप से आलेख [डेटा इन्जेस्चन के बारे में](data-sources.md) और [पॉवर क्वेरी कनेक्टर का उपयोग करके डेटा स्रोतों को आयात करना](connect-power-query.md) की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="9a5a7-114">निम्नलिखित जानकारी मानती है कि आप सामान्य रूप से इन्जेस्ट होते डेटा से परिचित हैं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="9a5a7-115">ईकॉमर्स प्लेटफॉर्म से ग्राहक डेटा अंतर्ग्रहण करें</span><span class="sxs-lookup"><span data-stu-id="9a5a7-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="9a5a7-116">**ईकॉमर्स** नामक डेटा स्रोत बनाएं, आयात विकल्प चुनें, और **टेक्स्ट/CSV** कनेक्टर चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9a5a7-117">ईकामर्स संपर्कों के लिए URL दर्ज करें https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="9a5a7-118">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9a5a7-119">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="9a5a7-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9a5a7-120">**जन्म की तारीख** : दिनांक</span><span class="sxs-lookup"><span data-stu-id="9a5a7-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9a5a7-121">**CreatedOn**: दिनांक/समय/क्षेत्र</span><span class="sxs-lookup"><span data-stu-id="9a5a7-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="जन्मतिथि को तारीख में बदलना.":::

5. <span data-ttu-id="9a5a7-123">दाईं ओर के फ़लक पर 'नाम' फ़ील्ड में, अपने डेटा स्रोत का नाम **क्वेरी** से **eCommerceContacts** में बदलें</span><span class="sxs-lookup"><span data-stu-id="9a5a7-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="9a5a7-124">डेटा स्रोत **सहेजें**.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="9a5a7-125">ऑनलाइन खरीद डेटा</span><span class="sxs-lookup"><span data-stu-id="9a5a7-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="9a5a7-126">उसी **ईकॉमर्स** डेटा स्रोत में एक और डेटा सेट जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="9a5a7-127">**टेक्स्ट/CSV** कनेक्टर को फिर से चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="9a5a7-128">**ऑनलाइन खरीद** डेटा https://aka.ms/ciadclassonline के लिए URL दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="9a5a7-129">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9a5a7-130">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="9a5a7-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9a5a7-131">**PurchasedOn**: दिनांक/समय</span><span class="sxs-lookup"><span data-stu-id="9a5a7-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="9a5a7-132">**TotalPrice**: मुद्रा</span><span class="sxs-lookup"><span data-stu-id="9a5a7-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="9a5a7-133">साइड फ़लक पर **नाम** फ़ील्ड में, अपने डेटा स्रोत का नाम **क्वेरी** से बदल कर **eCommercePurchases** करें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="9a5a7-134">डेटा स्रोत सहेजें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="9a5a7-135">लॉयल्टी स्कीमा से ग्राहक डेटा अंतर्ग्रहण करें</span><span class="sxs-lookup"><span data-stu-id="9a5a7-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="9a5a7-136">**LoyaltyScheme** नामित एक डेटा स्रोत बनाएँ, आयात विकल्प चुनें, और **Text/CSV** कनेक्टर चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9a5a7-137">ईकामर्स संपर्कों के लिए URL दर्ज करें https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="9a5a7-138">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9a5a7-139">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="9a5a7-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9a5a7-140">**जन्म की तारीख** : दिनांक</span><span class="sxs-lookup"><span data-stu-id="9a5a7-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9a5a7-141">**RewardsPoints** डिफ़ॉल्ट पूर्णांक मान</span><span class="sxs-lookup"><span data-stu-id="9a5a7-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="9a5a7-142">**CreatedOn**: बनाने का दिनांक/समय</span><span class="sxs-lookup"><span data-stu-id="9a5a7-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="9a5a7-143">दाईं ओर के फ़लक पर **नाम** फ़ील्ड में, अपना डेटा स्रोत का नाम **क्वेरी** से **loyCustomers** में बदलें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="9a5a7-144">डेटा स्रोत सहेजें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="9a5a7-145">कार्य 2 - डेटा एकीकरण</span><span class="sxs-lookup"><span data-stu-id="9a5a7-145">Task 2 - Data unification</span></span>

<span data-ttu-id="9a5a7-146">डेटा इन्जेस्ट करने के बाद अब हम एकीकृत ग्राहक प्रोफ़ाइल बनाने के लिए **मैप, मिलान, मर्ज** प्रक्रिया शुरू करते हैं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="9a5a7-147">अधिक जानकारी के लिए, [डेटा एकीकरण](data-unification.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="9a5a7-148">मैप</span><span class="sxs-lookup"><span data-stu-id="9a5a7-148">Map</span></span>

1. <span data-ttu-id="9a5a7-149">डेटा को अंतर्ग्रहण करने के बाद, संपर्कों को ई-कॉमर्स और लॉयल्टी डेटा से सामान्य डेटा प्रकारों में मैप करें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="9a5a7-150">**डेटा** > **एकीकृत** > **मैप** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="9a5a7-151">उन निकायों को चुनें जो ग्राहक प्रोफ़ाइल – **eCommerceContacts** और **loyCustomers** का प्रतिनिधित्व करते हैं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![ईकॉमर्स और लॉयल्टी डेटास्रोत एकीकृत करें.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="9a5a7-153">**eCommerceContacts** के लिए प्राथमिक कुंजी के रूप में **ContactId** और **loyCustomers** के लिए प्राथमिक कुंजी के रूप में **LoyaltyID** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![LoyaltyId को प्राथमिक कुंजी के रूप में एकीकृत करें.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="9a5a7-155">मिलान</span><span class="sxs-lookup"><span data-stu-id="9a5a7-155">Match</span></span>

1. <span data-ttu-id="9a5a7-156">**मिलान** टैब पर जाएँ और **क्रम सेट करें** टैब चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="9a5a7-157">**प्राथमिक** ड्रॉप-डाउन सूची में, प्राथमिक स्रोत के रूप में **eCommerceContacts : ईकॉमर्स** चुनें और सभी रिकॉर्ड शामिल करें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="9a5a7-158">**निकाय 2** ड्रॉप-डाउन सूची में, **loyCustomers : LoyaltyScheme** चुनें और सभी रिकॉर्ड शामिल करें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![ईकॉमर्स और लॉयल्टी का एकीकरण में मिलान करें.](media/unify-match-order.png)

4. <span data-ttu-id="9a5a7-160">**एक नया नियम बनाएं** चयन करें</span><span class="sxs-lookup"><span data-stu-id="9a5a7-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="9a5a7-161">FullName का उपयोग करके अपनी पहली शर्त जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="9a5a7-162">eCommerceContacts के लिए ड्रॉप-डाउन में **FullName** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="9a5a7-163">loyCustomers के लिए ड्रॉप-डाउन में **FullName** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="9a5a7-164">**सामान्यीकृत** ड्रॉप डाउन का चयन करें और **प्रकार (फोन, नाम, पता, ...)** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="9a5a7-165">**सटिकता स्तर** सेट करें: **बेसिक** और **मूल्य**: **उच्च**.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="9a5a7-166">नए नियम के लिए नाम **FullName, ईमेल** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="9a5a7-167">**पता जोड़ें** का चयन करके ईमेल पते के लिए दूसरी शर्त जोड़ें</span><span class="sxs-lookup"><span data-stu-id="9a5a7-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="9a5a7-168">निकाय eCommerceContacts के लिए, ड्रॉप-डाउन में **ईमेल** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="9a5a7-169">निकाय loyCustomers के लिए, ड्रॉप-डाउन में **ईमेल** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="9a5a7-170">सामान्यीकृत खाली छोड़ दें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="9a5a7-171">**सटिकता स्तर** सेट करें: **बेसिक** और **मूल्य**: **उच्च**.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![नाम और ईमेल के लिए मिलान के नियम को एकीकृत करें.](media/unify-match-rule.png)

7. <span data-ttu-id="9a5a7-173">**सहेजें** और **रन करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="9a5a7-174">मर्ज करें</span><span class="sxs-lookup"><span data-stu-id="9a5a7-174">Merge</span></span>

1. <span data-ttu-id="9a5a7-175">**मर्ज** टैब पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="9a5a7-176">**ContactId** पर **loyCustomers** निकाय के लिए, इसे इन्जेस्ट की गई दूसरी ID से अलग करने के लिए प्रदर्शन नाम को **ContactIdLOYALTY** में बदलें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![नाम को contactid से loyalty id में बदलें.](media/unify-merge-contactid.png)

1. <span data-ttu-id="9a5a7-178">मर्ज प्रक्रिया प्रारंभ करने के लिए **सहेजें** और **रन करें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="9a5a7-179">कार्य 3 - उत्पाद सुझाव पूर्वानुमान कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="9a5a7-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="9a5a7-180">एकीकृत ग्राहक प्रोफ़ाइल लागू होने के साथ, हम अब सदस्यता चर्न पूर्वानुमान चला सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="9a5a7-181">**इंटेलिजेंस** > **पूर्वानुमान** पर जाएं, **उत्पाद सुझाव** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="9a5a7-182">**आरंभ करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-182">Select **Get started**.</span></span>

1. <span data-ttu-id="9a5a7-183">मॉडल का नाम **OOB उत्पाद सुझाव मॉडल पूर्वानुमान** करें और आउटपुट निकाय **OOBProductRecommendationModelPrediction** करें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="9a5a7-184">मॉडल के लिए तीन शर्तों को परिभाषित करें:</span><span class="sxs-lookup"><span data-stu-id="9a5a7-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="9a5a7-185">**उत्पादों की संख्या**: इस मान को **5** पर सेट करें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="9a5a7-186">यह सेटिंग परिभाषित करती है कि आप अपने ग्राहकों को कितने उत्पादों का सुझाव देना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="9a5a7-187">**सुझाए गए उत्पाद ग्राहकों ने हाल ही में खरीदे हैं?**: यह दर्शाने के लिए **हां** चुनें कि आप उन उत्पादों को सुझाव में शामिल करना चाहते हैं जिन्हें आपके ग्राहकों ने पहले खरीदा है.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="9a5a7-188">**पीछे की विंडो देखें:** कम से कम **365 दिन** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="9a5a7-189">यह सेटिंग परिभाषित करती है कि ग्राहक की गतिविधि पर मॉडल कितनी पीछे तक देखेगा, ताकि उनके सुझाव के इनपुट के रूप में उपयोग किया जा सके.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="उत्पाद सुझाव मॉडल के लिए मॉडल प्राथमिकताएं.":::

1. <span data-ttu-id="9a5a7-191">**आवश्यक डेटा** चुनें और खरीदारी इतिहास के लिए **डेटा जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="9a5a7-192">**eCommercePurchases: ईकॉमर्स** निकाय जोड़ें और ईकॉमर्स से संबंधित फ़ील्ड से वे फ़ील्ड मैप करें जो मॉडल द्वारा आवश्यक हैं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="9a5a7-193">**eCommerceContacts: eCommerce** के साथ **eCommercePurchases: eCommerce** निकाय को जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![ईकॉमर्स निकायों को जोड़ें.](media/model-purchase-join.png)

1. <span data-ttu-id="9a5a7-195">मॉडल शेड्यूल सेट करने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="9a5a7-196">जब नए डेटा को इन्जेस्ट किया जाता है तो नए पैटर्न सीखने के लिए मॉडल को नियमित रूप से प्रशिक्षित करना होता है.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="9a5a7-197">इस उदाहरण के लिए, **मासिक** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="9a5a7-198">सभी विवरणों की समीक्षा करने के बाद, **सहेजें और चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="9a5a7-199">कार्य 4 - मॉडल परिणामों और स्पष्टीकरण की समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="9a5a7-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="9a5a7-200">मॉडल को डेटा के प्रशिक्षण और स्कोरिंग को पूरा करने दें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="9a5a7-201">अब आप उत्पाद सुझाव मॉडल स्पष्टीकरण की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="9a5a7-202">अधिक जानकारी के लिए, [पूर्वधारणा स्थिति और परिणामों की समीक्षा करें](predict-subscription-churn.md#review-a-prediction-status-and-results) देखें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="9a5a7-203">कार्य 5 - ज़्यादा खरीदे गए उत्पादों का अनुभाग बनाएं</span><span class="sxs-lookup"><span data-stu-id="9a5a7-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="9a5a7-204">उत्पादन मॉडल को चलाने से एक नया निकाय बनता है जिसे आप **डेटा** > **निकायों** में देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="9a5a7-205">आप मॉडल द्वारा बनाए गए निकाय के आधार पर एक नया सेगमेंट बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="9a5a7-206">**सेगमेंट** अनुभाग पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-206">Go to **Segments**.</span></span> <span data-ttu-id="9a5a7-207">**नया** चुनें और **से बनाएं** >  **इंटेलिजेंस** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![मॉडल आउटपुट के साथ सेगमेंट बनाना.](media/segment-intelligence.png)

1. <span data-ttu-id="9a5a7-209">**OOBProductRecommendationModelPrediction** समाप्ति बिंदु चुनें और अनुभाग को परिभाषित करें:</span><span class="sxs-lookup"><span data-stu-id="9a5a7-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="9a5a7-210">फ़ील्ड: ProductID</span><span class="sxs-lookup"><span data-stu-id="9a5a7-210">Field: ProductID</span></span>
   - <span data-ttu-id="9a5a7-211">ऑपरेटर: मान</span><span class="sxs-lookup"><span data-stu-id="9a5a7-211">Operator: Value</span></span>
   - <span data-ttu-id="9a5a7-212">मान: शीर्ष तीन उत्पाद ID का चयन करें</span><span class="sxs-lookup"><span data-stu-id="9a5a7-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="मॉडल के परिणामों से अनुभाग बनाएं.":::

<span data-ttu-id="9a5a7-214">अब आपके पास एक अनुभाग है जो गतिशील रूप से अपडेट किया गया है जो उन ग्राहकों की पहचान करता है जो तीन सबसे ज़्यादा सुझाए गए उत्पादों को खरीदने के लिए ज़्यादा इच्छुक हैं</span><span class="sxs-lookup"><span data-stu-id="9a5a7-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="9a5a7-215">अधिक जानकारी के लिए, [अनुभाग बनाएँ और प्रबंधित करें](segments.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="9a5a7-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]