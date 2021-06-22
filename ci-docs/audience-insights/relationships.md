---
title: निकायों और निकाय पथों के बीच संबंध
description: कई डेटा स्रोतों से निकायों के बीच संबंध बनाएं और प्रबंधित करें.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171166"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="33602-103">निकाय के बीच संबंध</span><span class="sxs-lookup"><span data-stu-id="33602-103">Relationships between entities</span></span>

<span data-ttu-id="33602-104">संबंध निकायों को कनेक्ट करते हैं और जब निकाय एक समान पहचानकर्ता, एक विदेशी कुंजी को साझा करते हैं, तो आपके डेटा का एक ग्राफ़ परिभाषित करते हैं.</span><span class="sxs-lookup"><span data-stu-id="33602-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="33602-105">इस विदेशी कुंजी को एक निकाय से दूसरी निकाय में संदर्भित किया जा सकता है.</span><span class="sxs-lookup"><span data-stu-id="33602-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="33602-106">कनेक्ट किए गए निकाय एक से अधिक डेटा स्रोतों के आधार पर अनुभागों और उपाय परिभाषित करते हैं.</span><span class="sxs-lookup"><span data-stu-id="33602-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="33602-107">संबंध तीन प्रकार के होते हैं:</span><span class="sxs-lookup"><span data-stu-id="33602-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="33602-108">डेटा एकीकरण प्रक्रिया के भाग के रूप में सिस्टम द्वारा बनाए गए गैर-संपादन योग्य सिस्टम संबंध</span><span class="sxs-lookup"><span data-stu-id="33602-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="33602-109">गैर-संपादन योग्य इनहेरिट किए गए संबंध, जो डेटा स्रोतों को अंतर्ग्रहण करने से स्वचालित रूप से बनाए जाते हैं</span><span class="sxs-lookup"><span data-stu-id="33602-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="33602-110">संपादन योग्य कस्टम संबंध, जिन्हें उपयोगकर्ताओं द्वारा बनाया और कॉन्फ़िगर किया गया</span><span class="sxs-lookup"><span data-stu-id="33602-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="33602-111">गैर-संपादन योग्य सिस्टम संबंध</span><span class="sxs-lookup"><span data-stu-id="33602-111">Non-editable system relationships</span></span>

<span data-ttu-id="33602-112">डेटा एकीकरण के दौरान, इंटेलिजेंट मैचिंग के आधार पर सिस्टम संबंध स्वचालित रूप से बनाए जाते हैं.</span><span class="sxs-lookup"><span data-stu-id="33602-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="33602-113">इन संबंधों से दूसरी संगत इकाइयों के रिकॉर्ड को ग्राहक प्रोफ़ाइल रिकॉर्ड से तुलना करने में मदद मिलती है.</span><span class="sxs-lookup"><span data-stu-id="33602-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="33602-114">निम्नलिखित डायग्राम तीन सिस्टम-आधारित संबंध के निर्माण को दर्शाता है.</span><span class="sxs-lookup"><span data-stu-id="33602-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="33602-115">एकीकृत *ग्राहक* निकाय बनाने के लिए ग्राहक निकाय का अन्य निकायों के साथ मिलान किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="33602-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="तीन 1-n संबंध के साथ ग्राहक निकाय के संबंध पथ का डायग्राम.":::

- <span data-ttu-id="33602-117">*ग्राहक* निकाय और *संपर्क* निकाय के बीच ***CustomerToContact* संबंध** बनाया गया.</span><span class="sxs-lookup"><span data-stu-id="33602-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="33602-118">*ग्राहक* निकाय को की फ़ील्ड **Contact_contactID** प्राप्त होता है, जो *संपर्क* निकाय की फ़ील्ड **contactID** से संबद्ध होता है.</span><span class="sxs-lookup"><span data-stu-id="33602-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="33602-119">***CustomerToAccount* संबंध** *ग्राहक* निकाय और *खाता* निकाय के बीच बनाया गया था.</span><span class="sxs-lookup"><span data-stu-id="33602-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="33602-120">*ग्राहक* निकाय को की फ़ील्ड **Account_accountID** प्राप्त होता है, जो *खाता* निकाय की फ़ील्ड **accountID** से संबंद्ध होता है.</span><span class="sxs-lookup"><span data-stu-id="33602-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="33602-121">***CustomerToWebAccount* संबंध** *ग्राहक* निकाय और *WebAccount* निकाय के बीच बनाया गया था.</span><span class="sxs-lookup"><span data-stu-id="33602-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="33602-122">*ग्राहक* निकाय को की फ़ील्ड **WebAccount_webaccountID** प्राप्त होता है, जो *WebAccount* निकाय की फ़ील्ड **webaccountID** से संबंद्ध होता है.</span><span class="sxs-lookup"><span data-stu-id="33602-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="33602-123">असंपादनयोग्य इनहेरिटेड संबंध</span><span class="sxs-lookup"><span data-stu-id="33602-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="33602-124">डेटा अंतर्ग्रहण प्रक्रिया के दौरान, सिस्टम मौजूदा संबंधों के लिए डेटा स्रोतों की जाँच करता है.</span><span class="sxs-lookup"><span data-stu-id="33602-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="33602-125">यदि कोई संबंध मौजूद नहीं है, तो सिस्टम स्वचालित रूप से उन्हें बनाता है.</span><span class="sxs-lookup"><span data-stu-id="33602-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="33602-126">इन संबंधों का उपयोग डाउनस्ट्रीम प्रक्रियाओं में भी किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="33602-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="33602-127">एक कस्टम संबंध बनाएं</span><span class="sxs-lookup"><span data-stu-id="33602-127">Create a custom relationship</span></span>

<span data-ttu-id="33602-128">संबंध में एक *स्रोत निकाय* होता है जिसमें विदेशी कुंजी और एक *लक्षित निकाय* होता है जिसे स्रोत निकाय की विदेशी कुंजी इंगित करती है.</span><span class="sxs-lookup"><span data-stu-id="33602-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="33602-129">ऑडियंस इनसाइट में, **डेटा** > **संबंध** पर जाएं.</span><span class="sxs-lookup"><span data-stu-id="33602-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="33602-130">**नया संबंध** चुनें.</span><span class="sxs-lookup"><span data-stu-id="33602-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="33602-131">**नया संबंध** फलक में, निम्न जानकारी प्रदान करें:</span><span class="sxs-lookup"><span data-stu-id="33602-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="खाली इनपुट फ़ील्ड्स के साथ नया संबंध साइड फलक.":::

   - <span data-ttu-id="33602-133">**संबंध नाम**: वह नाम जो संबंध का उद्देश्य दर्शाता है.</span><span class="sxs-lookup"><span data-stu-id="33602-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="33602-134">उदाहरणः CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="33602-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="33602-135">**वर्णन**: संबंध का विवरण.</span><span class="sxs-lookup"><span data-stu-id="33602-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="33602-136">**स्रोत निकाय**: वह निकाय जिसका उपयोग संबंध में स्रोत के रूप में किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="33602-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="33602-137">उदाहरणः SupportCase.</span><span class="sxs-lookup"><span data-stu-id="33602-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="33602-138">**लक्ष्य निकाय**: वह निकाय जिसका उपयोग संबंध में लक्ष्य के रूप में किया जाता है.</span><span class="sxs-lookup"><span data-stu-id="33602-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="33602-139">उदाहरणः ग्राहक.</span><span class="sxs-lookup"><span data-stu-id="33602-139">Example: Customer.</span></span>
   - <span data-ttu-id="33602-140">**स्रोत कार्डिनालिटी**: स्रोत निकाय की कार्डिनालिटी निर्दिष्ट करें.</span><span class="sxs-lookup"><span data-stu-id="33602-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="33602-141">कार्डिनालिटी एक सेट में संभावित तत्वों की संख्या का वर्णन करती है.</span><span class="sxs-lookup"><span data-stu-id="33602-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="33602-142">इसका संबंध हमेशा लक्ष्य कार्डिनैलिटी से होता है.</span><span class="sxs-lookup"><span data-stu-id="33602-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="33602-143">आप **एक** और **अनेक** के बीच चुन सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="33602-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="33602-144">केवल अनेक से एक और एक से एक संबंध ही समर्थित हैं.</span><span class="sxs-lookup"><span data-stu-id="33602-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="33602-145">अनेक-से-एक: एकाधिक स्रोत रिकॉर्ड का एक लक्ष्य रिकॉर्ड से संबंध हो सकता है.</span><span class="sxs-lookup"><span data-stu-id="33602-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="33602-146">उदाहरण: एकल ग्राहक से कई समर्थन मामले.</span><span class="sxs-lookup"><span data-stu-id="33602-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="33602-147">एक-से-एक: एक एकल स्रोत रिकॉर्ड का संबंध एक लक्ष्य रिकॉर्ड से होता है.</span><span class="sxs-lookup"><span data-stu-id="33602-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="33602-148">उदाहरण: एकल ग्राहक के लिए एक लॉयल्टी ID.</span><span class="sxs-lookup"><span data-stu-id="33602-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="33602-149">अनेक-से-अनेक संबंध दो अनेक-से-एक संबंधों और एक लिंकिंग निकाय का उपयोग करके बनाए जा सकते हैं, जो स्रोत निकाय और लक्ष्य निकाय को जोड़ता है.</span><span class="sxs-lookup"><span data-stu-id="33602-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="33602-150">**लक्ष्य की कार्डिनेलिटी**: लक्ष्य इकाई रिकोर्ड की कार्डिनेलिटी का चयन करें.</span><span class="sxs-lookup"><span data-stu-id="33602-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="33602-151">**स्रोत कुंजी फ़ील्ड**: स्रोत निकाय में विदेशी कुंजी फ़ील्ड.</span><span class="sxs-lookup"><span data-stu-id="33602-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="33602-152">उदाहरण: SupportCase, CaseID को विदेशी कुंजी फ़ील्ड के रूप में उपयोग कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="33602-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="33602-153">**लक्ष्य कुंजी फ़ील्ड**: लक्ष्य निकाय का मुख्य फ़ील्ड.</span><span class="sxs-lookup"><span data-stu-id="33602-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="33602-154">उदाहरणः ग्राहक **CustomerID** कुंजी फ़ील्ड का उपयोग कर सकता है.</span><span class="sxs-lookup"><span data-stu-id="33602-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="33602-155">कस्टम संबंध बनाने के लिए **सहेजें** चुनें.</span><span class="sxs-lookup"><span data-stu-id="33602-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="33602-156">संबंध देखें</span><span class="sxs-lookup"><span data-stu-id="33602-156">View relationships</span></span>

<span data-ttu-id="33602-157">संबंध पृष्ठ बनाए गए सभी सभी संबंधों को सूचीबद्ध करता है.</span><span class="sxs-lookup"><span data-stu-id="33602-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="33602-158">प्रत्येक पंक्ति एक संबंध का प्रतिनिधित्व करती है, जिसमें स्रोत निकाय, लक्ष्य निकाय और कार्डिनालिटी के बारे में विवरण भी शामिल होता है.</span><span class="sxs-lookup"><span data-stu-id="33602-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="संबंध पेज के एक्शन बार में संबंधों और विकल्पों की सूची.":::

<span data-ttu-id="33602-160">यह पेज मौजूदा और नए संबंधों के लिए विकल्पों का एक सेट प्रदान करता है:</span><span class="sxs-lookup"><span data-stu-id="33602-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="33602-161">**नया संबंध**: [कस्टम संबंध बनाएं](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="33602-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="33602-162">**विज़ुअलाइज़र**: [संबंध विज़ुअलाइज़र का अन्वेषण करें](#explore-the-relationship-visualizer) मौजूदा संबंधों और उनकी कार्डिनालिटी का नेटवर्क आरेख देखने के लिए.</span><span class="sxs-lookup"><span data-stu-id="33602-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="33602-163">**इसके अनुसार फ़िल्टर करें**: सूची में दिखाने के लिए संबंधों का प्रकार चुनें.</span><span class="sxs-lookup"><span data-stu-id="33602-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="33602-164">**संबंध खोजें**: संबंधों के गुणों पर पाठ-आधारित खोज का उपयोग करें.</span><span class="sxs-lookup"><span data-stu-id="33602-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="33602-165">संबंध विज़ुअलाइज़र का अन्वेषण करें</span><span class="sxs-lookup"><span data-stu-id="33602-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="33602-166">संबंध विज़ुअलाइज़र जुड़े हुए निकाय और उनकी कार्डिनालिटी के बीच मौजूदा संबंधों का एक नेटवर्क आरेख दिखाता है.</span><span class="sxs-lookup"><span data-stu-id="33602-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="33602-167">दृश्य को अनुकूलित करने के लिए, आप बॉक्स को कैनवास पर खींचकर उनकी स्थिति बदल सकते हैं.</span><span class="sxs-lookup"><span data-stu-id="33602-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="संबंधित निकायों के बीच कनेक्शन के साथ संबंध विज़ुअलाइज़र नेटवर्क आरेख का स्क्रीनशॉट.":::

<span data-ttu-id="33602-169">उपलब्ध विकल्प:</span><span class="sxs-lookup"><span data-stu-id="33602-169">Available options:</span></span> 
- <span data-ttu-id="33602-170">**छवि के रूप में निर्यात करें**: वर्तमान दृश्य को छवि फ़ाइल के रूप में सहेजें.</span><span class="sxs-lookup"><span data-stu-id="33602-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="33602-171">**क्षैतिज/ऊर्ध्वाधर लेआउट में बदलें**: निकायों और संबंधों का संरेखण बदलें.</span><span class="sxs-lookup"><span data-stu-id="33602-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="33602-172">**संपादित करें**: संपादन फलक में कस्टम संबंधों के गुणों को अपडेट करें और परिवर्तनों को सहेजें.</span><span class="sxs-lookup"><span data-stu-id="33602-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="33602-173">मौजूदा संबंधों को प्रबंधित करें</span><span class="sxs-lookup"><span data-stu-id="33602-173">Manage existing relationships</span></span> 

<span data-ttu-id="33602-174">संबंध पेज पर, प्रत्येक संबंध को एक पंक्ति द्वारा दर्शाया जाता है.</span><span class="sxs-lookup"><span data-stu-id="33602-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="33602-175">एक संबंध चुनें और निम्नलिखित विकल्पों में से एक चुनें:</span><span class="sxs-lookup"><span data-stu-id="33602-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="33602-176">**संपादित करें**: संपादन फलक में कस्टम संबंधों के गुणों को अपडेट करें और परिवर्तनों को सहेजें.</span><span class="sxs-lookup"><span data-stu-id="33602-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="33602-177">**हटाएं**: कस्टम संबंध हटाएं.</span><span class="sxs-lookup"><span data-stu-id="33602-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="33602-178">**देखें**: सिस्टम-निर्मित और इनहेरिट किए गए संबंध देखें.</span><span class="sxs-lookup"><span data-stu-id="33602-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="33602-179">अगला चरण</span><span class="sxs-lookup"><span data-stu-id="33602-179">Next step</span></span>

<span data-ttu-id="33602-180">सिस्टम और कस्टम संबंधों का उपयोग कई डेटा स्रोतों के आधार पर [खंड बनाने](segments.md) के लिए किया जाता है, जिन्हें अलग नहीं किया गया हो.</span><span class="sxs-lookup"><span data-stu-id="33602-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
