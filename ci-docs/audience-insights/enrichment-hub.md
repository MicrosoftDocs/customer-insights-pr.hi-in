---
title: समृद्ध एकीकृत ग्राहक प्रोफाइल
description: अपने ग्राहक डेटा को समृद्ध करने के लिए क्षमताओं का उपयोग करें.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896007"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="50eff-103">ग्राहक प्रोफाइल के लिए संवर्धन (पूर्वावलोकन)</span><span class="sxs-lookup"><span data-stu-id="50eff-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="50eff-104">अपने ग्राहक डेटा संवर्धन के लिए Microsoft और अन्य भागीदारों जैसे स्रोतों से डेटा का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="50eff-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="संवर्द्धन हब पेज":::

<span data-ttu-id="50eff-106">ऑडियंस इनसाइट्स में, एनरिचमेंट विकल्पों के साथ काम करने के लिए **डेटा** > **एनरिचमेंट** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="50eff-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="50eff-107">संवर्दन बनाने या संपादित करने के लिए आपके पास योगदानकर्ता या व्यवस्थापक की अनुमति होनी चाहिए.</span><span class="sxs-lookup"><span data-stu-id="50eff-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="50eff-108">अधिक जानकारी के लिए, [अनुमतियाँ](permissions.md) देखें.</span><span class="sxs-lookup"><span data-stu-id="50eff-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="50eff-109">**अन्वेषण करें** टैब पर, आपको निम्नलिखित समृद्धि मिलेंगे:</span><span class="sxs-lookup"><span data-stu-id="50eff-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="50eff-110">Microsoft द्वारा प्रदान किया गया [ब्रान्ड](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="50eff-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="50eff-111">Microsoft द्वारा प्रदान किया गया [रूचियाँ](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="50eff-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="50eff-112">Leadspace द्वारा प्रदान किया गया [कंपनी का डेटा](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="50eff-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="50eff-113">एक्सपीरियन द्वारा प्रदान की गई [जनसांख्यिकी](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="50eff-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="50eff-114">HERE Technologies द्वारा प्रदान की गई [स्थान डेटा](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="50eff-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="50eff-115">सिक्योर फाइल ट्रांसफर प्रोटोकॉल (SFTP) के माध्यम से [कस्टम डेटा](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="50eff-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="50eff-116">**मेरी संवर्धन** टैब पर, आप उन समृद्धियों को देख सकते हैं जिन्हें आपने कॉन्फ़िगर किया है और उनकी विशेषताओं को संपादित कर सकतें हैं.</span><span class="sxs-lookup"><span data-stu-id="50eff-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="50eff-117">मौजूदा संवर्धन प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="50eff-117">Manage existing enrichments</span></span>

<span data-ttu-id="50eff-118">सभी कॉन्फ़िगर किए गए संवर्धन देखने के लिए **मेरे संवर्धन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="50eff-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="50eff-119">प्रत्येक संवर्धन को पंक्ति के रूप में दर्शाया जाता है जिसमें संवर्धन के बारे में अतिरिक्त जानकारी शामिल होती है.</span><span class="sxs-lookup"><span data-stu-id="50eff-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="50eff-120">उपलब्ध विकल्पों को देखने के लिए संवर्धन का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="50eff-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="50eff-121">आप विकल्प देखने के लिए सूची आइटम पर एलिप्सिस (...) भी चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="50eff-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="संवर्धन की सूची में संवर्धन का प्रबंधन करने के लिए विकल्प":::

- <span data-ttu-id="50eff-123">**दृश्य** समृद्ध ग्राहक प्रोफाइल की संख्या के साथ संवर्धन विवरण.</span><span class="sxs-lookup"><span data-stu-id="50eff-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="50eff-124">संवर्धन कॉन्फ़िगरेशन **संपादित करें**.</span><span class="sxs-lookup"><span data-stu-id="50eff-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="50eff-125">**चलाएँ** नवीनतम डेटा के साथ ग्राहक प्रोफ़ाइल अद्यतन करने के लिए संवर्धन.</span><span class="sxs-lookup"><span data-stu-id="50eff-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="50eff-126">प्रत्येक शेड्यूल्ड रिफ्रेश के साथ स्वचालित रूप से रिफ्रेश होने से रोकने के लिए मौजूदा संवर्धन **निष्क्रिय** करें.</span><span class="sxs-lookup"><span data-stu-id="50eff-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="50eff-127">अंतिम सफल रिफ्रेश का डेटा उपलब्ध रहेगा.</span><span class="sxs-lookup"><span data-stu-id="50eff-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="50eff-128">निष्क्रिय संवर्धन को प्रत्येक शेड्यूल किए गए रिफ्रेश के साथ स्वचालित रिफ्रेश के पुनारंभ करने के लिए **सक्रिय** करें.</span><span class="sxs-lookup"><span data-stu-id="50eff-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="50eff-129">एनरिचमेंट **मिटा** दें.</span><span class="sxs-lookup"><span data-stu-id="50eff-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="50eff-130">आप सूची में चयन करके एक ही बार में कई संवर्द्धन को चला या निष्क्रिय कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="50eff-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="50eff-131">दृश्य और संपादन विकल्प बल्क कार्रवाई के रूप में उपलब्ध नहीं हैं और केवल एक समय में एक संवर्धन के लिए काम करते हैं.</span><span class="sxs-lookup"><span data-stu-id="50eff-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="50eff-132">एनरिचमेंट और कनेक्शन</span><span class="sxs-lookup"><span data-stu-id="50eff-132">Enrichments and connections</span></span>

<span data-ttu-id="50eff-133">तृतीय-पक्ष संवर्धन [कनेक्शन](connections.md) का उपयोग करके कॉन्फ़िगर किए जाते हैं, जिसे एक व्यवस्थापक क्रेडेंशियल्स के साथ सेट करता है और डेटा ट्रांसफ़र के लिए सहमति प्रदान करता है.</span><span class="sxs-lookup"><span data-stu-id="50eff-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="50eff-134">कनेक्शन व्यवस्थापकों और योगदानकर्ताओं द्वारा संवर्धन को कॉन्फ़िगर करने के लिए इस्तेमाल किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="50eff-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="50eff-135">एक ही प्रकार के कई संवर्धन</span><span class="sxs-lookup"><span data-stu-id="50eff-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="50eff-136">समृद्ध होने वाली निकाय को संवर्धन विन्यास के दौरान निर्दिष्ट किया गया है, जो आपको अपने प्रोफ़ाइल के केवल सबसेट को समृद्ध करने की अनुमति देता है.</span><span class="sxs-lookup"><span data-stu-id="50eff-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="50eff-137">उदाहरण के लिए, केवल एक विशिष्ट सेगमेंट के लिए डेटा को समृद्ध करें.</span><span class="sxs-lookup"><span data-stu-id="50eff-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="50eff-138">आप एक ही प्रकार के कई संवर्धनों को कॉन्फ़िगर कर सकते हैं और एक ही कनेक्शन का पुन: उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="50eff-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="50eff-139">कुछ संवर्धनों में एक ही प्रकार के संवर्धनों की संख्या की सीमाएं होंगी जिन्हें बनाया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="50eff-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="50eff-140">सीमा और वर्तमान उपयोग **एनरिचमेंट** पृष्ठ पर देखा जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="50eff-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
