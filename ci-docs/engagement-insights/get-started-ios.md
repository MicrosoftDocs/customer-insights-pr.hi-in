---
title: iOS SDK के साथ प्रारंभ करें
description: जानें कि कैसे iOS SDK वैयक्तिकृत और चलाया जाता है
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036875"
---
# <a name="get-started-with-the-ios-sdk"></a>iOS SDK के साथ प्रारंभ करें

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

यह ट्यूटोरियल आपके iOS ऐप्लिकेशन को इंस्ट्रूमेंट करने के माध्यम से Dynamics 365 Customer Insights संलग्नता इनसाइट्स SDK पर आपको दिशानिर्देश देता है। आपको अपने पोर्टल में पाँच मिनट या उससे पहले के ईवेंट दिखाई देने लगेंगे।

## <a name="configuration-options"></a>कॉन्फ़िगरेशन विकल्प

निम्नलिखित कॉन्फ़िगरेशन विकल्प प्रदान किए गए `EIConfig.plist` फ़ाइल के माध्यम से SDK को पास किए जा सकते हैं:

- **अंतर्ग्रहण कुंजी**: आपके प्रोजेक्ट पर ईवेंट भेजने के लिए अंतर्ग्रहण कुंजी का उपयोग किया जाता है।
- **autocollectAction**: एक्शन इवेंट के ऑटो-इंस्ट्रूमेंटेशन को सक्षम या अक्षम करने के लिए एक बूलियन मान।
- **autocollectView**: दृश्य इवेंट के ऑटो-इंस्ट्रूमेंटेशन को सक्षम या अक्षम करने के लिए एक बूलियन मान।
- **endpointUrl**: समाप्ति बिंदु URL जहां इवेंट निर्देशित किए जाएंगे।

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- Xcode संस्करण 9+
- iOS संस्करण 8.2+
- एक अंतर्ग्रहण कुंजी (प्राप्त करने के लिए नीचे दिए गए निर्देश देखें)

## <a name="integrate-the-sdk-into-your-application"></a>SDK को अपने एप्लीकेशन में एकीकृत करें

iOS मोबाइल प्लेटफॉर्म का चयन करके, और SDK डाउनलोड करके कार्य करने के कार्यस्थान का चयन करके प्रक्रिया शुरू करें।

- अपने कार्यस्थान का चयन करने के लिए बाएं नेविगेशन फलक में कार्यस्थान स्विचर का उपयोग करें।

- यदि आपके पास कोई मौजूदा कार्यस्थान नहीं है, तो **नया कार्यस्थान** चुनें और [नया कार्यस्थान](create-workspace.md) बनाने के लिए चरणों का पालन करें।

## <a name="configure-the-sdk"></a>SDK कॉन्फ़िगर करें

एक बार जब आप SDK डाउनलोड कर लेते हैं, तो आप इवेंट को सक्षम और परिभाषित करने के लिए Xcode में इसके साथ काम कर सकते हैं।

1. आपके द्वारा कार्यस्थान बनाने के बाद, **व्यवस्थापक** > **कार्यस्थान** पर जाएँ और फिर **इंस्टॉलेशन गाइड** चुनें।

1. [संलग्नता अंतर्दृष्टि iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) डाउनलोड करें, और `Frameworks` फ़ोल्डर में `EIObjC.xcframework` फ़ाइल को रखें ।

1. यदि `Frameworks` फ़ोल्डर मौजूद नहीं है, प्रोजेक्ट फ़ोल्डर में एक बनाएं।

## <a name="enable-auto-instrumentation"></a>ऑटो-इंस्ट्रूमेंटेशन सक्षम करें
 
आप बिना कोडिंग के आसानी से ऑटो-इंस्ट्रूमेंटेशन को सक्षम कर सकते हैं। जब प्रोजेक्ट चलता है, तो यह स्वचालित रूप से कॉन्फ़िगर की गई अंतर्ग्रहण कुंजी का उपयोग करके `view` तथा`action` इवेंट को ट्रैक करेगा। 

1. अपडेट करें और निम्नलिखित क्षेत्रों के लिए प्रदान किए गए `EIConfig.plist` फ़ाइल को अपने प्रोजेक्ट निर्देशिका फ़ोल्डर में शामिल करें:
    - अंतर्ग्रहण कुंजी = `"Your-Ingestion-Key"`
    - autocollectView = YES
    - autocollectAction = YES

2. फिर Xcode में `EIConfig.plist` फ़ाइल को अपने प्रोजेक्ट से जोड़ें। 



स्वतः-इंस्ट्रूमेंटेशन अक्षम करने के लिए, अपने प्रोजेक्ट निर्देशिका फ़ोल्डर में शामिल किए गए `EIConfig.plist` फ़ाइल में निम्न फ़ील्ड अपडेट करें: 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>कस्टम ईवेंट लागू करें

1. Xcode में अपना प्रोजेक्ट खोलें, और **सामान्य** सेटिंग्‍स पर नेविगेट करें। 
1. 'फ़्रेमवर्क, लाइब्रेरी, और एम्बेडेड सामग्री' सेक्शन के तहत प्रोजेक्ट में `EIObjC.xcframework` जोड़ें।

1. निम्न स्निपेट के साथ AppDelegate.m में फ़्रेमवर्क हेडर फ़ाइल आयात करें:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. एप्लीकेशन से संलग्नता इनसाइट्स SDK शुरु करें: didFinishLaunchingWithOptions।
1. **इंस्टॉलेशन गाइड** से XML स्निपेट कॉपी करें।

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. किसी इवेंट को ट्रैक करें।

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>अपने ईवेंट के लिए उपयोगकर्ता विवरण सेट करें

SDK आपको वह उपयोगकर्ता जानकारी को परिभाषित करने देता है जिसे हर इवेन्ट के साथ भेजा जा सकता है. आप SDK पर `setUser:(nonnull EIUser *)user` API को कॉल करके उपयोगकर्ता जानकारी निर्दिष्ट कर सकते हैं।

`Analytics` स्तर पर उपयोगकर्ता विवरण निर्दिष्ट करने का अर्थ है कि सभी टेलीमेट्री में यह जानकारी होगी। हालाँकि, यदि आप EIEvent ऑब्जेक्ट पर `setUser:(nonnull EIUser *)user` API कॉल करके ईवेंट स्तर पर निर्दिष्ट करते हैं, तो केवल उस विशिष्ट इवेंट में जानकारी होगी।

`EIUser` डेटा श्रेणी में निम्नलिखित NSString गुण हैं:

- **localId**: उपयोगकर्ता की स्थानीय ID.
- **authId**: प्रमाणित उपयोगकर्ता ID.
- **authType**: प्रमाणित उपयोगकर्ता ID पाने के लिए प्रमाणीकरण प्रकार का उपयोग किया जाता है.
- **नाम**: उपयोगकर्ता का नाम.
- **ईमेल**: उपयोगकर्ता का ईमेल पता.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
