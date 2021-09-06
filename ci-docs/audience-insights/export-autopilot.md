---
title: Eksportere Customer Insights-data til Autopilot
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c9ada8a6f4e4546990a1360567b400033050119c4c4c9a3df1af8fcaab75e157
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032037"
---
# <a name="export-segments-to-autopilot-preview"></a>Eksportere segmenter til Autopilot (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til Autopilot, og bruk dem for e-postmarkedsføring i Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

-   Du har en [Autopilot-konto](https://www.autopilothq.com/) og tilhørende påloggingsinformasjon for administrator.
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 100 000 profiler totalt til Autopilot.
- Eksport til Autopilot er begrenset til segmenter.
- Det kan ta opptil noen timer å eksportere opptil 100 000 profiler til Autopilot. 
- Antallet profiler du kan eksportere til Autopilot, er avhengig av og begrenset til kontrakten din med Autopilot.

## <a name="set-up-connection-to-autopilot"></a>Konfigurere tilkobling til Autopilot

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Autopilot** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

3. Angi [API-nøkkelen for Autopilot](https://autopilot.docs.apiary.io/#).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Autopilot.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Autopilot-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

3. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**.

1. Velg segmentene du vil eksportere. Vi **anbefaler på det sterkeste at du ikke eksporterer mer enn 100 000 kundeprofiler totalt** til Autopilot. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Autopilot, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Autopilot oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
