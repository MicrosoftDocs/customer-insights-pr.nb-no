---
title: Eksportere Customer Insights-data til ActiveCampaign
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 14d420205a5c60d471ef21a04ab6d02295a65ca8fd5205ba782a300703b06102
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032221"
---
# <a name="export-segments-to-activecampaign-preview"></a>Eksportere segmenter til ActiveCampaign (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til ActiveCampaign, og bruk dem for markedsføringsaktiviteter.

## <a name="prerequisites"></a>Forutsetninger

-   Du har en [ActiveCampaign-konto](https://www.activecampaign.com/) og tilsvarende administratorlegitimasjon.
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt med en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 1 million profiler per eksport til ActiveCampaign, og det kan ta opptil 90 minutter å fullføre den.
- Eksport til ActiveCampaign er begrenset til segmenter.
- Antall profiler du kan eksportere til ActiveCampaign, avhenger av kontrakten med ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Konfigurere tilkobling til ActiveCampaign

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **ActiveCampaign** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi [ActiveCampaign-API-nøkkel og vertsnavn for REST-endepunkt](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). REST-endepunktvertsnavnet er bare vertsnavnet, uten https://. 

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å starte tilkoblingen til ActiveCampaign.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere en eksport hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg feltet **Tilkobling for eksport**, og velg en tilkobling fra ActiveCampaign-delen. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi [**ActiveCampaign-liste-IDen**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

3. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. Det kreves at du eksporterer segmenter til ActiveCampaign. Du kan eventuelt eksportere Fornavn, Etternavn og Telefon for å opprette mer tilpassede e-postmeldinger. Velg Legg til attributt for å tilordne disse feltene.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du gjør det mulig for Dynamics 365 Customer Insights å overføre data til ActiveCampaign, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data som personlige data. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at ActiveCampaign oppfyller personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.
