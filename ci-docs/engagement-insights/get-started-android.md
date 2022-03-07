---
title: Android SDK के साथ प्रारंभ करें
description: जानें कि कैसे Android SDK वैयक्तिकृत और चलाया जाता है
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: b06822b2c2d6a859bdf808f7800baef43c4ab874
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226171"
---
# <a name="get-started-with-the-android-sdk"></a>Android SDK के साथ प्रारंभ करें

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

यह ट्यूटोरियल आपके Android ऐप को इंस्ट्रूमेंट करने की प्रक्रिया के माध्यम से Dynamics 365 Customer Insights संलग्नता इनसाइट्स SDK पर आपको दिशानिर्देश देता है। आपको अपने पोर्टल में पाँच मिनट या उससे पहले के ईवेंट दिखाई देने लगेंगे।

## <a name="configuration-options"></a>कॉन्फ़िगरेशन विकल्प
निम्नलिखित कॉन्फ़िगरेशन विकल्प SDK को पास किए जा सकते हैं:

- **अंतर्ग्रहण कुंजी** : आपके कार्यस्थान पर ईवेंट भेजने के लिए अंतर्ग्रहण कुंजी का उपयोग किया जाता है।

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- Android Studio

- न्यूनतम Android API स्तर: 16 (Jelly Bean)

- एक अंतर्ग्रहण कुंजी (प्राप्त करने के तरीके के बारे में निर्देशों के लिए नीचे देखें)

## <a name="integrate-the-sdk-into-your-application"></a>SDK को अपने एप्लीकेशन में एकीकृत करें
कार्यक्षेत्र का चयन करके प्रक्रिया शुरू करें, Android मोबाइल प्लेटफॉर्म का चयन करें, और Android SDK डाउनलोड करें।

- अपने कार्यस्थान का चयन करने के लिए बाएं नेविगेशन फलक में कार्यस्थान स्विचर का उपयोग करें।

- यदि आपके पास कोई मौजूदा कार्यस्थान नहीं है, तो **नया कार्यस्थान** चुनें और [नया कार्यस्थान](create-workspace.md) बनाने के लिए चरणों का पालन करें।

- आपके द्वारा कार्यस्थान बनाने के बाद, **व्यवस्थापक** > **कार्यस्थान** पर जाएँ और फिर **इंस्टॉलेशन गाइड** चुनें।

## <a name="configure-the-sdk"></a>SDK कॉन्फ़िगर करें

एक बार जब आप SDK डाउनलोड कर लेते हैं, तो आप ईवेंट को सक्षम और परिभाषित करने के लिए Android Studio में इसके साथ काम कर सकते हैं. ऐसा करने के दो तरीके हैं:
### <a name="option-1-use-jitpack-recommended"></a>विकल्प 1: जितपैक का उपयोग करें (अनुशंसित)
1. अपने रूट `build.gradle` में JitPack रिपॉजिटरी जोड़ें:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. निर्भरता जोड़ें:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>विकल्प 2: डाउनलोड लिंक का उपयोग करें
1. [संलग्नता अंतर्दृष्टि Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) डाउनलोड करें, और `libs` फ़ोल्डर में `eiandroidsdk-debug.aar` फ़ाइल को रखें ।

1. अपनी प्रोजेक्ट स्तरीय `build.gradle` फ़ाइल खोलें और निम्न स्निपेट्स जोड़ें:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>ऑटो-इंस्ट्रूमेंटेशन सक्षम करें

1. `manifests` फ़ोल्डर के अंतर्गत स्थित अपनी `AndroidManifest.xml` फ़ाइल में नेटवर्क और इंटरनेट की अनुमति जोड़ें.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. अपनी `AndroidManifest.xml` फ़ाइल के माध्यम से सहभागिता इनसाइट्स SDK कॉन्फ़िगरेशन सेट करें.

1. **इंस्टॉलेशन गाइड** से XML स्निपेट कॉपी करें। `Your-Ingestion-Key` स्वचालित रूप से पॉप्युलेट होना चाहिए।

   > [!NOTE]
   > आपको `${applicationId}` अनुभाग प्रतिस्थापित करने की आवश्यकता नहीं है। यह स्वचालित रूप से पॉप्युलेट होता है.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. उपरोक्त `autoCapture` फ़ील्ड को `true` या `false` पर सेट करके `View` इवेंट की स्वतः-कैप्चर को सक्षम या अक्षम करें। 

   >[!NOTE]
   >`Action` ईवेंट को मैन्युअल रूप से जोड़ने की आवश्यकता है।

1. (वैकल्पिक) अन्य कॉन्फ़िगरेशन में एंडपॉइंट कलेक्टर URL सेट करना शामिल है। उन्हें . में अंतर्ग्रहण कुंजी मेटाडेटा के अंतर्गत जोड़ा जा सकता है`AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>कस्टम ईवेंट लागू करें

SDK को शुरु करने के बाद, आप `MainActivity` परिवेश में ईवेंट और उनके गुणों के साथ काम कर सकते हैं.


Java:
```java
Analytics analytics = new Analytics();
```

कोटलिन:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>सभी इवेंट के लिए गुण सेट करें (वैकल्पिक)

Java:
```java
analytics.setProperty("year", 2021);
```

कोटलिन:
```kotlin
analytics.setProperty("year", 2021)
```

संदर्भ इवेंट गुणों के लिए निम्नलिखित प्रकार समर्थित हैं:
- String
- तारीख
- दुगुना
- लंबा
- Boolean
- UUID

### <a name="track-an-event"></a>किसी इवेंट को ट्रैक करें

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

कोटलिन:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>अपने ईवेंट के लिए उपयोगकर्ता विवरण सेट करें (वैकल्पिक)

SDK आपको वह उपयोगकर्ता जानकारी को परिभाषित करने देता है जिसे हर इवेन्ट के साथ भेजा जा सकता है. आप `Analytics` स्तर पर `setUser(user: User)` API को कॉल करके उपयोगकर्ता जानकारी निर्दिष्ट कर सकते हैं।

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

कोटलिन:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

`User` डेटा श्रेणी में निम्नलिखित स्ट्रिंग गुण हैं:

- **localId**: उपयोगकर्ता की स्थानीय ID.
- **authId**: प्रमाणित उपयोगकर्ता ID.
- **authType** : प्रमाणित उपयोगकर्ता ID प्राप्त करने के लिए उपयोग किया जाने वाला प्रमाणीकरण प्रकार।
- **नाम**: उपयोगकर्ता का नाम.
- **ईमेल**: उपयोगकर्ता का ईमेल पता.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
