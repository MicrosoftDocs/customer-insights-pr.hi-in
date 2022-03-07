---
title: iOS SDK नमूना चलाएँ
description: iOS SDK के बारे में जानने के लिए नमूना प्रोजेक्ट
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: hi-IN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232844"
---
# <a name="run-the-ios-sdk-sample"></a>iOS SDK नमूना चलाएँ

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

यह नमूना iOS प्रोजेक्ट आपको यह समझने में मदद करता है कि SDK किसी ऐप में कैसे काम करता है। आपको कोड नहीं लिखना होगा। बस अपनी अंतर्ग्रहण कुंजी जोड़ें और आप तुरंत अपने कार्यस्थान में ईवेंट देख सकते हैं।

## <a name="prerequisites"></a>पूर्वावश्यकताएँ

- [Xcode संस्करण 9+](https://developer.apple.com/xcode/downloads/)
- [अंतर्ग्रहण कुंजी](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>iOS SDK नमूना डाउनलोड करें

1. [संलग्नता इनसाइट्स iOS SDK नमूना डाउनलोड करें](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. कम्प्रेस्ड फ़ाइल `ei-ios-sample.zip` को अनज़िप करें.
1. Xcode में नमूना ऐप प्रोजेक्ट खोलें।
1. `EIConfig.plist` फाइल में, **व्यवस्थापन** > **कार्यस्थान** > **स्थापना निर्देशिका** के अंतर्गत संलग्नता इनसाइट्स से अपने कार्यस्थान अंतर्ग्रहण कुंजी के साथ `ingestionKey` फ़ील्ड में `“YOUR-INGESTION-KEY”` स्ट्रिंग को बदलें।
1. नमूना प्रोजेक्ट प्रारंभ करने के लिए, **रन करें** का चयन करें.
1. अपने कार्यस्थान में इवेंट्स देखें।

[!INCLUDE[footer-include](../includes/footer-banner.md)]
