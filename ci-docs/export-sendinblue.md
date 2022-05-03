---
title: Eksportere Customer Insights-data til Sendinblue
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e6d63e0017caa50379426cd5f9b663571b568de7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646766"
---
# <a name="export-segments-to-sendinblue-preview"></a>Eksportere segmenter til Sendinblue (forhåndsvisning)

Eksporter segmenter for enhetlige kundeprofiler for å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Sendinblue.

## <a name="prerequisites-for-connection"></a>Forutsetninger for tilkobling

-   Du har en [Sendinblue-konto](https://www.sendinblue.com/) og tilsvarende administratorlegitimasjon.
-   Det finnes eksisterende lister i Sendinblue og de tilhørende IDene.
-   Du har [konfigurerte segmenter](segments.md).
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million kundeprofiler per eksport til Sendinblue.
- Eksport til Sendinblue er begrenset til segmenter.
- Det kan ta opptil 90 minutter å eksportere segmenter med totalt 1 million kundeprofiler. 
- Antall kundeprofiler du kan eksportere til Sendinblue, avhenger av og begrenses til kontrakten med Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Konfigurere tilkobling til Sendinblue

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Sendinblue** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **[API-nøkkelen for SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar** og velg **Koble til** for å initialisere tilkoblingen til Sendinblue.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg feltet **Tilkobling for eksport**, og velg en tilkobling fra Sendinblue-delen. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi **Sendinblue-liste-IDen** 

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. 

1. Du kan eventuelt eksportere **Fornavn**, **Etternavn** og **Telefon** for å opprette mer tilpassede e-postmeldinger. Velg **Legg til attributt** for å tilordne disse feltene.

1. Velg segmentene du vil eksportere. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du gjør det mulig for Dynamics 365 Customer Insights å overføre data til Sendinblue, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data som personlige data. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Sendinblue oppfyller personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.


[!INCLUDE [footer-include](includes/footer-banner.md)]
