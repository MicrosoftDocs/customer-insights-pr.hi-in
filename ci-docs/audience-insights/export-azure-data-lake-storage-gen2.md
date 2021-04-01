---
title: Azure Data Lake Storage Gen2 के लिए Customer Insights डेटा निर्यात करें
description: Azure Data Lake Storage Gen2 के लिए कनेक्शन को कॉन्फ़िगर करने का तरीका जानें.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596639"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="6c7b1-103">Azure Data Lake Storage Gen2 के लिए कनेक्टर (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="6c7b1-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="6c7b1-104">अपने Customer Insights डेटा को Azure Data Lake Storage Gen2 में स्टोर करें या इसका इस्तेमाल अपने डेटा को दूसरे एप्लिकेशन में भेजने के लिए करें.</span><span class="sxs-lookup"><span data-stu-id="6c7b1-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="6c7b1-105">कनेक्टर को Azure Data Lake Storage Gen2 के लिए कॉन्फ़िगर करें</span><span class="sxs-lookup"><span data-stu-id="6c7b1-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="6c7b1-106">ऑडिएंस इनसाइट्स में, **व्यवस्थापक** > **निर्यात गंतव्य** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="6c7b1-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6c7b1-107">**Azure Data Lake Storage Gen2** के अंतर्गत, **सेट अप** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6c7b1-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="6c7b1-108">अपने गंतव्य-स्थल को **प्रदर्शन नाम** फील्ड में पहचान करने योग्य नाम दें.</span><span class="sxs-lookup"><span data-stu-id="6c7b1-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="6c7b1-109">अपने Azure Data Lake Storage Gen2 के लिए **अकाउंट नाम**, **अकाउंट कुंजी** और **कंटेनर** दर्ज करें.</span><span class="sxs-lookup"><span data-stu-id="6c7b1-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="6c7b1-110">Azure Data Lake Storage Gen2 के साथ उपयोग करने के लिए स्टोरेज अकाउंट बनाने का तरीका जानने के लिए, [स्टोरेज अकाउंट बनाएं](/azure/storage/blobs/create-data-lake-storage-account) देखें.</span><span class="sxs-lookup"><span data-stu-id="6c7b1-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="6c7b1-111">Azure Data Lake Gen2 संग्रहण अकाउंट नाम और अकाउंट कुंजी को खोजने के तरीके के बारे में अधिक जानने के लिए, [Azure पोर्टल में संग्रहण अकाउंट सेटिंग प्रबंधित करें](/azure/storage/common/storage-account-manage) देखें.</span><span class="sxs-lookup"><span data-stu-id="6c7b1-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="6c7b1-112">**अगला** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6c7b1-112">Select **Next**.</span></span>

1. <span data-ttu-id="6c7b1-113">उस प्रत्येक निकाय के सामने दिए गए बॉक्स को चुनें जिसे आप इस गंतव्य-स्थल में एक्सपोर्ट करना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="6c7b1-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="6c7b1-114">**सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="6c7b1-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6c7b1-115">डेटा निर्यात करें</span><span class="sxs-lookup"><span data-stu-id="6c7b1-115">Export the data</span></span>

<span data-ttu-id="6c7b1-116">आप [मांग पर डेटा निर्यात](export-destinations.md#export-data-on-demand) कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="6c7b1-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="6c7b1-117">निर्यात भी प्रत्येक [निर्धारित रिफ्रेश के साथ चलेगा](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6c7b1-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>