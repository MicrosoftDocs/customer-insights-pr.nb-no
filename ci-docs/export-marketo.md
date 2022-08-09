---
title: Eksportere segmenter til Marketo (forhåndsvisning)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195256"
---
# <a name="export-segments-to-marketo-preview"></a>Eksportere segmenter til Marketo (forhåndsvisning)

Du kan eksportere segmenter av enhetlige kundeprofiler for å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Marketo.

## <a name="prerequisites"></a>Forutsetning

- En [Marketo-konto](https://login.marketo.com/) og tilhørende administratorlegitimasjon.
- En [Marketo-klient-ID, klienthemmelighet og vertsnavn for REST-endepunkt](https://developers.marketo.com/rest-api/authentication/).
- [Eksisterende lister i Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) og de tilsvarende ID-ene.
- [Konfigurerte segmenter](segments.md).
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million kundeprofiler per eksport til Marketo, som kan ta opptil 3 timer. Antall kundeprofiler du kan eksportere til Marketo, avhenger av kontrakten med Marketo.
- Bare segmenter.

## <a name="set-up-connection-to-marketo"></a>Konfigurere tilkobling til Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Marketo**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **Marketo-klient-ID-en, klienthemmeligheten og vertsnavnet for REST-endepunktet**. REST-endepunktvertsnavnet er bare vertsnavnet, uten https://. Eksempel: xyz-abc-123.mktorest.com.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Marketo-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Angi **ID for Marketo-liste**. Liste-ID-en er en ren numerisk verdi. Hvis ID-en for Marketo-liste for eksempel er ST12345A7, fjerner du tegnet før og etter tallene og angir *12345*.

1. I **Datasamsvar**-delen velger du minst ett felt som representerer kundens e-postadresse eller en kundes Marketo-ID.

1. Eksporter eventuelt **Fornavn**, **Etternavn**, **Poststed**, **Delstat** og **Land/område** for å opprette mer tilpassede e-poster. Velg **Legg til attributt** for å tilordne disse feltene.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

I Marketo finner du segmentene under [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
