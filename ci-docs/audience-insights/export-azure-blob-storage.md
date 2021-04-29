---
title: एक Azure ब्लॉब स्टोरेज के लिए Customer Insights डेटा निर्यात करें
description: कनेक्शन को कॉन्फ़िगर करने और ब्लॉब स्टोरेज विज्ञापन प्रबंधक को निर्यात करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760191"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="cb0e6-103">Azure ब्लॉब स्टोरेज (पूर्वावलोकन) के लिए सेगमेंट सूची और अन्य डेटा को निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="cb0e6-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="cb0e6-104">अपने Customer Insights डेटा को ब्लॉब स्टोरेज में स्टोर करें या इसका इस्तेमाल अपने डेटा को दूसरे एप्लिकेशन में भेजने के लिए करें.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="cb0e6-105">ब्लॉब संग्रहण में कनेक्शन सेट अप करें</span><span class="sxs-lookup"><span data-stu-id="cb0e6-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="cb0e6-106">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cb0e6-107">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Azure ब्लॉब संग्रहण** चुनें.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="cb0e6-108">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cb0e6-109">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cb0e6-110">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="cb0e6-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cb0e6-111">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-111">Choose who can use this connection.</span></span> <span data-ttu-id="cb0e6-112">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="cb0e6-113">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cb0e6-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="cb0e6-114">अपने ब्लॉब स्टोरेज अकाउंट के लिए **अकाउंट का नाम**, **अकाउंट की कुंजी**, और **कंटेनर** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="cb0e6-115">ब्लॉब स्टोरेज अकाउंट का नाम और अकाउंट कुंजी खोजने के तरीके के बारे में अधिक जानने के लिए, देखें [Azure पोर्टल में स्टोरेज अकाउंट सेटिंग्स का प्रबंधन करें](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="cb0e6-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="cb0e6-116">कंटेनर बनाने के बारे में जानने के लिए, [कंटेनर बनाएँ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) देखें.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="cb0e6-117">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="cb0e6-118">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="cb0e6-118">Configure an export</span></span>

<span data-ttu-id="cb0e6-119">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cb0e6-120">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="cb0e6-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cb0e6-121">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cb0e6-122">एक नया निर्यात बनाने के लिए, **डेस्टिनेशन जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="cb0e6-123">**निर्यात के लिए कनेक्शन** में, Azure Blob Storage अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="cb0e6-124">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="cb0e6-125">उस प्रत्येक निकाय के सामने दिए गए बॉक्स को चुनें जिसे आप इस गंतव्य-स्थल में एक्सपोर्ट करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="cb0e6-126">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-126">Select **Save**.</span></span>

<span data-ttu-id="cb0e6-127">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="cb0e6-128">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="cb0e6-129">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="cb0e6-130">निर्यात किया गया डेटा आपके द्वारा कॉन्फ़िगर किए गए ब्लॉब स्टोरेज कंटेनर में संग्रहीत किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="cb0e6-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="cb0e6-131">आपके कंटेनर में निम्नलिखित फोल्डर पथ अपने आप बनेंगे:</span><span class="sxs-lookup"><span data-stu-id="cb0e6-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="cb0e6-132">स्रोत निकायों और सिस्टम द्वारा उत्पन्न स्रोत निकायों के लिए: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="cb0e6-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="cb0e6-133">उदाहरण: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="cb0e6-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="cb0e6-134">निर्यात किए गए निकायों के लिए model.json %ExportDestinationName% स्तर पर होगा</span><span class="sxs-lookup"><span data-stu-id="cb0e6-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="cb0e6-135">उदाहरण: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="cb0e6-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
