---
title: Foreslåtte segmenter basert på aktivitet (forhåndsversjon)
description: La maskinlæring hjelpe deg med å finne nye og interessante segmenter basert på kundeaktivitet.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170601"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Foreslåtte segmenter basert på aktivitet (forhåndsversjon)

Oppdag interessante segmenter av kundene basert på kundeaktivitetsdata som er hentet inn i Customer Insights. Eksempler på aktivitetsdata er transaksjoner, samtalevarighet, kjøp eller returer. For å foreslå segmenter analyseres aktivitetsdata for nylighet, hyppighet og pengeverdi (eller varighet). Du kan også generere [foreslåtte segmenter for å forbedre et mål, eller bedre forstå hva som har innvirkning på et attributt](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Fanen Foreslåtte segmenter som viser segmentforslag for aktivitetsbaserte og attributtbaserte segmenter.":::

## <a name="categorize-customers-by-activity"></a>Kategoriser kunder etter aktivitet

Med [aktivitetsdata](activities.md) tilgjengelige i Customer Insights kan vi generere forslag som representerer kundegrupper:

- mest aktive kunder 
- kunder som har gjort flest kjøp 
- kunder som genererte mest omsetning 
- kunder som ikke har vært aktive i det siste 
- kunder som ofte samhandler med virksomheten din  

Hvis du har en detaljvirksomhet, kan du finne ut hvilke kunder som genererer størst omsetning, og belønne dem med en rabattkuponger. Du kan også identifisere tilfeldige kunder og tilby dem å delta i et belønningsprogram, slik at de oftere besøker bedriften.
Hvis du tilbyr offentlige helsetjenester og målet er å redusere utgiftene for enkeltpasienter, kan du prøve å redusere antall regelmessige besøk ved å gi best mulig behandling med så få besøk som mulig. I dette tilfellet er målet å holde besøksfrekvensen lav og redusere regelmessige kostnader for pasientene. Du kan også identifisere segmenter av pasienter som har hyppige avtaler og høye regelmessige kostnader, og analysere disse sakene for å forbedre behandling av den enkelte.

## <a name="required-data"></a>Obligatoriske data

Forslagene genereres basert på de valgte inndataene.

- Kundeprofiler: Alle kunder eller medlemmer i et bestemt segment.

- Tidsperiode: Siste måned, forrige år eller egendefinerte tidsrammer.

- Aktivitetstype: kjøp, detaljhandelstransaksjoner, elektroniske transaksjoner, kundestøttesaker, abonnementer og så videre.  

- Enhet i Customer Insights som inneholder aktivitetsdataene: UnifiedActivity-enheten eller enheten for en bestemt aktivitet.

- Dimensjonene som skal inkluderes: Nylighet, hyppighet eller pengedimensjon, avhengig av forretningskravene.

## <a name="generate-suggested-segments"></a>Generer foreslåtte segmenter

1. Gå til **Segmenter**, og velg fanen **Forslag (forhåndsversjon)**.

1. Velg **Finn nye forslag** og velg **Se eller forvent kundevirkemåte**. Velg **Start**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Første trinn i konfigurasjonsveiviseren for et foreslått segment basert på aktivitet.":::

1. Angi de nødvendige inndataene, og velg **Neste**.

   - Velg kunder: Inkluder alle kunder eller et bestemt segment.
   - Velg aktivitet: Velg aktivitetstypen og enhetene som beskriver aktiviteten.
   - Innstillinger: Angi tidsperioden som skal vurderes, faktorer for forslag og tilordne attributtene.

1. Gå gjennom inndataene og velg **Kjør** for å kjøre modellen og generere forslag.

Det kan ta noen minutter å fullføre, avhengig av antall kundeprofiler og valgte aktiviteter.

Når du har generert forslagene, kan du filtrere dem etter dimensjonen eller verdien du er mest interessert i.

## <a name="manage-suggested-segments"></a>Administrer foreslåtte segmenter

Gå til **Segmenter**, og velg fanen **Forslag (forhåndsvisning)**. I delen **Aktivitetsbaserte forslag** velger du et foreslått segment for å vise tilgjengelige handlinger.

- **Se forslag** for å vise detaljene for dette segmentet, for eksempel omfanget av hver dimensjon sammenlignet med målgruppen. Den fremhever også antall potensielle medlemmer i segmentet og den tilsvarende prosentandelen av totalkundene.
- **Opprett segment** for å lagre forslaget som et segment. Det vises i fanen **Alle segmenter** og kan [oppdateres eller slettes](segments.md). Du kan ikke redigere segmentdetaljene. Du kan imidlertid endre inndatavilkårene for forslagene og generere ulike forslag.
- **Rediger forslag** for å endre de konfigurerte attributtene som erstatter de gjeldende forslagene.
- **Oppdater forslag** for å oppdatere forslagene samtidig som du beholder konfigurerte attributter.

[!INCLUDE [footer-include](includes/footer-banner.md)]
