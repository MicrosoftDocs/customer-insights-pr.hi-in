---
title: API के साथ काम करें
description: API का उपयोग करें और सीमाओं को समझें.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689132"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="fae19-103">Customer Insights API के साथ काम करें</span><span class="sxs-lookup"><span data-stu-id="fae19-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="fae19-104">Dynamics 365 Customer Insights आपको Customer Insights में डेटा के आधार पर आपके स्वयं के अनुप्रयोग बनाने के लिए API देता है.</span><span class="sxs-lookup"><span data-stu-id="fae19-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fae19-105">इन API के विवरण, [Customer Insights API संदर्भ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) पर सूचीबद्ध हैं.</span><span class="sxs-lookup"><span data-stu-id="fae19-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="fae19-106">उनमें परिचालनों, मापदंडों और प्रतिक्रियाओं के बारे में अतिरिक्त जानकारी शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="fae19-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="fae19-107">यह आलेख आपको Customer Insights API तक पहुंचने के लिए मार्गदर्शन करता है, Azure अनुप्रयोग पंजीकरण बनाता है, और उपलब्ध क्लाइंट लाइब्रेरी के साथ शुरू करने में आपकी सहायता करता है.</span><span class="sxs-lookup"><span data-stu-id="fae19-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="fae19-108">Customer Insights API आज़माना शुरू करें</span><span class="sxs-lookup"><span data-stu-id="fae19-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="fae19-109">Customer Insights से [साइन-इन](https://home.ci.ai.dynamics.com) करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="fae19-110">यदि आपके पास अभी तक कोई सदस्यता नहीं है, तो [Customer Insights के परीक्षण के लिए साइन अप करें](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="fae19-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="fae19-111">अपने Customer Insights परिवेश में API को सक्षम करने के लिए, **व्यवस्थापक** >  **अनुमतियाँ** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="fae19-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="fae19-112">आपको ऐसा करने के लिए व्यवस्थापक अनुमतियाँ चाहिए होगी.</span><span class="sxs-lookup"><span data-stu-id="fae19-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="fae19-113">**API** टैब पर जाएं और **सक्षम करें** बटन चुनें.</span><span class="sxs-lookup"><span data-stu-id="fae19-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="fae19-114">API को सक्षम करना आपके उदाहरण के लिए प्राथमिक और द्वितीयक सदस्यता कुंजी बनाता है, जिनको API अनुरोधों में उपयोग किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="fae19-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="fae19-115">आप **व्यवस्थापक** > **अनुमतियाँ** > **API** में **प्राइमरी रीजेनरेट करें** या **सेकेंडरी रीजेनरेट करें** का चयन करके कुंजियों को फिर से हासिल कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fae19-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights APIs सक्षम करें":::

1. <span data-ttu-id="fae19-117">API आज़माने के लिए **हमारे API की छानबीन करें** को चुनें.</span><span class="sxs-lookup"><span data-stu-id="fae19-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="fae19-118">एक API परिचालन चुनें और **इसे आज़माएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fae19-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="fae19-119">साइड के फलक में, **निहित** करने के लिए मान को **प्राधिकरण** ड्रॉप-डाउन मेनू में सेट करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="fae19-120">`Authorization`प्राधिकरण\` हेडर एक बीयरर टोकन के साथ जुड़ जाता है.</span><span class="sxs-lookup"><span data-stu-id="fae19-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="fae19-121">आपकी सदस्यता कुंजी स्वचालित रूप से पाप्यूलेट हो जाएगी.</span><span class="sxs-lookup"><span data-stu-id="fae19-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="fae19-122">वैकल्पिक रूप से, सभी आवश्यक क्वेरी मापदंड जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="fae19-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="fae19-123">साइड फलक के नीचे स्क्रॉल करें और **भेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fae19-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="fae19-124">जल्द ही HTTP प्रतिक्रिया नीचे दिखाई देगी.</span><span class="sxs-lookup"><span data-stu-id="fae19-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="fae19-125">Azure पोर्टल में एक नया अनुप्रयोग पंजीकरण बनाएं</span><span class="sxs-lookup"><span data-stu-id="fae19-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="fae19-126">ये चरण आपको Customer Insights API का उपयोग करके Azure अनुप्रयोग में प्रत्यायोजित अनुमतियों का उपयोग करना शुरू करने में मदद करते हैं.</span><span class="sxs-lookup"><span data-stu-id="fae19-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="fae19-127">सुनिश्चित करें कि [शुरू करें अनुभाग](#get-started-trying-the-customer-insights-apis) पहले ही पूरा कर लिया जाता है.</span><span class="sxs-lookup"><span data-stu-id="fae19-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="fae19-128">उस खाते के साथ [Azure पोर्टल](https://portal.azure.com) में साइन इन करें जो Customer Insights डेटा तक पहुंच सकता है.</span><span class="sxs-lookup"><span data-stu-id="fae19-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="fae19-129">बाईं ओर, **अनुप्रयोग पंजीकरण** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fae19-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="fae19-130">**नया पंजीकरण** चुनें एक एप्लिकेशन का नाम दें और खाता प्रकार चुनें.</span><span class="sxs-lookup"><span data-stu-id="fae19-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="fae19-131">वैकल्पिक रूप से, एक रीडायरेक्ट URL जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="fae19-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="fae19-132">http://localhost आपके स्थानीय कंप्यूटर पर अनुप्रयोग बनाने के लिए पर्याप्त है.</span><span class="sxs-lookup"><span data-stu-id="fae19-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="fae19-133">अपने नए अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="fae19-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="fae19-134">**एक अनुमति जोड़ें** चुनें और साइड फलक में **Customer Insights** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="fae19-135">**अनुमति प्रकार** के लिए, **मान्य अनुमतियाँ** का चयन करें और **user_impersonation** अनुमति का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="fae19-136">**अनुमतियाँ जोड़ें** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-136">Select **Add permissions**.</span></span> <span data-ttu-id="fae19-137">यदि आपको उपयोगकर्ता द्वारा साइन इन किए बिना API तक पहुंचने की आवश्यकता है, तो [सर्वर-से-सर्वर अनुप्रयोग अनुमतियाँ](#server-to-server-application-permissions) अनुभाग की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="fae19-138">अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="fae19-139">आप API में अपने अनुरोध के साथ बीयरर टोकन प्राप्त करने के लिए Microsoft Authentication Library (MSAL) के साथ इस अनुप्रयोग पंजीकरण के लिए अनुप्रयोग/क्लाइंट ID का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fae19-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="fae19-140">MSAL के बारे में अधिक जानकारी के लिए, [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) देखें.</span><span class="sxs-lookup"><span data-stu-id="fae19-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="fae19-141">Azure में अनुप्रयोग पंजीकरण के बारे में अधिक जानकारी के लिए, [नया Azure पोर्टल अनुप्रयोग पंजीकरण अनुभव](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide) देखें.</span><span class="sxs-lookup"><span data-stu-id="fae19-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="fae19-142">API की हमारी क्लाइंट लाइब्रेरी का उपयोग करने के बारे में जानकारी के लिए, [Customer Insights क्लाइंट लाइब्रेरी](#customer-insights-client-libraries) देखें.</span><span class="sxs-lookup"><span data-stu-id="fae19-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="fae19-143">सर्वर-से-सर्वर अनुप्रयोग अनुमतियाँ</span><span class="sxs-lookup"><span data-stu-id="fae19-143">Server-to-server application permissions</span></span>

<span data-ttu-id="fae19-144">[अनुप्रयोग पंजीकरण अनुभाग](#create-a-new-app-registration-in-the-azure-portal) यह बताता है कि ऐसे अनुप्रयोग को कैसे पंजीकृत करना है जो प्रमाणीकरण के लिए उपयोगकर्ता को साइन इन करना आवश्यक करता है.</span><span class="sxs-lookup"><span data-stu-id="fae19-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="fae19-145">ऐसा अनुप्रयोग पंजीकरण बनाना सीखें, जिसके लिए उपयोगकर्ता का इंटरेक्शन आवश्यक नहीं है और इसे सर्वर पर चलाया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="fae19-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="fae19-146">Azure पोर्टल में अपने अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="fae19-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="fae19-147">**एक अनुमति जोड़ें** चुनें और साइड फलक में **Customer Insights** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="fae19-148">**अनुमति प्रकार** के लिए, **एप्लिकेशन अनुमतियाँ** का चयन करें और **CustomerInsights.Api.All** अनुमतियों को चुनें.</span><span class="sxs-lookup"><span data-stu-id="fae19-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="fae19-149">**अनुमतियाँ जोड़ें** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="fae19-150">इस अनुप्रयोग की अनुमति पर व्यवस्थापक की सहमति देने के लिए, आपको एक सर्विस प्रिंसिपल को जोड़ना होगा.</span><span class="sxs-lookup"><span data-stu-id="fae19-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="fae19-151">Azure Active Directory (AD) PowerShell मॉड्यूल स्थापित करें: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="fae19-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="fae19-152">अपने AD खाते से कनेक्ट करें: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="fae19-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="fae19-153">आप अपनी टेनेंट ID **अवलोकन** > **Azure Active Directory** पर पा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fae19-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="fae19-154">Azure AD सर्विस प्रिंसिपल को जोड़ने के लिए निम्नलिखित कमांड चलाएं: \`\`New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"\` AppId मापदंड Customer Insights API अनुप्रयोग से संबंधित है.</span><span class="sxs-lookup"><span data-stu-id="fae19-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="सर्विस प्रिंसिपल नमूना":::

1. <span data-ttu-id="fae19-156">अपने अनुप्रयोग पंजीकरण के लिए **API अनुमतियाँ** पर वापस जाएं.</span><span class="sxs-lookup"><span data-stu-id="fae19-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="fae19-157">अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="fae19-158">पूरा करने के लिए, हमें Customer Insights में अनुप्रयोग पंजीकरण का नाम एक उपयोगकर्ता के रूप में जोड़ना होगा.</span><span class="sxs-lookup"><span data-stu-id="fae19-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="fae19-159">Customer Insights खोलें, **व्यवस्थापक** > **अनुमतियाँ** पर जाएं और **उपयोगकर्ता जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fae19-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="fae19-160">अपने अनुप्रयोग पंजीकरण के नाम को खोजें, इसे खोज परिणामों से चुनें, और **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="fae19-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="fae19-161">Customer Insights क्‍लाइंट लाइब्रेरी</span><span class="sxs-lookup"><span data-stu-id="fae19-161">Customer Insights client libraries</span></span>

<span data-ttu-id="fae19-162">यह अनुभाग आपको Customer Insights API के लिए उपलब्ध क्लाइंट लाइब्रेरी इस्तेमाल करने में मदद करता है.</span><span class="sxs-lookup"><span data-stu-id="fae19-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="fae19-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="fae19-163">C# NuGet</span></span>

<span data-ttu-id="fae19-164">NuGet.org से C# क्लाइंट लाइब्रेरी का उपयोग शुरू करने का तरीका जानें. NuGet पैकेज के बारे में अधिक जानकारी के लिए, [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) देखें.</span><span class="sxs-lookup"><span data-stu-id="fae19-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="fae19-165">फिलहाल, यह पैकेज netstandard2.0 और netcoreapp2.0 फ्रेमवर्क को लक्षित करता है.</span><span class="sxs-lookup"><span data-stu-id="fae19-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="fae19-166">C# क्लाइंट लाइब्रेरी को C# प्रोजेक्ट में जोड़ें</span><span class="sxs-lookup"><span data-stu-id="fae19-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="fae19-167">Visual Studio में, अपने प्रोजेक्ट के लिए **NuGet पैकेज प्रबंधक** खोलें.</span><span class="sxs-lookup"><span data-stu-id="fae19-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="fae19-168">**Microsoft.Dynamics.CustomerInsights.Api** को खोजें.</span><span class="sxs-lookup"><span data-stu-id="fae19-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="fae19-169">प्रोजेक्ट में पैकेज जोड़ने के लिए **इंस्टॉल करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="fae19-170">वैकल्पिक रूप से, इस कमांड को **NuGet पैकेज प्रबंधक कंसोल में चलाएं**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="fae19-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Visual Studio प्रोजेक्ट में NuGet पैकेज जोड़ें":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="fae19-172">C# क्लाइंट लाइब्रेरी का उपयोग करें</span><span class="sxs-lookup"><span data-stu-id="fae19-172">Use the C# client library</span></span>

1. <span data-ttu-id="fae19-173">अपने मौजूदा [Azure अनुप्रयोग पंजीकरण](#create-a-new-app-registration-in-the-azure-portal) का उपयोग करके `AccessToken` पाने के लिए [Microsoft प्रमाणीकरण लाइब्रेरी(MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="fae19-174">एक टोकन को सफलतापूर्वक प्रमाणित करने और हासिल करने के बाद, एक नया बनाएं या मौजूदा `HttpClient` के साथ अतिरिक्त **DefaultRequestHeaders "प्राधिकरण"** सेट को **धारक <access token>** और **Ocp-Apim-Subscription-Key** सेट से [अपने Customer Insights परिवेश से **सदस्यता कुंजी**](#get-started-trying-the-customer-insights-apis) को उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="fae19-175">उपयुक्त होने पर **प्राधिकरण** हेडर को रीसेट करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="fae19-176">उदाहरण के लिए, जब टोकन समाप्त हो गया है.</span><span class="sxs-lookup"><span data-stu-id="fae19-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="fae19-177">इस `HttpClient` को `CustomerInsights` क्लाइंट के निर्माण में पास करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient का नमूना":::

1. <span data-ttu-id="fae19-179">"एक्सटेंशन विधियों" के लिए क्लाइंट के साथ कॉल करें, उदाहरण के लिए, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="fae19-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="fae19-180">यदि अंतर्निहित `Microsoft.Rest.HttpOperationResponse` को एक्सेस करने को प्राथमिकता दी जाती है, तो "http संदेश विधियों" का उपयोग करें, उदाहरण के लिए `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="fae19-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="fae19-181">प्रतिक्रिया शायद `object` प्रकार की होगी, क्योंकि विधि कई प्रकारों को लौटा सकती है (उदाहरण के लिए, `IList<InstanceInfo>` and \`\`ApiErrorResult\`).</span><span class="sxs-lookup"><span data-stu-id="fae19-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="fae19-182">लौटाने के प्रकार की जांच करने के लिए, आप उस परिचालन के लिए वस्तुओं को सुरक्षित रूप से [API विवरण पृष्ठ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) पर निर्दिष्ट प्रकारों में डाल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="fae19-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="fae19-183">यदि अनुरोध पर अधिक जानकारी चाहिए, तो अधूरी प्रतिक्रिया ऑब्जेक्ट तक पहुंचने के लिए **http संदेश विधियों** का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="fae19-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>
