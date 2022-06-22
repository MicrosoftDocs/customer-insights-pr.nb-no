---
title: Forbedrede firmadata
description: Suppler og normaliser firmadata med Microsoft-modeller.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953961"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Supplering av firmaprofiler med forbedrede firmadata

Bruk Microsofts-modeller og kompilerte firmadata til å korrigere, supplere og standardisere firmaprofilene. Vi skal bruke formatet [Common Data Model-formatet](/common-data-model/schema/core/applicationcommon/account) for bedre nøyaktighet og innsikt.

Du kan også [forbedre firmadata på datakilder](data-sources-enrichment.md) for å forbedre samsvarsnøyaktigheten i dataforeningsprosessen.

For offentlige selskaper i USA er informasjon som omsetning, aksje-ticker, bransje og mer tilgjengelig.  

## <a name="how-we-enhance-company-data"></a>Slik forbedreder vi firmadata

Modellen vår går gjennom en totrinnsprosess for å forbedre en bedriftsprofil. Først normaliserer det firmanavnet. *Microsoft Corp* korrigeres og standardiseres for eksempel til *Microsoft Corporation*. Den prøver å finne et treff i Microsofts kompilerte firmadata. Hvis det blir funnet et treff, forbedrer vi firmaprofilen med informasjon fra de kompilerte firmadataene, inkludert firmanavnet.

### <a name="example"></a>Eksempel

Firmainformasjonen din følger kanskje ikke et standardisert format og inneholder stavefeil. Modellen prøver å løse disse problemene og opprette konsekvent informasjon.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Begrensninger

Modellen vil ikke:

- Bekreft identiteten til firmaet. Vi kontrollerer ikke om inndataene er en eksisterende organisasjon, eller om et selskap bruker utdataene som standardnavn.
- Dekker selskaper globalt. Microsofts kompilerte firmadata har global dekning, men tilbyr mest dekning i Australia, Canada, Storbritannia og USA.
- Standardiser firmaadresser globalt. Vi støtter for øyeblikket standardisering av adresser i disse landene eller områdene: Australia, Canada, Frankrike, Tyskland, Italia, Japan, Storbritannia og USA.
- Garanterer nøyaktighet eller oppdaterte data. Etter hvert som forretningsinformasjonen endres ofte, kan vi ikke garantere at de forbedrede firmadataene som leveres, alltid er nøyaktige eller oppdaterte.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på flisen **Forbedrede firmadata**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Suppleringsflis i suppleringshuben for firmadata.":::

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Velg **kundedatasettet** og velg profilen eller segmentet du vil supplere. *Kunde*-enheten supplerer alle kundeprofilene dine, mens segmentsuppleringer bare supplerer kundeprofiler i det segmentet.

1. Velg hvilken type felt fra firmaprofilene som skal brukes til samsvar med Microsofts kompilerte firmadata. Dette valget påvirker tilordningsfeltene du har tilgang til i neste trinn.

1. Velg **Neste**.

1. Tildel firmafeltene til firmadataene fra Microsoft. Hvis du vil ha høyere samsvarsnøyaktighet, legger du til flere felter.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Datatilordningstrinn når du konfigurerer firmasupplering.":::

1. Velg **Neste** for å fullføre felttilordningen.

1. Angi et **Navn** for suppleringen og **Utdataenheten**.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

1. Velg **Kjør** for å starte suppleringsprosessen, eller lukk for å gå tilbake til siden **Suppleringer**.

## <a name="enrichment-results"></a>Resultater av supplering

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Oversiktskort

Flisen **Oversikt over kundeendringer** viser detaljer om dekningen til suppleringen

- **Selskaper som er behandlet og endret**: Antall kundeselskapsprofiler som er supplert.
- **Selskaper som er behandlet og uendret**: Antall kundeselskapsprofiler som er gjenkjent, men ikke endret. Dette skjer vanligvis når inndataene er gyldige og ikke kan forbedres av suppleringen.
- **Selskaper som ikke er behandlet og uendret**: Antall kundeselskapsprofiler som ikke ble gjenkjent. Dette skjer vanligvis for inndata som er ugyldige eller ikke støttes av suppleringen.

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
