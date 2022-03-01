---
title: Eksportere Customer Insights-data til Microsoft Advertising
description: Finn ut hvordan du konfigurerer tilkoblingen og eksporten til Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124528"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Eksportere segmenter til Microsoft Advertising (forhåndsversjon)

Eksporter Customer Insights-segmenter til Microsoft Advertising for å opprette Customer Match-målgrupper. Bruk disse målgruppene for annonsekampanjene.

## <a name="prerequisites"></a>Forutsetninger

-   En [Microsoft Advertising-konto](https://ads.microsoft.com/) og tilhørende administratorlegitimasjon.
-   Du har godtatt vilkårene for bruk for Customer Match. 
-   [Konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt med en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 500 000 profiler per eksport til Microsoft Advertising.
- Eksport til Microsoft Advertising er begrenset til segmenter.
- Det kan ta opptil 10 minutter å eksportere 500 000 profiler til Microsoft Advertising. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Konfigurere tilkoblingen til Microsoft Advertising

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Microsoft Advertising** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Standarden er administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Microsoft Advertising.

1. Velg **Godkjenn med Microsoft Advertising**, og angi legitimasjonen for administrator for Microsoft Advertising.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Microsoft Advertising-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Velg segmentene som skal eksporteres. Customer Match-målgruppene i Microsoft Advertising opprettes automatisk med navnet på segmentene som er valgt for eksport. Hvert segment fører til en egen Customer Match-målgruppe. 

1. Angi **Kunde-ID og konto-ID for Microsoft Advertising**. Du finner kunde-ID-en (`cid`) og konto-ID-en (`aid`) i parameterne for nettadressen når du er logget på Microsoft Advertising.

1. Velg feltet i den enhetlige kundeprofilen med e-postadressen til en kunde i feltet **E-post** i delen **Datasamsvar**. Det kreves for å eksportere segmenter til Microsoft Advertising.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for å overføre data til Microsoft Advertising, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Microsoft Advertising oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Administratoren for Dynamics 365 Customer Insights kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
