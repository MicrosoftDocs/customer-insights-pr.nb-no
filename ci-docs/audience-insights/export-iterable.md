---
title: Eksportere Customer Insights-data til Iterable
description: Finn ut hvordan du konfigurerer og eksporterer til Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4de499fcc4a5a0dcc2dfd3bae02913c81a59647b
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524161"
---
# <a name="export-segment-lists-to-iterable-preview"></a>Eksportere segmentlister til Iterable (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Iterable, og bruk dem for markedsføringsaktiviteter.

## <a name="prerequisites"></a>Krav

-   Du har en [Iterable-konto](https://iterable.com/) og tilsvarende administratorlegitimasjon.
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Eksport til Iterable er begrenset til segmenter.
- Det kan ta opptil 30 minutter å eksportere 1 million kundeprofiler til Iterable. 
- Antall kundeprofiler du kan eksportere til Iterable, avhenger av og begrenses til kontrakten med Iterable.

## <a name="set-up-connection-to-iterable"></a>Konfigurere tilkoblingen til Iterable

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Iterable** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Oppgi [API-nøkkelen for Iterable](https://support.iterable.com/hc/en-us/articles/360043464871) for å fortsette å logge på. 

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Iterable.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Iterable-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

3. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Du må eksportere segmenter til Iterable. Listen som opprettes i Iterable, får nøyaktig samme navn som segmentnavnet i Dynamics 365 Customer Insights.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Iterable, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Iterable oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
