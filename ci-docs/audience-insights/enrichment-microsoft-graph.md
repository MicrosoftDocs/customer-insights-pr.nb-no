---
title: Supplere kundeprofiler med Microsoft Graph
description: Bruk proprietære data fra Microsoft Graph til å supplere kundedataene med merke- og interesseaffiniteter.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406503"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Supplere kundeprofiler med merke- og interesseaffiniteter (forhåndsvisning)

Bruk proprietære data fra Microsoft Graph til å supplere kundedataene med merke- og interesseaffiniteter. Disse affinitetene fastsettes basert på data fra personer med liknende demografiske data som kundene dine. Ved hjelp av denne informasjonen kan du bedre forstå og segmentere kunder basert på deres affinitet til bestemte merker og interesser.

I målgruppeinnsikt går du til **Data** > **Supplering** for å [konfigurere og vise suppleringer](enrichment-hub.md).

Hvis du vil konfigurere merkeaffinitet som skal berikes, går du til kategorien **Utforsk** og velger **Suppler dataene** på **Merker**-flisen.

Hvis du vil konfigurere interesseaffinitet som skal berikes, går du til kategorien **Utforsk** og velger **Suppler dataene** på **Interesser**-flisen.

   > [!div class="mx-imgBorder"]
   > ![Fliser for merker og interesser](media/BrandsInterest-tile-Hub.png "Fliser for merker og interesser")

## <a name="about-microsoft-graph"></a>Om Microsoft Graph

Vi bruker elektroniske søkedata fra Microsoft Graph til å finne affinitet for merker og interesser på tvers av forskjellige demografiske segmenter (definert etter alder, kjønn eller sted). Det elektroniske søkevolumet for et merke eller en interesse avgjør hvor mye affinitet et demografisk segment, sammenlignet med andre segmenter, har til merket eller interessen.

[Finn ut mer om Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Affinitetspoengsum og konfidens

En **affinitetspoengsum** blir beregnet på en 100-punktsskala, der 100 representerer segmentet som har den høyeste affinitet for et merke eller en interesse.

**Affinitetstrygghet** blir også beregnet på en 100-punktsskala. Det angir systemets trygghetsnivå for at et segment har en affinitet for merket eller interessen. Konfidensnivået er basert på segmentstørrelsen og detaljnivået for segmentet. Segmentstørrelse bestemmes av mengden data vi har for et gitt segment. Detaljnivå for segmentet bestemmes av hvor mange attributter (alder, kjønn, sted) som er tilgjengelige i en profil.

Vi normaliserer ikke resultatene for datasettet ditt. Det kan derfor hende at du ikke ser alle mulige verdier for affinitet for datasettet ditt. Det kan for eksempel hende at det ikke finnes en supplert kundeprofil med affinitet på 100 i dataene. Det er mulig at det ikke finnes noen kunder i det demografiske segmentet som oppnådde 100 for et gitt merke eller en interesse.

> [!TIP]
> Når du [oppretter segmenter](segments.md) ved hjelp av affinitetspoengsummer, kan du se gjennom distribusjonen av affinitetspoengsummen for datasett før du bestemmer deg for de aktuelle grenseverdiene for poengsum. En affinitetspoengsum på 10 kan for eksempel anses som viktig i en datasett som har en høyeste affinitet på bare 25 for et bestemt merke eller en interesse.

## <a name="supported-countriesregions"></a>Støttede land/områder

Vi støtter for øyeblikket følgende alternativer for land/område: Australia, Canada (engelsk), Frankrike, Tyskland, Storbritannia eller USA (engelsk).

Du velger et land ved å åpne **Merkesupplering** eller **Interessesupplering** og velger **Endre** ved siden av **Land/område**. Velg et alternativ i ruten **Innstillinger for land/område**, og velg **Bruk**.

### <a name="implications-related-to-country-selection"></a>Implikasjoner knyttet til valg av land

- Når du [velger dine egne merker](#define-your-brands-or-interests), kommer vi med forslag basert på det valgte landet/området.

- Ved [valg av bransje](#define-your-brands-or-interests) identifiserer vi de mest relevante merkene eller interessene basert på det valgte landet/området.

- Hvis feltet Land/område ikke tilordnes når du [tilordner feltene](#map-your-fields), bruker vi Microsoft Graph-data fra det valgte landet/området til å supplere kundeprofilene. Vi bruker også dette valget til å supplere kundeprofilene uten tilgjengelige data for land/område.

- Når du [supplerer profiler](#refresh-enrichment), supplerer vi alle kundeprofilene der vi har Microsoft Graph-data tilgjengelige for de valgte merkene og interessene, inkludert profiler som ikke er i det valgte landet/området. Hvis du for eksempel valgte Tyskland, supplerer vi profiler i USA hvis vi har Microsoft Graph-data tilgjengelige for de valgte merkene og interessene i USA.

## <a name="configure-enrichment"></a>Konfigurere supplering

Konfigurasjon av merker eller interesser består av to trinn:

### <a name="define-your-brands-or-interests"></a>Definer merker og interesser

Velg ett av følgende alternativer:

- **Bransje**: Systemet identifiserer de mest populære merkene og interessene som er relevante for bransjen, og supplerer kundedataene med dem.
- **Velg dine egne**: Velg opptil fem elementer fra listen over merker og interesser som er mest relevante for organisasjonen.

Hvis du vil legge til et merke eller en interesse, angir du det i inndataområdet for å få forslag basert på samsvarende betingelser. Hvis vi ikke viser et merke eller en interesse du leter etter, kan du sende oss tilbakemelding ved hjelp av **Foreslå**-koblingen.

### <a name="map-your-fields"></a>Tilordne feltene

Tilordne felt fra den enhetlige kundeenheten til minst to attributter for å definere det demografiske segmentet du vil at vi skal bruke til å forbedre kundedataene. Velg **Rediger** for å definere tilordningen av feltene, og velg **Bruk** når du er ferdig. Velg **Lagre** for å fullføre felttilordningen.

Følgende formater og verdier støttes (det skilles ikke mellom små og store bokstaver i verdier):

- **Fødselsdato**: Vi anbefaler at fødselsdatoen konverteres til en DateTime-type under datainntak. Alternativt kan den være en streng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-formatet «ÅÅÅÅ-MM-DD» eller «ÅÅÅÅ-MM-DDTtt:mm:ssZ».
- **Kjønn**: hann, hunn, ukjent
- **Postnummer**: Femsifrede postnumre for USA, standard postnummer alle andre steder
- **Sted**: Navn på poststed på engelsk
- **Delstat/område**: Forkortelse på to bokstaver for USA og Canada. Forkortelse på to eller tre bokstaver for Australia. Gjelder ikke for Frankrike, Tyskland eller Storbritannia.
- **Land/område**:

  - US: Amerikas forente stater, De forente stater, USA, US, Amerika
  - CA: Canada, CA
  - GB: Storbritannia, UK, Great Britain, GB, Det forente kongerike Storbritannia og Nord-Irland, United Kingdom of Great Britain
  - AU: Australia, AU, Commonwealth of Australia
  - FR: Frankrike, FR, Republikken Frankrike
  - DE: Tyskland, German, Deutschland, Allemagne, DE, Forbundsrepublikken Tyskland, Republic of Germany

## <a name="refresh-enrichment"></a>Oppdatere supplering

Kjør suppleringen etter å ha konfigurert merker, interesser og felttilordningen for demografi. Hvis du vil starte prosessen, velger du **Kjør** på siden for merke- eller interessekonfigurasjon. I tillegg kan du la systemet kjøre suppleringen automatisk som en del av en planlagt oppdatering.
Avhengig av størrelsen på kundedataene kan det ta flere minutter å fullføre en supplering.

> [!TIP]
> Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser. De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies). Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben. Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.

## <a name="enrichment-results"></a>Resultater av supplering

Når du har kjørt suppleringsprosessen, går du til **Mine suppleringer** for å se du gjennom det totale antallet supplerte kunder, og en analyse over merker og interesser i de supplerte kundeprofilene.

:::image type="content" source="media/my-enrichments.png" alt-text="Forhåndsvisning av resultater etter kjøring av suppleringsprosessen":::

Se gjennom de supplerte dataene ved å velge **Vis supplerte data** i diagrammet. Supplerte data for merker går til **BrandAffinityFromMicrosoft**-enheten. Data for interesser er i **InterestAffinityFromMicrosoft**-enheten. Du finner også disse enhetene oppført i gruppen **Supplering** i **Data** > **Enheter**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Vise supplerte data på kundekortet

Merke- og interesseaffiniteter kan også vises på individuelle kundekort. Gå til **Kunder**, og velg en kundeprofil. På kundekortet finner du diagrammer for merker eller interesser som personer i kundens demografiske profil har affinitet for.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundekort med supplerte data":::

## <a name="next-steps"></a>Neste trinn

Bygg på toppen av de supplerte kundedataene. Opprett [segmenter](segments.md), [mål](measures.md) og til og med [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.
