---
title: Forbedrede firmadata
description: Suppler og normaliser firmadata med Microsoft-modeller.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7a576621c71b925bd1563827aca10cad4ef9b4eb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229415"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Supplering av firmaprofiler med forbedrede firmadata

Bruk Microsofts-modeller og kompilerte firmadata til å korrigere, supplere og standardisere firmaprofilene. Vi skal bruke formatet [Common Data Model-formatet](/common-data-model/schema/core/applicationcommon/account) for bedre nøyaktighet og innsikt.

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

Det er noen få begrensninger med de forbedrede dataene. Elementene i listen nedenfor støttes ikke av modellen.

1.  Bekreft identiteten til firmaet. Vi kontrollerer ikke om inndataene er en eksisterende organisasjon, eller om et selskap bruker utdataene som standardnavn.
2.  Dekker selskaper globalt. Microsofts kompilerte firmadata har global dekning, men tilbyr mest dekning i Australia, Canada, Storbritannia og USA.
3.  Standardiser firmaadresser globalt. Vi støtter for øyeblikket standardisering av adresser i disse landene eller områdene: Australia, Canada, Frankrike, Tyskland, Italia, Japan, Storbritannia og USA.
4.  Garanterer nøyaktighet eller oppdaterte data. Etter hvert som forretningsinformasjonen endres ofte, kan vi ikke garantere at de forbedrede firmadataene som leveres, alltid er nøyaktige eller oppdaterte.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**.

1. Velg **Suppler dataene** på flisen **Forbedrede firmadata**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Suppleringsflis i suppleringshuben for firmadata.":::

1. Velg **kundedatasettet**, og velg enheten som inneholder adressene du vil supplere. Du kan velge *kundeenheten* for å supplere adressene i alle kundeprofilene, eller velge en segmentenhet for å supplere adresser bare i kundeprofiler i det segmentet.

1. Velg hvilken type felt fra firmaprofilene som skal brukes til samsvar med Microsofts kompilerte firmadata. Dette valget påvirker tilordningsfeltene du har tilgang til i neste trinn.

1.  Tilordne firmafeltene fra den enhetlige kundeenheten. Jo flere nøkkelidentifikatorer og felt du tilordner, jo større er sannsynligheten for høyere samsvarsrate.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Datatilordningstrinn når du konfigurerer firmasupplering.":::

1. Velg **Neste** for å fullføre felttilordningen.

1. Angi et navn for suppleringen og utdataenheten.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

## <a name="enrichment-results"></a>Resultater av supplering

Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen. Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab). Behandlingstiden avhenger av størrelsen på kundedataene.

Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**. I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.

Du kan se et eksempel på de supplerte dataene på **forhåndsvisningsflisen for supplerte kunder**. Velg **Vis mer**, og velg fanen **Data** for å få tilgang til en detaljert visning av hver supplerte profil.

### <a name="overview-card"></a>Oversiktskort

Oversiktskortet viser detaljer om dekningen til suppleringen. 

* **Selskaper som er behandlet og endret**: Antall kundeselskapsprofiler som er supplert.

* **Selskaper som er behandlet og uendret**: Antall kundeselskapsprofiler som er gjenkjent, men ikke endret. Dette skjer vanligvis når inndataene er gyldige og ikke kan forbedres av suppleringen.

* **Selskaper som ikke er behandlet og uendret**: Antall kundeselskapsprofiler som ikke ble gjenkjent. Dette skjer vanligvis for inndata som er ugyldige eller ikke støttes av suppleringen.

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
