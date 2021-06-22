---
title: ग्राहक आजीवन पूर्वानुमान नमूना गाइड
description: ग्राहक के आजीवन मान पूर्वानुमान मॉडल को आज़माने के लिए इस नमूना मार्गदर्शिका का उपयोग करें.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129947"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="85769-103">ग्राहक आजीवन मान (CLV) भविष्यवाणी नमूना गाइड</span><span class="sxs-lookup"><span data-stu-id="85769-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="85769-104">यह मार्गदर्शिका आपको नमूना डेटा का उपयोग करके Customer Insights में ग्राहक आजीवन मूल्य (CLV) पूर्वानुमान का एंड-टू-एंड उदाहरण तक ले जाएगी.</span><span class="sxs-lookup"><span data-stu-id="85769-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="85769-105">परिदृश्य</span><span class="sxs-lookup"><span data-stu-id="85769-105">Scenario</span></span>

<span data-ttu-id="85769-106">Contoso एक ऐसी कंपनी है जो उच्च गुणवत्ता वाली कॉफी और कॉफी मशीन बनाती है.</span><span class="sxs-lookup"><span data-stu-id="85769-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="85769-107">वे अपनी Contoso कॉफी वेबसाइट के माध्यम से उत्पाद बेचते हैं.</span><span class="sxs-lookup"><span data-stu-id="85769-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="85769-108">कंपनी उस मान (राजस्व) को समझना चाहती है जो उनके ग्राहक अगले 12 महीनों में उत्पन्न कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="85769-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="85769-109">अगले 12 महीनों में अपने ग्राहकों के अपेक्षित मूल्य को जानने से उन्हें उच्च मान वाले ग्राहकों पर अपने मार्केटिंग प्रयासों को चलाने में मदद मिलेगी.</span><span class="sxs-lookup"><span data-stu-id="85769-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85769-110">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="85769-110">Prerequisites</span></span>

- <span data-ttu-id="85769-111">ऑडियंस इनसाइट में कम से कम [योगदानकर्ता अनुमतियां](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="85769-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="85769-112">हम सिफारिश करते हैं कि आप [नए परिवेश में](manage-environments.md) निम्नलिखित चरणों को लागू करें.</span><span class="sxs-lookup"><span data-stu-id="85769-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="85769-113">कार्य 1 - इन्जेस्ट डेटा</span><span class="sxs-lookup"><span data-stu-id="85769-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="85769-114">[डेटा अंतर्ग्रहण संबंधित](data-sources.md) आलेखों की समीक्षा और [Power Query कनेक्टर्स का उपयोग करके डेटा स्रोत आयात करना](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="85769-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="85769-115">निम्नलिखित जानकारी मानती है कि आप सामान्य रूप से इन्जेस्ट होते डेटा से परिचित हैं.</span><span class="sxs-lookup"><span data-stu-id="85769-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="85769-116">ईकॉमर्स प्लेटफॉर्म से ग्राहक डेटा अंतर्ग्रहण करें</span><span class="sxs-lookup"><span data-stu-id="85769-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="85769-117">**eCommerce** नाम का एक डेटा स्रोत बनाएं, आयात विकल्प चुनें और **टेक्स्ट/CSV** कनेक्टर चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="85769-118">eCommerce संपर्क के लिए URL दर्ज करें [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="85769-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="85769-119">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="85769-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="85769-120">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="85769-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="85769-121">**जन्म की तारीख** : दिनांक</span><span class="sxs-lookup"><span data-stu-id="85769-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="85769-122">**CreatedOn**: दिनांक/समय/क्षेत्र</span><span class="sxs-lookup"><span data-stu-id="85769-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="जन्मतिथि को तारीख में बदलना.":::

1. <span data-ttu-id="85769-124">दाईं ओर के फ़लक पर 'नाम' फ़ील्ड में, अपने डेटा स्रोत का नाम **क्वेरी** से **eCommerceContacts** में बदलें</span><span class="sxs-lookup"><span data-stu-id="85769-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="85769-125">डेटा स्रोत **सहेजें**.</span><span class="sxs-lookup"><span data-stu-id="85769-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="85769-126">ऑनलाइन खरीद डेटा</span><span class="sxs-lookup"><span data-stu-id="85769-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="85769-127">उसी **ईकॉमर्स** डेटा स्रोत में एक और डेटा सेट जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="85769-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="85769-128">**टेक्स्ट/CSV** कनेक्टर को फिर से चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="85769-129">**ऑनलाइन खरीद** डेटा https://aka.ms/ciadclassonline के लिए URL दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="85769-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="85769-130">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="85769-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="85769-131">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="85769-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="85769-132">**PurchasedOn**: दिनांक/समय</span><span class="sxs-lookup"><span data-stu-id="85769-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="85769-133">**TotalPrice**: मुद्रा</span><span class="sxs-lookup"><span data-stu-id="85769-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="85769-134">साइड फ़लक पर **नाम** फ़ील्ड में, अपने डेटा स्रोत का नाम **क्वेरी** से बदल कर **eCommercePurchases** करें.</span><span class="sxs-lookup"><span data-stu-id="85769-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="85769-135">डेटा स्रोत **सहेजें**.</span><span class="sxs-lookup"><span data-stu-id="85769-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="85769-136">लॉयल्टी स्कीमा से ग्राहक डेटा अंतर्ग्रहण करें</span><span class="sxs-lookup"><span data-stu-id="85769-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="85769-137">**LoyaltyScheme** नामित एक डेटा स्रोत बनाएँ, आयात विकल्प चुनें, और **Text/CSV** कनेक्टर चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="85769-138">ईकामर्स संपर्कों के लिए URL दर्ज करें https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="85769-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="85769-139">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="85769-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="85769-140">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="85769-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="85769-141">**जन्म की तारीख** : दिनांक</span><span class="sxs-lookup"><span data-stu-id="85769-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="85769-142">**RewardsPoints** डिफ़ॉल्ट पूर्णांक मान</span><span class="sxs-lookup"><span data-stu-id="85769-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="85769-143">**CreatedOn**: बनाने का दिनांक/समय</span><span class="sxs-lookup"><span data-stu-id="85769-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="85769-144">दाईं ओर के फ़लक पर **नाम** फ़ील्ड में, अपना डेटा स्रोत का नाम **क्वेरी** से **loyCustomers** में बदलें.</span><span class="sxs-lookup"><span data-stu-id="85769-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="85769-145">डेटा स्रोत **सहेजें**.</span><span class="sxs-lookup"><span data-stu-id="85769-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="85769-146">वेबसाइट समीक्षाओं से ग्राहक डेटा अंतर्ग्रहण करें</span><span class="sxs-lookup"><span data-stu-id="85769-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="85769-147">**वेबसाइट** नामित एक डेटा स्रोत बनाएँ, आयात विकल्प चुनें, और **Text/CSV** कनेक्टर चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="85769-148">ईकामर्स संपर्कों के लिए URL दर्ज करें https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="85769-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="85769-149">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="85769-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="85769-150">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="85769-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="85769-151">**ReviewRating**: दशमलव संख्या</span><span class="sxs-lookup"><span data-stu-id="85769-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="85769-152">**ReviewDate**: दिनांक</span><span class="sxs-lookup"><span data-stu-id="85769-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="85769-153">दाएं फलक पर 'नाम' फ़ील्ड में, अपने डेटा स्रोत का नाम **समीक्षा**  से बदल कर **क्वेरी** करें.</span><span class="sxs-lookup"><span data-stu-id="85769-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="85769-154">डेटा स्रोत **सहेजें**.</span><span class="sxs-lookup"><span data-stu-id="85769-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="85769-155">कार्य 2 - डेटा एकीकरण</span><span class="sxs-lookup"><span data-stu-id="85769-155">Task 2 - Data unification</span></span>

<span data-ttu-id="85769-156">डेटा अंतर्ग्रहण करने के बाद, अब हम एक एकीकृत ग्राहक प्रोफ़ाइल बनाने के लिए डेटा एकीकरण प्रक्रिया शुरू करते हैं.</span><span class="sxs-lookup"><span data-stu-id="85769-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="85769-157">अधिक जानकारी के लिए, [डेटा एकीकरण](data-unification.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="85769-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="85769-158">मैप</span><span class="sxs-lookup"><span data-stu-id="85769-158">Map</span></span>

1. <span data-ttu-id="85769-159">डेटा को अंतर्ग्रहण करने के बाद, संपर्कों को ई-कॉमर्स और लॉयल्टी डेटा से सामान्य डेटा प्रकारों में मैप करें.</span><span class="sxs-lookup"><span data-stu-id="85769-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="85769-160">**डेटा** > **एकीकृत** > **मैप** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="85769-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="85769-161">उन निकायों को चुनें जो ग्राहक प्रोफ़ाइल – **eCommerceContacts** और **loyCustomers** का प्रतिनिधित्व करते हैं.</span><span class="sxs-lookup"><span data-stu-id="85769-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="85769-162">फिर, **लागू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-162">Then, select **Apply**.</span></span>

   ![ईकॉमर्स और लॉयल्टी डेटास्रोत एकीकृत करें.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="85769-164">**eCommerceContacts** के लिए प्राथमिक कुंजी के रूप में **ContactId** और **loyCustomers** के लिए प्राथमिक कुंजी के रूप में **LoyaltyID** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![LoyaltyId को प्राथमिक कुंजी के रूप में एकीकृत करें.](media/unify-loyaltyid.png)

1. <span data-ttu-id="85769-166">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="85769-167">मिलान</span><span class="sxs-lookup"><span data-stu-id="85769-167">Match</span></span>

1. <span data-ttu-id="85769-168">**मिलान** टैब पर जाएँ और **क्रम सेट करें** टैब चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="85769-169">**प्राथमिक** ड्रॉप-डाउन सूची में, प्राथमिक स्रोत के रूप में **eCommerceContacts : ईकॉमर्स** चुनें और सभी रिकॉर्ड शामिल करें.</span><span class="sxs-lookup"><span data-stu-id="85769-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="85769-170">**निकाय 2** ड्रॉप-डाउन सूची में, **loyCustomers : LoyaltyScheme** चुनें और सभी रिकॉर्ड शामिल करें.</span><span class="sxs-lookup"><span data-stu-id="85769-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![ईकॉमर्स और लॉयल्टी का एकीकरण में मिलान करें.](media/unify-match-order.png)

1. <span data-ttu-id="85769-172">**नियम जोड़ें** चुनें</span><span class="sxs-lookup"><span data-stu-id="85769-172">Select **Add rule**</span></span>

1. <span data-ttu-id="85769-173">FullName का उपयोग करके अपनी पहली शर्त जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="85769-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="85769-174">eCommerceContacts के लिए ड्रॉप-डाउन में **FullName** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="85769-175">loyCustomers के लिए ड्रॉप-डाउन में **FullName** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="85769-176">**सामान्यीकृत** ड्रॉप-डाउन का चयन करें और **प्रकार (फोन, नाम, पता, ...)** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="85769-177">**सटिकता स्तर** सेट करें: **बेसिक** और **मूल्य**: **उच्च**.</span><span class="sxs-lookup"><span data-stu-id="85769-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="85769-178">नए नियम के लिए नाम **FullName, ईमेल** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="85769-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="85769-179">**पता जोड़ें** का चयन करके ईमेल पते के लिए दूसरी शर्त जोड़ें</span><span class="sxs-lookup"><span data-stu-id="85769-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="85769-180">निकाय eCommerceContacts के लिए, ड्रॉप-डाउन में **ईमेल** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="85769-181">निकाय loyCustomers के लिए, ड्रॉप-डाउन में **ईमेल** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="85769-182">सामान्यीकृत खाली छोड़ दें.</span><span class="sxs-lookup"><span data-stu-id="85769-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="85769-183">**सटिकता स्तर** सेट करें: **बेसिक** और **मूल्य**: **उच्च**.</span><span class="sxs-lookup"><span data-stu-id="85769-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![नाम और ईमेल के लिए मिलान के नियम को एकीकृत करें.](media/unify-match-rule.png)

1. <span data-ttu-id="85769-185">**पूर्ण** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="85769-185">Select **Done**.</span></span>

1. <span data-ttu-id="85769-186">**सहेजें** और **रन करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="85769-187">मर्ज करें</span><span class="sxs-lookup"><span data-stu-id="85769-187">Merge</span></span>

1. <span data-ttu-id="85769-188">**मर्ज** टैब पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="85769-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="85769-189">**ContactId** पर **loyCustomers** निकाय के लिए, इसे इन्जेस्ट की गई दूसरी ID से अलग करने के लिए प्रदर्शन नाम को **ContactIdLOYALTY** में बदलें.</span><span class="sxs-lookup"><span data-stu-id="85769-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![नाम को contactid से loyalty id में बदलें.](media/unify-merge-contactid.png)

1. <span data-ttu-id="85769-191">**सहेजें** और **मर्ज और डाउनस्ट्रीम प्रक्रियाएं चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="85769-192">टास्क 3 - ग्राहक के जीवनकाल मान पूर्वानुमान को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="85769-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="85769-193">एकीकृत ग्राहक प्रोफाइल के साथ, अब हम ग्राहक जीवनकाल मान पूर्वानुमान चला सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="85769-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="85769-194">विस्तृत चरणों के लिए, [ग्राहक आजीवन मूल्य पूर्वानुमान (पूर्वावलोकन)](predict-customer-lifetime-value.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="85769-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="85769-195">**इंटेलिजेंस**  > **पूर्वानुमान** पर जाएं और **ग्राहक जीवनकाल मान मॉडल** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="85769-196">साइड फलक में जानकारी देखें और **आरंभ करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="85769-197">मॉडल को **OOB eCommerce CLV पूर्वानुमान** और आउटपुट निकाय को **OOBeCommerceCLVPrediction** नाम दें.</span><span class="sxs-lookup"><span data-stu-id="85769-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="85769-198">CLV मॉडल के लिए मॉडल प्राथमिकताएं निर्धारित करें:</span><span class="sxs-lookup"><span data-stu-id="85769-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="85769-199">**पूर्वानुमान समयावधि**: **12 महीने या 1 साल**.</span><span class="sxs-lookup"><span data-stu-id="85769-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="85769-200">यह सेटिंग निर्धारित करती है कि भविष्य में ग्राहक के जीवनकाल के मान का कितना अनुमान लगाया जाए.</span><span class="sxs-lookup"><span data-stu-id="85769-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="85769-201">**सक्रिय ग्राहक**: निर्दिष्ट करें कि आपके व्यवसाय के लिए सक्रिय ग्राहकों का क्या अर्थ है.</span><span class="sxs-lookup"><span data-stu-id="85769-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="85769-202">ऐतिहासिक समय सीमा निर्धारित करें जिसमें ग्राहक के पास सक्रिय माने जाने के लिए कम से कम एक लेन-देन होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="85769-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="85769-203">मॉडल केवल सक्रिय ग्राहकों के लिए CLV की भविष्यवाणी करेगा.</span><span class="sxs-lookup"><span data-stu-id="85769-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="85769-204">मॉडल को ऐतिहासिक लेनदेन डेटा के आधार पर समय अवधि की गणना करने या एक विशिष्ट समय सीमा प्रदान करने के बीच चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="85769-205">इस नमूना मार्गदर्शिका में, हम **मॉडल को खरीद अंतराल की गणना करने देते हैं**, जो कि डिफ़ॉल्ट विकल्प है.</span><span class="sxs-lookup"><span data-stu-id="85769-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="85769-206">**उच्च मान वाले ग्राहक**: उच्च मान वाले ग्राहकों को शीर्ष-भुगतानकर्ता ग्राहकों के प्रतिशत के रूप में निर्दिष्ट करें.</span><span class="sxs-lookup"><span data-stu-id="85769-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="85769-207">मॉडल इस इनपुट का उपयोग ऐसे परिणाम प्रदान करने के लिए करता है जो उच्च मान वाले ग्राहकों की आपकी व्यावसायिक परिभाषा के अनुकूल हों.</span><span class="sxs-lookup"><span data-stu-id="85769-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="85769-208">आप मॉडल को उच्च मान वाले ग्राहकों को परिभाषित करने देना चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="85769-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="85769-209">यह एक अनुभवजन्य नियम का उपयोग करता है जो प्रतिशतक प्राप्त करता है.</span><span class="sxs-lookup"><span data-stu-id="85769-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="85769-210">आप उच्च मान वाले ग्राहकों को भविष्य के शीर्ष भुगतानकर्ता ग्राहकों के प्रतिशत के रूप में भी निर्धारित कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="85769-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="85769-211">इस नमूना मार्गदर्शिका में, हम मैन्युअल रूप से उच्च मान वाले ग्राहकों को **सक्रिय भुगतान करने वाले ग्राहकों के शीर्ष 30%** के रूप में निर्धारित करते हैं और **अगला** चुनते हैं.</span><span class="sxs-lookup"><span data-stu-id="85769-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV मॉडल के लिए निर्देशित अनुभव में वरीयताएं चरण.":::

1. <span data-ttu-id="85769-213">**आवश्यक डेटा** चरण में, लेन-देन इतिहास डेटा प्रदान करने के लिए **डेटा जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="85769-214">**eCommercePurchases: eCommerce** निकाय जोड़ें और मॉडल द्वारा अपेक्षित विशेषताओं को मैप करें:</span><span class="sxs-lookup"><span data-stu-id="85769-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="85769-215">लेन देन ID: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="85769-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="85769-216">लेन देन तिथिः eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="85769-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="85769-217">लेन देन राशिः eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="85769-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="85769-218">उत्पाद आईडी: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="85769-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="85769-219">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-219">Select **Next**.</span></span>

1. <span data-ttu-id="85769-220">**eCommercePurchases: eCommerce** निकाय और **eCommerceContacts: eCommerce** के बीच संबंध स्थापित करें.</span><span class="sxs-lookup"><span data-stu-id="85769-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="85769-221">**अतिरिक्त डेटा (वैकल्पिक)** चरण आपको अधिक ग्राहक गतिविधि डेटा जोड़ने की अनुमति देता है.</span><span class="sxs-lookup"><span data-stu-id="85769-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="85769-222">यह डेटा आपके व्यवसाय के साथ ग्राहक सहभागिता के लिए अधिक इनसाइट्स प्राप्त करने में मदद कर सकता है, जो CLV में योगदान कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="85769-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="85769-223">वेब लॉग्स, ग्राहक सेवा लॉग्स, या पुरस्कार कार्यक्रम इतिहास जैसी प्रमुख ग्राहक सहभागिता जोड़ने से पूर्वानुमानों की सटीकता में सुधार हो सकता है.</span><span class="sxs-lookup"><span data-stu-id="85769-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="85769-224">अधिक ग्राहक गतिविधि डेटा शामिल करने के लिए **डेटा जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="85769-225">ग्राहक गतिविधि निकाय जोड़ें और उसके फ़ील्ड नामों को मॉडल के लिए आवश्यक संबंधित फ़ील्ड में मैप करें:</span><span class="sxs-lookup"><span data-stu-id="85769-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="85769-226">ग्राहक गतिविधि निकाय: समीक्षा: वेबसाइट</span><span class="sxs-lookup"><span data-stu-id="85769-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="85769-227">प्राथमिक कुंजी: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="85769-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="85769-228">टाइमस्टैम्पः Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="85769-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="85769-229">इवेंट (गतिविधि का नाम): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="85769-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="85769-230">विवरण (राशि या मान): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="85769-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="85769-231">**अगला** चुनें और गतिविधि और लेन-देन डेटा और ग्राहक डेटा के बीच संबंध कॉन्फ़िगर करें:</span><span class="sxs-lookup"><span data-stu-id="85769-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="85769-232">गतिविधि प्रकार: मौजूदा चुनें</span><span class="sxs-lookup"><span data-stu-id="85769-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="85769-233">गतिविधि लेबल: समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="85769-233">Activity label: Review</span></span>
   - <span data-ttu-id="85769-234">संबंधित लेबल: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="85769-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="85769-235">ग्राहक निकाय: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="85769-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="85769-236">संबंध: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="85769-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="85769-237">मॉडल शेड्यूल सेट करने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="85769-238">जब कोई नया डेटा डाला जाता है, तो नए पैटर्न सीखने के लिए मॉडल को नियमित रूप से प्रशिक्षित करने की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="85769-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="85769-239">इस उदाहरण के लिए, **मासिक** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="85769-240">सभी विवरणों की समीक्षा करने के बाद, **सहेजें और चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="85769-241">कार्य 4 - मॉडल परिणामों और स्पष्टीकरण की समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="85769-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="85769-242">मॉडल को डेटा के प्रशिक्षण और स्कोरिंग को पूरा करने दें.</span><span class="sxs-lookup"><span data-stu-id="85769-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="85769-243">इसके बाद, आप CLV मॉडल के परिणामों और स्पष्टीकरणों की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="85769-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="85769-244">अधिक जानकारी के लिए, [पूर्वधारणा स्थिति और परिणामों की समीक्षा करें](predict-customer-lifetime-value.md#review-prediction-status-and-results) देखें.</span><span class="sxs-lookup"><span data-stu-id="85769-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="85769-245">टास्क 5 - उच्च मान वाले ग्राहकों का एक खंड बनाएं</span><span class="sxs-lookup"><span data-stu-id="85769-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="85769-246">मॉडल चलाने से एक नया निकाय बनता है, जो **डेटा** > **निकाय** पर सूचीबद्ध होता है.</span><span class="sxs-lookup"><span data-stu-id="85769-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="85769-247">आप मॉडल द्वारा बनाए गए निकाय के आधार पर एक नया ग्राहक खंड बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="85769-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="85769-248">**सेगमेंट** अनुभाग पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="85769-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="85769-249">**नया** चुनें और **इससे बनाएं** > **इंटेलिजेंस** चुनें.</span><span class="sxs-lookup"><span data-stu-id="85769-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![मॉडल आउटपुट के साथ सेगमेंट बनाना.](media/segment-intelligence.png)

1. <span data-ttu-id="85769-251">**OOBeCommerceCLVPrediction** निकाय चुनें और खंड निर्धारित करें:</span><span class="sxs-lookup"><span data-stu-id="85769-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="85769-252">फील्डः CLVScore</span><span class="sxs-lookup"><span data-stu-id="85769-252">Field: CLVScore</span></span>
  - <span data-ttu-id="85769-253">ऑपरेटर: इससे अधिक है</span><span class="sxs-lookup"><span data-stu-id="85769-253">Operator: greater than</span></span>
  - <span data-ttu-id="85769-254">मान: 1500</span><span class="sxs-lookup"><span data-stu-id="85769-254">Value: 1500</span></span>

1. <span data-ttu-id="85769-255">**समीक्षा करें** चुनें और खंड **सहेजें**.</span><span class="sxs-lookup"><span data-stu-id="85769-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="85769-256">अब आपके पास एक ऐसा खंड है जो उन ग्राहकों की पहचान करता है जिनके बारे में अगले 12 महीनों में $1500 से अधिक राजस्व उत्पन्न करने का पूर्वानुमान लगाया गया है.</span><span class="sxs-lookup"><span data-stu-id="85769-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="85769-257">यदि अधिक डेटा का अंतर्ग्रहण किया जाता है तो यह खंड गतिशील रूप से अपडेट हो जाता है.</span><span class="sxs-lookup"><span data-stu-id="85769-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="85769-258">अधिक जानकारी के लिए, [अनुभाग बनाएँ और प्रबंधित करें](segments.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="85769-258">For more information, see [Create and manage segments](segments.md).</span></span>
