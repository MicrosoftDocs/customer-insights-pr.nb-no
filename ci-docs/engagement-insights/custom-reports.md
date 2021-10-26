---
title: Om egendefinerte rapporter
description: Finn ut hvordan du oppretter egendefinerte rapporter.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3fa801bfc8b0aee65c21b90de2423a3d5d5e4e26
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582889"
---
# <a name="create-and-edit-custom-reports"></a>Opprett og rediger egendefinerte rapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

I tillegg til innebygde rapporter kan du bygge en egendefinert rapport med diagram- og tabellvisualiseringer for å hjelpe deg med å forstå brukeratferd. Denne artikkelen forklarer hvordan du oppretter en rapport med dataene du trenger, ved hjelp av tabell- og diagramvisualiseringer. Hvis du vil ha mer informasjon om innebygde rapporter, kan du se [Vise rapporter](view-reports.md).

## <a name="create-a-custom-report"></a>Opprett en egendefinert rapport

1. Gå til **Analyser** > **Egendefinert** for å få tilgang til listen over egendefinerte rapporter.

1. Velg **Ny rapport** for å begynne å opprette en egendefinert rapport.

   :::image type="content" source="media/new-custom-report.png" alt-text="Nye egendefinerte rapporter.":::

1. Bestem rapporttypen du vil bygge:

    - Velg **Legg til visuell effekt** på kommandolinjen for å opprette en standard tabellvisualisering.
    - Du kan også velge en kolonne-, stolpe-, linje-, område-, sektor-, donut- eller tabellvisualisering fra ruten **Redigeringsprogram for rapporter**.

1. I **Data**-delen i ruten **Redigeringsprogram for visualisering** velger du et av de tilgjengelige alternativene (for eksempel sidevisninger) fra rullegardinlisten **Metrikkverdier**. Du kan også legge til **Dimensjoner** (for eksempel land) for å vise i visualiseringen. Hvis du vil ha mer informasjon, kan du se [Vise og opprette metrikkverdier](metrics.md) og [Vise og opprette dimensjoner](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Velg en metrikkverdi for rapporten.":::

1. Velg **Utforming**-delen i ruten **Redigeringsprogram for visualisering** for å legge til **Titteltekst** og aktivere/deaktivere **Tittel**.  Du kan også endre visualiseringstypen ved å velge et annet diagram, for eksempel **sektordiagram**.

1. Slik endrer du størrelsen og posisjonen for en visualisering:
   - Merk visualiseringen, og dra deretter i et av hjørnene eller kantene for å justere størrelsen.
   - Velg visualiseringen, og flytt den til en ny posisjon. Du kan også bruke piltastene til å endre posisjon.
1. Velg **Legg til visuell effekt** på kommandolinjen for å legge til en ny visualisering.
1. Når du har lagt til visualiseringene du ønsker for rapporten, velger du **Lagre** på kommandolinjen.

1. Angi et navn for den egendefinerte rapporten, og velg **Lagre** for å opprette den.
 
## <a name="filter-a-custom-report"></a>Filtrere en egendefinert rapport

Du kan velge datotidsramme eller datointervall i en egendefinert rapport for å fokusere på en verdi eller tidsperiode.

For å velge en tidsramme velger du en verdi fra rullegardinlisten for rapporten i øvre høyre hjørne av rapportvisningen. Du kan også velge en **Fast datointervall*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrere etter klokkeslett eller datointervall.":::

For de fleste rapporter velger du **+ Legg til betingelse** for å velge en dimensjon eller et segment som skal filtrere rapporten. Hvis du vil ha mer informasjon, kan du se [Vise og opprette segmenter](segments.md).

## <a name="edit-a-custom-report"></a>Rediger en egendefinert rapport

1. Gå til **Analyser** > **Egendefinert** for å få tilgang til listen over egendefinerte rapporter.

1. Velg **Mer [...]** i listen over egendefinerte rapporter. 

1. Velg **Rediger navn** for å endre navnet på rapporten.

1. Velg navnet på rapporten, og bruk alternativene **+ Legg til visuell effekt** og **Rediger** for å legge til, fjerne, flytte eller endre størrelse på visualiseringene.

1. Hvis du vil endre egenskapene for en visualisering, velger du den visuelle effekten og deretter **...** og **Rediger visuell effekt**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Rediger diagramegenskaper for egendefinerte rapporter.":::

1. Når du har redigert rapporten, kan du velge **Lagre** for å ta i bruk endringene. 

## <a name="delete-a-custom-report"></a>Slett en egendefinert rapport

1. Gå til **Analyser** > **Egendefinert** for å få tilgang til listen over egendefinerte rapporter.

1. Velg **...** i listen over egendefinerte rapporter.

1. Velg **Slett** for å fjerne rapporten.

1. Bekreft slettingen for å fjerne rapporten permanent.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
