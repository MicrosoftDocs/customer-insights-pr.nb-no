---
title: Søke etter og filtrere kundeprofiler
description: Finn informasjon raskt om enhetlige kundeprofiler, og filtrer etter bestemte attributter.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e53d87c4f633cba09fecbc1c219f0ac2ec6bb5598a7902cbcf7398d26d6d7c6b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029411"
---
# <a name="customer-profiles-search--filter-index"></a>Kundeprofiler: Søk- og filterindeks

Resultatet av å samle kundedata er en kundeprofilenhet som gir en enhetlig visning av den totale kundebasen. Hvis du raskt vil [finne informasjon om en bestemt kunde eller kundegruppe](customer-profiles.md), kan du konfigurere funksjonene **Søk** og **Filter** på siden **Kunder**. Les videre for å finne ut hvordan administratorer kan redigere attributtene på siden **Søk- og filterindeks**, som er tilgjengelige for brukere for søk og filtrering.

> [!div class="mx-imgBorder"]
> ![Søkefilter.](media/search-filter.png "Søkefilter")

## <a name="add-fields-and-specify-attributes"></a>Legge til felt og angi attributter

Hvis det er første gang du definerer søkbare attributter som en administrator, må du først definere indekserte felt. Vi foreslår at du velger alle attributtene som brukere kan søke og filtrere kunder etter på siden **Kunder**. Du kan bare angi attributter som finnes i kundeprofilenheten du opprettet i løpet av datasamlingsprosessen.

1. Åpne **Kunder**-siden, og velg **Søk- og filterindeks**.

2. Velg **+ Legg til** for å angi de indekserte feltene.

3. Velg attributtene på listen du vil legge til som indekserte felt. Du kan alltid legge til flere attributter ved å velge **Legg til**. Du kan også fjerne valgte attributter ved å velge **Fjern**-symbolet.

## <a name="explore-the-indexed-customer-fields-table"></a>Utforsk tabellen for indekserte kundefelt

Følgende informasjon vises i tabellen.

- **Navn**: Representerer navnet på attributtet slik det vises i kundeprofilenheten.
- **Datatype**: Angir om datatypen er en streng, et tall eller en dato.
- **Inkludert i søk**: Angir om dette attributtet kan brukes til å søke etter kunder på siden **Kunder** ved hjelp av feltet **Søk**.
- **Legg til filter**: Kontroll for å definere hvordan dette attributtet kan brukes til filtrering på siden **Kunder**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Redigere filtreringsalternativer for et gitt attributt

Menyen **Filter** på siden **Kunder** kan inneholde et varierende antall attributtnivåer (for eksempel forskjellige aldersgrupper for å filtrere kunder etter).

1. Velg **Legg til filter** for et gitt attributt på siden **Søk- og filterindeks**. Du kan definere antall resultater og rekkefølgen de skal organiseres i. Avhengig av datatypen for attributtet vises én av følgende ruter.

- Strengattributter: Angi antall ønskede resultater i ruten **Alternativer for strengfilter** og ordrepolicyen de skal organiseres etter.

- Numeriske attributter: Angi intervallene som er inkludert i ruten **Alternativer for nummerfiltrering** og ordrepolicyen de skal organiseres etter.

- Datoattributter: Angi intervallene som er inkludert i ruten **Alternativer for datofilter** og ordrepolicyen de skal organiseres etter.

2. Velg **Lagre** for å ta i bruk endringene.

3. Velg **Kjør** når du er klar til å bruke innstillingene.

## <a name="next-steps"></a>Neste trinn

Gå gjennom [siden for enhetlige profiler](customer-profiles.md) for å søke etter profiler eller bruke de indekserte feltene for å vise et delsett med alle enhetlige profiler.


[!INCLUDE[footer-include](../includes/footer-banner.md)]