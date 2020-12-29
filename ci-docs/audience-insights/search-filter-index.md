---
title: Søke etter og filtrere kundeprofiler
description: Finn informasjon raskt om enhetlige kundeprofiler, og filtrer etter bestemte attributter.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406538"
---
# <a name="customer-profiles-search--filter-index"></a>Kundeprofiler: Søk- og filterindeks

Resultatet av å samle kundedata er en kundeprofilenhet som gir en enhetlig visning av den totale kundebasen. Hvis du raskt vil [finne informasjon om en bestemt kunde eller kundegruppe](customer-profiles.md), kan du konfigurere funksjonene **Søk** og **Filter** på siden **Kunder**. Les videre for å finne ut hvordan administratorer kan redigere attributtene på siden **Søk- og filterindeks**, som er tilgjengelige for brukere for søk og filtrering.

> [!div class="mx-imgBorder"]
> ![Søkefilter](media/search-filter.png "Søkefilter")

## <a name="add-fields-and-specify-attributes"></a>Legge til felt og angi attributter

Hvis det er første gang du definerer søkbare attributter som en administrator, må du først definere indekserte felt. Vi foreslår at du velger alle attributtene som brukere kan søke og filtrere kunder etter på siden **Kunder**. Du kan bare angi attributter som finnes i kundeprofilenheten du opprettet i løpet av datasamlingsprosessen.

1. Åpne **Kunder**-siden, og velg **Søk- og filterindeks**.

> [!NOTE]
> Vi oppretter en standard konfigurasjon for søkeindeks på de tilgjengelige attributtene i kundeenheten fra følgende semantiske typer, slik det er definert på tilordningssiden.
> - Personens fornavn, etternavn, mellomnavn, fullt navn
> - Navn på organisasjon
> - E-postadresse
> - Telefon
> - Plasseringsinformasjon

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
