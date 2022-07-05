---
title: Eksporter segmenter til Braze (forhåndsversjon)
description: Finn ut hvordan du konfigurerer og eksporterer til Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081493"
---
# <a name="export-segments-to-braze-preview"></a>Eksporter segmenter til Braze (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Braze, og bruk dem for markedsføringsaktiviteter.

## <a name="prerequisites"></a>Forutsetning

- En [Braze-konto](https://www.braze.com/) og tilsvarende administratorlegitimasjon.
- Eksisterende [segmenter i Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse og en Kunde-ID for Braze.

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

1. Velg en tilkobling fra Braze-delen i feltet **Tilkobling for eksport**. Hvis denne delen ikke vises, er ingen tilkoblinger av denne typen tilgjengelige for deg.  

1. Legg til et **visningsnavn** for eksporten.

1. Legg til API-identifikatoren for Braze-segmentet som du vil eksportere til, i feltet **API-identifikator for Braze-segment**. Du finner identifikatoren i segmentdetaljene på Braze-plattformen.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Velg feltet som representerer kundens Braze-ID i feltet **Kunde-ID**. Det kreves for å eksportere segmenter til Braze. Du kan eventuelt velge flere felter.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Braze, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Braze oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
