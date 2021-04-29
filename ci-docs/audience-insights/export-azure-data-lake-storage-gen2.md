---
title: Azure Data Lake Storage Gen2 के लिए Customer Insights डेटा निर्यात करें
description: Azure Data Lake Storage Gen2 के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760053"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="e64ec-103">Azure Data Lake Storage Gen2 (पूर्वावलोकन) के लिए कनेक्शन को सेट करें</span><span class="sxs-lookup"><span data-stu-id="e64ec-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="e64ec-104">**व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="e64ec-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e64ec-105">**कनेक्शन जोड़ें** का चयन करें और कनेक्शन को कॉन्फ़िगर करने के लिए **Azure Data Lake Gen 2** चुनें.</span><span class="sxs-lookup"><span data-stu-id="e64ec-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="e64ec-106">**डिस्प्ले नाम** फ़ील्ड में अपने कनेक्शन को पहचानने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="e64ec-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e64ec-107">कनेक्शन का नाम और प्रकार इस कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="e64ec-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e64ec-108">हम एक नाम चुनने की सलाह देते हैं जो कनेक्शन के उद्देश्य और लक्ष्य को बताता है।</span><span class="sxs-lookup"><span data-stu-id="e64ec-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e64ec-109">चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="e64ec-109">Choose who can use this connection.</span></span> <span data-ttu-id="e64ec-110">यदि आप कोई कार्रवाई नहीं करते हैं, तो व्यवस्थापक डिफ़ॉल्ट होंगे.</span><span class="sxs-lookup"><span data-stu-id="e64ec-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e64ec-111">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e64ec-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e64ec-112">अपने Azure Data Lake Storage Gen2 के लिए **अकाउंट नाम**, **अकाउंट कुंजी** और **कंटेनर** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="e64ec-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="e64ec-113">Azure Data Lake Storage Gen2 के साथ उपयोग करने के लिए स्टोरेज अकाउंट बनाने का तरीका जानने के लिए, [स्टोरेज अकाउंट बनाएं](/azure/storage/blobs/create-data-lake-storage-account) देखें.</span><span class="sxs-lookup"><span data-stu-id="e64ec-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="e64ec-114">Azure Data Lake Gen2 स्टोरेज अकाउंट का नाम और अकाउंट कुंजी के बारे में अधिक जानने के लिए, देखें [Azure पोर्टल में स्टोरेज अकाउंट सेटिंग्स का प्रबंधन करें](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e64ec-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="e64ec-115">कनेक्शन पूरा करने के लिए **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e64ec-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e64ec-116">एक निर्यात कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="e64ec-116">Configure an export</span></span>

<span data-ttu-id="e64ec-117">यदि आपके पास इस प्रकार के कनेक्शन का एक्सेस है तो आप इस निर्यात को कॉन्फ़िगर कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e64ec-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e64ec-118">अधिक जानकारी के लिए, देखें [एक निर्यात को कॉन्फ़िगर करने के लिए आवश्यक अनुमतियां](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e64ec-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e64ec-119">**डेटा** > **निर्यात** पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="e64ec-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e64ec-120">एक नया निर्यात बनाने के लिए, **निर्यात जोड़ें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e64ec-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="e64ec-121">**निर्यात के लिए कनेक्शन** में, **Azure Data Lake** अनुभाग से एक कनेक्शन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="e64ec-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="e64ec-122">यदि आपको इस अनुभाग का नाम दिखाई नहीं देता है, तो आपके लिए इस प्रकार का कोई कनेक्शन उपलब्ध नहीं है.</span><span class="sxs-lookup"><span data-stu-id="e64ec-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e64ec-123">उस प्रत्येक निकाय के सामने दिए गए बॉक्स को चुनें जिसे आप इस गंतव्य-स्थल में एक्सपोर्ट करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="e64ec-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="e64ec-124">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="e64ec-124">Select **Save**.</span></span>

<span data-ttu-id="e64ec-125">निर्यात को सहेजने से निर्यात तुरंत नहीं चलता है.</span><span class="sxs-lookup"><span data-stu-id="e64ec-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e64ec-126">निर्यात हर [शेड्यूल रिफ़्रेश](system.md#schedule-tab) के साथ चलता है.</span><span class="sxs-lookup"><span data-stu-id="e64ec-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e64ec-127">आप [मांग पर डेटा निर्यात](export-destinations.md#run-exports-on-demand) भी कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="e64ec-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="e64ec-128">निर्यात किया गया डेटा आपके द्वारा कॉन्फ़िगर किए गए Azure Data Lake Gen2 स्टोरेज कंटेनर में संग्रहीत किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="e64ec-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
