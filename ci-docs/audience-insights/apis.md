---
title: API के साथ काम करें
description: API का उपयोग करें और सीमाओं को समझें.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304744"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="b29f4-103">Customer Insights API के साथ काम करें</span><span class="sxs-lookup"><span data-stu-id="b29f4-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="b29f4-104">Dynamics 365 Customer Insights, Customer Insights में आपके डेटा के आधार पर आपके स्वयं के अनुप्रयोग बनाने के लिए API प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="b29f4-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b29f4-105">इन API के विवरण, [Customer Insights API संदर्भ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) पर सूचीबद्ध हैं।</span><span class="sxs-lookup"><span data-stu-id="b29f4-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="b29f4-106">उनमें परिचालनों, मापदंडों और प्रतिक्रियाओं के बारे में अतिरिक्त जानकारी शामिल हैं.</span><span class="sxs-lookup"><span data-stu-id="b29f4-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="b29f4-107">यह आलेख वर्णन करता है कि Customer Insights API तक कैसे पहुँचें, एक Azure ऐप पंजीकरण कैसे बनाएँ, और उपलब्ध क्लाइंट लाइब्रेरी के साथ आरंभ करें।</span><span class="sxs-lookup"><span data-stu-id="b29f4-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="b29f4-108">Customer Insights API आज़माना शुरू करें</span><span class="sxs-lookup"><span data-stu-id="b29f4-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="b29f4-109">Customer Insights से [साइन-इन](https://home.ci.ai.dynamics.com) करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="b29f4-110">यदि आपके पास अभी तक कोई सदस्यता नहीं है, तो [Customer Insights के परीक्षण के लिए साइन अप करें](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="b29f4-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="b29f4-111">अपने Customer Insights परिवेश में API को सक्षम करने के लिए, **व्यवस्थापक** > **अनुमतियाँ** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="b29f4-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="b29f4-112">आपको ऐसा करने के लिए व्यवस्थापक अनुमतियाँ चाहिए होगी.</span><span class="sxs-lookup"><span data-stu-id="b29f4-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="b29f4-113">**API** टैब पर जाएं और **सक्षम करें** बटन चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="b29f4-114">API को सक्षम करना आपके उदाहरण के लिए प्राथमिक और द्वितीयक सदस्यता कुंजी बनाता है, जिनको API अनुरोधों में उपयोग किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="b29f4-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="b29f4-115">आप **व्यवस्थापक** > **अनुमतियाँ** > **API** में **प्राइमरी रीजेनरेट करें** या **सेकेंडरी रीजेनरेट करें** का चयन करके कुंजियों को फिर से हासिल कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b29f4-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights APIs सक्षम करें":::

1. <span data-ttu-id="b29f4-117">**API आजमाएं** के लिए [हमारे API एक्सप्लोर करें](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="b29f4-118">एक API परिचालन चुनें और **इसे आज़माएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="b29f4-119">बगल के फलक में, मान को **अंतर्निहित** करने के लिए **अधिकृत करें** ड्रॉपडाउन मेनू में सेट करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="b29f4-120">`Authorization` हेडर एक बियरर टोकन के साथ जुड़ जाता है।</span><span class="sxs-lookup"><span data-stu-id="b29f4-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="b29f4-121">आपकी सदस्यता कुंजी स्वचालित रूप से पाप्यूलेट हो जाएगी.</span><span class="sxs-lookup"><span data-stu-id="b29f4-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="b29f4-122">वैकल्पिक रूप से, सभी आवश्यक क्वेरी मापदंड जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="b29f4-123">साइड फलक के नीचे स्क्रॉल करें और **भेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="b29f4-124">जल्द ही HTTP प्रतिक्रिया नीचे दिखाई देगी.</span><span class="sxs-lookup"><span data-stu-id="b29f4-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="API का परीक्षण कैसे करें।":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="b29f4-126">Azure पोर्टल में एक नया अनुप्रयोग पंजीकरण बनाएं</span><span class="sxs-lookup"><span data-stu-id="b29f4-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="b29f4-127">ये चरण आपको सौंपी गईं अनुमतियों का उपयोग करके Azure अनुप्रयोग में Customer Insights API का उपयोग शुरू करने में मदद करते हैं.</span><span class="sxs-lookup"><span data-stu-id="b29f4-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="b29f4-128">पहले [अनुभाग आरंभ करना](#get-started-trying-the-customer-insights-apis) को पूरा करना सुनिश्चित करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="b29f4-129">उस खाते के साथ [Azure पोर्टल](https://portal.azure.com) में साइन इन करें जो Customer Insights डेटा तक पहुंच सकता है.</span><span class="sxs-lookup"><span data-stu-id="b29f4-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="b29f4-130">बाईं ओर, **अनुप्रयोग पंजीकरण** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="b29f4-131">**नया पंजीकरण** चुनें, एक अनुप्रयोग का नाम दें और खाता प्रकार चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="b29f4-132">वैकल्पिक रूप से, एक रीडायरेक्ट URL जोड़ें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="b29f4-133">http://localhost आपके स्थानीय कंप्यूटर पर अनुप्रयोग बनाने के लिए पर्याप्त है.</span><span class="sxs-lookup"><span data-stu-id="b29f4-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="b29f4-134">अपने नए अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="b29f4-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="ऐप पंजीकरण में API अनुमतियां कैसे सेट करें।":::

1. <span data-ttu-id="b29f4-136">**एक अनुमति जोड़ें** चुनें और साइड फलक में **Customer Insights** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="b29f4-137">**अनुमति प्रकार** के लिये, **सौंपी गई अनुमतियाँ** चुनें और फिर **उपयोगकर्ता_प्रतिरूपण** अनुमति चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="b29f4-138">**अनुमतियाँ जोड़ें** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-138">Select **Add permissions**.</span></span> <span data-ttu-id="b29f4-139">यदि आपको उपयोगकर्ता द्वारा साइन इन किए बिना API तक पहुंचने की आवश्यकता है, तो [सर्वर-से-सर्वर अनुप्रयोग अनुमतियाँ](#server-to-server-application-permissions) अनुभाग की समीक्षा करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="b29f4-140">अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="b29f4-141">आप API में अपने अनुरोध के साथ बीयरर टोकन प्राप्त करने के लिए Microsoft Authentication Library (MSAL) के साथ इस अनुप्रयोग पंजीकरण के लिए अनुप्रयोग/क्लाइंट ID का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b29f4-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="व्यवस्थापक की सहमति कैसे दें.":::

<span data-ttu-id="b29f4-143">MSAL के बारे में अधिक जानकारी के लिए, [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) देखें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="b29f4-144">Azure में ऐप पंजीकरण के बारे में अधिक जानकारी के लिए, [एक अनुप्रयोग पंजीकृत करें](/azure/active-directory/develop/quickstart-register-app.md#register-an-application) देखें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="b29f4-145">हमारे क्लाइंट लाइब्रेरी में API का उपयोग करने के बारे में जानकारी के लिए, [Customer Insights क्लाइंट लाइब्रेरी](#customer-insights-client-libraries) देखें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="b29f4-146">सर्वर-से-सर्वर अनुप्रयोग अनुमतियाँ</span><span class="sxs-lookup"><span data-stu-id="b29f4-146">Server-to-server application permissions</span></span>

<span data-ttu-id="b29f4-147">[अनुप्रयोग पंजीकरण अनुभाग](#create-a-new-app-registration-in-the-azure-portal) यह बताता है कि ऐसे अनुप्रयोग को कैसे पंजीकृत करना है जो प्रमाणीकरण के लिए उपयोगकर्ता को साइन इन करना आवश्यक करता है.</span><span class="sxs-lookup"><span data-stu-id="b29f4-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="b29f4-148">ऐसा अनुप्रयोग पंजीकरण बनाना सीखें, जिसके लिए उपयोगकर्ता का इंटरेक्शन आवश्यक नहीं है और इसे सर्वर पर चलाया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="b29f4-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="b29f4-149">Azure पोर्टल में अपने अनुप्रयोग पंजीकरण पर, **API अनुमतियाँ** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="b29f4-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="b29f4-150">**अनुमति जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="b29f4-151">**मेरे संगठन द्वारा उपयोग किए जाने वाले API** टैब चुनें और सूची से **Customer Insights के  लिए Dynamics 365 AI** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="b29f4-152">**अनुमति प्रकार** के लिये, **अनुप्रयोग अनुमतियाँ** चुनें और फिर **CustomerInsights.Api.All** अनुमति चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="b29f4-153">**अनुमतियाँ जोड़ें** चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="b29f4-154">अपने अनुप्रयोग पंजीकरण के लिए **API अनुमतियाँ** पर वापस जाएं.</span><span class="sxs-lookup"><span data-stu-id="b29f4-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="b29f4-155">अनुप्रयोग पंजीकरण को पूरा करने के लिए **... के लिए व्यवस्थापक सहमति की अनुमति दें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="व्यवस्थापक की सहमति कैसे दें.":::

1. <span data-ttu-id="b29f4-157">पूरा करने के लिए, हमें Customer Insights में अनुप्रयोग पंजीकरण का नाम एक उपयोगकर्ता के रूप में जोड़ना होगा.</span><span class="sxs-lookup"><span data-stu-id="b29f4-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="b29f4-158">Customer Insights खोलें, **व्यवस्थापक** > **अनुमतियाँ** पर जाएं और **उपयोगकर्ता जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="b29f4-159">अपने अनुप्रयोग पंजीकरण के नाम को खोजें, इसे खोज परिणामों से चुनें, और **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="b29f4-160">Customer Insights क्‍लाइंट लाइब्रेरी</span><span class="sxs-lookup"><span data-stu-id="b29f4-160">Customer Insights client libraries</span></span>

<span data-ttu-id="b29f4-161">यह अनुभाग आपको Customer Insights API के लिए उपलब्ध क्लाइंट लाइब्रेरी इस्तेमाल करने में मदद करता है.</span><span class="sxs-lookup"><span data-stu-id="b29f4-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="b29f4-162">सभी लाइब्रेरी स्रोत कोड और नमूना एप्लिकेशन [Customer Insights GitHub पेज](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) पर देखे जा सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b29f4-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="b29f4-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="b29f4-163">C# NuGet</span></span>

<span data-ttu-id="b29f4-164">NuGet.org से C# क्लाइंट लाइब्रेरी का उपयोग शुरू करने का तरीका जानें. NuGet पैकेज के बारे में अधिक जानकारी के लिए, [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) देखें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="b29f4-165">फिलहाल, यह पैकेज netstandard2.0 और netcoreapp2.0 फ्रेमवर्क को लक्षित करता है.</span><span class="sxs-lookup"><span data-stu-id="b29f4-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="b29f4-166">C# क्लाइंट लाइब्रेरी को C# प्रोजेक्ट में जोड़ें</span><span class="sxs-lookup"><span data-stu-id="b29f4-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="b29f4-167">Visual Studio में, अपने प्रोजेक्ट के लिए **NuGet पैकेज प्रबंधक** खोलें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="b29f4-168">**Microsoft.Dynamics.CustomerInsights.Api** को खोजें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="b29f4-169">प्रोजेक्ट में पैकेज जोड़ने के लिए **इंस्टॉल करें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="b29f4-170">वैकल्पिक रूप से, इस कमांड को **NuGet पैकेज प्रबंधक कंसोल में चलाएं**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="b29f4-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Visual Studio प्रोजेक्ट में NuGet पैकेज जोड़ें":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="b29f4-172">C# क्लाइंट लाइब्रेरी का उपयोग करें</span><span class="sxs-lookup"><span data-stu-id="b29f4-172">Use the C# client library</span></span>

1. <span data-ttu-id="b29f4-173">अपने मौजूदा [Azure अनुप्रयोग पंजीकरण](#create-a-new-app-registration-in-the-azure-portal) का उपयोग करके `AccessToken` पाने के लिए [Microsoft प्रमाणीकरण लाइब्रेरी(MSAL)](/azure/active-directory/develop/msal-overview) का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="b29f4-174">एक टोकन को सफलतापूर्वक प्रमाणित करने और हासिल करने के बाद, एक नया बनाएं या मौजूदा `HttpClient` के साथ अतिरिक्त **DefaultRequestHeaders "प्राधिकरण"** सेट को **धारक <access token>** और **Ocp-Apim-Subscription-Key** सेट से [अपने Customer Insights परिवेश से **सदस्यता कुंजी**](#get-started-trying-the-customer-insights-apis) को उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="b29f4-175">उपयुक्त होने पर **प्राधिकरण** हेडर को रीसेट करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="b29f4-176">उदाहरण के लिए, जब टोकन समाप्त हो गया है.</span><span class="sxs-lookup"><span data-stu-id="b29f4-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="b29f4-177">इस `HttpClient` को `CustomerInsights` क्लाइंट के निर्माण में पास करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient का नमूना":::

1. <span data-ttu-id="b29f4-179">"एक्सटेंशन विधियों" के लिए क्लाइंट के साथ कॉल करें"—उदाहरण के लिए, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="b29f4-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="b29f4-180">यदि अंतर्निहित `Microsoft.Rest.HttpOperationResponse` को एक्सेस करने को प्राथमिकता दी जाती है, तो "http संदेश विधियों" का उपयोग करें"—उदाहरण के लिए, `GetAllInstancesWithHttpMessagesAsync`।</span><span class="sxs-lookup"><span data-stu-id="b29f4-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="b29f4-181">प्रतिक्रिया शायद `object` प्रकार की होगी, क्योंकि विधि कई प्रकारों को लौटा सकती है (उदाहरण के लिए, `IList<InstanceInfo>` and \`\`ApiErrorResult\`).</span><span class="sxs-lookup"><span data-stu-id="b29f4-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="b29f4-182">लौटाने के प्रकार की जांच करने के लिए, आप उस परिचालन के लिए वस्तुओं को सुरक्षित रूप से [API विवरण पृष्ठ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) पर निर्दिष्ट प्रकारों में डाल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="b29f4-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="b29f4-183">यदि अनुरोध पर अधिक जानकारी चाहिए, तो अधूरी प्रतिक्रिया ऑब्जेक्ट तक पहुंचने के लिए **http संदेश विधियों** का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="b29f4-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="b29f4-184">NodeJS पैकेज</span><span class="sxs-lookup"><span data-stu-id="b29f4-184">NodeJS package</span></span>

<span data-ttu-id="b29f4-185">NPM के जरिए उपलब्ध NodeJS क्लाइंट लाइब्रेरी का उपयोग करें: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="b29f4-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="b29f4-186">Python पैकेज</span><span class="sxs-lookup"><span data-stu-id="b29f4-186">Python package</span></span>

<span data-ttu-id="b29f4-187">PyPi के जरिए Python क्लाइंट लाइब्रेरी को उपयोग करें: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="b29f4-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
