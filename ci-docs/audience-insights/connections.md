---
title: Customer Insights से अन्य सेवाओं के लिए कनेक्शन.
description: डेटा को अन्य सेवाओं में साझा करें.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896099"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="5aeb8-103">कनेक्शन (पूर्वावलोकन) का अवलोकन</span><span class="sxs-lookup"><span data-stu-id="5aeb8-103">Connections (preview) overview</span></span>

<span data-ttu-id="5aeb8-104">कनेक्शन Customer Insights से डेटा साझा करने में सक्षम बनाने के लिए महत्वपूर्ण हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="5aeb8-105">प्रत्येक कनेक्शन एक विशिष्ट सेवा के साथ डेटा साझा करना तय करता है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="5aeb8-106">कनेक्शन [तीसरे पक्ष के संवर्धन को कॉन्फ़िगर करने](enrichment-hub.md) और [निर्यात कॉन्फ़िगर करने](export-destinations.md) की बुनियाद हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="5aeb8-107">एक ही कनेक्शन का उपयोग कई बार किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="5aeb8-108">उदाहरण के लिए, Dynamics 365 Marketing के लिए एक कनेक्शन कई निर्यातों के लिए काम करता है और एक लीडस्पेस कनेक्शन का उपयोग कई संवर्धनों के लिए किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="5aeb8-109">कनेक्शन बनाने और देखने के लिए **व्यवस्थापक** > **कनेक्शन** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="5aeb8-110">**कनेक्शन** टैब आपको सभी सक्रिय कनेक्शन दिखाता है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="5aeb8-111">सूची प्रत्येक कनेक्शन के लिए एक पंक्ति दिखाती है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="5aeb8-112">एक त्वरित अवलोकन, विवरण प्राप्त करें, और पता लगाएं कि आप **डिस्कवर** टैब पर प्रत्येक विस्तार विकल्प के साथ क्या कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="5aeb8-113">निर्यात</span><span class="sxs-lookup"><span data-stu-id="5aeb8-113">Exports</span></span>

<span data-ttu-id="5aeb8-114">केवल व्यवस्थापक नए कनेक्शन को कॉन्फ़िगर कर सकते हैं लेकिन वे मौजूदा कनेक्शन का उपयोग करने के लिए योगदानकर्ताओं को एक्सेस दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="5aeb8-115">व्यवस्थापक डेटा की आवाजाही का नियंत्रण कर सकते हैं, योगदानकर्ता पेलोड और आवृत्ति को परिभाषित करते हैं जो उनकी आवश्यकताओं के लिए उपयुक्त हों.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="5aeb8-116">अधिक जानकारी के लिए, देखें [योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5aeb8-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="5aeb8-117">संवर्धन</span><span class="sxs-lookup"><span data-stu-id="5aeb8-117">Enrichments</span></span>

<span data-ttu-id="5aeb8-118">केवल व्यवस्थापक नए कनेक्शन कॉन्फ़िगर कर सकते हैं लेकिन बनाए गए कनेक्शन हमेशा व्यवस्थापकों और योगदानकर्ताओं दोनों के लिए उपलब्ध होते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="5aeb8-119">व्यवस्थापक क्रेडेंशियल्स का प्रबंधन करते हैं और डेटा ट्रांसफर को सहमति देते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="5aeb8-120">कनेक्शन व्यवस्थापकों और योगदानकर्ताओं दोनों द्वारा संवर्धन के लिए इस्तेमाल किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="5aeb8-121">एक नया कनेक्शन जोड़ें</span><span class="sxs-lookup"><span data-stu-id="5aeb8-121">Add a new connection</span></span>

<span data-ttu-id="5aeb8-122">कनेक्शन जोड़ने के लिए, आपके पास [व्यवस्थापक की अनुमति](permissions.md) होना चाहिए.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="5aeb8-123">यदि आप अन्य Microsoft सेवाओं से कनेक्ट होते हैं, तो हम मानते हैं कि दोनों सेवाएं एक ही संगठन में हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="5aeb8-124">**व्यवस्थापक** > **कनेक्शन (पूर्वावलोकन)** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="5aeb8-125">**कनेक्शन** टैब पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="5aeb8-126">नया कनेक्शन बनाने के लिए **कनेक्शन जोड़ें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="5aeb8-127">ड्रॉप-डाउन मेनू से चुनें कि आप किस प्रकार का कनेक्शन बनाना चाहते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="5aeb8-128">**कनेक्शन सेट अप करें** फलक में, आवश्यक विवरण प्रदान करें.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="5aeb8-129">**डिस्प्ले नाम** और कनेक्शन का प्रकार एक कनेक्शन का वर्णन करता है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="5aeb8-130">हम एक ऐसा नाम चुनने की सलाह देते हैं जो इस कनेक्शन के उद्देश्य और लक्ष्य को बताता है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="5aeb8-131">सटीक फ़ील्ड इस बात पर निर्भर करता है कि आप किस सेवा से जुड़ रहे हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="5aeb8-132">आप टारगेट सेवा से जुड़े लेख में एक विशिष्ट कनेक्शन प्रकार के विवरण के बारे में जान सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="5aeb8-133">कनेक्शन बनाने के लिए **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="5aeb8-134">आप भी **सेट अप** पर एक टाइल पर **डिस्कवर** टैब चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="5aeb8-135">योगदानकर्ताओं को निर्यात के लिए कनेक्शन का उपयोग करने की अनुमति दें</span><span class="sxs-lookup"><span data-stu-id="5aeb8-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="5aeb8-136">निर्यात कनेक्शन सेट करते या संपादित करते समय, आप चुनते हैं कि किन उपयोगकर्ताओं को [निर्यात](export-destinations.md) को परिभाषित करने के लिए इस विशिष्ट कनेक्शन का उपयोग करने की अनुमति है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="5aeb8-137">डिफ़ॉल्ट रूप से एक कनेक्शन एक व्यवस्थापक की भूमिका वाले उपयोगकर्ताओं के लिए उपलब्ध है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="5aeb8-138">आप इस सेटिंग को **चुनें कि इस कनेक्शन का उपयोग कौन कर सकता है** के तहत बदल सकते हैं कि और योगदानकर्ता भूमिका वाले उपयोगकर्ताओं को इस कनेक्शन का उपयोग करने की अनुमति दे सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="5aeb8-139">योगदानकर्ता कनेक्शन को देखने या संपादित करने में सक्षम नहीं होंगे.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="5aeb8-140">वे केवल एक निर्यात बनाते समय डिस्प्ले का नाम और उसके प्रकार देखेंगे.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="5aeb8-141">कनेक्शन साझा करके, आप योगदानकर्ताओं को कनेक्शन का उपयोग करने की अनुमति देते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="5aeb8-142">जब वे निर्यात स्थापित करते हैं तो योगदानकर्ताओं को साझा कनेक्शन दिखाई देंगे.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="5aeb8-143">वे इस विशिष्ट कनेक्शन का उपयोग करने वाले प्रत्येक निर्यात का प्रबंधन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="5aeb8-144">आप योगदानकर्ताओं द्वारा पहले से परिभाषित किए गए निर्यातों को रखते हुए इस सेटिंग को बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="5aeb8-145">एक कनेक्शन संपादित करें</span><span class="sxs-lookup"><span data-stu-id="5aeb8-145">Edit a connection</span></span>

1. <span data-ttu-id="5aeb8-146">**व्यवस्थापक** > **कनेक्शन (पूर्वावलोकन)** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="5aeb8-147">**कनेक्शन** टैब पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="5aeb8-148">आप जिस कनेक्शन को हटाना चाहते हैं, उसके लिए वर्टिकल एलिप्सिस चुनें.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="5aeb8-149">**संपादित करें** चुनें।</span><span class="sxs-lookup"><span data-stu-id="5aeb8-149">Select **Edit**.</span></span>

1. <span data-ttu-id="5aeb8-150">उन मानों को बदलें जिसे आप अपडेट करना चाहते हैं और **सहेजें** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="5aeb8-151">एक कनेक्शन निकालें</span><span class="sxs-lookup"><span data-stu-id="5aeb8-151">Remove a connection</span></span>

<span data-ttu-id="5aeb8-152">यदि आप जिस कनेक्शन को हटा रहे हैं, वह संवर्धन या निर्यात द्वारा उपयोग किया जाता है, तो आपको पहले उन्हें अलग करने या हटाने की आवश्यकता होती है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="5aeb8-153">हटाएं डायलॉग आपको प्रासंगिक संवर्धन या निर्यात के लिए मार्गदर्शन करेगा.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="5aeb8-154">अलग किए गए संवर्धन और निर्यात निष्क्रिय हो जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="5aeb8-155">आप उन्हें [संवर्धन](enrichment-hub.md) या [निर्यात](export-destinations.md) पृष्ठ पर एक और कनेक्शन जोड़कर फिर से सक्रिय करते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="5aeb8-156">**व्यवस्थापक** > **कनेक्शन (पूर्वावलोकन)** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="5aeb8-157">**कनेक्शन** टैब पर जाएँ.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="5aeb8-158">आप जिस कनेक्शन को हटाना चाहते हैं, उसके लिए वर्टिकल एलिप्सिस चुनें.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="5aeb8-159">ड्रॉपडाउन मेनू से **हटाएं** चुनें.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="5aeb8-160">एक पुष्टिकरण संवाद दिखाई देता है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="5aeb8-161">यदि इस कनेक्शन का उपयोग करने से संवर्धन या निर्यात होते हैं, तो यह देखने के लिए बटन का चयन करें कि कनेक्शन का उपयोग क्या कर रहा है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="5aeb8-162">**निर्यात:** आप कनेक्शन को हटाने में सक्षम होने के लिए निर्यात को हटाने या डिस्कनेक्ट करने का चयन कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="5aeb8-163">किसी निर्यात को डिस्कनेक्ट करने के लिए, व्यवस्थापक **डिस्कनेक्ट करें** कार्रवाई का उपयोग कर सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="5aeb8-164">यह कार्रवाई व्यक्तिगत और कई चयनित निर्यात के लिए उपलब्ध है.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="5aeb8-165">डिस्कनेक्ट करके आप एक्सपोर्ट कॉन्फ़िग रखते हैं, लेकिन इसे तब तक रन नहीं किया जाएगा जब तक कि इसमें दूसरा कनेक्शन नहीं जोड़ा जाता.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="5aeb8-166">**एनरिचमेंट:** आप कनेक्शन को हटाने में सक्षम होने के लिए एनरिचमेंट को हटाने या निष्क्रिय करने का विकल्प चुन सकते हैं।</span><span class="sxs-lookup"><span data-stu-id="5aeb8-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="5aeb8-167">एक बार जब कनेक्शन में अधिक निर्भरता नहीं होती है, तो **व्यवस्थापक** > **कनेक्शन** पर वापस जाएं और कनेक्शन को फिर से हटाने का प्रयास करें.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="5aeb8-168">मिटाने की पुष्टि करने के लिए **हटाएं** का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="5aeb8-168">To confirm the deletion select **Remove**.</span></span>

