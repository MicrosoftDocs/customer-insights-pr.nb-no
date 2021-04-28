---
title: Eksporter Customer Insights-data til AdRoll
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895971"
---
# <a name="export-segment-lists-to-adroll-preview"></a>Eksportere segmentlister til AdRoll (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til AdRoll, og bruk dem for reklame. 

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

-   Du har en [AdRoll-konto](https://www.adroll.com/) og tilhørende legitimasjon for administrator.
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 250 000 profiler per eksport til AdRoll.
- Du kan ikke eksportere segmenter med færre enn 100 profiler til AdRoll. 
- Eksport til AdRoll er begrenset til segmenter.
- Det kan ta opptil 10 minutter å eksportere opptil 250 000 profiler til AdRoll. 
- Antallet profiler du kan eksportere til AdRoll, er avhengig av og begrenset til kontrakten din med AdRoll.

## <a name="set-up-connection-to-adroll"></a>Konfigurer tilkobling til AdRoll

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **AdRoll** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til AdRoll.

1. Velg **Godkjenn med AdRoll**, og angi administratorlegitimasjonen din for AdRoll. 

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra AdRoll-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Skriv inn **ID for AdRoll-annonsør** Hvis du vil ha mer informasjon, kan du se [Profiler for AdRoll-annonsør](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. Dette kreves for å eksportere segmenter til AdRoll.

1. Velg segmentene du vil eksportere. Velg et segment med minst 100 medlemmer. Du kan ikke eksportere mindre segmenter. I tillegg er maksimumsstørrelsen for et segment som skal eksporteres, 250 000 medlemmer per eksport. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til AdRoll, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at AdRoll oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
