---
title: Bruk målgruppeinnsiktssegmenter til å filtrere engasjementsinnsiktrapporter
description: Bruk målgruppeinnsiktssegmenter i interaktive analyser av atferdsdata som er registrert av engasjementsinnsikt på en kundes nettsted.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230498"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Bruk målgruppeinnsiktssegmenter til å filtrere engasjementsinnsiktrapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med engasjementsinnsikt kan du bruke målgruppeinnsiktssegmenter i interaktive analyser av atferdsdata som er registrert av engasjementsinnsikt på nettstedet ditt.

## <a name="prerequisite"></a>Forutsetning

- Et engasjementsinnsiktmiljø der du har data om målgruppeinnsiktssegmenter koblet til målgruppeinnsiktsmiljøet der segmentene og kundeprofilene er opprettet. Mer informasjon: [Opprett en kobling mellom målgruppeinnsikt og engasjementsinnsikt](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Opprett målgruppeinnsiktssegmenter 

> [!IMPORTANT]
> Hvis målgruppeinnsiktssegmenter skal vises i engasjementsinnsikt, må du først [kjøre sammenslåings- og nedstrømsprosesser](../audience-insights/merge-entities.md). Nedstrømsprosesser er viktige fordi de genererer en unik tabell som klargjør målgruppeinnsiktssegmenter som skal deles med engasjementsinnsikt. (Hvis en systemoppdatering planlegges, vil den automatisk inkludere nedstrømsprosesser.)

Du kan bruke målgruppeinnsiktssegmenter i standardrapporter for engasjementsinnsikt, eller egendefinerte rapporter du har opprettet. Hvis du vil ha mer informasjon, kan du gå til med [Standard profilrapporter](profile-reports.md) og [Opprett og rediger egendefinerte rapporter](custom-reports.md).

**Slik bruker du målgruppeinnsiktssegmenter i engasjementsinnsiktrapporter**

1. Velg **Arbeidsområde**-siden velger du **Data** og deretter fanen **Segmenter**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Velg Segmenter-fanen.":::

   >[!NOTE]
   > Når du velger et målgruppeinnsiktssegment, tas du til målgruppeinnsikt, der du kan finne ut hvordan dette segmentet ble opprettet i form av regler og logikk. Hvis du vil ha mer informasjon om målgruppeinnsiktssegmenter, kan du gå til [Vis og opprett segmenter](../audience-insights/segments.md).

2. Velg en standardrapport, eller [opprett en egendefinert rapport](custom-reports.md), og velg deretter **Legg til betingelse**. (I dette eksemplet valgte vi **Sidevisninger**-rapporten.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Legg til en betingelse.":::

3. Velg **Filtrer etter segment**, utvid **Segmenttype**-listen og velg deretter **Demografi**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Velg den demografiske segmenttypen.":::

4. Utvid **Segmentnavn**-listen, og velg deretter et målgruppeinnsiktssegment.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Velg et segment.":::

5. Du kan bruke en eller flere segmenter, inkludert atferdsinnsikt (engasjementsinnsikt) og demografi (målgruppeinnsiktssegmenter). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Sidevisninger er begrenset til segmentene USA-kunder og Startside.":::

I det foregående bildet er segmentene **USA-kunder** og **Startside** valgt, noe som begrenser **sidevisningsrapporten** til å vise bare de to segmentene. 


>[!NOTE]
> Du kan bruke målgruppeinnsiktssegmenter til å filtrere ut standardrapporter, egendefinerte rapporter og trakter i engasjementsinnsikt. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]