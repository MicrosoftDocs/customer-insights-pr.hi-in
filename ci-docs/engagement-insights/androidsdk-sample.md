---
title: Android SDK नमूना
description: Android SDK के बारे में जानने के लिए नमूना परियोजना
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035828"
---
# <a name="run-the-android-sdk-sample"></a>Android SDK नमूना चलाएँ

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

यह नमूना Android प्रोजेक्ट आपको यह समझने में मदद करता है कि SDK किसी ऐप में कैसे काम करता है। आपको कोड नहीं लिखना होगा। बस अपनी अंतर्ग्रहण कुंजी जोड़ें और आप तुरंत अपने कार्यस्थान में ईवेंट देख सकते हैं।

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- [Android Studio](https://developer.android.com/studio)
- [अंतर्ग्रहण कुंजी](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Android SDK नमूना डाउनलोड करें

1. [सहभागिता इनसाइट्स Android SDK नमूना डाउनलोड करें](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. कम्प्रेस्ड फ़ाइल `ei-android-sample.zip` को अनज़िप करें.
1. Android Studio में अनज़िप किए गए फ़ोल्डर खोलें।
1. `AndroidManifest.xml` फाइल में, **व्यवस्थापक** > **कार्यस्थान** > **स्थापना निर्देशिका** के अंतर्गत सहभागिता इनसाइट्स से अपने कार्यस्थान इंजेस्चन कुंजी के साथ `"Your-Ingestion-Key"` स्ट्रिंग को बदलें. 

   > [!NOTE]
   > आपको `${applicationId}` अनुभाग प्रतिस्थापित करने की आवश्यकता नहीं है। यह स्वचालित रूप से पॉप्युलेट होता है.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. नमूना प्रोजेक्ट प्रारंभ करने के लिए, **रन करें** का चयन करें.
1. अपने कार्यस्थान में इवेंट्स देखें।


[!INCLUDE[footer-include](../includes/footer-banner.md)]
