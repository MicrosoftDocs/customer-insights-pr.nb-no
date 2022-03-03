---
title: Søke etter og filtrere kundeprofiler
description: Finn informasjon raskt om enhetlige kundeprofiler, og filtrer etter bestemte attributter.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 4445f44b87a5947c3dfcf43ddb49dca9f25b69aa
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354521"
---
# <a name="customer-profiles-search--filter-index"></a>Kundeprofiler: Søk- og filterindeks

Resultatet av å samle kundedata er en kundeprofilenhet som gir en enhetlig visning av den totale kundebasen. Hvis du raskt vil [finne informasjon om en bestemt kunde eller kundegruppe](customer-profiles.md), kan du konfigurere funksjonene **Søk** og **Filter** på siden **Kunder**. Les videre for å finne ut hvordan administratorer kan redigere attributtene på siden **Søk- og filterindeks**, som er tilgjengelige for brukere for søk og filtrering.

   :::image type="content" source="media/search-filter.png" alt-text="Søkefilter":::

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

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

3. Velg **Kjør** når du er klar til å bruke innstillingene. Når endringene er behandlet, finner du dem i [kundekortene på kundesiden](customer-profiles.md). 

## <a name="next-steps"></a>Neste trinn

Gå gjennom [siden for enhetlige profiler](customer-profiles.md) for å søke etter profiler eller bruke de indekserte feltene for å vise et delsett med alle enhetlige profiler.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
