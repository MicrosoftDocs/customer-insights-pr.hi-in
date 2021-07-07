---
title: लेन-देन संबंधी चर्न पूर्वानुमान नमूना मार्गदर्शिका
description: आउट ऑफ बॉक्स लेन-देन संबंधी चर्न पूर्वानुमान मॉडल आज़माने के लिए इस नमूना मार्गदर्शिका का उपयोग करें.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306122"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="3c517-103">लेन-देन संबंधी चर्न के पूर्वानुमान (पूर्वावलोकन) की नमूना मार्गदर्शिका</span><span class="sxs-lookup"><span data-stu-id="3c517-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="3c517-104">यह मार्गदर्शिका आपको नीचे दिए गए डेटा का उपयोग करके Customer Insights में लेन-देन संबंधी चर्न के पूर्वानुमान के शुरू से अंत तक की जानकारी देगी.</span><span class="sxs-lookup"><span data-stu-id="3c517-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="3c517-105">इस गाइड में उपयोग किया गया सभी डेटा वास्तविक ग्राहक डेटा नहीं है और Contoso डेटासेट हिस्सा है जो आपकी Customer Insights सदस्यता के भीतर *डेमो* परिवेश में पाया गया।</span><span class="sxs-lookup"><span data-stu-id="3c517-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="3c517-106">परिदृश्य</span><span class="sxs-lookup"><span data-stu-id="3c517-106">Scenario</span></span>

<span data-ttu-id="3c517-107">Contoso एक ऐसी कंपनी है जो उच्च गुणवत्ता वाली कॉफी और कॉफी मशीन बनाती है, जिसे वे अपनी Contoso कॉफी वेबसाइट के माध्यम से बेचते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c517-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="3c517-108">उनका लक्ष्य यह जानना है कि कौन से ग्राहक जो आमतौर पर नियमित रूप से अपने उत्पाद खरीदते हैं, वे अगले 60 दिनों में सक्रिय ग्राहक बनना बंद हो जाएंगे.</span><span class="sxs-lookup"><span data-stu-id="3c517-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="3c517-109">उनके किस ग्राहक के **चर्न करने की संभावना है** को जानकर, उन्हें बनाए रखने पर ध्यान केंद्रित करके मार्केटिंग प्रयासों को बचाने में मदद कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c517-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3c517-110">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="3c517-110">Prerequisites</span></span>

- <span data-ttu-id="3c517-111">Customer Insights में कम से कम [योगदानकर्ता की अनुमतियां](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3c517-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="3c517-112">हम सिफारिश करते हैं कि आप [नए परिवेश में](manage-environments.md) निम्नलिखित चरणों को लागू करें.</span><span class="sxs-lookup"><span data-stu-id="3c517-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="3c517-113">कार्य 1 - इन्जेस्ट डेटा</span><span class="sxs-lookup"><span data-stu-id="3c517-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="3c517-114">विशेष रूप से आलेख [डेटा इन्जेस्चन के बारे में](data-sources.md) और [पॉवर क्वेरी कनेक्टर का उपयोग करके डेटा स्रोतों को आयात करना](connect-power-query.md) की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="3c517-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="3c517-115">निम्नलिखित जानकारी मानती है कि आप सामान्य रूप से इन्जेस्ट होते डेटा से परिचित हैं.</span><span class="sxs-lookup"><span data-stu-id="3c517-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="3c517-116">ईकॉमर्स प्लेटफॉर्म से ग्राहक डेटा अंतर्ग्रहण करें</span><span class="sxs-lookup"><span data-stu-id="3c517-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="3c517-117">**eCommerce** नाम का एक डेटा स्रोत बनाएं, आयात विकल्प चुनें और **टेक्स्ट/CSV** कनेक्टर चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3c517-118">ईकामर्स संपर्कों के लिए URL दर्ज करें https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="3c517-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="3c517-119">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="3c517-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3c517-120">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="3c517-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="3c517-121">**जन्म की तारीख** : दिनांक</span><span class="sxs-lookup"><span data-stu-id="3c517-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="3c517-122">**CreatedOn**: दिनांक/समय/क्षेत्र</span><span class="sxs-lookup"><span data-stu-id="3c517-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="3c517-123">![जन्मतिथि को दिनांक में बदलें](media/ecommerce-dob-date.PNG "जन्मदिवस को तारीख में बदलना")</span><span class="sxs-lookup"><span data-stu-id="3c517-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="3c517-124">दाईं ओर के फ़लक पर **नाम** फ़ील्ड में, अपने डेटा स्रोत का नाम **क्वेरी** से **eCommerceContacts** में बदलें</span><span class="sxs-lookup"><span data-stu-id="3c517-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="3c517-125">डेटा स्रोत सहेजें.</span><span class="sxs-lookup"><span data-stu-id="3c517-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="3c517-126">ऑनलाइन खरीद डेटा</span><span class="sxs-lookup"><span data-stu-id="3c517-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="3c517-127">उसी **ईकॉमर्स** डेटा स्रोत में एक और डेटा सेट जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="3c517-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="3c517-128">**टेक्स्ट/CSV** कनेक्टर को फिर से चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="3c517-129">**ऑनलाइन खरीद** डेटा https://aka.ms/ciadclassonline के लिए URL दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="3c517-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="3c517-130">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="3c517-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3c517-131">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="3c517-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="3c517-132">**PurchasedOn**: दिनांक/समय</span><span class="sxs-lookup"><span data-stu-id="3c517-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="3c517-133">**TotalPrice**: मुद्रा</span><span class="sxs-lookup"><span data-stu-id="3c517-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="3c517-134">दाईं ओर की फ़लक पर **नाम** फ़ील्ड में, अपने डेटा स्रोत का नाम **क्वेरी** से **eCommercePurchases** बदलें.</span><span class="sxs-lookup"><span data-stu-id="3c517-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="3c517-135">डेटा स्रोत सहेजें.</span><span class="sxs-lookup"><span data-stu-id="3c517-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="3c517-136">लॉयल्टी स्कीमा से ग्राहक डेटा अंतर्ग्रहण करें</span><span class="sxs-lookup"><span data-stu-id="3c517-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="3c517-137">**LoyaltyScheme** नामित एक डेटा स्रोत बनाएँ, आयात विकल्प चुनें, और **Text/CSV** कनेक्टर चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3c517-138">ईकामर्स संपर्कों के लिए URL दर्ज करें https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="3c517-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="3c517-139">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="3c517-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3c517-140">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="3c517-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="3c517-141">**जन्म की तारीख** : दिनांक</span><span class="sxs-lookup"><span data-stu-id="3c517-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="3c517-142">**RewardsPoints** डिफ़ॉल्ट पूर्णांक मान</span><span class="sxs-lookup"><span data-stu-id="3c517-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="3c517-143">**CreatedOn**: बनाने का दिनांक/समय</span><span class="sxs-lookup"><span data-stu-id="3c517-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="3c517-144">दाईं ओर के फ़लक पर **नाम** फ़ील्ड में, अपना डेटा स्रोत का नाम **क्वेरी** से **loyCustomers** में बदलें.</span><span class="sxs-lookup"><span data-stu-id="3c517-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="3c517-145">डेटा स्रोत सहेजें.</span><span class="sxs-lookup"><span data-stu-id="3c517-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="3c517-146">कार्य 2 - डेटा एकीकरण</span><span class="sxs-lookup"><span data-stu-id="3c517-146">Task 2 - Data unification</span></span>

<span data-ttu-id="3c517-147">डेटा इन्जेस्ट करने के बाद अब हम एकीकृत ग्राहक प्रोफ़ाइल बनाने के लिए **मैप, मिलान, मर्ज** प्रक्रिया शुरू करते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c517-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="3c517-148">अधिक जानकारी के लिए, [डेटा एकीकरण](data-unification.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="3c517-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="3c517-149">मैप</span><span class="sxs-lookup"><span data-stu-id="3c517-149">Map</span></span>

1. <span data-ttu-id="3c517-150">डेटा को अंतर्ग्रहण करने के बाद, संपर्कों को ई-कॉमर्स और लॉयल्टी डेटा से सामान्य डेटा प्रकारों में मैप करें.</span><span class="sxs-lookup"><span data-stu-id="3c517-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="3c517-151">**डेटा** > **एकीकृत** > **मैप** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="3c517-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="3c517-152">उन निकायों को चुनें जो ग्राहक प्रोफ़ाइल – **eCommerceContacts** और **loyCustomers** का प्रतिनिधित्व करते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c517-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ईकॉमर्स और लॉयल्टी डेटास्रोत एकीकृत करें.":::

1. <span data-ttu-id="3c517-154">**eCommerceContacts** के लिए प्राथमिक कुंजी के रूप में **ContactId** और **loyCustomers** के लिए प्राथमिक कुंजी के रूप में **LoyaltyID** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId को प्राथमिक कुंजी के रूप में एकीकृत करें.":::

### <a name="match"></a><span data-ttu-id="3c517-156">मिलान</span><span class="sxs-lookup"><span data-stu-id="3c517-156">Match</span></span>

1. <span data-ttu-id="3c517-157">**मिलान** टैब पर जाएँ और **क्रम सेट करें** टैब चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="3c517-158">**मुख्य** ड्रॉपडाउन सूची में, **eCommerceContacts : eCommerce** को प्राथमिक स्रोत के रूप में चुनें और सभी रिकॉर्ड शामिल करें।</span><span class="sxs-lookup"><span data-stu-id="3c517-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="3c517-159">**निकाय 2** ड्रॉपडाउन सूची में, **loyCustomers: LoyaltyScheme** चुनें और सभी रिकॉर्ड शामिल करें।</span><span class="sxs-lookup"><span data-stu-id="3c517-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="ईकॉमर्स और लॉयल्टी का एकीकरण में मिलान करें.":::

1. <span data-ttu-id="3c517-161">**एक नया नियम बनाएं** चयन करें</span><span class="sxs-lookup"><span data-stu-id="3c517-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="3c517-162">FullName का उपयोग करके अपनी पहली शर्त जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="3c517-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="3c517-163">eCommerceContacts के लिए ड्रॉपडाउन में **पूरा नाम** चुनें।</span><span class="sxs-lookup"><span data-stu-id="3c517-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="3c517-164">loyCustomers के लिए ड्रॉपडाउन में **पूरा नाम** चुनें।</span><span class="sxs-lookup"><span data-stu-id="3c517-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="3c517-165">**सामान्यीकृत** ड्रॉप डाउन का चयन करें और **प्रकार (फोन, नाम, पता, ...)** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="3c517-166">**सटिकता स्तर** सेट करें: **बेसिक** और **मूल्य**: **उच्च**.</span><span class="sxs-lookup"><span data-stu-id="3c517-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="3c517-167">नए नियम के लिए नाम **FullName, ईमेल** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="3c517-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="3c517-168">**पता जोड़ें** का चयन करके ईमेल पते के लिए दूसरी शर्त जोड़ें</span><span class="sxs-lookup"><span data-stu-id="3c517-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="3c517-169">इकाई eCommerceContacts के लिए, ड्रॉपडाउन में **ईमेल** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="3c517-170">इकाई loyCustomers के लिए, ड्रॉपडाउन में **ईमेल** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="3c517-171">सामान्यीकृत खाली छोड़ दें.</span><span class="sxs-lookup"><span data-stu-id="3c517-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="3c517-172">**सटिकता स्तर** सेट करें: **बेसिक** और **मूल्य**: **उच्च**.</span><span class="sxs-lookup"><span data-stu-id="3c517-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="नाम और ईमेल के लिए मिलान के नियम को एकीकृत करें.":::

7. <span data-ttu-id="3c517-174">**सहेजें** और **रन करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="3c517-175">मर्ज करें</span><span class="sxs-lookup"><span data-stu-id="3c517-175">Merge</span></span>

1. <span data-ttu-id="3c517-176">**मर्ज** टैब पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="3c517-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="3c517-177">**ContactId** पर **loyCustomers** निकाय के लिए, इसे इन्जेस्ट की गई दूसरी ID से अलग करने के लिए प्रदर्शन नाम को **ContactIdLOYALTY** में बदलें.</span><span class="sxs-lookup"><span data-stu-id="3c517-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="नाम को contactid से loyalty id में बदलें.":::

1. <span data-ttu-id="3c517-179">मर्ज प्रक्रिया प्रारंभ करने के लिए **सहेजें** और **रन करें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="3c517-180">कार्य 3 - लेन-देन चर्न पूर्वानुमान को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="3c517-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="3c517-181">एकीकृत ग्राहक प्रोफ़ाइल लागू होने के साथ, हम अब सदस्यता चर्न पूर्वानुमान चला सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c517-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="3c517-182">विस्तृत चरणों के लिए, [सदस्यता चर्न का पूर्वानुमान (पूर्वावलोकन)](predict-subscription-churn.md) आलेख देखें.</span><span class="sxs-lookup"><span data-stu-id="3c517-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="3c517-183">**इंटेलिजेंस** > **डिस्कवर** पर जाएं और **ग्राहक चर्न मॉडल** का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="3c517-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="3c517-184">**ट्रांज़ैक्सन संबंधी** विकल्प चुनें और **शुरू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="3c517-185">मॉडल को **OOB ईकॉमर्स लेन-देन चर्न पूर्वानुमान** और आउटपुट निकाय को **OOBeCommerceChurnPrediction** का नाम दें.</span><span class="sxs-lookup"><span data-stu-id="3c517-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="3c517-186">चर्न मॉडल के लिए दो शर्तों को परिभाषित करें:</span><span class="sxs-lookup"><span data-stu-id="3c517-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="3c517-187">**पूर्वानुमान विंडो**: **कम से कम 60** दिन.</span><span class="sxs-lookup"><span data-stu-id="3c517-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="3c517-188">यह सेटिंग यह निर्धारित करती है कि भविष्य में हम ग्राहक चर्न का पूर्वानुमान करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c517-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="3c517-189">**चर्न परिभाषा**: **कम से कम 60** दिन.</span><span class="sxs-lookup"><span data-stu-id="3c517-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="3c517-190">खरीद के बिना अवधि जिसके बाद एक ग्राहक को चर्न किया माना जाता है.</span><span class="sxs-lookup"><span data-stu-id="3c517-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="मॉडल लीवर्स पूर्वानुमान विंडो और चर्न परिभाषा का चयन करें.":::

1. <span data-ttu-id="3c517-192">**खरीदारी इतिहास (आवश्यक)** का चयन करें और खरीदारी इतिहास के लिए **डेटा जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="3c517-193">**eCommercePurchases: ईकॉमर्स** निकाय जोड़ें और ईकॉमर्स से संबंधित फ़ील्ड से वे फ़ील्ड मैप करें जो मॉडल द्वारा आवश्यक हैं.</span><span class="sxs-lookup"><span data-stu-id="3c517-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="3c517-194">**eCommerceContacts: eCommerce** के साथ **eCommercePurchases: eCommerce** निकाय को जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="3c517-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="ईकॉमर्स निकायों को जोड़ें.":::

1. <span data-ttu-id="3c517-196">मॉडल शेड्यूल सेट करने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="3c517-197">जब नए डेटा को इन्जेस्ट किया जाता है तो नए पैटर्न सीखने के लिए मॉडल को नियमित रूप से प्रशिक्षित करना होता है.</span><span class="sxs-lookup"><span data-stu-id="3c517-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="3c517-198">इस उदाहरण के लिए, **मासिक** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="3c517-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="3c517-199">सभी विवरणों की समीक्षा करने के बाद, **सहेजें और चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="3c517-200">कार्य 4 - मॉडल परिणामों और स्पष्टीकरण की समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="3c517-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="3c517-201">मॉडल को डेटा के प्रशिक्षण और स्कोरिंग को पूरा करने दें.</span><span class="sxs-lookup"><span data-stu-id="3c517-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="3c517-202">अब आप सदस्यता चर्न मॉडल स्पष्टीकरणों की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c517-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="3c517-203">अधिक जानकारी के लिए, [पूर्वधारणा स्थिति और परिणामों की समीक्षा करें](predict-subscription-churn.md#review-a-prediction-status-and-results) देखें.</span><span class="sxs-lookup"><span data-stu-id="3c517-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="3c517-204">कार्य 5 - उच्च चर्न जोखिम वाले ग्राहकों का सेगमेंट बनाएं</span><span class="sxs-lookup"><span data-stu-id="3c517-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="3c517-205">उत्पादन मॉडल को चलाने से एक नया निकाय बनता है जिसे आप **डेटा** > **निकायों** में देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c517-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="3c517-206">आप मॉडल द्वारा बनाए गए निकाय के आधार पर एक नया सेगमेंट बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="3c517-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="3c517-207">**सेगमेंट** अनुभाग पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="3c517-207">Go to **Segments**.</span></span> <span data-ttu-id="3c517-208">**नया** चुनें और **से बनाएं** >  **इंटेलिजेंस** चुनें.</span><span class="sxs-lookup"><span data-stu-id="3c517-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="मॉडल आउटपुट के साथ सेगमेंट बनाना.":::

1. <span data-ttu-id="3c517-210">**OOBSubscriptionChurnPrediction** अंतिम बिंदु चुनें और सेगमेंट को परिभाषित करें:</span><span class="sxs-lookup"><span data-stu-id="3c517-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="3c517-211">फ़ील्ड: चर्नस्कोर</span><span class="sxs-lookup"><span data-stu-id="3c517-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="3c517-212">ऑपरेटर: इससे अधिक है</span><span class="sxs-lookup"><span data-stu-id="3c517-212">Operator: greater than</span></span>
   - <span data-ttu-id="3c517-213">मान: 0.6</span><span class="sxs-lookup"><span data-stu-id="3c517-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="सदस्यता चर्न सेगमेंट सेट करें.":::

<span data-ttu-id="3c517-215">अब आपके पास ऐसा सेगमेंट है जो गतिशील रूप से अद्यतन किया गया है, जो इस सदस्यता व्यवसाय के लिए उच्च चर्न-जोखिम वाले ग्राहकों की पहचान करता है.</span><span class="sxs-lookup"><span data-stu-id="3c517-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="3c517-216">अधिक जानकारी के लिए, [अनुभाग बनाएँ और प्रबंधित करें](segments.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="3c517-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]