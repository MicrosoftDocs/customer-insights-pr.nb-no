---
title: Oversikt over mål
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
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170833"
---
# <a name="measures-overview"></a>Oversikt over mål

Tiltak hjelper deg med å få bedre forståelse av kundeatferd og forretningsytelse. De ser på relevante verdier fra [enhetlige profiler](data-unification.md). En virksomhet vil for eksempel se *totalkostnaden per kunde* for å forstå en individuell kundes kjøpshistorikk eller måle *totalt salg av firmaet* for å forstå omsetningen på aggregert nivå i hele virksomheten.

Opprett mål for å planlegge forretningsaktiviteter ved å spørre etter kundedata og trekke ut innsikt. Du kan for eksempel opprette et mål for *totalkostnad per kunde* og *total avkastning per kunde* for å gjøre det enklere å identifisere en gruppe kunder som kjøper mye og kommer ofte tilbake. Du kan deretter [opprette et segment](segments.md) basert på disse målene for å få de neste beste handlingene.

## <a name="create-a-measure"></a>Opprette et mål

Velg hvordan du vil opprette et må basert på målgruppen.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

- Fra grunnen av med måleverktøyet: [Bygg din egen](measure-builder.md).
- Fra ofte brukte mål: [Bruk forhåndsdefinerte maler](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

Fra grunnen av med måleverktøyet: [Bygg din egen](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Administrer eksisterende mål

Gå til **Mål**-siden for å vise målene du opprettet, statusen deres, måltypen og sist gang dataene ble oppdatert. Du kan sortere listen over mål etter en hvilken som helst kolonne, eller bruke søkeboksen til å finne målet du vil administrere.

Merk av for et mål for å vise tilgjengelige handlinger. Velg målnavnet for å forhåndsvise utdataene og laste ned en CSV-fil.

:::image type="content" source="media/measures-actions.png" alt-text="Handlinger for å administrere enkeltmål."lightbox="media/measures-actions.png":::

- **Rediger** målet for å endre egenskapene.
- **Oppdater** målet for å ta med de nyeste dataene.
- **Gi nytt navn** til målet.
- **Aktiver** eller **Deaktiver** målet. Inaktive mål blir ikke oppdatert under en [planlagt oppdatering](system.md#schedule-tab) og har **Status** oppført som **Hoppet over**, som tyder på at en oppdatering ikke ble forsøkt.
- **Merk** for å [administrere merker](work-with-tags-columns.md#manage-tags) for målet.
- **Slett** målet.
- **Kolonner** for å [tilpasse kolonnene](work-with-tags-columns.md#customize-columns) som vises.
- **Filtrer** for å [filtrere på merker](work-with-tags-columns.md#filter-on-tags).
- **Søkenavn** for å søke etter målnavn.

## <a name="refresh-measures"></a>Oppdater mål

Mål kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov. Hvis du vil oppdatere en eller flere mål manuelt, velger du dem og velger **Oppdater**. Hvis du vil [planlegge en automatisk oppdatering](system.md#schedule-tab), går du til **Administrator** > **System** > **Plan**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
