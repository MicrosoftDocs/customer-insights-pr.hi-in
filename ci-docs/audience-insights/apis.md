---
title: API के साथ काम करें
description: API का उपयोग करें और सीमाओं को समझें.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 59161456914df84d7e72402ed1f5faf70a5119ba
ms.sourcegitcommit: a39e00a50ad3eda820fd756c5611081f0ca04662
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/09/2021
ms.locfileid: "5873664"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="9da5c-103">Customer Insights API के साथ काम करें</span><span class="sxs-lookup"><span data-stu-id="9da5c-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="9da5c-104">Dynamics 365 Customer Insights आपको Customer Insights में डेटा के आधार पर आपके स्वयं के अनुप्रयोग बनाने के लिए API देता है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9da5c-105">इन API के विवरण, [Customer Insights API संदर्भ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) पर सूचीबद्ध हैं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="9da5c-106">उनमें परिचालनों, मापदंडों और प्रतिक्रियाओं के बारे में अतिरिक्त जानकारी शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="9da5c-107">यह आलेख आपको Customer Insights API तक पहुंचने के लिए मार्गदर्शन करता है, Azure अनुप्रयोग पंजीकरण बनाता है, और उपलब्ध क्लाइंट लाइब्रेरी के साथ शुरू करने में आपकी सहायता करता है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="9da5c-108">Customer Insights API आज़माना शुरू करें</span><span class="sxs-lookup"><span data-stu-id="9da5c-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="9da5c-109">Customer Insights से [साइन-इन](https://home.ci.ai.dynamics.com) करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="9da5c-110">यदि आपके पास अभी तक कोई सदस्यता नहीं है, तो [Customer Insights के परीक्षण के लिए साइन अप करें](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="9da5c-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="9da5c-111">अपने Customer Insights परिवेश में API को सक्षम करने के लिए, **व्यवस्थापक** > **अनुमतियाँ** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="9da5c-112">आपको ऐसा करने के लिए व्यवस्थापक अनुमतियाँ चाहिए होगी.</span><span class="sxs-lookup"><span data-stu-id="9da5c-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="9da5c-113">**API** टैब पर जाएं और **सक्षम करें** बटन चुनें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="9da5c-114">API को सक्षम करना आपके उदाहरण के लिए प्राथमिक और द्वितीयक सदस्यता कुंजी बनाता है, जिनको API अनुरोधों में उपयोग किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="9da5c-115">आप **व्यवस्थापक** > **अनुमतियाँ** > **API** में **प्राइमरी रीजेनरेट करें** या **सेकेंडरी रीजेनरेट करें** का चयन करके कुंजियों को फिर से हासिल कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights APIs सक्षम करें":::

1. <span data-ttu-id="9da5c-117">**API आजमाएं** के लिए [हमारे API एक्सप्लोर करें](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) चुनें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="9da5c-118">एक API परिचालन चुनें और **इसे आज़माएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="9da5c-119">साइड के फलक में, **निहित** करने के लिए मान को **प्राधिकरण** ड्रॉप-डाउन मेनू में सेट करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="9da5c-120">`Authorization`प्राधिकरण\` हेडर एक बीयरर टोकन के साथ जुड़ जाता है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="9da5c-121">आपकी सदस्यता कुंजी स्वचालित रूप से पाप्यूलेट हो जाएगी.</span><span class="sxs-lookup"><span data-stu-id="9da5c-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="9da5c-122">वैकल्पिक रूप से, सभी आवश्यक क्वेरी मापदंड जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="9da5c-123">साइड फलक के नीचे स्क्रॉल करें और **भेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="9da5c-124">जल्द ही HTTP प्रतिक्रिया नीचे दिखाई देगी.</span><span class="sxs-lookup"><span data-stu-id="9da5c-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="API का परीक्षण करने का तरीका दिखाने वाला एनिमेटेड gif":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="9da5c-126">Azure पोर्टल में एक नया अनुप्रयोग पंजीकरण बनाएं</span><span class="sxs-lookup"><span data-stu-id="9da5c-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="9da5c-127">ये चरण आपको Customer Insights API का उपयोग करके Azure अनुप्रयोग में प्रत्यायोजित अनुमतियों का उपयोग करना शुरू करने में मदद करते हैं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="9da5c-128">सुनिश्चित करें कि [शुरू करें अनुभाग](#get-started-trying-the-customer-insights-apis) पहले ही पूरा कर लिया जाता है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="9da5c-129">उस खाते के साथ [Azure पोर्टल](https://portal.azure.com) में साइन इन करें जो Customer Insights डेटा तक पहुंच सकता है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="9da5c-130">बाईं ओर, **अनुप्रयोग पंजीकरण** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="9da5c-131">**नया पंजीकरण** चुनें एक एप्लिकेशन का नाम दें और खाता प्रकार चुनें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="9da5c-132">वैकल्पिक रूप से, एक रीडायरेक्ट URL जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="9da5c-133">http://localhost आपके स्थानीय कंप्यूटर पर अनुप्रयोग बनाने के लिए पर्याप्त है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="9da5c-134">अपने नए अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="ऐप पंजीकरण में API अनुमति निर्धारित करने के लिए एनिमेटेड gif.":::

1. <span data-ttu-id="9da5c-136">**एक अनुमति जोड़ें** चुनें और साइड फलक में **Customer Insights** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="9da5c-137">**अनुमति प्रकार** के लिए, **मान्य अनुमतियाँ** का चयन करें और **user_impersonation** अनुमति का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="9da5c-138">**अनुमतियाँ जोड़ें** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-138">Select **Add permissions**.</span></span> <span data-ttu-id="9da5c-139">यदि आपको उपयोगकर्ता द्वारा साइन इन किए बिना API तक पहुंचने की आवश्यकता है, तो [सर्वर-से-सर्वर अनुप्रयोग अनुमतियाँ](#server-to-server-application-permissions) अनुभाग की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="9da5c-140">अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="9da5c-141">आप API में अपने अनुरोध के साथ बीयरर टोकन प्राप्त करने के लिए Microsoft Authentication Library (MSAL) के साथ इस अनुप्रयोग पंजीकरण के लिए अनुप्रयोग/क्लाइंट ID का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="व्यवस्थापक सहमति देने के लिए एनिमेटेड gif.":::

<span data-ttu-id="9da5c-143">MSAL के बारे में अधिक जानकारी के लिए, [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) देखें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="9da5c-144">Azure में अनुप्रयोग पंजीकरण के बारे में अधिक जानकारी के लिए, [नया Azure पोर्टल अनुप्रयोग पंजीकरण अनुभव](/azure/active-directory/develop/app-registration-portal-training-guide) देखें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="9da5c-145">API की हमारी क्लाइंट लाइब्रेरी का उपयोग करने के बारे में जानकारी के लिए, [Customer Insights क्लाइंट लाइब्रेरी](#customer-insights-client-libraries) देखें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="9da5c-146">सर्वर-से-सर्वर अनुप्रयोग अनुमतियाँ</span><span class="sxs-lookup"><span data-stu-id="9da5c-146">Server-to-server application permissions</span></span>

<span data-ttu-id="9da5c-147">[अनुप्रयोग पंजीकरण अनुभाग](#create-a-new-app-registration-in-the-azure-portal) यह बताता है कि ऐसे अनुप्रयोग को कैसे पंजीकृत करना है जो प्रमाणीकरण के लिए उपयोगकर्ता को साइन इन करना आवश्यक करता है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="9da5c-148">ऐसा अनुप्रयोग पंजीकरण बनाना सीखें, जिसके लिए उपयोगकर्ता का इंटरेक्शन आवश्यक नहीं है और इसे सर्वर पर चलाया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="9da5c-149">Azure पोर्टल में अपने अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="9da5c-150">**एक अनुमति जोड़ें** चुनें और साइड फलक में **Customer Insights** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="9da5c-151">**अनुमति प्रकार** के लिए, **एप्लिकेशन अनुमतियाँ** का चयन करें और **CustomerInsights.Api.All** अनुमतियों को चुनें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="9da5c-152">**अनुमतियाँ जोड़ें** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="9da5c-153">इस अनुप्रयोग की अनुमति पर व्यवस्थापक की सहमति देने के लिए, आपको एक सर्विस प्रिंसिपल को जोड़ना होगा.</span><span class="sxs-lookup"><span data-stu-id="9da5c-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="9da5c-154">Azure Active Directory (AD) PowerShell मॉड्यूल स्थापित करें: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="9da5c-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="9da5c-155">अपने AD खाते से कनेक्ट करें: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="9da5c-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="9da5c-156">आप अपनी टेनेंट ID **अवलोकन** > **Azure Active Directory** पर पा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="9da5c-157">Azure AD सर्विस प्रिंसिपल को जोड़ने के लिए निम्नलिखित कमांड चलाएं: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId मापदंड Customer Insights API अनुप्रयोग से संबंधित है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="सर्विस प्रिंसिपल नमूना":::

1. <span data-ttu-id="9da5c-159">अपने अनुप्रयोग पंजीकरण के लिए **API अनुमतियाँ** पर वापस जाएं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="9da5c-160">अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="व्यवस्थापक सहमति देने के लिए एनिमेटेड gif.":::

1. <span data-ttu-id="9da5c-162">पूरा करने के लिए, हमें Customer Insights में अनुप्रयोग पंजीकरण का नाम एक उपयोगकर्ता के रूप में जोड़ना होगा.</span><span class="sxs-lookup"><span data-stu-id="9da5c-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="9da5c-163">Customer Insights खोलें, **व्यवस्थापक** > **अनुमतियाँ** पर जाएं और **उपयोगकर्ता जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="9da5c-164">अपने अनुप्रयोग पंजीकरण के नाम को खोजें, इसे खोज परिणामों से चुनें, और **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="9da5c-165">Customer Insights क्‍लाइंट लाइब्रेरी</span><span class="sxs-lookup"><span data-stu-id="9da5c-165">Customer Insights client libraries</span></span>

<span data-ttu-id="9da5c-166">यह अनुभाग आपको Customer Insights API के लिए उपलब्ध क्लाइंट लाइब्रेरी इस्तेमाल करने में मदद करता है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="9da5c-167">सभी लाइब्रेरी स्रोत कोड और नमूना एप्लिकेशन [Customer Insights GitHub पेज](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) पर देखे जा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="9da5c-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="9da5c-168">C# NuGet</span></span>

<span data-ttu-id="9da5c-169">NuGet.org से C# क्लाइंट लाइब्रेरी का उपयोग शुरू करने का तरीका जानें. NuGet पैकेज के बारे में अधिक जानकारी के लिए, [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) देखें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="9da5c-170">फिलहाल, यह पैकेज netstandard2.0 और netcoreapp2.0 फ्रेमवर्क को लक्षित करता है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="9da5c-171">C# क्लाइंट लाइब्रेरी को C# प्रोजेक्ट में जोड़ें</span><span class="sxs-lookup"><span data-stu-id="9da5c-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="9da5c-172">Visual Studio में, अपने प्रोजेक्ट के लिए **NuGet पैकेज प्रबंधक** खोलें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="9da5c-173">**Microsoft.Dynamics.CustomerInsights.Api** को खोजें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="9da5c-174">प्रोजेक्ट में पैकेज जोड़ने के लिए **इंस्टॉल करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="9da5c-175">वैकल्पिक रूप से, इस कमांड को **NuGet पैकेज प्रबंधक कंसोल में चलाएं**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="9da5c-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Visual Studio प्रोजेक्ट में NuGet पैकेज जोड़ें":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="9da5c-177">C# क्लाइंट लाइब्रेरी का उपयोग करें</span><span class="sxs-lookup"><span data-stu-id="9da5c-177">Use the C# client library</span></span>

1. <span data-ttu-id="9da5c-178">अपने मौजूदा [Azure अनुप्रयोग पंजीकरण](#create-a-new-app-registration-in-the-azure-portal) का उपयोग करके `AccessToken` पाने के लिए [Microsoft प्रमाणीकरण लाइब्रेरी(MSAL)](/azure/active-directory/develop/msal-overview) का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="9da5c-179">एक टोकन को सफलतापूर्वक प्रमाणित करने और हासिल करने के बाद, एक नया बनाएं या मौजूदा `HttpClient` के साथ अतिरिक्त **DefaultRequestHeaders "प्राधिकरण"** सेट को **धारक <access token>** और **Ocp-Apim-Subscription-Key** सेट से [अपने Customer Insights परिवेश से **सदस्यता कुंजी**](#get-started-trying-the-customer-insights-apis) को उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="9da5c-180">उपयुक्त होने पर **प्राधिकरण** हेडर को रीसेट करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="9da5c-181">उदाहरण के लिए, जब टोकन समाप्त हो गया है.</span><span class="sxs-lookup"><span data-stu-id="9da5c-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="9da5c-182">इस `HttpClient` को `CustomerInsights` क्लाइंट के निर्माण में पास करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient का नमूना":::

1. <span data-ttu-id="9da5c-184">"एक्सटेंशन विधियों" के लिए क्लाइंट के साथ कॉल करें, उदाहरण के लिए, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="9da5c-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="9da5c-185">यदि अंतर्निहित `Microsoft.Rest.HttpOperationResponse` को एक्सेस करने को प्राथमिकता दी जाती है, तो "http संदेश विधियों" का उपयोग करें, उदाहरण के लिए `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="9da5c-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="9da5c-186">प्रतिक्रिया शायद `object` प्रकार की होगी, क्योंकि विधि कई प्रकारों को लौटा सकती है (उदाहरण के लिए, `IList<InstanceInfo>` and \`\`ApiErrorResult\`).</span><span class="sxs-lookup"><span data-stu-id="9da5c-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="9da5c-187">लौटाने के प्रकार की जांच करने के लिए, आप उस परिचालन के लिए वस्तुओं को सुरक्षित रूप से [API विवरण पृष्ठ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) पर निर्दिष्ट प्रकारों में डाल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="9da5c-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="9da5c-188">यदि अनुरोध पर अधिक जानकारी चाहिए, तो अधूरी प्रतिक्रिया ऑब्जेक्ट तक पहुंचने के लिए **http संदेश विधियों** का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="9da5c-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="9da5c-189">NodeJS पैकेज</span><span class="sxs-lookup"><span data-stu-id="9da5c-189">NodeJS package</span></span>

<span data-ttu-id="9da5c-190">NPM के जरिए उपलब्ध NodeJS क्लाइंट लाइब्रेरी का उपयोग करें: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="9da5c-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="9da5c-191">Python पैकेज</span><span class="sxs-lookup"><span data-stu-id="9da5c-191">Python package</span></span>

<span data-ttu-id="9da5c-192">PyPi के जरिए Python क्लाइंट लाइब्रेरी को उपयोग करें: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="9da5c-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
