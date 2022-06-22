---
title: Eksportere Customer Insights-data til Snapchat
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d64b482c322af8632e29ec41d6e34c390c5e646c
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947288"
---
# <a name="export-segments-to-snapchat-preview"></a>Eksportere segmenter til Snapchat (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Snapchat, og bruk dem til reklame. 

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

-   Du har en [Snapchat-forretningskonto](https://business.snapchat.com/), en [Snapchat-annonsekonto](https://ads.snapchat.com/) og tilsvarende administratorlegitimasjon. Du må minst være medlem av en organisasjonskonto og dataansvarlig for en bestemt annonsekonto. 
-   Du må ha minst én målgruppe i Snapchat Audience Manager av typen SAM (Snap Audience Match). 
-   Du har [konfigurerte segmenter](segments.md) i Customer Insights.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Eksport til Snapchat er begrenset til segmenter.
- Det kan ta opptil 15 minutter å eksportere 1 million kundeprofiler til Snapchat. 

## <a name="set-up-connection-to-snapchat"></a>Konfigurere tilkobling til Snapchat

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Snapchat** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Snapchat.

1. Velg **Godkjenn med Snapchat**, og angi legitimasjonen for administrator for Snapchat. 

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Snapchat-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi [**ID-en for Snapchat-segmentet/-målgruppen**](https://businesshelp.snapchat.com/s/article/custom-audiences). ID-en for målgruppe finner du i nettadressen etter at du har valgt målgruppe Snapchat Audience Manager. 

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Det kreves for å eksportere segmenter til Snapchat.

1. Velg segmentene du vil eksportere. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for å overføre data til Snapchat, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, for eksempel personlige opplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Snapchat oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
