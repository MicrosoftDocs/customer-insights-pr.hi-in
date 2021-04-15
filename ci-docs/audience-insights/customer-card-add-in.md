---
title: ग्राहक कार्ड ऐड-इन को इंस्टॉल और कॉन्फ़िगर करें
description: Dynamics 365 Customer Insights के लिए ग्राहक कार्ड ऐड-इन को स्थापित और कॉन्फ़िगर करें.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597329"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="040cf-103">ग्राहक कार्ड ऐड-इन (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="040cf-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="040cf-104">Dynamics 365 अनुप्रयोगों में सीधे अपने ग्राहकों का 360-डिग्री दृश्य प्राप्त करें.</span><span class="sxs-lookup"><span data-stu-id="040cf-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="040cf-105">ग्राहक कार्ड ऐड-इन के साथ जनसांख्यिकीय, इनसाइट्स और गतिविधि टाइमलाइन देखें.</span><span class="sxs-lookup"><span data-stu-id="040cf-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="040cf-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="040cf-106">Prerequisites</span></span>

- <span data-ttu-id="040cf-107">Dynamics 365 अनुप्रयोग (जैसे विक्रय हब या Customer Service हब), संस्करण 9.0 और बाद के में एकीकृत इंटरफ़ेस सक्षम किया गया.</span><span class="sxs-lookup"><span data-stu-id="040cf-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="040cf-108">ग्राहक प्रोफाइल [Common Data Service का उपयोग करके Dynamics 365 अनुप्रयोग से इन्जेस्ट किया गया](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="040cf-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="040cf-109">ग्राहक कार्ड ऐड-इन के उपयोगकर्ताओं को ऑडियंस इनसाइट्स में [उपयोगकर्ताओं के रूप में जोड़ा गया](permissions.md) होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="040cf-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="040cf-110">[कॉन्फ़िगर किए गए खोज और फ़िल्टर क्षमताएं](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="040cf-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="040cf-111">जनसांख्यिकीय नियंत्रण: जनसांख्यिकीय फ़ील्ड, (जैसे उम्र या लिंग) एकीकृत ग्राहक प्रोफ़ाइल में उपलब्ध हैं.</span><span class="sxs-lookup"><span data-stu-id="040cf-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="040cf-112">संवर्द्धन नियंत्रण: ग्राहक प्रोफ़ाइल पर लागू सक्रिय [संवर्द्धन](enrichment-hub.md) आवश्यक.</span><span class="sxs-lookup"><span data-stu-id="040cf-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="040cf-113">इंटेलिजेंस नियंत्रण: Azure मशीन लर्निंग ([पूर्वानुमानों](predictions.md) या [कस्टम मॉडल](custom-models.md)) का उपयोग कर उत्पन्न किए गए डेटा की मांग करता है</span><span class="sxs-lookup"><span data-stu-id="040cf-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="040cf-114">साधन नियंत्रण: [कॉन्फ़िगर किए गए साधन](measures.md) की मांग करता है.</span><span class="sxs-lookup"><span data-stu-id="040cf-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="040cf-115">टाइमलाइन नियंत्रण: [कॉन्फ़िगर किए गए गतिविधियों](activities.md) की मांग करता है.</span><span class="sxs-lookup"><span data-stu-id="040cf-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="040cf-116">कस्टमर कार्ड एड-इन स्थापित करें</span><span class="sxs-lookup"><span data-stu-id="040cf-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="040cf-117">ग्राहक कार्ड ऐड-इन, Dynamics 365 में Customer Engagement अनुप्रयोग के लिए समाधान है.</span><span class="sxs-lookup"><span data-stu-id="040cf-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="040cf-118">समाधान स्थापित करने के लिए, AppSource पर जाएं और **Dynamics ग्राहक कार्ड** खोजें.</span><span class="sxs-lookup"><span data-stu-id="040cf-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="040cf-119">[AppSource पर ग्राहक कार्ड एड-इन](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) चुनें और **इसे अभी पाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="040cf-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="040cf-120">समाधान इंस्टॉल करने के लिए आपको Dynamics 365 अनुप्रयोग के लिए अपने व्यवस्थापक क्रेडेंशियल्स के साथ साइन इन करना पड़ सकता है.</span><span class="sxs-lookup"><span data-stu-id="040cf-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="040cf-121">आपके परिवेश में समाधान स्थापित होने में कुछ समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="040cf-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="040cf-122">ग्राहक कार्ड ऐड-इन कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="040cf-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="040cf-123">एक व्यवस्थापक के रूप में, Dynamics 365 में **सेटिंग** अनुभाग में जाएं और **समाधान** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="040cf-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="040cf-124">**Dynamics 365 Customer Insights ग्राहक कार्ड एड-इन (पूर्वावलोकन)** समाधान के लिए **प्रदर्शन नाम** लिंक चुनें.</span><span class="sxs-lookup"><span data-stu-id="040cf-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="040cf-125">![प्रदर्शन नाम चुनें](media/select-display-name.png "प्रदर्शन नाम चुनें")</span><span class="sxs-lookup"><span data-stu-id="040cf-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="040cf-126">**साइन इन** चुनें और उस व्यवस्थापक खाते के लिए क्रेडेंशियल्स दर्ज करें जिसका उपयोग आप Customer Insights को कॉन्फ़िगर करने के लिए करते हैं.</span><span class="sxs-lookup"><span data-stu-id="040cf-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="040cf-127">जाँचें कि जब आप **साइन इन** बटन का चयन करते हैं तो ब्राउज़र पॉप-अप ब्लॉकर प्रमाणीकरण विंडो को ब्लॉक तो नहीं करता है.</span><span class="sxs-lookup"><span data-stu-id="040cf-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="040cf-128">उस परिवेश का चयन करें, जिससे आप डेटा प्राप्त करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="040cf-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="040cf-129">परिभाषित करें कि कौन-सा फ़ील्ड Dynamics 365 अनुप्रयोग में रिकॉर्ड के लिए मैपिंग करता है.</span><span class="sxs-lookup"><span data-stu-id="040cf-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="040cf-130">किसी संपर्क के साथ मैप करने के लिए, ग्राहक निकाय में फ़ील्ड का चयन करें जो आपकी संपर्क निकाय की ID से मेल खाता है.</span><span class="sxs-lookup"><span data-stu-id="040cf-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="040cf-131">किसी खाते के साथ मैप करने के लिए, ग्राहक निकाय में फ़ील्ड का चयन करें जो आपकी खाता निकाय की ID से मेल खाता है.</span><span class="sxs-lookup"><span data-stu-id="040cf-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="040cf-132">![संपर्क ID फ़ील्ड](media/contact-id-field.png "संपर्क ID फ़ील्ड")</span><span class="sxs-lookup"><span data-stu-id="040cf-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="040cf-133">सेटिंग को सहेजने के लिए **सहेजें कॉन्फ़िगरेशन** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="040cf-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="040cf-134">इसके बाद, आपको Dynamics 365 में सुरक्षा भूमिकाएँ असाइन करने की आवश्यकता होती है ताकि उपयोगकर्ता ग्राहक कार्ड को अनुकूलित कर सकें और देख सकें.</span><span class="sxs-lookup"><span data-stu-id="040cf-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="040cf-135">Dynamics 365 में, **सेटिंग्स** > **सुरक्षा** > **उपयोगकर्ता** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="040cf-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="040cf-136">उपयोगकर्ता भूमिकाओं को संपादित करने के लिए उपयोगकर्ताओं को चुनें और **भूमिकाएँ प्रबंधित करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="040cf-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="040cf-137">उन ग्राहकों को **Customer Insights कार्ड अनुकूलक** भूमिका सौंपे जो पूरे संगठन के लिए कार्ड पर दिखाई गई सामग्री को अनुकूल करेंगे.</span><span class="sxs-lookup"><span data-stu-id="040cf-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="040cf-138">फॉर्म में ग्राहक कार्ड नियंत्रण जोड़ें</span><span class="sxs-lookup"><span data-stu-id="040cf-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="040cf-139">अपने संपर्क प्रपत्र में ग्राहक कार्ड नियंत्रण जोड़ने के लिए, Dynamics 365 में **सेटिंग्स** > **अनुकूलन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="040cf-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="040cf-140">**सिस्टम अनुकूलित करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="040cf-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="040cf-141">**संपर्क** निकाय में ब्राउज़ करें, इसे खोलें और **प्रपत्र** चुनें.</span><span class="sxs-lookup"><span data-stu-id="040cf-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="040cf-142">वह संपर्क प्रपत्र चुनें, जिसमें आप ग्राहक कार्ड नियंत्रण जोड़ना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="040cf-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="040cf-143">![संपर्क प्रपत्र का चयन करें](media/contact-active-forms.png "संपर्क प्रपत्र का चयन करें")</span><span class="sxs-lookup"><span data-stu-id="040cf-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="040cf-144">प्रपत्र संपादक में, कोई नियंत्रण जोड़ने के लिए, **फ़ील्ड एक्सप्लोरर** से किसी भी फ़ील्ड को उस स्थान तक खींचें जहाँ आप नियंत्रण प्रदर्शित करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="040cf-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="040cf-145">उस प्रपत्र पर वह फ़ील्ड चुनें जिसे आपने अभी अभी जोड़ा है, और **गुण बदलें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="040cf-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="040cf-146">**नियंत्रण** टैब पर जाएं और **नियंत्रण जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="040cf-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="040cf-147">उपलब्ध कस्टम नियंत्रणों में से एक का चयन करें और **जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="040cf-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="040cf-148">**फ़ील्ड विशेषताएं** संवाद में **प्रपत्र में प्रदर्शन लेबल** चेक बॉक्स को साफ़ करें.</span><span class="sxs-lookup"><span data-stu-id="040cf-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="040cf-149">नियंत्रण के लिए **वेब** विकल्प चुनें.</span><span class="sxs-lookup"><span data-stu-id="040cf-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="040cf-150">संवर्द्धन नियंत्रण के लिए, चुनें कि आप **enrichmentType** फ़ील्ड को कॉन्फ़िगर करके किस संवर्द्धन प्रकार को प्रदर्शित करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="040cf-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="040cf-151">हर एक संवर्धन प्रकार के लिए अलग संवर्धन नियंत्रण जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="040cf-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="040cf-152">अपडेट किए गए संपर्क प्रपत्र को प्रकाशित करने के लिए **सहेजें** और **प्रकाशित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="040cf-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="040cf-153">प्रकाशित संपर्क प्रपत्र पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="040cf-153">Go to the published contact form.</span></span> <span data-ttu-id="040cf-154">आप नया-नया जोड़ा गया नियंत्रण देखेंगे.</span><span class="sxs-lookup"><span data-stu-id="040cf-154">You'll see the newly added control.</span></span> <span data-ttu-id="040cf-155">आपको इसका उपयोग करने के लिए पहली बार साइन इन करना पड़ सकता है.</span><span class="sxs-lookup"><span data-stu-id="040cf-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="040cf-156">कस्टम नियंत्रण पर आप जो दिखाना चाहते हैं उसे अनुकूलित करने के लिए, ऊपरी-दाएं कोने में संपादन बटन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="040cf-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="040cf-157">ग्राहक कार्ड ऐड-इन अपग्रेड करें</span><span class="sxs-lookup"><span data-stu-id="040cf-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="040cf-158">कस्टमर कार्ड ऐड-इन स्वचालित रूप से अपग्रेड नहीं होता है.</span><span class="sxs-lookup"><span data-stu-id="040cf-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="040cf-159">नवीनतम संस्करण में अपग्रेड करने के लिए, Dynamics 365 ऐप में इस प्रक्रिया का पालन करें, जिसमें ऐड-इन इंस्टॉल है.</span><span class="sxs-lookup"><span data-stu-id="040cf-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="040cf-160">Dynamics 365 ऐप में, **सेटिंग** > **कस्टमाइज़ेशन** पर जाएं और **समाधान** चुनें.</span><span class="sxs-lookup"><span data-stu-id="040cf-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="040cf-161">ऐड-इन की टेबल में **CustomerInsightsCustomerCard** खोजें और पंक्ति का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="040cf-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="040cf-162">एक्शन बार में **समाधान अपग्रेड लागू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="040cf-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 ऐप्स के कस्टमाइज़ेशन क्षेत्र में समाधान अपग्रेड करें":::

1. <span data-ttu-id="040cf-164">अपग्रेड प्रक्रिया शुरू करने के बाद, अपग्रेड पूरा होने तक आपको लोडिंग इंडिकेटर दिखाई देगा.</span><span class="sxs-lookup"><span data-stu-id="040cf-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="040cf-165">अगर कोई नया संस्करण नहीं है, तो अपग्रेड, एक त्रुटि संदेश दिखाएगा.</span><span class="sxs-lookup"><span data-stu-id="040cf-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]