---
title: Komme i gang med iOS SDK
description: Finne ut hvordan du tilpasser og kjører iOS SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226227"
---
# <a name="get-started-with-the-ios-sdk"></a>Komme i gang med iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Denne opplæringen veileder deg gjennom instrumentering av iOS-appen med en Dynamics 365 Customer Insights-engasjementsinnsikts-SDK. Du kommer til å se hendelser i portalen om fem minutter eller tidligere.

## <a name="configuration-options"></a>Konfigurasjonsalternativer

Følgende konfigurasjonsalternativer kan sendes til SDK via den angitte `EIConfig.plist`-filen:

- **ingestionKey**: Inkluderingsnøkkelen brukes til å sende hendelser til prosjektet.
- **autocollectAction**: En boolsk verdi for å aktivere eller deaktivere automatisk instrumentering av handlingshendelsen.
- **autocollectView**: En boolsk verdi for å aktivere eller deaktivere automatisk instrumentering av visningshendelsen.
- **endpointUrl**: Endepunkt URL-adressen der hendelsene skal rettes.

## <a name="prerequisites"></a>Forutsetninger

- Xcode-versjon 9+
- iOS-version 8.2+
- En inkluderingsnøkkel (se instruksjonene nedenfor for å hente)

## <a name="integrate-the-sdk-into-your-application"></a>Integrere SDKen i programmet

Start prosessen ved å velge et arbeidsområde du vil arbeide i, velg iOS-mobilplattformen, og last ned SDK.

- Bruk arbeidsområdeveksleren i den venstre navigasjonsruten til å velge arbeidsområdet.

- Hvis du ikke har et eksisterende arbeidsområde, velger du **Nytt arbeidsområde** og følger fremgangsmåten for å opprette [et nytt arbeidsområde](create-workspace.md).

- Når du har opprettet et arbeidsområde, går du til **Administrator** > **Arbeidsområde**, og deretter velger du **Installasjonsveiledning**.

## <a name="configure-the-sdk"></a>Konfigurere SDKen

Når du har lastet ned SDKen, kan du arbeide med den i Xcode for å aktivere og definere hendelser. Du kan gjøre dette på to ulike måter

### <a name="option-1-using-cocoapods-recommended"></a>Alternativ 1: Bruk av CocoaPods (anbefales)
CocoaPods er avhengighetsansvarlig for Swift- og Objective-C-cocoa-prosjekter. Ved hjelp av det blir det enklere å integrere engasjementsinnsikts-SDK for iOS. Med CocoaPods kan du også oppgradere til den nyeste versjonen av engasjementsinnsikts-SDK. Slik bruker CocoaPods til å integrere engasjementsinnsikts-SDK i Xcode-prosjektet. 

1. Installer CocoaPods. 

1. Opprett en ny fil med navnet Podfile i rotkatalogen for prosjektet, og legg til følgende setninger i den. Bytt YOUR_TARGET_PROJECT_NAME med navnet på Xcode-prosjektet. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Pod-konfigurasjonen ovenfor inneholder både feilrettings- og lanseringsversjonene for SDK-en. Velg hvilken som helst av dem som passer best for prosjektet.

1. Installer poden ved å utføre følgende kommando: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Alternativ 2: Bruk av nedlastingskobling

1. Last ned [Engasjementinnsikt iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip), og plasser `EIObjC.xcframework`-filen i `Frameworks`-mappen.

1. Hvis en `Frameworks`-mappe ikke finnes, oppretter du en i prosjektmappen.

## <a name="enable-auto-instrumentation"></a>Aktivere automatisk instrumentering
 
Du kan enkelt aktivere automatisk instrumentering uten koding. Når prosjektet kjører, spores `view`- og `action`-hendelsene ved hjelp av den konfigurerte inkluderingsnøkkelen. 

1. Oppdater og inkluder den angitte `EIConfig.plist`-filen i prosjektkatalogmappen for følgende felt:
    - inkluderingsnøkkel = `"Your-Ingestion-Key"`
    - autocollectView = JA
    - autocollectAction = JA

2. Legg deretter til `EIConfig.plist`-filen i prosjektet i Xcode. 



For å deaktivere automatisk instrumentering, oppdaterer du følgende felt i den inkluderte `EIConfig.plist`-filen i prosjektkatalogmappen. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementere egendefinerte hendelser

1. Åpne prosjektet i Xcode, og naviger til **Generelt**-innstillingene. 
1. Legg til `EIObjC.xcframework` i prosjektet under delen for rammeverk, biblioteker og innebygd innhold.

1. Importer header-filen for rammeverk i AppDelegate.m med følgende snutt:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Initialiser engasjements-SDK-en fra programmet: didFinishLaunchingWithOptions.
1. Kopier XML-snutten fra **installasjonsveiledningen**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Spor en hendelse:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Angi brukerdetaljer for hendelsen

Med SDK-en kan du definere brukerinformasjon som kan sendes med hver hendelse. Du kan angi brukerinformasjon ved å kalle opp `setUser:(nonnull EIUser *)user`-APIen på SDKen.

Angivelse av brukerdetaljer på `Analytics`-nivå betyr at alle telemetrier har denne informasjonen. Hvis du imidlertid angir på hendelsesnivået ved å kalle `setUser:(nonnull EIUser *)user`-API-en for EIEvent-objektet, vil bare den spesifikke hendelsen inneholde informasjonen.

Dataklassen `EIUser` inneholder følgende NSString-egenskaper:

- **localId**: Brukerens lokale ID.
- **authId**: Den godkjente bruker-ID-en.
- **authType**: Godkjenningstypen som brukes til å hente den godkjente bruker-ID-en.
- **name**: Brukerens navn.
- **email**: Brukerens e-postadresse.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
