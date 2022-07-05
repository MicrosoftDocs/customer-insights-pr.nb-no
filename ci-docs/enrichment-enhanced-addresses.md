---
title: Suppler kundeprofiler med forbedrede adresser (inneholder video)
description: Suppler og normaliser adresseinformasjonen for kundeprofiler med Microsofts modeller.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081228"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Suppler kundeprofiler med forbedrede adresser

Adresser i dataene kan være ustrukturerte, ufullstendige eller feil. Bruk Microsofts modeller til å normalisere og forbedre adressene i [Common Data Model-formatet](/common-data-model/schema/core/applicationcommon/address) for bedre nøyaktighet og innsikt.

Du kan også [supplere adresser på datakilder](data-sources-enrichment.md) for å forbedre samsvarsnøyaktigheten i dataforeningsprosessen. 

## <a name="how-we-enhance-addresses"></a>Slik forbedrer vi adressene

Modellen vår går gjennom en totrinnsprosess for å forbedre en adresse. Først analyseres adressen for å identifisere komponentene og plassere dem i et strukturert format. Deretter bruker vi AI til å korrigere, fullføre og standardisere verdiene i adressen.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Eksempel

Adresseinformasjon kan være i et format som ikke er standard, og inneholder stavefeil. Modellen kan løse disse problemene og opprette ensartede adresser i enhetlige kundeprofiler.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Begrensninger

Forbedrede adresser fungerer bare med verdiene som allerede finnes i de innlagte adressedataene. Modellen vil ikke:

1. kontrollere om adressen er en gyldig adresse
2. kontrollere om noen av verdiene, for eksempel postnumre eller gatenavn, er gyldige
3. endre verdier den ikke gjenkjenner

Modellen bruker maskinlæringsbaserte teknikker for å forbedre adressene. På samme måte som med alle maskinlæringsbaserte modeller, er ikke 100 prosent nøyaktighet garantert.

## <a name="supported-countries-or-regions"></a>Støttede land eller områder

Vi støtter for øyeblikket supplering av adresser i disse landene eller områdene:

- Australia
- Canada
- Frankrike
- Tyskland
- Italia
- Japan
- Storbritannia
- USA

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene mine** på flisen **Forbedrede adresser**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Skjermbilde av flisen Forbedrede adresser.":::

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Velg **kundedatasettet** og velg profilen eller segmentet du vil supplere. *Kunde*-enheten supplerer alle kundeprofilene dine, mens segmentsuppleringer bare supplerer kundeprofiler i det segmentet.

1. Velg hvordan adresser formateres i datasettet. Velg **Adresse for enkeltattributt** hvis adressene i dataene bruker ett enkelt felt. Velg **Adresse for flere attributter** hvis adressene i dataene bruker mer enn ett datafelt.

1. Velg **Neste**, og tildel adressefeltene fra enheten for enhetlig kunde.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Forbedret adresse-felttilordningsside.":::

   > [!NOTE]
   > Land/område er obligatorisk både i adresser med enkeltattributter og flere attributter. Adresser som ikke inneholder gyldige eller støttede land-/områdeverdier, blir ikke supplert.

1. Velg **Neste** for å fullføre felttilordningen.

1. Angi et **Navn** for suppleringen og **Utdataenheten**.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

## <a name="view-enrichment-results"></a>Vis suppleringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antall kunder supplert av feltet** gir en neddrilling i dekningen av hvert supplerte felt.

### <a name="overview-card"></a>Oversiktskort

Kortet **Oversikt over kundeendringer** viser detaljer om dekningen til suppleringen:

- **Adresser som er behandlet og endret**: Antall kundeprofiler med adresser som er supplert.
- **Adresser som er behandlet og uendret**: Antall kundeprofiler med adresser som er gjenkjent, men ikke endret. Det skjer vanligvis når inndataene er gyldige og ikke kan forbedres av suppleringen.
- **Adresser som ikke er behandlet og uendret**: Antall kundeprofiler med adresser som ikke er gjenkjent. Dette skjer vanligvis for inndata som er ugyldige eller ikke støttes av suppleringen.

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
