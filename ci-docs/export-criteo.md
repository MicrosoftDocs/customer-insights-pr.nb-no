---
title: Eksportere Customer Insights-data til Criteo
description: Finn ut hvordan du konfigurerer og eksporterer til Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 854f5f0c53f053fc5d742d69a045db1926fec00c
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808773"
---
# <a name="export-segments-to-criteo-preview"></a>Eksporter segmenter til Criteo (forhåndsversjon)

Eksporter segmenter for enhetlige kundeprofiler til å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Criteo.

## <a name="prerequisites-for-connection"></a>Forutsetninger for tilkobling

-   Du har en [Criteo Dynamics Retargeting-konto](https://www.criteo.com/login/) og tilsvarende administratorlegitimasjon.
-   Du har [konfigurerte segmenter](segments.md).
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million kundeprofiler per eksport til Criteo.
- Eksport til Criteo er begrenset til segmenter.
- Det kan ta opptil 30 minutter å eksportere segmenter med totalt 1 million kundeprofiler. 
- Antall kundeprofiler du kan eksportere til Criteo, avhenger av og begrenses til kontrakten med Criteo.

## <a name="set-up-connection-to-criteo"></a>Konfigurere tilkoblingen til Criteo

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Criteo** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg **Jeg godtar** for å bekrefte **datapersonvern og samsvar**, og velg **Koble til** for å starte tilkoblingen til Criteo.

1. Velg **Godkjenn med Criteo**, og angi administratornavn og legitimasjon for Criteo. 

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Criteo-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg. 

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. 

1. Alternativt kan du eksportere **annonsør-ID** og **navn**

1. Velg segmentene du vil eksportere. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Criteo, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Criteo oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](includes/footer-banner.md)]
