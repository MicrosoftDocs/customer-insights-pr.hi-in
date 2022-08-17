---
title: अपना प्रयोग करें Azure Data Lake Storage Gen2 खाता
author: mukeshpo
description: अपने स्वयं के उपयोग की आवश्यकताओं के बारे में जानें Azure Data Lake Storage Customer Insights डेटा संग्रहीत करने के लिए खाता।
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: d2ff49c324c5c5c28213f362ff330d441fcb6052
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: hi-IN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246203"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>अपना प्रयोग करें Azure Data Lake Storage Gen2 खाता

Dynamics 365 Customer Insights आपको अपना सारा डेटा स्टोर करने का विकल्प देता है [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

डेटा लेक स्टोरेज में डेटा सहेज कर, आप सहमति देते हैं कि डेटा उस Azure संग्रहण खाते के लिए उपयुक्त भौगोलिक स्थान पर स्थानांतरित और संग्रहीत किया जाएगा। अधिक जानकारी के लिए देखें [माइक्रोसॉफ्ट ट्रस्ट सेंटर।](https://www.microsoft.com/trust-center)

Customer Insights के व्यवस्थापक कर सकते हैं [वातावरण बनाएं](create-environment.md) तथा[डेटा संग्रहण विकल्प निर्दिष्ट करें](create-environment.md#step-2-configure-data-storage) प्रक्रिया में है।

## <a name="prerequisites-to-use-your-storage-account"></a>आपके संग्रहण खाते का उपयोग करने के लिए पूर्वापेक्षाएँ

- Azure Data Lake Storage खाते उसी Azure क्षेत्र में होने चाहिए जिसे आपने Customer Insights परिवेश बनाते समय चुना था। आप Customer Insights परिवेश के क्षेत्र की जाँच कर सकते हैं **व्यवस्थापक** > **व्यवस्था** > **के बारे में**.
- डेटा लेक स्टोरेज Gen2 होना चाहिए और होना चाहिए [पदानुक्रमित नाम स्थान सक्षम](/azure/storage/blobs/create-data-lake-storage-account). Gen1 संग्रहण खाते समर्थित नहीं हैं।
- नाम का एक कंटेनर`customerinsights` भंडारण खाते पर मौजूद होना चाहिए। Customer Insights में अपने स्वयं के Data Lake Storage का उपयोग करने से पहले आपको इसे बनाना होगा। Customer Insights परिवेश की स्थापना करने वाले व्यवस्थापक को संग्रहण खाते पर संग्रहण ब्लॉब डेटा सहयोगी या संग्रहण ब्लॉब डेटा स्वामी की भूमिका की आवश्यकता होती है या`customerinsights` कंटेनर। संग्रहण खाते में अनुमति प्रदान करने के बारे में अधिक जानकारी के लिए, देखें [एक भंडारण खाता बनाएँ](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Customer Insights को अपने संग्रहण खाते से कनेक्ट करें

जब आप एक नया परिवेश बनाते हैं, तो सुनिश्चित करें कि डेटा लेक संग्रहण खाता मौजूद है और सभी पूर्वापेक्षाएँ पूरी की गई हैं।

1. में **आधार सामग्री भंडारण** पर्यावरण निर्माण के दौरान कदम, सेट **आउटपुट डेटा सहेजें** प्रति**Azure Data Lake Storage यूनिवर्सल Gen2**.
1. चुनें कि कैसे करें **अपना संग्रहण कनेक्ट करें**. आप प्रमाणीकरण के लिए संसाधन-आधारित विकल्प और सदस्यता-आधारित विकल्प के बीच चयन कर सकते हैं। अधिक जानकारी के लिए देखें [एक से कनेक्ट करें Azure Data Lake Storage Azure सेवा प्रिंसिपल का उपयोग करके खाता](connect-service-principal.md).
   - के लिये **Azure सदस्यता**, चुनना**अंशदान**, **ाधन समूह**, तथा**भंडारण खाता** जिसमें शामिल है`customerinsights` कंटेनर।
   - के लिये **खाता कुंजी**, प्रदान करना**खाता नाम** और यह **खाता कुंजी** डेटा लेक स्टोरेज खाते के लिए। इस प्रमाणीकरण पद्धति का उपयोग करने का तात्पर्य है कि यदि आपका संगठन कुंजियों को घुमाता है तो आपको सूचित किया जाता है। आपको चाहिए [पर्यावरण कॉन्फ़िगरेशन अपडेट करें](manage-environments.md#edit-an-existing-environment) घुमाए जाने पर नई कुंजी के साथ।
1. चुनें कि क्या आप संग्रहण खाते से कनेक्ट करने के लिए Azure Private Link का उपयोग करना चाहते हैं और [निजी लिंक से कनेक्शन बनाएं](security-overview.md#set-up-an-azure-private-link) दो-चरणीय प्रक्रिया के साथ।

जब सिस्टम प्रक्रिया जैसे डेटा अंतर्ग्रहण पूर्ण हो जाता है, तो सिस्टम संग्रहण खाते में संगत फ़ोल्डर बनाता है। डेटा फ़ाइलें और *model.json* फ़ाइलें प्रक्रिया नाम के आधार पर बनाई और फ़ोल्डर में जोड़ी जाती हैं.

यदि आप Customer Insights के अनेक परिवेश बनाते हैं और उन परिवेशों से आउटपुट निकायों को अपने संग्रहण खाते में सहेजना चुनते हैं, तो Customer Insights कंटेनर में `ci_environmentID` के साथ प्रत्येक परिवेश के लिए अलग फ़ोल्डर बनाता है.
