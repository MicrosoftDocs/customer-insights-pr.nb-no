---
title: Eksportere Customer Insights-data til Omnisend
description: Finn ut hvordan du konfigurerer tilkoblingen og eksporterer til Omnisend.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 70bd94ea5e4060094c3d215e3fc263a98df51229
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647166"
---
# <a name="export-segments-to-omnisend-preview"></a>Eksportere segmenter til Omnisend (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Omnisend, og bruk dem til markedsføringsaktiviteter.

## <a name="prerequisites"></a>Forutsetninger

-   Du har en [Omnisend-konto](https://www.omnisend.com/) og tilhørende administratorlegitimasjon.
-   Du har [konfigurerte segmenter](segments.md) i Customer Insights.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Det kan ta opptil 4 timer å eksportere 1 million kundeprofiler per eksport til Omnisend.
- Eksport til Omnisend er begrenset til segmenter.
- Antall kundeprofiler du kan eksportere til per eksport til Omnisend, avhenger av kontrakten med Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Konfigurere tilkobling til Omnisend

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Omnisend** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi [API-nøkkel for Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Omnisend.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Omnisend-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Det kreves for å eksportere segmenter til Omnisend. Du kan eventuelt eksportere Fornavn, Etternavn, Adresse, Land/område, Delstat, Poststed og Postnummer for å opprette mer tilpassede e-poster. Velg **Legg til attributt** for å tilordne disse feltene.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for å overføre data til Ommisend, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Omnisend oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.
