---
title: Komme i gang med Android SDK
description: Finn ut hvordan du tilpasser og kjører Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a060ac60db71a7b0fb8c0d7a3b0e266004fbee6a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494287"
---
# <a name="get-started-with-the-android-sdk"></a>Komme i gang med Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Denne opplæringen veileder deg gjennom prosessen med å instrumentere Android-appen med en Dynamics 365 Customer Insights-engasjementsinnsikts-SDK. Du kommer til å se hendelser i portalen om fem minutter eller tidligere.

## <a name="configuration-options"></a>Konfigurasjonsalternativer
Følgende konfigurasjonsalternativer kan sendes til SDK:

- **ingestionKey**: Inkluderingsnøkkelen brukes til å sende hendelser til arbeidsområdet.

## <a name="prerequisites"></a>Forutsetninger

- Android Studio

- Minimum Android API-nivå: 16 (Jelly Bean)

- En inkluderingsnøkkel (se nedenfor for instruksjoner om hvordan du skaffer)

## <a name="integrate-the-sdk-into-your-application"></a>Integrere SDKen i programmet
Start prosessen ved å velge et arbeidsområde, velg Android-mobilplattformen, og last ned Android SDK.

- Bruk arbeidsområdeveksleren i den venstre navigasjonsruten til å velge arbeidsområdet.

- Hvis du ikke har et eksisterende arbeidsområde, velger du **Nytt arbeidsområde** og følger fremgangsmåten for å opprette [et nytt arbeidsområde](create-workspace.md).

- Når du har opprettet et arbeidsområde, går du til **Administrator** > **Arbeidsområde**, og deretter velger du **Installasjonsveiledning**. 

## <a name="configure-the-sdk"></a>Konfigurere SDKen

Når du har lastet ned SDKen, kan du arbeide med den i Android Studio for å aktivere og definere hendelser. Du kan gjøre dette på to ulike måter:
### <a name="option-1-using-jitpack-recommended"></a>Alternativ 1: Bruk av JitPack (anbefales)
1. Legg til JitPack-repositorium i roten `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Legg til avhengigheten:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-using-download-link"></a>Alternativ 2: Bruk av nedlastingskobling
1. Last ned [Engasjementinnsikt Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip), og plasser `eiandroidsdk-debug.aar`-filen i `libs`-mappen.

1. Åpne filen `build.gradle` for prosjektnivå, og legg til følgende snutter:
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

1. Legg til tillatelse for nettverk og Internett i `AndroidManifest.xml`-filen under `manifests`-mappen. 
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
    
1. Konfigurer engasjementsinnsikt-SDK-konfigurasjonen via `AndroidManifest.xml`-filen. 

## <a name="enable-auto-instrumentation"></a>Aktivere automatisk instrumentering
1. Kopier XML-snutten fra **installasjonsveiledningen**. `Your-Ingestion-Key` fylles ut automatisk.

   > [!NOTE]
   > Du trenger ikke å erstatte `${applicationId}`-delen. Den fylles ut automatisk.
   

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

1. Aktiver eller deaktiver autosporing for `View`-hendelser ved å sette `autoCapture`-feltet ovenfor til `true` eller `false`. For øyeblikket må `Action`-hendelser legges til manuelt.

1. (Valgfritt) Andre konfigurasjoner inkluderer angivelse av samle-URL for endepunkt. De kan legges til under inkluderingsnøkkelmetadataene i `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="implement-custom-events"></a>Implementere egendefinerte hendelser

Når du har initialisert SDK-en, kan du arbeide med hendelser og egenskapene deres i `MainActivity`-miljøet.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Angi egenskap for alle hendelser (valgfritt)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Følgende typer støttes for egenskaper for konteksthendelser:
- String
- Dato
- Dobbel
- Lang
- Boolean
- UUID

### <a name="track-an-event"></a>Spor en hendelse

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Angi brukerdetaljer for hendelsen (valgfritt)

Med SDK-en kan du definere brukerinformasjon som kan sendes med hver hendelse. Du kan angi brukerinformasjon ved å kalle opp `setUser(user: User)`-APIen på `Analytics`-nivå.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Dataklassen `User` inneholder følgende strengegenskaper:

- **localId**: Brukerens lokale ID.
- **authId**: Den godkjente bruker-ID-en.
- **authType:** Godkjenningstypen som brukes til å få godkjent bruker-ID.
- **name**: Brukerens navn.
- **email**: Brukerens e-postadresse.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
