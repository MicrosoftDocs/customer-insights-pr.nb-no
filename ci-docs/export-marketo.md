---
title: Eksportere segmenter til Marketo (forhåndsvisning)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8cd24cf436bd5fdfd4ec3834d35baa1495e37ca4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053217"
---
# <a name="export-segments-to-marketo-preview"></a>Eksportere segmenter til Marketo (forhåndsvisning)

Du kan eksportere segmenter av enhetlige kundeprofiler for å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Marketo.

## <a name="prerequisites-for-connection"></a>Forutsetninger for tilkobling

-   Du har en [Marketo-konto](https://login.marketo.com/) og tilhørende påloggingsinformasjon for administrator.
-   Det finnes eksisterende lister i Marketo og de tilsvarende ID-ene. Hvis du vil ha mer informasjon, kan du se [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Du har [konfigurerte segmenter](segments.md).
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million kundeprofiler per eksport til Marketo.
- Eksport til Marketo er begrenset til segmenter.
- Det kan ta opptil 3 timer å eksportere segmenter med totalt 1 million kundeprofiler. 
- Antall kundeprofiler du kan eksportere til Marketo, avhenger av og begrenses til kontrakten med Marketo.

## <a name="set-up-connection-to-marketo"></a>Konfigurere tilkobling til Marketo

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Marketo** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **[Marketo-klient-ID-en, klienthemmeligheten og vertsnavnet for REST-endepunktet](https://developers.marketo.com/rest-api/authentication/)**. REST-endepunktvertsnavnet er bare vertsnavnet, uten `https://`. Eksempel: `xyz-abc-123.mktorest.com`. 

1. Velg **Jeg godtar** for å bekrefte **datapersonvern og -samsvar**, og velg **Koble til** for å initialisere tilkoblingen til Marketo.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Marketo-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi **[ID-en for Marketo-listen](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. Liste-ID-en er en ren numerisk verdi. Hvis Marketo-liste-ID-en for eksempel er ST12345A7, fjerner du tegnet før og etter tallene og angir `12345`. 

1. I **Datasamsvar**-delen velger du minst ett felt som representerer kundens e-postadresse eller en kundes Marketo-ID. 

1. Du kan eventuelt eksportere **Fornavn**, **Etternavn**, **Poststed**, **Delstat** og **Land/område** for å opprette mer tilpassede e-poster. Velg **Legg til attributt** for å tilordne disse feltene.

1. Velg segmentene du vil eksportere. Du kan eksportere opptil 1 million kundeprofiler totalt til Marketo.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). I Marketo kan du nå finne segmentene under [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Marketo, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Marketo oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE [footer-include](includes/footer-banner.md)]
