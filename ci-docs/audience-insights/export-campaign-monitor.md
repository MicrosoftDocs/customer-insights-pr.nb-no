---
title: Eksportere Customer Insights-data til Campaign Monitor
description: Lær hvordan du konfigurerer tilkoblingen og eksporten til Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d2cc3ec944faa1d77ffb44e8abb422d753c5625d0ccef75cbb7efb14cb7c3741
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031899"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Eksportere segmenter til Campaign Monitor (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Campaign Monitor, og bruk dem for markedsføringsaktiviteter.

## <a name="prerequisites"></a>Forutsetninger

-   Du har en [Campaign Monitor-konto](https://www.campaignmonitor.com/) og tilhørende administratorlegitimasjon.
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 1 million profiler per eksport til Campaign Monitor.
- Eksport til Campaign Monitor er begrenset til segmenter.
- Det kan ta opptil 20 minutter å eksportere 1 million profiler til Campaign Monitor. 
- Antall profiler du kan eksportere til Campaign Monitor, er avhengig av og begrenset av kontrakten med Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Konfigurer tilkoblingen til Campaign Monitor

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Campaign Monitor** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Campaign Monitor.

1. Velg **Godkjenn med Campaign Monitor**, og angi legitimasjonen for administrator for Campaign Monitor.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Campaign Monitor-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi [**liste-ID-en for Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Generer API-nøkkelen](https://www.campaignmonitor.com/api/getting-started/) fra **Kontoinnstillinger** i Campaign Monitor først for å vise API-liste-IDen.  

3. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. Det kreves for å eksportere segmenter til Campaign Monitor.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for å overføre data til Campaign Monitor, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, for eksempel personlige opplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Campaign Monitor oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
