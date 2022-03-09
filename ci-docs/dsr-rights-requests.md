---
title: GDPR के तहत डेटा सब्जेक्ट राइट्स(DSR) अनुरोध | Microsoft Docs
description: Dynamics 365 Customer Insights ऑडिएंस इनसाइट्स क्षमता के लिए डेटा विषय अनुरोधों का जवाब दें.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350271"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR के तहत डेटा विषय अधिकार (DSR) अनुरोध

यूरोपीय संघ का जनरल डेटा प्रोटेक्शन रेग्यूलेशन (GDPR) 25 मई, 2018 से प्रभावी है. यह व्यक्तियों को उनके डेटा के संबंध में महत्वपूर्ण अधिकार देता है. GDPR व्यक्तियों के गोपनीयता अधिकारों की रक्षा और उन्हें सक्षम करने के बारे में है. आप [Microsoft ट्रस्ट सेंटर](https://www.microsoft.com/trust-center) पर सुरक्षा और अनुपालन के लिए Microsoft की प्रतिबद्धता के बारे में अधिक पढ़ सकते हैं.

हम अपने ग्राहकों को उनकी GDPR आवश्यकताओं को पूरा करने में मदद करने के लिए प्रतिबद्ध हैं. इसमें डेटा को मिटाने और निर्यात करने का अधिकार शामिल है जिसमें उपयोगकर्ता की ID, फ़ोन नंबर और ईमेल पते जैसी व्यक्तिगत जानकारी शामिल है. व्यवस्थापक व्यक्तिगत डेटा को मिटाने या निर्यात करने के लिए उपयोगकर्ता के अनुरोधों को लागू कर सकते हैं.

## <a name="audience-insights"></a>ऑडिएंस इनसाइट

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>जीडीपीआर डेटा विषय का जवाब देते हुए Dynamics 365 Customer Insights ऑडियंस इनसाइट्स क्षमता के अनुरोधों को हटाएं

“मिटाने का अधिकार” किसी संगठन के ग्राहक डेटा से व्यक्तिगत डेटा को हटाना जनरल डेटा प्रोटेक्शन रेग्यूलेशन (GDPR) में एक महत्वपूर्ण सुरक्षा है. व्यक्तिगत डेटा निकालने में सभी व्यक्तिगत डेटा और सिस्टम-जनरेटेड लॉग निकालना शामिल है, जिनमें ऑडिट लॉग जानकारी शामिल नहीं है.

#### <a name="manage-data-subject-delete-requests"></a>डेटा विषय हटाएं अनुरोध प्रबंधित करें

ऑडियंस इनसाइट्स किसी विशिष्ट ग्राहक या उपयोगकर्ता के लिए व्यक्तिगत डेटा को हटाने के लिए निम्नलिखित इन-प्रोडक्ट अनुभव प्रदान करता है:

- **ग्राहक डेटा के लिए अनुरोध हटाएं प्रबंधित करें**: Customer Insights में ग्राहक डेटा मूल डेटा स्रोतों से बाहरी Customer Insights तक पहुंचाया जाता है. सभी GDPR हटाने के अनुरोधों को मूल डेटा स्रोत में पूरा किया जाना चाहिए.
- **ग्राहक इनसाइट उपयोगकर्ता डेटा के लिए हटाने के अनुरोधों का प्रबंधन करें**: उपयोगकर्ताओं के लिए डेटा Customer Insights द्वारा बनाया गया है. सभी GDPR हटाने के अनुरोधों को Customer Insights में पूरा किया जाना चाहिए.

##### <a name="manage-requests-to-delete-customer-data"></a>ग्राहक डेटा हटाने के अनुरोधों को प्रबंधित करें

Customer Insights व्यवस्थापक डेटा स्रोत में हटाए गए ग्राहक डेटा हटाने के लिए इन चरणों का पालन कर सकते हैं:

1. Dynamics 365 Customer Insights में साइन इन करें.
2. ऑडिएंस इनसाइट्स में, **डेटा** > **डेटा स्रोत** पर जाएं
3. सूची में प्रत्येक डेटा स्रोत के लिए जिसमें ग्राहक डेटा हटा दिया गया है:
   1. (...) का चयन करें और फिर **रिफ़्रेश करें** चुनें.
   2. **स्थिति** के तहत डेटा स्रोत की स्थिति की जाँच करें. चेक मार्क का मतलब है कि रिफ्रेश सफल था. चेतावनी त्रिकोण का मतलब कुछ गलत हो गया. यदि चेतावनी त्रिकोण प्रदर्शित होता है, तो D365CI@microsoft.com से संपर्क करें.

> [!div class="mx-imgBorder"]
> ![ग्राहक डेटा के लिए GDPR हटाने के अनुरोधों को संभालना.](audience-insights/media/gdpr-data-sources.png "ग्राहक डेटा के लिए GDPR हटाने के अनुरोधों को संभालना")

##### <a name="manage-delete-requests-for-user-data"></a>उपयोगकर्ता डेटा के लिए अनुरोध हटाएं प्रबंधित करें

एक Customer Insights व्यवस्थापक Customer Insights उपयोगकर्ता डेटा को हटाने के लिए इन चरणों का पालन कर सकता है:

1. Dynamics 365 Customer Insights में साइन इन करें.
2. ऑडियंस इनसाइट्स में, **व्यवस्थापक** > **अनुमतियाँ** पर जाएं.
3. उस उपयोगकर्ता के लिए चेक बॉक्स चुनें जिसे आप हटाना चाहते हैं.
4. **निकालें** चुनें.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>जीडीपीआर डेटा विषय निर्यात अनुरोधों का जवाब देना

जनरल डेटा प्रोटेक्शन रेग्यूलेशन (GDPR) के लिए आपकी यात्रा पर आपके साथ भागीदारी करने के लिए हमारी प्रतिबद्धता के हिस्से के रूप में, हमने आपको तैयार करने में मदद करने के लिए दस्तावेज विकसित किए हैं. यह दस्तावेज़ीकरण उन कदमों का वर्णन करता है जो आप ऑडियंस इनसाइट्स का उपयोग करते समय जीडीपीआर अनुपालन का समर्थन करने के लिए आज ले सकते हैं.

#### <a name="manage-export-and-view-requests"></a>एक्सपोर्ट प्रबंधित करें और अनुरोध देखें

डेटा पोर्टेबिलिटी का अधिकार एक इलेक्ट्रॉनिक प्रारूप व्यक्तिगत डेटा की एक प्रति का अनुरोध करने की अनुमति देता है("एक संरचित, आमतौर पर इस्तेमाल किया जाने वाला, मशीन पठनीय और इंटरऑपरेबल प्रारूप")जिसे दूसरे डेटा कंट्रोलर को प्रेषित किया जा सकता है.

##### <a name="export-customer-data-tenant-admin"></a>ग्राहक डेटा (टेनेंट व्यवस्थापक) निर्यात करें

एक टेनेंट व्यवस्थापक डेटा एक्सपोर्ट करने के लिए इन चरणों का पालन कर सकता है:

1. अनुरोध में ग्राहक के ईमेल पते को निर्दिष्ट करते हुए D365CI@microsoft.com पर एक ईमेल भेजें. Customer Insights टीम पंजीकृत टेनेंट व्यवस्थापक ईमेल पते पर एक ईमेल भेजेगी, जिसमें डेटा निर्यात करने के लिए पुष्टि की मांग की जाएगी.
2. अनुरोधित ग्राहक के लिए डेटा एक्सपोर्ट करने की पुष्टि को स्वीकार करें.
3. टेनेंट व्यवस्थापक ईमेल पते के माध्यम से एक्सपोर्ट किए गए डेटा प्राप्त करें.

##### <a name="export-user-data-tenant-admin"></a>उपयोगकर्ता डेटा (टेनेंट व्यवस्थापक) एक्सपोर्ट करें

1. अनुरोध में उपयोगकर्ता के ईमेल पते को निर्दिष्ट करते हुए D365CI@microsoft.com पर एक ईमेल भेजें. Customer Insights टीम पंजीकृत टेनेंट व्यवस्थापक ईमेल पते पर एक ईमेल भेजेगी, जिसमें डेटा निर्यात करने के लिए पुष्टि की मांग की जाएगी.
2. अनुरोधित उपयोगकर्ता के लिए डेटा एक्सपोर्ट करने की पुष्टि को स्वीकार करें.
3. टेनेंट व्यवस्थापक ईमेल पते के माध्यम से एक्सपोर्ट किए गए डेटा प्राप्त करें.

## <a name="consent-management-preview"></a>सहमति प्रबंधन (पूर्वावलोकन)

सहमति प्रबंधन क्षमता सीधे उपयोगकर्ता डेटा एकत्र नहीं करती है। यह केवल सहमति डेटा को आयात और संसाधित करता है जो अन्य अनुप्रयोगों में उपयोगकर्ताओं द्वारा प्रदान किया जाता है।

विशिष्ट उपयोगकर्ताओं के बारे में सहमति डेटा निकालने के लिए, सहमति प्रबंधन क्षमता के लिए अंतर्ग्रहीत डेटा स्रोतों में इसे हटा दें। डेटा स्रोत को रीफ़्रेश करने के बाद, हटाए गए डेटा को सहमति केंद्र में भी मिटा दिया जाएगा. सहमति निकाय का उपयोग करने वाले एप्लिकेशन भी उस डेटा को हटा देंगे जिसे स्रोत पर एक . के बाद हटा दिया गया था[ताज़ा करें।](audience-insights/system.md#refresh-processes) अन्य सभी प्रक्रियाओं और अनुप्रयोगों से उपयोगकर्ता के डेटा को निकालने के लिए डेटा विषय अनुरोध का जवाब देने के बाद हम डेटा स्रोतों को तुरंत ताज़ा करने की अनुशंसा करते हैं।


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]