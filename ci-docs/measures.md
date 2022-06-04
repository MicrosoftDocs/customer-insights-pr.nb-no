---
title: Forstå og administrer tiltak
description: Finn ut hvordan tiltak hjelper deg med å analysere og gjenspeile selskapets ytelse.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 84a3a10a2517258c1f895800882b9c67391ec3de
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646827"
---
# <a name="measures-overview"></a>Oversikt over mål

Tiltak hjelper deg med å få bedre forståelse av kundeatferd og forretningsytelse. De ser på relevante verdier fra [enhetlige profiler](data-unification.md). En virksomhet vil for eksempel se *totalkostnaden per kunde* for å forstå en individuell kundes kjøpshistorikk eller måle *totalt salg av firmaet* for å forstå omsetningen på aggregert nivå i hele virksomheten.  

Tiltak opprettes [ved hjelp av måleverktøyet](measure-builder.md), en dataspørringsplattform med forskjellige operatorer og enkle tilordningsalternativer. Den lar deg filtrere dataene, gruppere resultater, registrere [enhetsrelasjonsbaner](relationships.md) og forhåndsvise utdataene. Du kan [bruke forhåndsdefinerte maler](measure-templates.md) til å konfigurere vanlige mål på en effektiv måte.

Bruk måleverktøyet til å planlegge forretningsaktiviteter ved å spørre etter kundedata og trekke ut innsikt. Hvis du for eksempel oppretter et mål for *totalkostnad per kunde* og *total avkastning per kunde*, blir det enklere å identifisere en gruppe kunder med høy avkastning, men likevel høy avkastning. Du kan [opprette et segment](segments.md) basert på disse tiltakene for å få de neste beste handlingene.

## <a name="manage-your-measures"></a>Administrer målene dine

Du finner mållisten på **Mål**-siden.

Du finner informasjon om måltypen, oppretteren, opprettingsdato, status og tilstand. Når du velger et mål fra listen, kan du forhåndsvise utdataene og laste ned en CSV-fil.

:::image type="content" source="media/measures-actions.png" alt-text="Handlinger for å administrere enkeltmål."lightbox="media/measures-actions.png":::

Følgende handlinger er tilgjengelige når du velger et mål:

- **Rediger** konfigurasjonen av målet.
- **Dupliser** et mål. Du kan velge å redigere egenskapene med en gang, eller ganske enkelt lagre duplikatet.
- **Oppdater** målet basert på de nyeste dataene. Hvis du vil oppdatere alle målene samtidig, velger du alle målene og deretter **Oppdater**.
- **Gi nytt navn** til målet.
- **Aktiver** eller **Deaktiver**. Inaktive tiltak oppdateres ikke under en [planlagt oppdatering](system.md#schedule-tab).
- **Merke** for å [administrere merker](work-with-tags-columns.md#manage-tags) for segmentet.
- **Slett** målet.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Neste trinn

Du kan bruke eksisterende målinger til å opprette [et kundesegment](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]