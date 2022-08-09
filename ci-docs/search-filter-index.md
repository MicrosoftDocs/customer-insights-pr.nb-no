---
title: Administrer søke- og filterindeksen for kundeprofiler
description: Finn informasjon raskt om enhetlige kundeprofiler, og filtrer etter bestemte attributter.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187921"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Administrer søke- og filterindeksen for kundeprofiler

Resultatet av å samle kundedata er en *Kunde*-enhet som gir en enhetlig visning av den totale kundebasen. For at brukere raskt skal kunne [finne informasjon om en bestemt kunde eller kundegruppe](customer-profiles.md), må en administrator konfigurere funksjonene **Søk** og **Filter** på **Kunder**-siden.

   :::image type="content" source="media/search-filter.png" alt-text="Søkefilter":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definere søkbare attributter og indekserte felter

Hvis det er første gang du definerer søkbare attributter som en administrator, definerer du først indekserte felter. Vi foreslår at du velger alle attributtene som brukere kan søke og filtrere kunder etter på siden **Kunder**. Bare attributter som er i *Kunde*-enheten du opprettet i løpet av datasamlingsprosessen, kan angis.

1. Gå til **Kunder**-siden, og velg **Søke- og filterindeks**.

1. Velg **+ Legg til**.

1. Velg attributtene du vil legge til som indekserte felt, fra listen, og klikk på **Bruk**.

1. Hvis du vil legge til flere attributter, velger du **Legg til**. Hvis du vil fjerne et valgt attributt, velger du attributtet og deretter **Slett**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Siden Søke- og filterindeks.":::

1. Velg **Kjør** når du er klar til å bruke innstillingene for søk og filter. Når endringene er behandlet, vises de på [kundekortene på kundesiden](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definer filtreringsalternativer for et gitt attributt

Konfigurer feltene som kan brukes til å filtrere kunder, på **Kunder**-siden.

1. Gå til **Kunder**-siden, og velg **Søke- og filterindeks**.

1. Velg et attributt og **Legg til filter**. Definer antall resultater og rekkefølgen de skal organiseres i. Avhengig av datatypen for attributtet vises én av følgende ruter.

   - Strengattributter: Angi antall ønskede resultater i ruten **Strengfilter** og rekkefølgepolicyen de skal organiseres etter.

   - Numeriske attributter: Angi intervallene som er inkludert i ruten **Nummerfiltrering** og rekkefølgepolicyen de skal organiseres etter.

   - Datoattributter: Angi intervallene som er inkludert i ruten **Datofilter** og rekkefølgepolicyen de skal organiseres etter.

1. Velg **OK**. Gjenta dette for alle attributter du vil filtrere etter.

1. Velg **Kjør** når du er klar til å bruke innstillingene for søk og filter. Når endringene er behandlet, vises de på [kundekortene på kundesiden](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Vis indekserte kundefelter

Siden **Søke- og filterindeks** inneholder følgende informasjon:

- **Navn**: Representerer navnet på attributtet slik det vises i *Kunde*-enheten.
- **Datatype**: Angir om datatypen er en streng, et tall eller en dato.
- **Inkludert i søk**: Angir om dette attributtet kan brukes til å søke etter kunder på siden **Kunder** ved hjelp av feltet **Søk**.
- **Legg til filter**: Kontroll for å definere hvordan dette attributtet kan brukes til filtrering på siden **Kunder**.

## <a name="next-steps"></a>Neste trinn

Gå gjennom [siden for enhetlige profiler](customer-profiles.md) for å søke etter profiler eller bruke de indekserte feltene for å vise et delsett med alle enhetlige profiler.

[!INCLUDE [footer-include](includes/footer-banner.md)]
