---
title: Vise kundeprofiler
description: Vis de enhetlige kundedataene, inkludert bruk av søk og filter
ms.date: 06/08/2022
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
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303795"
---
# <a name="view-customer-profiles"></a>Vise kundeprofiler

Kundeprofiler er tilgjengelige når du [oppretter den enhetlige *Kunde*-enheten](data-unification.md). Den kombinerte visningen for de enhetlige kundeprofilene vises på **Kunder**-siden. Kunder kan være enkeltpersoner eller organisasjoner.

Gå til **Kunder**-siden for å vise kundene og profilene deres. Hver kundeprofil representeres av en flis. Bruk pagineringskontrollene til å hente flere oppføringer. Kortet viser felt fra *Kunde*-enheten som definert i **Søk- og filterindeks**. Rekkefølgen på feltene innenfor hvert kort plukkes av systemet.

> [!NOTE]
> Hvis du ikke kan se flisene når du velger **Kunder**, må administratoren [definere minst ett søkbart attributt](search-filter-index.md) i **Søk- og filterindeks**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Kundesiden viser resultatfliser.":::

Velg en av følgende handlinger:
- [Vis kundedetaljer](#view-customer-details)
- [Behandle søke- og filterindeksen](search-filter-index.md) (bare administratorer)
- [Filtrer kunder](#filter-customers)
- **Vis kort** eller **Skjul kort** for å vise eller skjule informasjonen som vises på kundeflisen
- **Sorter etter** et bestemt attributt
- [Søke etter kunder](#search-for-customers)

  > [!NOTE]
  > Hvis en administrator skal bruke søk og filter, må vedkommende konfigurere de søkbare attributtene og definere feltene som kan filtreres, ved hjelp av søke- og filterindeksen.

## <a name="search-for-customers"></a>Søke etter kunder

Søk etter kunder ved å angi et navn eller et annet attributt i **Søk etter kunder**. Attributtene du kan søke etter, defineres av administratoren og kommer fra en enhetlige *Kunde*-enheten.

> [!NOTE]
> **Streng** er den eneste datatypen som tas med i søket. Bruk den i feltet **Søk etter kunder** på Kunder-siden til å søke etter kunder.

## <a name="filter-customers"></a>Filtrer kunder

Filtrer kunder etter *Kunde*-enhetsfeltene. Filtrerbare felter defineres av administratoren.

1. Velg **Vis filtre** på **Kunder**-siden. Filter-ruten vises.

1. Merk av i boksene ved siden av attributtene du vil filtrere kunder etter.

1. Fjern alle filtre ved å velge **Fjern filtre**, eller fjern merket for et valgt attributt.

1. Velg **Skjul filtre** for å lukke filterruten.

1. Hvis du vil lagre filterresultatene som et [segment](segments.md), velger du **Lagre filtre som segment**.
   1. Skriv inn et navn for segmentet.
   1. Velg **Lagre** for å lagre segmentet.
   1. Velg om du vil kjøre segmentet nå ved å velge **Aktiver**, eller kjøre det **Senere**.

## <a name="view-customer-details"></a>Vis kundedetaljer

På **Kunder**-siden velger du en kundeflis for å vise detaljer for den valgte kunden.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Kundedetaljer-siden.":::

Kundedetaljene inkluderer:

**Kundeprofilflis** viser de ulike verdiene fra den enhetlige *Kunder*-enheten. Hvis et felt ikke har noen verdi for den valgte kundeprofilen, vises det ikke unntatt adressefeltet. Flisen er strukturert i deler:

- Den første delen viser et forhåndsdefinert sett med felt etterfulgt av alle felt som er en del av søke- og filterindeksen. Alle adresserelaterte felter kombineres til én enkelt linje, som vises selv om profilen ikke inneholder noen adresseinformasjon.
- **Kontakter for denne kunden** vises i miljøer for forretningskontoer (B2B). Hver kontakt vises med de tilhørende feltene. Tomme felt er skjult.
- **Tilleggsfelter** viser de resterende feltene for den valgte kunden, unntatt ID-er.
- **ID-er** viser alle ID-ene under det tilsvarende enhetsnavnet. Felter identifiseres som ID-er av semantikken.

**Aktivitetstidslinje** viser data hvis du har konfigurert [aktiviteter](activities.md). Tidslinjevisningen inneholder kronologisk sorterte aktiviteter for den valgte kunden fra og med den nyeste aktiviteten.

**Innsikt**:

- **Mål** viser om du har konfigurert [kundeattributtmål](measures.md). De inkluderer beregnede KPI-er rundt kundene på det enkelte kundenivået.

- **Potensielle interesser, potensielle merker** viser om du konfigurerte et [affinitetssupplement for merke eller interesse](enrichment-microsoft.md). Den representerer potensielle interesser og tilknytninger for merker basert på andre kunder som har en profil som ligner på den valgte kundeprofilen.

Velg **Tilbake til Kunder** for å gå tilbake til **Kunde**-siden.

## <a name="next-steps"></a>Neste trinn

[Legg til flere datakilder](data-sources.md), [berik enhetlige profiler](enrichment-hub.md), eller [opprett segmenter](segments.md) for å arbeide med enhetlige kundeprofiler i andre programmer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
