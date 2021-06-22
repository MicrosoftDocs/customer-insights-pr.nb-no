---
title: Eksportere Customer Insights-data til RollWorks
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124101"
---
# <a name="export-segments-to-rollworks-preview"></a>Eksportere segmenter til RollWorks (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til RollWorks, og bruk dem til reklame. 

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

-   Du har en [RollWorks-konto](https://www.rollworks.com/) og tilhørende administratorlegitimasjon.
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 250 000 profiler per eksport til RollWorks.
- Du kan ikke eksportere segmenter med færre enn 100 profiler til RollWorks. 
- Eksport til RollWorks er begrenset til segmenter.
- Det kan ta opptil 10 minutter å eksportere opptil 250 000 profiler til RollWorks. 
- Antall profiler du kan eksportere til RollWorks, er avhengig av og begrenset av kontrakten med RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Konfigurer tilkoblingen til RollWorks

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **RollWorks** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til RollWorks.

1. Velg **Godkjenn med RollWorks**, og angi legitimasjonen for administrator for RollWorks.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra RollWorks-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi **ID for RollWorks-annonser** [RollWorks-annonser](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. Det kreves for å eksportere segmenter til RollWorks.

1. Velg segmentene du vil eksportere. Velg et segment med minst 100 medlemmer. Du kan ikke eksportere mindre segmenter. I tillegg er maksimumsstørrelsen for et segment som skal eksporteres, 250 000 medlemmer per eksport. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for å overføre data til RollWorks, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, for eksempel personlige opplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at RollWorks oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
