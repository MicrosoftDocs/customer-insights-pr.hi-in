---
title: Customer Insights डेटा Azure Synapse Analytics में निर्यात करें
description: Azure Synapse Analytics से कनेक्शन को कॉन्फ़िगर करने की विधि जानें.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977379"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="f4302-103">Azure Synapse Analytics में डेटा निर्यात करें (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="f4302-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="f4302-104">Azure Synapse विश्लेषण सेवा है, जो डेटा वेयरहाउस और बड़े डेटा सिस्टम में इनसाइट के लिए समय की गति को बढ़ाती है.</span><span class="sxs-lookup"><span data-stu-id="f4302-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="f4302-105">आप [Azure Synapse](/azure/synapse-analytics/overview-what-is) में अपने Customer Insights डेटा को अंतर्ग्रहित करके उसका उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f4302-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4302-106">पूर्वावश्यकताएँ</span><span class="sxs-lookup"><span data-stu-id="f4302-106">Prerequisites</span></span>

<span data-ttu-id="f4302-107">Customer Insights से Azure Synapse में कनेक्शन कॉन्फ़िगर करने के लिए निम्नलिखित पूर्वापेक्षाएं पूरी होनी चाहिए.</span><span class="sxs-lookup"><span data-stu-id="f4302-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="f4302-108">सुनिश्चित करें कि वर्णित सभी **भूमिका असाइनमेंट** सेट किए जाएं.</span><span class="sxs-lookup"><span data-stu-id="f4302-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="f4302-109">Customer Insights में पूर्वापेक्षाएं</span><span class="sxs-lookup"><span data-stu-id="f4302-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="f4302-110">ऑडियंस इनसाइट में आपकी **व्यवस्थापक** की भूमिका होती है.</span><span class="sxs-lookup"><span data-stu-id="f4302-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="f4302-111">[ऑडिएंस इनसाइट्स में उपयोगकर्ता अनुमतियां सेटिंग्स](permissions.md#assign-roles-and-permissions) के बारे में और अधिक जानें</span><span class="sxs-lookup"><span data-stu-id="f4302-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="f4302-112">Azure में:</span><span class="sxs-lookup"><span data-stu-id="f4302-112">In Azure:</span></span> 

- <span data-ttu-id="f4302-113">एक सक्रिय Azure सदस्यता.</span><span class="sxs-lookup"><span data-stu-id="f4302-113">An active Azure subscription.</span></span>

- <span data-ttu-id="f4302-114">यदि एक नए Azure Data Lake Storage Gen2 खाते का उपयोग कर रहे हैं, तो *ऑडिएंस इनसाइट के लिए सेवा प्रिंसिपल* को **स्टोरेज ब्लॉब डेटा योगदानकर्ता** अनुमतियों की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="f4302-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="f4302-115">[ऑडिएंस इनसाइट के लिए Azure सेवा प्रिंसिपल के साथ Azure Data Lake Storage Gen2 खाते से कनेक्ट करने](connect-service-principal.md) के बारे में और जानें.</span><span class="sxs-lookup"><span data-stu-id="f4302-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="f4302-116">Data Lake Storage Gen2 में [पदानुक्रमिक नामस्थान](/azure/storage/blobs/data-lake-storage-namespace) **अवश्य** सक्षम होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="f4302-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="f4302-117">संसाधन समूह पर Azure Synapse कार्यस्थान स्थित है, *सर्विस प्रिंसिपल* और *ऑडियंस इनसाइट के लिए उपयोगकर्ता* को कम से कम **रीडर** अनुमतियां असाइन करना आवश्यक है.</span><span class="sxs-lookup"><span data-stu-id="f4302-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="f4302-118">अधिक जानकारी के लिए देखें, [Azure पोर्टल का उपयोग करके Azure भूमिकाएं असाइन करें](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="f4302-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="f4302-119">*उपयोगकर्ता* को Azure Data Lake Storage Gen2 खाते पर **स्टोरेज ब्लॉब डेटा योगदानकर्ता** अनुमतियां आवश्यक होती हैं, जहां डेटा स्थित होता है और Azure Synapse कार्यक्षेत्र से जुड़ा होता है.</span><span class="sxs-lookup"><span data-stu-id="f4302-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="f4302-120">[ब्लॉब और क्यू डेटा तक पहुंचने हेतु एक Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना के बारे में](/azure/storage/common/storage-auth-aad-rbac-portal) और [संग्रहण ब्लॉब डेटा योगदानकर्ता अनुमतियां](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="f4302-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="f4302-121">*[Azure Synapse कार्यक्षेत्र प्रबंधित पहचान](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* को Azure Data Lake Storage Gen2 खाता पर जहां डेटा स्थित है और Azure Synapse कार्यक्षेत्र से जुड़ा हुआ है, वहां **स्टोरेज ब्लॉब डेटा योगदानकर्ता** अनुमतियां आवश्यक हैं.</span><span class="sxs-lookup"><span data-stu-id="f4302-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="f4302-122">[ब्लॉब और क्यू डेटा तक पहुंच के लिए Azure भूमिका असाइन करने के लिए Azure पोर्टल का उपयोग करना](/azure/storage/common/storage-auth-aad-rbac-portal) और [ब्लॉब डेटा योगदानकर्ता अनुमतियां संग्रहण](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) के बारे में और अधिक जानें.</span><span class="sxs-lookup"><span data-stu-id="f4302-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="f4302-123">Azure Synapse कार्यस्थान पर, *ऑडिएंस इनसाइट के लिए सेवा प्रिंसिपल* को **Synapse व्यवस्थापक** भूमिका असाइन की जानी चाहिए.</span><span class="sxs-lookup"><span data-stu-id="f4302-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="f4302-124">अधिक जानकारी के लिए देखें, [अपने Synapse कार्यक्षेत्र के लिए पहुंच नियंत्रण कैसे सेट करें](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="f4302-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="f4302-125">कनेक्शन सेट करें और Azure Synapse में निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="f4302-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="f4302-126">एक कनेक्शन कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="f4302-126">Configure a connection</span></span>

1. <span data-ttu-id="f4302-127">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="f4302-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f4302-128">**कनेक्शन जोड़ें** चुनें और **Azure Synapse विश्लेषण** चुनें या कनेक्शन कॉन्फ़िगर करने के लिए **Azure Synapse विश्लेषण** टाइल पर **सेट अप करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f4302-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="f4302-129">डिस्प्ले नाम फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="f4302-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="f4302-130">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="f4302-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="f4302-131">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="f4302-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f4302-132">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="f4302-132">Choose who can use this connection.</span></span> <span data-ttu-id="f4302-133">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="f4302-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f4302-134">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f4302-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f4302-135">जिस सदस्यता में आप Customer Insights डेटा का उपयोग करना चाहते हैं, उसे चुनें और खोजें.</span><span class="sxs-lookup"><span data-stu-id="f4302-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="f4302-136">सदस्यता के चयन के साथ ही आप **कार्यस्थान**, **संग्रहण खाता** और **कंटेनर** भी चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f4302-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="f4302-137">कनेक्शन सहेजने के लिए **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f4302-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="f4302-138">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="f4302-138">Configure an export</span></span>

<span data-ttu-id="f4302-139">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f4302-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f4302-140">अधिक जानकारी के लिए, देखें [निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f4302-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f4302-141">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="f4302-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f4302-142">एक नया निर्यात बनाने के लिए, **निर्यात जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f4302-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="f4302-143">**निर्यात के लिए कनेक्शन** फ़ील्ड में, **Azure Synapse विश्लेषण** अनुभाग से एक कनेक्शन चुनें.</span><span class="sxs-lookup"><span data-stu-id="f4302-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="f4302-144">यदि आप इस अनुभाग का नाम नहीं देखते हैं, तो आपके लिए इस प्रकार का कोई [कनेक्शन](connections.md) उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="f4302-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="f4302-145">अपने निर्यात के लिए एक पहचानने योग्य **प्रदर्शन नाम** और एक **डेटाबेस नाम** प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="f4302-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="f4302-146">आप किन निकायों को Azure Synapse Analytics में निर्यात करना चाहते हैं उनका चयन करें.</span><span class="sxs-lookup"><span data-stu-id="f4302-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="f4302-147">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f4302-147">Select **Save**.</span></span>

<span data-ttu-id="f4302-148">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="f4302-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f4302-149">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="f4302-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f4302-150">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="f4302-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="f4302-151">निर्यात अपडेट करें</span><span class="sxs-lookup"><span data-stu-id="f4302-151">Update an export</span></span>

1. <span data-ttu-id="f4302-152">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="f4302-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f4302-153">जिसे आप अपडेट करना चाहते हैं उस निर्यात पर **संपादित करें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="f4302-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="f4302-154">चयन से निकायों को **जोड़ें** या **निकालें**.</span><span class="sxs-lookup"><span data-stu-id="f4302-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="f4302-155">यदि निकायों को चयन से निकाल दिया जाता है, पर उन्हें Synapse Analytics डेटाबेस से नहीं हटाया जाता है.</span><span class="sxs-lookup"><span data-stu-id="f4302-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="f4302-156">हालांकि, भविष्य में किए जाने वाले डेटा रीफ़्रेश में उस डेटाबेस में निकाले गए निकायों को अपडेट नहीं किया जाएगा.</span><span class="sxs-lookup"><span data-stu-id="f4302-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="f4302-157">**डेटाबेस का नाम बदलना** एक नया Synapse Analytics डेटाबेस बनाता है.</span><span class="sxs-lookup"><span data-stu-id="f4302-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="f4302-158">उस नाम वाला डेटाबेस, जिसे पहले कॉन्फ़िगर किया गया था, भविष्य के रीफ़्रेश में उसे कोई अपडेट प्राप्त नहीं होगा.</span><span class="sxs-lookup"><span data-stu-id="f4302-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
