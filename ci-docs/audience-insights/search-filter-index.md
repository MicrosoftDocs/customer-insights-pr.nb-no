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
ms.openlocfilehash: a6131d4dddce48b0fba153bcefe5631e0d22d808
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554033"
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

Gå til **Kunder**-siden for å søke etter kundeprofiler, eller bruk de indekserte feltene til å vise et delsett med alle kundeprofiler.


[!INCLUDE[footer-include](../includes/footer-banner.md)]