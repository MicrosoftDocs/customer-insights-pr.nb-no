---
title: Komme i gang med Android SDK
description: Finn ut hvordan du tilpasser og kjører Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036930"
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

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Trinn 1. Integrere SDKen i programmet
Start prosessen ved å velge et arbeidsområde, velg Android-mobilplattformen, og last ned Android SDK.

- Bruk arbeidsområdeveksleren i den venstre navigasjonsruten til å velge arbeidsområdet.

- Hvis du ikke har et eksisterende arbeidsområde, velger du **Nytt arbeidsområde** og følger fremgangsmåten for å opprette [et nytt arbeidsområde](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Trinn 2. Konfigurere SDKen

1. Når du har opprettet et arbeidsområde, går du til **Administrator** > **Arbeidsområde**, og deretter velger du **Installasjonsveiledning**. 

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

1. Konfigurer engasjementsinnsikt-SDK-konfigurasjonen via `AndroidManifest.xml`-filen under `manifests`-mappen. 
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

1. Aktiver eller deaktiver autosporing for `View`-hendelser ved å sette `autoCapture`-feltet ovenfor til `true` eller `false`.

1. (Valgfritt) Andre konfigurasjoner inkluderer angivelse av samle-URL for endepunkt. De kan legges til under inkluderingsnøkkelmetadataene i `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Trinn 3. Initialiser SDK fra MainActivity 

Når du har initialisert SDK-en, kan du arbeide med hendelser og egenskapene deres i MainActivity-miljøet.

    
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

### <a name="set-user-details-for-your-event-optional"></a>Angi brukerdetaljer for hendelsen (valgfritt)

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
