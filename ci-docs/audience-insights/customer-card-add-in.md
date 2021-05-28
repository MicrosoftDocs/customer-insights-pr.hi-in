---
title: Dynamics 365 ऐप के लिए ग्राहक कार्ड ऐड-इन
description: इस ऐड-इन के साथ Dynamics 365 ऐप में ऑडियंस इनसाइट से डेटा दिखाएं.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059590"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="0e72c-103">ग्राहक कार्ड ऐड-इन (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="0e72c-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0e72c-104">Dynamics 365 अनुप्रयोगों में सीधे अपने ग्राहकों का 360-डिग्री दृश्य प्राप्त करें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="0e72c-105">समर्थित Dynamics 365 ऐप में स्थापित ग्राहक कार्ड ऐड-इन के साथ आप जनसांख्यिकी, इनसाइट और गतिविधि टाइमलाइन प्रदर्शित करना चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="0e72c-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="0e72c-106">ऐड-इन कनेक्टेड Dynamics 365 ऐप में डेटा को प्रभावित किए बिना Customer Insights से डेटा फिर से प्राप्त करेगा.</span><span class="sxs-lookup"><span data-stu-id="0e72c-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0e72c-107">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="0e72c-107">Prerequisites</span></span>

- <span data-ttu-id="0e72c-108">ऐड-इन केवल Dynamics 365 मॉडल-चालित ऐप, जैसे बिक्री या ग्राहक सेवा, संस्करण 9.0 और अगले संस्करण के लिए काम करता है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="0e72c-109">ऑडियंस इनसाइट कस्टमर प्रोफाइल को मैप करने हेतु आपके Dynamics 365 डेटा के लिए उन्हें [Common Data Service कनेक्टर का उपयोग करके Dynamics 365 ऐप से अंतर्ग्रहण किया जाना चाहिए](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0e72c-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="0e72c-110">ग्राहक कार्ड ऐड-इन के सभी Dynamics 365 उपयोगकर्ता डेटा देखने के लिए ऑडियंस इनसाइट में [उपयोगकर्ताओं के रूप में जोड़ा गया](permissions.md) होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="0e72c-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="0e72c-111">[कॉन्फ़िगर खोज और फ़िल्टर क्षमताएं](search-filter-index.md) ऑडियंस इनसाइट में डेटा को काम करने हेतु लुकअप के लिए आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="0e72c-112">प्रत्येक ऐड-इन नियंत्रण ऑडियंस इनसाइट में विशिष्ट डेटा पर निर्भर करता है:</span><span class="sxs-lookup"><span data-stu-id="0e72c-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="0e72c-113">साधन नियंत्रण: [कॉन्फ़िगर किए गए साधन](measures.md) की मांग करता है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="0e72c-114">इंटेलिजेंस नियंत्रण:[पूर्वानुमान](predictions.md) या [कस्टम मॉडल](custom-models.md) का उपयोग करके जनरेट किए गए डेटा की ज़रूरत है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="0e72c-115">जनसांख्यिकीय नियंत्रण: जनसांख्यिकीय फ़ील्ड, (जैसे उम्र या लिंग) एकीकृत ग्राहक प्रोफ़ाइल में उपलब्ध हैं.</span><span class="sxs-lookup"><span data-stu-id="0e72c-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="0e72c-116">संवर्द्धन नियंत्रण: ग्राहक प्रोफ़ाइल पर लागू सक्रिय [संवर्द्धन](enrichment-hub.md) आवश्यक.</span><span class="sxs-lookup"><span data-stu-id="0e72c-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="0e72c-117">टाइमलाइन नियंत्रण: [कॉन्फ़िगर किए गए गतिविधियों](activities.md) की मांग करता है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="0e72c-118">कस्टमर कार्ड एड-इन स्थापित करें</span><span class="sxs-lookup"><span data-stu-id="0e72c-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="0e72c-119">ग्राहक कार्ड ऐड-इन, Dynamics 365 में Customer Engagement अनुप्रयोग के लिए समाधान है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="0e72c-120">समाधान स्थापित करने के लिए, AppSource पर जाएं और **Dynamics ग्राहक कार्ड** खोजें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="0e72c-121">[AppSource पर ग्राहक कार्ड एड-इन](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) चुनें और **इसे अभी पाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="0e72c-122">समाधान इंस्टॉल करने के लिए आपको Dynamics 365 अनुप्रयोग के लिए अपने व्यवस्थापक क्रेडेंशियल्स के साथ साइन इन करना पड़ सकता है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="0e72c-123">आपके परिवेश में समाधान स्थापित होने में कुछ समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="0e72c-124">ग्राहक कार्ड ऐड-इन कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="0e72c-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="0e72c-125">एक व्यवस्थापक के रूप में, Dynamics 365 में **सेटिंग** अनुभाग में जाएं और **समाधान** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="0e72c-126">**Dynamics 365 Customer Insights ग्राहक कार्ड एड-इन (पूर्वावलोकन)** समाधान के लिए **प्रदर्शन नाम** लिंक चुनें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0e72c-127">![प्रदर्शन नाम चुनें](media/select-display-name.png "प्रदर्शन नाम चुनें")</span><span class="sxs-lookup"><span data-stu-id="0e72c-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="0e72c-128">**साइन इन** चुनें और उस व्यवस्थापक खाते के लिए क्रेडेंशियल्स दर्ज करें जिसका उपयोग आप Customer Insights को कॉन्फ़िगर करने के लिए करते हैं.</span><span class="sxs-lookup"><span data-stu-id="0e72c-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0e72c-129">जाँचें कि जब आप **साइन इन** बटन का चयन करते हैं तो ब्राउज़र पॉप-अप ब्लॉकर प्रमाणीकरण विंडो को ब्लॉक तो नहीं करता है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="0e72c-130">वह Customer Insights परिवेश चुनें, जिससे आप डेटा प्राप्त करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="0e72c-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="0e72c-131">Dynamics 365 ऐप में फ़ील्ड मैपिंग को रिकॉर्ड में निर्धारित करें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="0e72c-132">Customer Insights में अपने डेटा के आधार पर आप निम्नलिखित विकल्पों को मैप करना चुन सकते हैं:</span><span class="sxs-lookup"><span data-stu-id="0e72c-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="0e72c-133">किसी संपर्क के साथ मैप करने के लिए, ग्राहक निकाय में फ़ील्ड का चयन करें जो आपकी संपर्क निकाय की ID से मेल खाता है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="0e72c-134">किसी खाते के साथ मैप करने के लिए, ग्राहक निकाय में फ़ील्ड का चयन करें जो आपकी खाता निकाय की ID से मेल खाता है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0e72c-135">![संपर्क ID फ़ील्ड](media/contact-id-field.png "संपर्क ID फ़ील्ड")</span><span class="sxs-lookup"><span data-stu-id="0e72c-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="0e72c-136">सेटिंग को सहेजने के लिए **सहेजें कॉन्फ़िगरेशन** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="0e72c-137">इसके बाद, आपको Dynamics 365 में सुरक्षा भूमिकाएँ असाइन करने की आवश्यकता होती है ताकि उपयोगकर्ता ग्राहक कार्ड को अनुकूलित कर सकें और देख सकें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="0e72c-138">Dynamics 365 में, **सेटिंग्स** > **सुरक्षा** > **उपयोगकर्ता** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="0e72c-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="0e72c-139">उपयोगकर्ता भूमिकाओं को संपादित करने के लिए उपयोगकर्ताओं को चुनें और **भूमिकाएँ प्रबंधित करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="0e72c-140">उन ग्राहकों को **Customer Insights कार्ड अनुकूलक** भूमिका सौंपे जो पूरे संगठन के लिए कार्ड पर दिखाई गई सामग्री को अनुकूल करेंगे.</span><span class="sxs-lookup"><span data-stu-id="0e72c-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="0e72c-141">फॉर्म में ग्राहक कार्ड नियंत्रण जोड़ें</span><span class="sxs-lookup"><span data-stu-id="0e72c-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="0e72c-142">अपने संपर्क प्रपत्र में ग्राहक कार्ड नियंत्रण जोड़ने के लिए, Dynamics 365 में **सेटिंग्स** > **अनुकूलन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="0e72c-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="0e72c-143">**सिस्टम अनुकूलित करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="0e72c-144">**संपर्क** निकाय में ब्राउज़ करें, इसे खोलें और **प्रपत्र** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="0e72c-145">वह संपर्क प्रपत्र चुनें, जिसमें आप ग्राहक कार्ड नियंत्रण जोड़ना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="0e72c-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0e72c-146">![संपर्क प्रपत्र का चयन करें](media/contact-active-forms.png "संपर्क प्रपत्र का चयन करें")</span><span class="sxs-lookup"><span data-stu-id="0e72c-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="0e72c-147">प्रपत्र संपादक में, कोई नियंत्रण जोड़ने के लिए, **फ़ील्ड एक्सप्लोरर** से किसी भी फ़ील्ड को उस स्थान तक खींचें जहाँ आप नियंत्रण प्रदर्शित करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="0e72c-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="0e72c-148">उस प्रपत्र पर वह फ़ील्ड चुनें जिसे आपने अभी अभी जोड़ा है, और **गुण बदलें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="0e72c-149">**नियंत्रण** टैब पर जाएं और **नियंत्रण जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="0e72c-150">उपलब्ध कस्टम नियंत्रणों में से एक का चयन करें और **जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="0e72c-151">**फ़ील्ड विशेषताएं** संवाद में **प्रपत्र में प्रदर्शन लेबल** चेक बॉक्स को साफ़ करें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="0e72c-152">नियंत्रण के लिए **वेब** विकल्प चुनें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="0e72c-153">संवर्द्धन नियंत्रण के लिए, चुनें कि आप **enrichmentType** फ़ील्ड को कॉन्फ़िगर करके किस संवर्द्धन प्रकार को प्रदर्शित करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="0e72c-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="0e72c-154">हर एक संवर्धन प्रकार के लिए अलग संवर्धन नियंत्रण जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="0e72c-155">अपडेट किए गए संपर्क प्रपत्र को प्रकाशित करने के लिए **सहेजें** और **प्रकाशित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="0e72c-156">प्रकाशित संपर्क प्रपत्र पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="0e72c-156">Go to the published contact form.</span></span> <span data-ttu-id="0e72c-157">आप नया-नया जोड़ा गया नियंत्रण देखेंगे.</span><span class="sxs-lookup"><span data-stu-id="0e72c-157">You'll see the newly added control.</span></span> <span data-ttu-id="0e72c-158">आपको इसका उपयोग करने के लिए पहली बार साइन इन करना पड़ सकता है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="0e72c-159">कस्टम नियंत्रण पर आप जो दिखाना चाहते हैं उसे अनुकूलित करने के लिए, ऊपरी-दाएं कोने में संपादन बटन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="0e72c-160">ग्राहक कार्ड ऐड-इन अपग्रेड करें</span><span class="sxs-lookup"><span data-stu-id="0e72c-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="0e72c-161">कस्टमर कार्ड ऐड-इन स्वचालित रूप से अपग्रेड नहीं होता है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="0e72c-162">नवीनतम संस्करण में अपग्रेड करने के लिए, Dynamics 365 ऐप में इस प्रक्रिया का पालन करें, जिसमें ऐड-इन इंस्टॉल है.</span><span class="sxs-lookup"><span data-stu-id="0e72c-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="0e72c-163">Dynamics 365 ऐप में, **सेटिंग** > **कस्टमाइज़ेशन** पर जाएं और **समाधान** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="0e72c-164">ऐड-इन की टेबल में **CustomerInsightsCustomerCard** खोजें और पंक्ति का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="0e72c-165">एक्शन बार में **समाधान अपग्रेड लागू करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="0e72c-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 ऐप्स के कस्टमाइज़ेशन क्षेत्र में समाधान अपग्रेड करें":::

1. <span data-ttu-id="0e72c-167">अपग्रेड प्रक्रिया शुरू करने के बाद, अपग्रेड पूरा होने तक आपको लोडिंग इंडिकेटर दिखाई देगा.</span><span class="sxs-lookup"><span data-stu-id="0e72c-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="0e72c-168">अगर कोई नया संस्करण नहीं है, तो अपग्रेड, एक त्रुटि संदेश दिखाएगा.</span><span class="sxs-lookup"><span data-stu-id="0e72c-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
