---
title: Android SDK-eksempel
description: Eksempel på prosjekt for å lære om Android SDK
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
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035838"
---
# <a name="run-the-android-sdk-sample"></a>Kjøre Android SDB-eksemplet

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dette Android-eksempelprosjektet hjelper deg med å forstå hvordan SDK fungerer i en app. Du behøver ikke å skrive kode. Bare legg til inkluderingssnøkkelen, og du kan se hendelser i arbeidsområdet med en gang.

## <a name="prerequisites"></a>Forutsetninger

- [Android Studio](https://developer.android.com/studio)
- [Inkluderingsnøkkel](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Laste ned Android SDK-eksemplet

1. [Last ned Android SDK-eksempelet for engasjementsinnsikt](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Pakk ut den komprimerte filen `ei-android-sample.zip`.
1. Åpne den utpakkede mappen i Android Studio.
1. I `AndroidManifest.xml`-filen erstatter du strengen `"Your-Ingestion-Key"` med inkluderingsnøkkelen for arbeidsområdet fra Engasjementinnsikt under **Admin** > **Arbeidsområde** > **Installasjonsveiledning**. 

   > [!NOTE]
   > Du trenger ikke å erstatte `${applicationId}`-delen. Den fylles ut automatisk.

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

1. Velg **Kjør** for å starte eksempelprosjektet.
1. Vise hendelsene i arbeidsområdet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
