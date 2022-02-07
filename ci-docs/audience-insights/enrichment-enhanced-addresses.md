---
title: Supplering av utvidede adresser (inneholder video)
description: Suppler og normaliser adresseinformasjonen for kundeprofiler med Microsofts modeller.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
---

# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Supplering av kundeprofiler med forbedrede adresser

Adresser i dataene kan være ustrukturerte, ufullstendige eller feil. Bruk Microsofts modeller til å normalisere og forbedre adressene i [Common Data Model-formatet](/common-data-model/schema/core/applicationcommon/address) for bedre nøyaktighet og innsikt.

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

Modellen bruker maskinlæringsbaserte teknikker for å forbedre adressene. Selv om vi bruker en terskel for høy konfidens for når modellen endrer en inndataverdi, på samme måte som med alle maskinlæringsbaserte modeller, er ikke 100 prosent nøyaktighet garantert.

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

Adresser må inneholde en land-/områdeverdi. Vi behandler ikke adresser for land eller områder som ikke støttes, og adresser som ikke har angitt land eller område.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**.

1. Velg **Suppler dataene mine** på flisen **Forbedrede adresser**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Skjermbilde av flisen Forbedrede adresser.":::

1. Velg **kundedatasettet**, og velg enheten som inneholder adressene du vil supplere. Du kan velge *kundeenheten* for å supplere adressene i alle kundeprofilene, eller velge en segmentenhet for å supplere adresser bare i kundeprofiler i det segmentet.

1. Velg hvordan adresser formateres i datasettet. Velg **Adresse for enkeltattributt** hvis adressene i dataene bruker ett enkelt felt. Velg **Adresse for flere attributter** hvis adressene i dataene bruker mer enn ett datafelt.

   > [!NOTE]
   > Land/område er obligatorisk både i adresser med enkeltattributter og flere attributter. Adresser som ikke inneholder gyldige eller støttede land-/områdeverdier, blir ikke supplert.

1.  Tilordne adressefeltene fra enheten for enhetlig kunde.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Forbedret adresse-felttilordningsside.":::

1. Velg **Neste** for å fullføre felttilordningen.

1. Angi et navn for suppleringen og utdataenheten.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

## <a name="enrichment-results"></a>Resultater av supplering

Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen. Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab). Behandlingstiden avhenger av størrelsen på kundedataene.

Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**. I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.

Du kan se et eksempel på de supplerte dataene på **forhåndsvisningsflisen for supplerte kunder**. Velg **Vis mer**, og velg fanen **Data** for å få tilgang til en detaljert visning av hver supplerte profil.

### <a name="overview-card"></a>Oversiktskort

Oversiktskortet viser detaljer om dekningen til suppleringen. 

* **Adresser som er behandlet og endret**: Antall kundeprofiler med adresser som er supplert.

* **Adresser som er behandlet og uendret**: Antall kundeprofiler med adresser som er gjenkjent, men ikke endret. Det skjer vanligvis når inndataene er gyldige og ikke kan forbedres av suppleringen.

* **Adresser som ikke er behandlet og uendret**: Antall kundeprofiler med adresser som ikke er gjenkjent. Dette skjer vanligvis for inndata som er ugyldige eller ikke støttes av suppleringen.

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
