---
title: Eksportere segmenter til AdRoll (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 13c7dd3b8556ad807fba6c537525b463480e860b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081564"
---
# <a name="export-segments-to-adroll-preview"></a>Eksportere segmenter til AdRoll (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til AdRoll, og bruk dem for reklame. 

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

- Du har en [AdRoll-konto](https://www.adroll.com/) og tilhørende legitimasjon for administrator.
- Du har [konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 250 000 kundeprofiler om gangen til AdRoll.
- Du kan ikke eksportere segmenter med under 100 kundeprofiler til AdRoll. 
- Eksport til AdRoll er begrenset til segmenter.
- Det kan ta opptil 10 minutter å eksportere opptil 250 000 kundeprofiler til AdRoll. 
- Antall kundeprofiler du kan eksportere til AdRoll, avhenger av og begrenses til kontrakten med AdRoll.

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

1. Velg en tilkobling fra AdRoll-delen i feltet **Tilkobling for eksport**. Hvis navnet på denne delen ikke vises, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi **ID for AdRoll-annonsør**. Hvis du vil ha mer informasjon, kan du se [AdRoll-annonsørprofiler](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Dette kreves for å eksportere segmenter til AdRoll.

1. Velg segmentene du vil eksportere. Velg et segment med minst 100 medlemmer. Du kan ikke eksportere mindre segmenter. I tillegg er maksimumsstørrelsen for et segment som skal eksporteres, 250 000 medlemmer per eksport. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). 

Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til AdRoll, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at AdRoll oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.
