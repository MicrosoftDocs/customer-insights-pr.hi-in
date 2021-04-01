---
title: एक सर्विस प्रिंसिपल के साथ एक Azure Data Lake Storage Gen2 खाते से कनेक्ट करें
description: ऑडिएंस इनसाइट्स से जुड़ते समय अपने खुद के Data Lake से कनेक्ट करने के लिए ऑडिएंस इनसाइट्स के लिए एक Azure service principal का उपयोग करें.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596501"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="43401-103">ऑडियंस इनसाइट्स के लिए एक Azure service principal के साथ एक Azure Data Lake Storage Gen2 खाते से कनेक्ट करें</span><span class="sxs-lookup"><span data-stu-id="43401-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="43401-104">Azure सेवाओं का उपयोग करने वाले स्वचालित उपकरणों में हमेशा प्रतिबंधित अनुमतियां होनी चाहिए.</span><span class="sxs-lookup"><span data-stu-id="43401-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="43401-105">एक पूरी तरह से विशेषाधिकार प्राप्त उपयोगकर्ता के रूप में एप्लिकेशन पर हस्ताक्षर करने के बजाय, Azure सर्विस प्रिंसिपल्स को प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="43401-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="43401-106">स्टोरेज खाते की कुंजी के बजाय एक Azure service principal का उपयोग करके एक Azure Data Lake Storage Gen2 खाते के साथ ऑडियंस इनसाइट्स को जोड़ने के तरीके जानने के लिए, पढ़ें.</span><span class="sxs-lookup"><span data-stu-id="43401-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="43401-107">आप सर्विस प्रिंसिपल का उपयोग सुरक्षित रूप से [डेटा स्रोत के रूप में एक सामान्य डेटा मॉडल फ़ोल्डर को जोड़ें या संपादित करें](connect-common-data-model.md) या [एक नया बनाएं या मौजूदा परिवेश को अपडेट करें](manage-environments.md#create-an-environment-in-an-existing-organization) करने के लिए कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="43401-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="43401-108">Azure Data Lake Gen2 स्टोरेज खाता, जो सेवा सिद्धांत का उपयोग करने का इरादा रखता है, उसके पास [पदानुक्रमित नाम स्थान (HNS) सक्षम होना चाहिए](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="43401-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="43401-109">आपको सर्विस प्रिंसिपल बनाने के लिए अपनी Azure सदस्यता के लिए व्यवस्थापक अनुमतियों की आवश्यकता है.</span><span class="sxs-lookup"><span data-stu-id="43401-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="43401-110">ऑडियंस इनसाइट्स के लिए Azure service principal बनाएं</span><span class="sxs-lookup"><span data-stu-id="43401-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="43401-111">ऑडियंस इनसाइट्स के लिए एक नया सर्विस प्रिंसिपल बनाने से पहले, यह जांच लें कि क्या यह आपके संगठन में पहले से मौजूद है.</span><span class="sxs-lookup"><span data-stu-id="43401-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="43401-112">एक मौजूदा सेवा प्रिंसिपल की तलाश करें</span><span class="sxs-lookup"><span data-stu-id="43401-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="43401-113">[Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं और अपने संगठन में हस्ताक्षर करें.</span><span class="sxs-lookup"><span data-stu-id="43401-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="43401-114">Azure सेवाओं से **Azure Active Directory** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="43401-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="43401-115">**प्रबंधित करें** के अंतर्गत, **एंटरप्राइज़ अनुप्रयोग** चुनें.</span><span class="sxs-lookup"><span data-stu-id="43401-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="43401-116">ऑडियंस इनसाइट्स की पहली पार्टी एप्लिकेशन ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` या `Dynamics 365 AI for Customer Insights`' के लिए नाम को खोजें.</span><span class="sxs-lookup"><span data-stu-id="43401-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="43401-117">अगर आपको कोई मिलता-जुलता रिकॉर्ड मिलता है, तो इसका मतलब है कि ऑडियंस इनसाइट्स के लिए सर्विस प्रिंसिपल मौजूद है.</span><span class="sxs-lookup"><span data-stu-id="43401-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="43401-118">आपको इसे फिर से बनाने की आवश्यकता नहीं है.</span><span class="sxs-lookup"><span data-stu-id="43401-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="मौजूदा सर्विस प्रिंसिपल दिखाता स्क्रीनशॉट.":::
   
6. <span data-ttu-id="43401-120">यदि कोई परिणाम वापस नहीं आता है, तो एक नया सर्विस प्रिंसिपल बनाएं.</span><span class="sxs-lookup"><span data-stu-id="43401-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="43401-121">नया सर्विस प्रिंसिपल बनाएँ</span><span class="sxs-lookup"><span data-stu-id="43401-121">Create a new service principal</span></span>

1. <span data-ttu-id="43401-122">**ग्राफ के लिए Azure Active Directory PowerShell** का नवीनतम संस्करण इंस्टॉल करें.</span><span class="sxs-lookup"><span data-stu-id="43401-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="43401-123">अधिक जानकारी के लिए, देखें [ग्राफ के लिए Azure Active Directory PowerShell इंस्टॉल करें](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="43401-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="43401-124">अपने पीसी पर, अपने कीबोर्ड पर विंडोज कुंजी का चयन करें और **विंडोज PowerShell** और **प्रशासक के रूप में चलाएं** के लिए खोज करें.</span><span class="sxs-lookup"><span data-stu-id="43401-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="43401-125">खुले PowerShell विंडो में, `Install-Module AzureAD` दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="43401-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="43401-126">Azure AD PowerShell मॉड्यूल के साथ ऑडियंस इनसाइट्स के लिए सर्विस प्रिंसिपल बनाएं.</span><span class="sxs-lookup"><span data-stu-id="43401-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="43401-127">PowerShell विंडो में, `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="43401-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="43401-128">"अपनी टेनेंट ID" को अपने टेनेंट की वास्तविक ID से बदलें जहां आप सर्विस प्रिंसिपल बनाना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="43401-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="43401-129">परिवेश नाम पैरामीटर `AzureEnvironmentName` वैकल्पिक है.</span><span class="sxs-lookup"><span data-stu-id="43401-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="43401-130">`New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="43401-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="43401-131">यह आदेश चयनित टेनेंट पर ऑडियंस इनसाइट्स के लिए सर्विस प्रिंसिपल बनाता है.</span><span class="sxs-lookup"><span data-stu-id="43401-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="43401-132">स्टोरेज खाते तक पहुंचने के लिए सर्विस प्रिंसिपल को अनुमति प्रदान करें</span><span class="sxs-lookup"><span data-stu-id="43401-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="43401-133">ऑडियंस इनसाइट्स में अपने मनचाहे स्टोरेज खाते का उपयोग करने हेतु सर्विस प्रिंसिपल को अनुमति देने के लिए Azure पोर्टल पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="43401-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="43401-134">[Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं और अपने संगठन में हस्ताक्षर करें.</span><span class="sxs-lookup"><span data-stu-id="43401-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="43401-135">वह स्टोरेज खाता खोलें जिसकी आप ऑडियंस इनसाइट्स के लिए सर्विस प्रिंसिपल तक पहुंच चाहते हो.</span><span class="sxs-lookup"><span data-stu-id="43401-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="43401-136">नेविगेशन फलक से **एक्सेस कंट्रोल (IAM)** चुनें और **जोड़ें** > **भूमिका असाइनमेंट जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="43401-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="भूमिका असाइनमेंट जोड़ते समय Azure पोर्टल दिखाता स्क्रिनशॉट.":::
   
1. <span data-ttu-id="43401-138">**भूमिका असाइनमेंट को जोड़ें** फलक में, निम्नलिखित गुणों को सेट करें:</span><span class="sxs-lookup"><span data-stu-id="43401-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="43401-139">भूमिका: *स्टोरेज ब्लॉब डेटा योगदानकर्ता*</span><span class="sxs-lookup"><span data-stu-id="43401-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="43401-140">एक्सेस असाइन करें: *उपयोगकर्ता, समूह या सर्विस प्रिंसिपल* को</span><span class="sxs-lookup"><span data-stu-id="43401-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="43401-141">चुनें: *Customer Insights के लिए Dynamics 365 AI* ( [आपके द्वारा बनाए गए सर्विस प्रिंसिपल](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="43401-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="43401-142">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="43401-142">Select **Save**.</span></span>

<span data-ttu-id="43401-143">बदलावों के प्रचार-प्रसार में 15 मिनट तक का समय लग सकता है.</span><span class="sxs-lookup"><span data-stu-id="43401-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="43401-144">ऑडियंस इनसाइट्स के लिए स्टोरेज खाता संलग्नक में Azure संसाधन ID या Azure सदस्यता विवरण दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="43401-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="43401-145">ऑडियंस इनसाइट्स में एक Azure Data Lake स्टोरेज खाता संलग्न करें [स्टोर आउटपुट डेटा](manage-environments.md) या [इसे डेटा स्रोत के रूप में उपयोग करें](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="43401-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="43401-146">Azure Data Lake विकल्प चुनने से आप संसाधन-आधारित या सदस्यता-आधारित दृष्टिकोण के बीच चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="43401-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="43401-147">चयनित दृष्टिकोण के बारे में आवश्यक जानकारी प्रदान करने के लिए नीचे दिए गए चरणों का पालन करें.</span><span class="sxs-lookup"><span data-stu-id="43401-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="43401-148">संसाधन-आधारित स्टोरेज खाता कनेक्शन</span><span class="sxs-lookup"><span data-stu-id="43401-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="43401-149">[Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं, अपनी सदस्यता पर साइन इन करें और स्टोरेज खाता खोलें.</span><span class="sxs-lookup"><span data-stu-id="43401-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="43401-150">नेविगेशन फलक पर **सेटिंग्स** > **गुण** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="43401-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="43401-151">स्टोरेज खाता के संसाधन ID मान को कॉपी करें.</span><span class="sxs-lookup"><span data-stu-id="43401-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="स्टोरेज खाता के संसाधन ID को कॉपी करें.":::

1. <span data-ttu-id="43401-153">ऑडियंस इनसाइट्स में, स्टोरेज खाता कनेक्शन स्क्रीन में प्रदर्शित संसाधन फ़ील्ड में संसाधन ID डालें.</span><span class="sxs-lookup"><span data-stu-id="43401-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="स्टोरेज खाता के संसाधन ID सूचना को दर्ज करें.":::   
   
1. <span data-ttu-id="43401-155">स्टोरेज खाता को संलग्न करने के लिए ऑडियंस इनसाइट्स में बचे हुए चरण जारी रखें.</span><span class="sxs-lookup"><span data-stu-id="43401-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="43401-156">सदस्यता आधारित स्टोरेज खाता कनेक्शन</span><span class="sxs-lookup"><span data-stu-id="43401-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="43401-157">[Azure व्यवस्थापक पोर्टल](https://portal.azure.com) पर जाएं, अपनी सदस्यता पर साइन इन करें और स्टोरेज खाता खोलें.</span><span class="sxs-lookup"><span data-stu-id="43401-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="43401-158">नेविगेशन फलक पर **सेटिंग्स** > **गुण** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="43401-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="43401-159">स्टोरेज खाते के **सदस्यता**, **संसाधन समूह**, और **नाम** की समीक्षा करें ताकि यह सुनिश्चित किया जा सके कि आप ऑडियंस इनसाइट्स में सही मानों का चयन करते हैं.</span><span class="sxs-lookup"><span data-stu-id="43401-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="43401-160">ऑडियंस इनसाइट्स में, स्टोरेज खाता संलग्न करते समय मानों या संबंधित फ़ील्ड के लिए चुनाव करें.</span><span class="sxs-lookup"><span data-stu-id="43401-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="43401-161">स्टोरेज खाता को संलग्न करने के लिए ऑडियंस इनसाइट्स में बचे हुए चरण जारी रखें.</span><span class="sxs-lookup"><span data-stu-id="43401-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]