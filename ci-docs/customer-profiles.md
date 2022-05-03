---
title: Vise kundeprofiler
description: Få en kombinert visning av dine enhetlige kundedata.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 45ef6abcd612178a097569825e32ff9ac779de01
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646592"
---
# <a name="customer-profiles"></a>Kundeprofiler

**Kunder**-siden viser en kombinert visning av dine enhetlige kundeprofiler. Kundeprofilene er tilgjengelige når du har [opprettet den enhetlige Kunde-enheten](data-unification.md). På siden kan du søke etter kunder og definere indeksen for dette søket.

Kunder kan være enkeltpersoner eller organisasjoner. Hver kundeprofil representeres av en flis. Bruk pagineringskontrollene til å hente flere oppføringer. Kortet viser felt fra *Kunde*-enheten som definert i **Søk- og filterindeks**. Rekkefølgen på feltene innenfor hvert kort plukkes av systemet.

Velg en flis for å vise data for den valgte kunden på en egen side kalt [Kundedetaljer](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Kundesiden viser resultatfliser](media/customers-page-result-tiles-B2C.png "Kundesiden viser resultatfliser")

> [!NOTE]
> Hvis du ikke kan se flisene når du velger **Kunder** i navigasjon, må administrator [definere minst ett søkbart attributt](search-filter-index.md) i **Søk- og filterindeks**.

## <a name="search-for-customers"></a>Søke etter kunder

Søk etter kunder ved å angi et navn eller et annet attributt i søkeboksen. Søket fungerer bare i _Kunde_-enheten som opprettes under dataenhetsprosessen.

Som administrator kan du konfigurere de søkbare attributtene ved hjelp av siden **Søk- og filterindeks**. Hvis du vil ha mer informasjon, kan du gå til [Behandle søke- og filterindeks](search-filter-index.md).

## <a name="filter-customers"></a>Filtrer kunder

Du kan filtrere kunder etter _Kunde_-enhetsfeltene. På samme måte som i søk må administratoren først definere feltene som filtrererbare ved hjelp av siden **Søk- og filterindeks**.

1. Velg **Vis filtre** på **Kunder**-siden.

1. Merk av i boksene ved siden av attributtene du vil filtrere kunder etter.

1. Fjern filtrene ved å velge **Fjern filtre** på **Kunder**-siden.

## <a name="customer-details-page"></a>Kundedetaljer-siden

Velg en hvilken som helst av kundeflisene for å åpne **Kundedetaljer**-siden. Denne visningen inneholder enhetlig informasjon om den valgte kunden. Kundedetaljer inkluderer følgende innhold:

**Kundeprofilflis**: Denne flisen viser de forskjellige verdiene fra den enhetlige  _Kunder_-enheten. Hvis et felt ikke har noen verdi for den valgte kundeprofilen, vises det ikke. Flisen er strukturert i deler:  
  - Den første delen viser et forhåndsdefinert sett med felt etterfulgt av alle felt som er en del av søke- og filterindeksen. Alle adresserelaterte felt kombineres til én enkelt linje hvis profilen inneholder slike felt. 
  - **Kontaktpersoner for denne kunden**: I miljøer for forretningsforbindelser ser du alle relaterte kontakter for denne kunden som den andre delen. Hver kontakt vises med de tilhørende feltene. Tomme felt er skjult.
  - **Tilleggsfelt**: Viser de resterende feltene for den valgte kunden, unntatt IDer. 
  - **IDer**: Viser alle IDene under det tilsvarende enhetsnavnet. Felt identifiseres som IDer av semantikken, som kategoriserer dem som sådan.

**Aktivitetstidslinje**: Viser data hvis du har konfigurert aktiviteter. Tidslinjevisningen inneholder kronologisk sorterte aktiviteter for den valgte kunden fra og med den nyeste aktiviteten. Hvis du vil ha mer informasjon, kan du gå til [Kundeaktiviteter](activities.md).

**Innsikt**:  
  - **Mål**: Viser om du har konfigurert ett eller flere mål for kundeattributtmål. De inkluderer beregnede KPI-er rundt kundene på det enkelte kundenivået. Hvis du vil ha mer informasjon, kan du gå til [Definere og behandle mål](measures.md).

  - **Potensielle interesser, potensielle merker**: Viser om du konfigurerte et merke eller en affinitetssupplement. Den representerer potensielle interesser og tilknytninger for merker basert på andre kunder som har en profil som ligner på den valgte kundeprofilen. Hvis du vil ha mer informasjon, kan du gå til [Berike kundeprofiler med merke- og interesseinfiniteter](enrichment-microsoft.md).

Hvis du vil gå tilbake til kundesøksiden, velger du **Tilbake til kunder**.

## <a name="next-steps"></a>Neste trinn

[Legg til flere datakilder](data-sources.md), [berik enhetlige profiler](enrichment-hub.md), eller [opprett segmenter](segments.md) for å arbeide med enhetlige kundeprofiler i andre programmer.


[!INCLUDE [footer-include](includes/footer-banner.md)]
