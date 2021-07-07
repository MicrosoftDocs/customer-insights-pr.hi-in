---
title: सदस्यता चर्न पूर्वानुमान नमूना मार्गदर्शिका
description: आउट ऑफ बॉक्स सदस्यता चर्न पूर्वानुमान मॉडल आज़माने के लिए इस नमूना मार्गदर्शिका का उपयोग करें.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306305"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="6e393-103">सदस्यता चर्न पूर्वानुमान (पूर्वावलोकन) नमूना मार्गदर्शिका</span><span class="sxs-lookup"><span data-stu-id="6e393-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="6e393-104">हम नीचे दिए गए नमूना डेटा का उपयोग करके आपको सदस्यता चर्न पूर्वानुमान के शुरू से अंत तक जानकारी देंगे.</span><span class="sxs-lookup"><span data-stu-id="6e393-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="6e393-105">परिदृश्य</span><span class="sxs-lookup"><span data-stu-id="6e393-105">Scenario</span></span>

<span data-ttu-id="6e393-106">Contoso एक ऐसी कंपनी है जो उच्च गुणवत्ता वाली कॉफी और कॉफी मशीन बनाती है, जिसे वे अपनी Contoso कॉफी वेबसाइट के माध्यम से बेचते हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="6e393-107">उन्होंने हाल ही में अपने ग्राहकों के लिए नियमित आधार पर कॉफी प्राप्त करने के लिए सदस्यता व्यवसाय शुरू किया.</span><span class="sxs-lookup"><span data-stu-id="6e393-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="6e393-108">उनका लक्ष्य यह समझना है कि अगले कुछ महीनों में कौन से सदस्य बने ग्राहक अपनी सदस्यता रद्द कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="6e393-109">उनके किस ग्राहक के **चर्न करने की संभावना है** को जानकर, उन्हें बनाए रखने पर ध्यान केंद्रित करके मार्केटिंग प्रयासों को बचाने में मदद कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6e393-110">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="6e393-110">Prerequisites</span></span>

- <span data-ttu-id="6e393-111">Customer Insights में कम से कम [योगदानकर्ता की अनुमतियां](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6e393-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="6e393-112">हम सिफारिश करते हैं कि आप [नए परिवेश में](manage-environments.md) निम्नलिखित चरणों को लागू करें.</span><span class="sxs-lookup"><span data-stu-id="6e393-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="6e393-113">कार्य 1 - इन्जेस्ट डेटा</span><span class="sxs-lookup"><span data-stu-id="6e393-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="6e393-114">विशेष रूप से आलेख [डेटा इन्जेस्चन के बारे में](data-sources.md) और [पॉवर क्वेरी कनेक्टर का उपयोग करके डेटा स्रोतों को आयात करना](connect-power-query.md) की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="6e393-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="6e393-115">निम्नलिखित जानकारी मानती है कि आप सामान्य रूप से इन्जेस्ट होते डेटा से परिचित हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="6e393-116">ईकॉमर्स प्लेटफॉर्म से ग्राहक डेटा अंतर्ग्रहण करें</span><span class="sxs-lookup"><span data-stu-id="6e393-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="6e393-117">**eCommerce** नाम का एक डेटा स्रोत बनाएं, आयात विकल्प चुनें और **टेक्स्ट/CSV** कनेक्टर चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6e393-118">ईकामर्स संपर्कों के लिए URL दर्ज करें https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="6e393-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="6e393-119">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="6e393-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="6e393-120">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="6e393-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="6e393-121">**जन्म की तारीख** : दिनांक</span><span class="sxs-lookup"><span data-stu-id="6e393-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="6e393-122">**CreatedOn**: दिनांक/समय/क्षेत्र</span><span class="sxs-lookup"><span data-stu-id="6e393-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="जन्मतिथि को तारीख में बदलना.":::

1. <span data-ttu-id="6e393-124">दाईं ओर के फ़लक पर **नाम** फ़ील्ड में, अपने डेटा स्रोत का नाम **क्वेरी** से **eCommerceContacts** में बदलें</span><span class="sxs-lookup"><span data-stu-id="6e393-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="6e393-125">डेटा स्रोत सहेजें.</span><span class="sxs-lookup"><span data-stu-id="6e393-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="6e393-126">लॉयल्टी स्कीमा से ग्राहक डेटा अंतर्ग्रहण करें</span><span class="sxs-lookup"><span data-stu-id="6e393-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="6e393-127">**LoyaltyScheme** नामित एक डेटा स्रोत बनाएँ, आयात विकल्प चुनें, और **Text/CSV** कनेक्टर चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6e393-128">ईकामर्स संपर्कों के लिए URL दर्ज करें https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="6e393-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="6e393-129">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="6e393-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="6e393-130">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="6e393-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="6e393-131">**जन्म की तारीख** : दिनांक</span><span class="sxs-lookup"><span data-stu-id="6e393-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="6e393-132">**RewardsPoints** डिफ़ॉल्ट पूर्णांक मान</span><span class="sxs-lookup"><span data-stu-id="6e393-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="6e393-133">**CreatedOn**: बनाने का दिनांक/समय</span><span class="sxs-lookup"><span data-stu-id="6e393-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="6e393-134">दाईं ओर के फ़लक पर **नाम** फ़ील्ड में, अपना डेटा स्रोत का नाम **क्वेरी** से **loyCustomers** में बदलें.</span><span class="sxs-lookup"><span data-stu-id="6e393-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="6e393-135">डेटा स्रोत सहेजें.</span><span class="sxs-lookup"><span data-stu-id="6e393-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="6e393-136">इन्जेस्ट सदस्‍यता की जानकारी</span><span class="sxs-lookup"><span data-stu-id="6e393-136">Ingest subscription information</span></span>

1. <span data-ttu-id="6e393-137">**SubscriptionHistory** नामक डेटा स्रोत बनाएं, आयात विकल्प चुनें, और **टेक्स्ट/CSV** कनेक्टर चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6e393-138">ईकामर्स संपर्कों के लिए URL दर्ज करें https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="6e393-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="6e393-139">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="6e393-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="6e393-140">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="6e393-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="6e393-141">**SubscriptioID**: संपूर्ण संख्या</span><span class="sxs-lookup"><span data-stu-id="6e393-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="6e393-142">**SubscriptionAmount**: मुद्रा</span><span class="sxs-lookup"><span data-stu-id="6e393-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="6e393-143">**SubscriptionEndDate**: दिनांक/समय</span><span class="sxs-lookup"><span data-stu-id="6e393-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="6e393-144">**SubscriptionStartDate**: दिनांक/समय</span><span class="sxs-lookup"><span data-stu-id="6e393-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="6e393-145">**TransactionDate**: दिनांक/समय</span><span class="sxs-lookup"><span data-stu-id="6e393-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="6e393-146">**IsRecurring**: सही/गलत</span><span class="sxs-lookup"><span data-stu-id="6e393-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="6e393-147">**Is_auto_renew**: सही/गलत</span><span class="sxs-lookup"><span data-stu-id="6e393-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="6e393-148">**RecurringFrequencyInMonths**: पूर्णांक</span><span class="sxs-lookup"><span data-stu-id="6e393-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="6e393-149">दाईं ओर के फ़लक पर **नाम** फ़ील्ड में, अपने डेटा स्रोत का नाम **क्वेरी** से **SubscriptionHistory** में बदलें.</span><span class="sxs-lookup"><span data-stu-id="6e393-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="6e393-150">डेटा स्रोत सहेजें.</span><span class="sxs-lookup"><span data-stu-id="6e393-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="6e393-151">वेबसाइट समीक्षाओं से ग्राहक डेटा अंतर्ग्रहण करें</span><span class="sxs-lookup"><span data-stu-id="6e393-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="6e393-152">**वेबसाइट** नामित एक डेटा स्रोत बनाएँ, आयात विकल्प चुनें, और **Text/CSV** कनेक्टर चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6e393-153">ईकामर्स संपर्कों के लिए URL दर्ज करें https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="6e393-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="6e393-154">डेटा संपादित करते समय, **ट्रांसफ़ॉर्म** चुनें और फिर **हेडर के रूप में पहली पंक्ति का इस्तेमाल करें**.</span><span class="sxs-lookup"><span data-stu-id="6e393-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="6e393-155">नीचे सूचीबद्ध कॉलम के लिए डेटाटाइप को अद्यतन करें:</span><span class="sxs-lookup"><span data-stu-id="6e393-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="6e393-156">**ReviewRating**: पूर्णांक</span><span class="sxs-lookup"><span data-stu-id="6e393-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="6e393-157">**ReviewDate**: दिनांक</span><span class="sxs-lookup"><span data-stu-id="6e393-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="6e393-158">दाएं फलक पर 'नाम' फ़ील्ड में, अपने डेटा स्रोत का नाम **क्वेरी** से **webReviews** बदलें.</span><span class="sxs-lookup"><span data-stu-id="6e393-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="6e393-159">कार्य 2 - डेटा एकीकरण</span><span class="sxs-lookup"><span data-stu-id="6e393-159">Task 2 - Data unification</span></span>

<span data-ttu-id="6e393-160">डेटा इन्जेस्ट करने के बाद अब हम एकीकृत ग्राहक प्रोफ़ाइल बनाने के लिए **मैप, मिलान, मर्ज** प्रक्रिया शुरू करते हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="6e393-161">अधिक जानकारी के लिए, [डेटा एकीकरण](data-unification.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="6e393-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="6e393-162">मैप</span><span class="sxs-lookup"><span data-stu-id="6e393-162">Map</span></span>

1. <span data-ttu-id="6e393-163">डेटा को अंतर्ग्रहण करने के बाद, संपर्कों को ई-कॉमर्स और लॉयल्टी डेटा से सामान्य डेटा प्रकारों में मैप करें.</span><span class="sxs-lookup"><span data-stu-id="6e393-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="6e393-164">**डेटा** > **एकीकृत** > **मैप** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="6e393-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="6e393-165">उन निकायों को चुनें जो ग्राहक प्रोफ़ाइल – **eCommerceContacts** और **loyCustomers** का प्रतिनिधित्व करते हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ईकॉमर्स और लॉयल्टी डेटास्रोत एकीकृत करें.":::

1. <span data-ttu-id="6e393-167">**eCommerceContacts** के लिए प्राथमिक कुंजी के रूप में **ContactId** और **loyCustomers** के लिए प्राथमिक कुंजी के रूप में **LoyaltyID** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId को प्राथमिक कुंजी के रूप में एकीकृत करें.":::

### <a name="match"></a><span data-ttu-id="6e393-169">मिलान</span><span class="sxs-lookup"><span data-stu-id="6e393-169">Match</span></span>

1. <span data-ttu-id="6e393-170">**मिलान** टैब पर जाएँ और **क्रम सेट करें** टैब चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="6e393-171">**मुख्य** ड्रॉपडाउन सूची में, **eCommerceContacts : eCommerce** को प्राथमिक स्रोत के रूप में चुनें और सभी रिकॉर्ड शामिल करें।</span><span class="sxs-lookup"><span data-stu-id="6e393-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="6e393-172">**निकाय 2** ड्रॉपडाउन सूची में, **loyCustomers: LoyaltyScheme** चुनें और सभी रिकॉर्ड शामिल करें।</span><span class="sxs-lookup"><span data-stu-id="6e393-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="ईकॉमर्स और लॉयल्टी का एकीकरण में मिलान करें.":::

1. <span data-ttu-id="6e393-174">**एक नया नियम बनाएं** चयन करें</span><span class="sxs-lookup"><span data-stu-id="6e393-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="6e393-175">FullName का उपयोग करके अपनी पहली शर्त जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="6e393-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="6e393-176">eCommerceContacts के लिए ड्रॉपडाउन में **पूरा नाम** चुनें।</span><span class="sxs-lookup"><span data-stu-id="6e393-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="6e393-177">loyCustomers के लिए ड्रॉपडाउन में **पूरा नाम** चुनें।</span><span class="sxs-lookup"><span data-stu-id="6e393-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="6e393-178">**सामान्यीकृत** ड्रॉप डाउन का चयन करें और **प्रकार (फोन, नाम, पता, ...)** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="6e393-179">**सटिकता स्तर** सेट करें: **बेसिक** और **मूल्य**: **उच्च**.</span><span class="sxs-lookup"><span data-stu-id="6e393-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="6e393-180">नए नियम के लिए नाम **FullName, ईमेल** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="6e393-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="6e393-181">**पता जोड़ें** का चयन करके ईमेल पते के लिए दूसरी शर्त जोड़ें</span><span class="sxs-lookup"><span data-stu-id="6e393-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="6e393-182">इकाई eCommerceContacts के लिए, ड्रॉपडाउन में **ईमेल** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="6e393-183">इकाई loyCustomers के लिए, ड्रॉपडाउन में **ईमेल** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="6e393-184">सामान्यीकृत खाली छोड़ दें.</span><span class="sxs-lookup"><span data-stu-id="6e393-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="6e393-185">**सटिकता स्तर** सेट करें: **बेसिक** और **मूल्य**: **उच्च**.</span><span class="sxs-lookup"><span data-stu-id="6e393-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="नाम और ईमेल के लिए मिलान के नियम को एकीकृत करें.":::

7. <span data-ttu-id="6e393-187">**सहेजें** और **रन करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="6e393-188">मर्ज करें</span><span class="sxs-lookup"><span data-stu-id="6e393-188">Merge</span></span>

1. <span data-ttu-id="6e393-189">**मर्ज** टैब पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="6e393-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="6e393-190">**ContactId** पर **loyCustomers** निकाय के लिए, इसे इन्जेस्ट की गई दूसरी ID से अलग करने के लिए प्रदर्शन नाम को **ContactIdLOYALTY** में बदलें.</span><span class="sxs-lookup"><span data-stu-id="6e393-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="नाम को contactid से loyalty id में बदलें.":::

1. <span data-ttu-id="6e393-192">मर्ज प्रक्रिया प्रारंभ करने के लिए **सहेजें** और **रन करें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="6e393-193">कार्य 3 - सदस्यता चर्न पूर्वानुमान को कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="6e393-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="6e393-194">एकीकृत ग्राहक प्रोफ़ाइल लागू होने के साथ, हम अब सदस्यता चर्न पूर्वानुमान चला सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="6e393-195">विस्तृत चरणों के लिए, [सदस्यता चर्न का पूर्वानुमान (पूर्वावलोकन)](predict-subscription-churn.md) आलेख देखें.</span><span class="sxs-lookup"><span data-stu-id="6e393-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="6e393-196">**इंटेलिजेंस** > **डिस्कवर** पर जाएं और **ग्राहक चर्न मॉडल** का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="6e393-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="6e393-197">**सदस्यता** विकल्प का चयन करें और **शुरू करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="6e393-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="6e393-198">मॉडल को **OOB सदस्यता चर्ण पूर्वानुमान** और आउटपुट निकाय **OOBSubscriptionChurnPrediction** नामित करें.</span><span class="sxs-lookup"><span data-stu-id="6e393-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="6e393-199">चर्न मॉडल के लिए दो शर्तों को परिभाषित करें:</span><span class="sxs-lookup"><span data-stu-id="6e393-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="6e393-200">**सदस्यता समाप्त होने के दिन**: **कम से कम 60** दिन.</span><span class="sxs-lookup"><span data-stu-id="6e393-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="6e393-201">यदि किसी ग्राहक ने अपनी सदस्यता समाप्त होने के बाद लंबे समय तक अपनी सदस्यता का नवीनीकरण नहीं करता है, तब उन्हें चर्न माना जाता है.</span><span class="sxs-lookup"><span data-stu-id="6e393-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="6e393-202">**चर्न परिभाषा**: **कम से कम 93** दिन.</span><span class="sxs-lookup"><span data-stu-id="6e393-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="6e393-203">मॉडल पूर्वानुमान की अवधि, जब ग्राहक चर्न कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="6e393-204">भविष्य में आप जितना आगे दिखेंगे, परिणाम उतने ही सटीक होंगे.</span><span class="sxs-lookup"><span data-stu-id="6e393-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="मॉडल लीवर्स पूर्वानुमान विंडो और चर्न परिभाषा का चयन करें.":::

1. <span data-ttu-id="6e393-206">**आवश्यक डेटा जोड़ें** का चयन करें और सदस्यता इतिहास के लिए **डेटा जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="6e393-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="6e393-207">**सब्सक्रिप्शन: SubscriptionHistory** निकाय जोड़ें और ईकॉमर्स से संबंधित फ़ील्ड से वे फ़ील्ड मैप करें जो मॉडल द्वारा आवश्यक हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="6e393-208">**eCommerceContacts: ईकॉमर्स** के साथ **सदस्यता: SubscriptionHistory** निकाय को जोड़ें, संबंध को **eCommerceSubscription** का नाम दें.</span><span class="sxs-lookup"><span data-stu-id="6e393-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="ईकॉमर्स निकायों को जोड़ें.":::

1. <span data-ttu-id="6e393-210">ग्राहक गतिविधियों में, **webReviews: वेबसाइट** निकाय जोड़ें और webReviews से संबंधित फ़ील्ड को मॉडल द्वारा आवश्यक फ़ील्ड में मैप करें.</span><span class="sxs-lookup"><span data-stu-id="6e393-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="6e393-211">प्राथमिक कुंजी: ReviewId</span><span class="sxs-lookup"><span data-stu-id="6e393-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="6e393-212">टाइमस्टैम्प: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="6e393-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="6e393-213">इवेंट: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="6e393-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="6e393-214">वेबसाइट समीक्षाओं के लिए एक गतिविधि कॉन्फ़िगर करें.</span><span class="sxs-lookup"><span data-stu-id="6e393-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="6e393-215">**समीक्षा करें** गतिविधि का चयन करें और **eCommerceContacts : ईकॉमर्स** के साथ **webReviews : वेबसाइट** निकाय में शामिल हों.</span><span class="sxs-lookup"><span data-stu-id="6e393-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="6e393-216">मॉडल शेड्यूल सेट करने के लिए **अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="6e393-217">जब नए डेटा को इन्जेस्ट किया जाता है तो नए पैटर्न सीखने के लिए मॉडल को नियमित रूप से प्रशिक्षित करना होता है.</span><span class="sxs-lookup"><span data-stu-id="6e393-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="6e393-218">इस उदाहरण के लिए, **मासिक** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="6e393-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="6e393-219">सभी विवरणों की समीक्षा करने के बाद, **सहेजें और चलाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="6e393-220">कार्य 4 - मॉडल परिणामों और स्पष्टीकरण की समीक्षा करें</span><span class="sxs-lookup"><span data-stu-id="6e393-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="6e393-221">मॉडल को डेटा के प्रशिक्षण और स्कोरिंग को पूरा करने दें.</span><span class="sxs-lookup"><span data-stu-id="6e393-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="6e393-222">अब आप सदस्यता चर्न मॉडल स्पष्टीकरणों की समीक्षा कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="6e393-223">अधिक जानकारी के लिए, [पूर्वधारणा स्थिति और परिणामों की समीक्षा करें](predict-subscription-churn.md#review-a-prediction-status-and-results) देखें.</span><span class="sxs-lookup"><span data-stu-id="6e393-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="6e393-224">कार्य 5 - उच्च चर्न जोखिम वाले ग्राहकों का सेगमेंट बनाएं</span><span class="sxs-lookup"><span data-stu-id="6e393-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="6e393-225">उत्पादन मॉडल को चलाने से एक नया निकाय बनता है जिसे आप **डेटा** > **निकायों** में देख सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="6e393-226">आप मॉडल द्वारा बनाए गए निकाय के आधार पर एक नया सेगमेंट बना सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6e393-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="6e393-227">**सेगमेंट** अनुभाग पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="6e393-227">Go to **Segments**.</span></span> <span data-ttu-id="6e393-228">**नया** चुनें और **से बनाएं** >  **इंटेलिजेंस** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6e393-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="मॉडल आउटपुट के साथ सेगमेंट बनाना.":::

1. <span data-ttu-id="6e393-230">**OOBSubscriptionChurnPrediction** अंतिम बिंदु चुनें और सेगमेंट को परिभाषित करें:</span><span class="sxs-lookup"><span data-stu-id="6e393-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="6e393-231">फ़ील्ड: चर्नस्कोर</span><span class="sxs-lookup"><span data-stu-id="6e393-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="6e393-232">ऑपरेटर: इससे अधिक है</span><span class="sxs-lookup"><span data-stu-id="6e393-232">Operator: greater than</span></span>
   - <span data-ttu-id="6e393-233">मान: 0.6</span><span class="sxs-lookup"><span data-stu-id="6e393-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="सदस्यता चर्न सेगमेंट सेट करें.":::

<span data-ttu-id="6e393-235">अब आपके पास ऐसा सेगमेंट है जो गतिशील रूप से अद्यतन किया गया है, जो इस सदस्यता व्यवसाय के लिए उच्च चर्न-जोखिम वाले ग्राहकों की पहचान करता है.</span><span class="sxs-lookup"><span data-stu-id="6e393-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="6e393-236">अधिक जानकारी के लिए, [अनुभाग बनाएँ और प्रबंधित करें](segments.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="6e393-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]