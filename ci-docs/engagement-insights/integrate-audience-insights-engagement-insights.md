---
title: ऑडिएंस इनसाइट्स और सहभागिता इनसाइट्स के बीच लिंक बनाएँ
description: डेटा के दो दिशाओं में साझाकरण को सक्षम करने के लिए ऑडिएंस इनसाइट्स और सहभागिता इनसाइट्स के बीच सक्रिय लिंक बनाएँ.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6aadd6b5018f63362f86c0e3e3ce085e94c47391
ms.sourcegitcommit: 5dd32dc2b18027cf2aa954356dded4bc6aab9801
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/12/2022
ms.locfileid: "8116016"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>ऑडिएंस इनसाइट्स और सहभागिता इनसाइट्स के बीच लिंक बनाएँ

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

सहभागिता इनसाइट्स और ऑडिएंस इनसाइट्स के बीच एकीकरण दोनों क्षमताओं से परिवेश को जोड़ता है और डेटा को उनके बीच दो दिशाओं के रूप से साझा करने में सक्षम बनाता है.

सहभागिता इनसाइट्स में अधिक विश्लेषण विकल्पों के लिए एकीकृत प्रोफ़ाइल और ऑडिएंस इनसाइट्स से सेगमेंट का उपयोग करें. ऐसे इवेंट निर्यात करें जिनका सहभागिता इनसाइट्स से उच्च व्यावसायिक मूल्य है. ऑडिएंस इनसाइट में एकीकृत प्रोफ़ाइल में डेटा जोड़ने के लिए इन इवेंट का उपयोग करें.

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- ऑडिएंस इनसाइट प्रोफ़ाइल को आपके स्वामित्व वाले Azure Data Lake Storage खाते में या [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash;प्रबंधित डेटा लेक में संग्रहित किया जाना चाहिए. 
- आपके ऑडियंस इनसाइट्स परिवेश में संबद्ध Dataverse परिवेश होना चाहिए. और अगर वह परिवेश डेटा संग्रहण के लिए Dataverse का भी उपयोग कर रहा है, तो सुनिश्चित करें कि आप ऑडियंस इनसाइट्स में **डेटा साझाकरण सक्षम करें** विकल्प पर निशान लगाते हैं. अधिक जानकारी के लिए [ऑडियंस इनसाइट्स में परिवेश बनाएं और कॉन्फ़िगर करें](../audience-insights/create-environment.md) देखें.
- आपको सहभागिता इनसाइट्स और ऑडिएंस इनसाइट्स परिवेशों दोनों के लिए व्यवस्थापक अनुमतियों की आवश्यकता है.
- लिंक किए गए परिवेश एक ही भौगोलिक क्षेत्र में होने चाहिए.

> [!NOTE]
> - यदि आपकी ऑडियंस इनसाइट्स सदस्यता ट्रायल है, जो आंतरिक रूप से प्रबंधित data lake ऑडियंस इनसाइट्स का उपयोग करती है, तो सहायता के लिए [pirequest@microsoft.com](mailto:pirequest@microsoft.com) से संपर्क करें. 
> - यदि आपकी ऑडिएंस इनसाइट्स परिवेश डेटा संग्रहित करने के लिए आपके खुद के Azure Data Lake Storage का उपयोग करती है, तो आपको अपने संग्रहण खाते में सहभागिता इनसाइट्स Azure सेवा प्रमुख जोड़ना होगा. विवरण के लिए, [ऑडिएंस इनसाइट्स के लिए Azure सेवा प्रमुख के साथ Azure Data Lake Storage खाते से कनेक्ट करें](../audience-insights/connect-service-principal.md) पर जाएँ. 


## <a name="create-an-environment-link"></a>लिंक परिवेश बनाएँ

आप सहभागिता इनसाइट्स में **व्यवस्थापक** > **परिवेश** सेटिंग अपडेट करके एक परिवेश लिंक बना सकते हैं.

**ऑडियंस इनसाइट्स और सहभागिता इनसाइट्स के बीच सक्रिय लिंक स्थापित करने के लिए**

1. **परिवेश व्यवस्थापक** पृष्ठ पर, **परिवेश लिंक करें** टैब चुनें.

    :::image type="content" source="media/integrate1.png" alt-text="परिवेश सेट अप करें.":::

1. ऊपरी-बाएँ कोने में या स्क्रीन के निचले भाग में **सेटअप परिवेश** चुनें.

     :::image type="content" source="media/integrate2.png" alt-text="ऑडिएंस इनसाइट्स परिवेश चुनें.":::

1. ऑडिएंस इनसाइट्स परिवेश चुनें और फिर समाप्त करने के लिए **अगला** चुनें. अब आप लिंक किए गए परिवेशों के लिए वैकल्पिक सुविधाओं का चयन कर सकते हैं.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>ऑडिएंस इनसाइट्स एकीकृत प्रोफ़ाइल एट्रिब्यूट और सेगमेंट्स को सक्षम करें

परिवेशों को जोड़ने के बाद, आप लिंक किए गए परिवेशों के लिए वैकल्पिक सुविधाओं का चयन कर सकते हैं. ये सुविधाएँ एकीकृत प्रोफ़ाइल एट्रिब्यूट और ग्राहक डेटा पर इंटरैक्टिव विश्लेषण के लिए ऑडिएंस इनसाइट्स से सेगमेंट सक्षम करती हैं.

> [!IMPORTANT]
> ऑडिएंस इनसाइट सेगमेंट को सहभागिता इनसाइट में दिखाने के लिए, आपको पहले [मर्ज और डाउनस्ट्रीम प्रक्रियाएं चलाना](../audience-insights/merge-entities.md) करना होगा. डाउनस्ट्रीम प्रक्रियाएं महत्वपूर्ण हैं क्योंकि वे एक अनूठी तालिका तैयार करती हैं जो ऑडिएंस इनसाइट्स सेगमेंट को सहभागिता इनसाइट्स के साथ साझा करने के लिए तैयार करती है. (यदि सिस्टम रीफ्रेश शेड्यूल किया गया है, तो इसमें स्वचालित रूप से डाउनस्ट्रीम प्रक्रियाएं शामिल हो जाएँगी.)

**सहभागिता इनसाइट्स में वेब डेटा का विश्लेषण करने के लिए**

1. **परिवेश व्यवस्थापक** पृष्ठ पर, **सहभागिता इनसाइट्स के साथ ऑडियंस इनसाइट्स से डेटा साझा करें** टॉगल चालू करें और फिर **अगला** चुनें.

    :::image type="content" source="media/integrate4.png" alt-text="सुविधाओं का चुनें.":::

1. उन एकीकृत प्रोफ़ाइल एट्रिब्यूट को चुनें, जो सहभागिता इनसाइट्स में आयाम बन जाएँगी. (सभी एट्रिब्यूट उपयोगी आयाम नहीं हैं. उदाहरण के लिए, इसकी संभावना नहीं है कि आपको अपनी वेबसाइट इवेंट के विश्लेषण के लिए एट्रिब्यूट के रूप में **प्रथम नाम** या **अंतिम नाम** की आवश्यकता होगी.)

    :::image type="content" source="media/integrate5.png" alt-text="क्यूरेट आयाम.":::

   >[!NOTE]
   > सभी ऑडियंस इनसाइट प्रोफ़ाइल विशेषताएँ जो पहचानकर्ताओं का प्रतिनिधित्व करती हैं (जैसे **ID** और **वैकल्पिक ID**) उपलब्ध विशेषताओं से फ़िल्टर की जाती हैं और सहभागिता जानकारी में आयाम बन जाती हैं.

1. जब आप विशेषताओं का चयन कर लें, तो **अगला** चुनें.
1. उन उपयोगकर्ताओं को जोड़ें जो सहभागिता इनसाइट्स में ऑडिएंस इनसाइट्स प्रोफ़ाइल आयाम और सेगमेंट देख सकते हैं.

    :::image type="content" source="media/integrate6.png" alt-text="ग्राहक डेटा तक पहुंच प्रबंधित करें.":::

   > [!IMPORTANT]
   > अगर आप इस चरण में स्पष्ट रूप से उपयोगकर्ताओं को नहीं जोड़ते हैं, तो डेटा उपयोगकर्ताओं से सहभागिता जानकारी में छिपा दिया जाएगा.
   > ऑडिएंस इनसाइट सेगमेंट को सहभागिता इनसाइट में दिखाने के लिए, आपको पहले [मर्ज और डाउनस्ट्रीम प्रक्रियाएं चलाना](../audience-insights/merge-entities.md) करना होगा. डाउनस्ट्रीम प्रक्रियाएं महत्वपूर्ण हैं क्योंकि वे एक अनूठी तालिका तैयार करती हैं जो ऑडिएंस इनसाइट्स सेगमेंट को सहभागिता इनसाइट्स के साथ साझा करने के लिए तैयार करती है. (यदि सिस्टम रीफ्रेश शेड्यूल किया गया है, तो इसमें स्वचालित रूप से डाउनस्ट्रीम प्रक्रियाएं शामिल हो जाएँगी.)

1. अपने चयन की समीक्षा करें और फिर **समाप्त करें** चुनें.

    :::image type="content" source="media/integrate7.png" alt-text="ग्राहक डेटा सेटिंग की समीक्षा करें.":::

## <a name="export-refined-events-to-audience-insights"></a>ऑडिएंस इनसाइट्स के लिए परिष्कृत इवेंट निर्यात करें

परिवेशों के बीच लिंक बनाने के बाद, आप सहभागिता इनसाइट्स से ऑडिएंस इनसाइट्स में परिष्कृत इवेंट निर्यात कर सकते हैं और उन्हें नए डेटा स्रोत के रूप में शामिल कर सकते हैं. 

अधिक जानकारी के लिए, [ऑडियंस इनसाइट्स के साथ सहभागिता इनसाइट्स से वेब डेटा एकीकृत करें](../audience-insights/integrate-engagement-insights.md) पर जाएँ.

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
