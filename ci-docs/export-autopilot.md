---
title: Eksportere segmenter til Autopilot (forhåndsvisning)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 449d2c5e32697e4a5d2c9dff4a5a1cbdb26aeb4d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195072"
---
# <a name="export-segments-to-autopilot-preview"></a>Eksportere segmenter til Autopilot (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til Autopilot, og bruk dem for e-postmarkedsføring i Autopilot.

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

- En [Autopilot-konto](https://www.autopilothq.com/) og tilhørende administratorlegitimasjon.
- En [API-nøkkel for Autopilot](https://autopilot.docs.apiary.io/#)
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 100 000 kundeprofiler per eksport til Autopilot, som kan ta opptil fem timer å fullføre. Antall kundeprofiler du kan eksportere til Autopilot, avhenger av kontrakten med Autopilot.
- Bare segmenter.

## <a name="set-up-connection-to-autopilot"></a>Konfigurere tilkobling til Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Autopilot**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi API-nøkkelen for Autopilot.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Autopilot-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet.

1. Eksporter eventuelt andre felt som **Fornavn** og **Etternavn**.

1. Velg segmentene du vil eksportere, ved å følge de kjente begrensningene.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
