---
title: Eksportere Customer Insights-data til Braze
description: Finn ut hvordan du konfigurerer og eksporterer til Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646676"
---
# <a name="export-segment-lists-to-braze-preview"></a>Eksportere segmentlister til Braze (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Braze, og bruk dem for markedsføringsaktiviteter.

## <a name="prerequisites"></a>Krav

-   Du har en [Braze-konto](https://www.braze.com/) og tilsvarende administratorlegitimasjon.
-   Du har [konfigurerte segmenter](segments.md) i Customer Insights.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse og en Kunde-ID for Braze. 

## <a name="known-limitations"></a>Kjente begrensninger

- Eksport til Braze er begrenset til segmenter.
- Det kan ta opptil 40 minutter å eksportere 1 million kundeprofiler til Braze. 
- Antall kundeprofiler du kan eksportere til Braze, avhenger av og begrenses til kontrakten med Braze.

## <a name="set-up-connection-to-braze"></a>Konfigurere tilkoblingen til Braze

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Braze** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Oppgi [API-nøkkelen for Braze](https://www.braze.com/docs/api/basics/) for å fortsette å logge på. 

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Braze.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Braze-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.  

3. I delen **Datasamsvar** i feltet **E-post** velger du feltet som representerer kundens e-postadresse, i "Kunde-ID"-feltet, og deretter velger du feltet som representerer kundens Braze-ID. Det kreves for å eksportere segmenter til Braze. Segmentene i Braze opprettes med samme navn på segmentet som i Dynamics 365 Customer Insights. Du kan velge flere valgfrie felt for samsvarende data. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Braze, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Braze oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
