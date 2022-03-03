---
title: Eksporter Customer Insights-data til Klaviyo
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 027aee70d9fdab0a92d7fd99209a6ac2ca3cc361
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225480"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Eksporter segmentlister til Klaviyo (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Klaviyo, og bruk dem for markedsføringsaktiviteter.

## <a name="prerequisites"></a>Forutsetninger

-   Du har en [Klaviyo-konto](https://www.klaviyo.com/) og tilsvarende administratorlegitimasjon.
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 100 000 kundeprofiler per eksport til Klaviyo.
- Eksport til Klaviyo er begrenset til segmenter.
- Det kan ta opptil 20 minutter å eksportere 1 million kundeprofiler til Klaviyo. 
- Antall kundeprofiler du kan eksportere til Klaviyo, avhenger av og begrenses til kontrakten med Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Konfigurer tilkoblingen til Klaviyo

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Klaviyo** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Oppgi [API-nøkkelen for Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) for å fortsette å logge på. 

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å starte tilkoblingen til Klaviyo.

1. Velg **Godkjenn med Klaviyo**, og oppgi administratorlegitimasjonen for Klaviyo.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg feltet **Tilkobling for eksport**, og velg en tilkobling fra Klaviyo-delen. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi [**Klaviyo-liste-ID-en**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Det kreves at du eksporterer segmenter til Klaviyo.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du gjør det mulig for Dynamics 365 Customer Insights å overføre data til Klaviyo, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data som personlige data. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Klaviyo oppfyller personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
