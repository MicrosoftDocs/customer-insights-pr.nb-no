---
title: Segmentinnsikt (forhåndsversjon)
description: Få innsikt om eksisterende segmenter for å se forskjeller og felles trekk.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171015"
---
# <a name="segment-insights-preview"></a>Segmentinnsikt (forhåndsversjon)

Oppdag mer informasjon og innsikt rundt eksisterende segmenter. Finn ut hva som skiller to segmenter fra hverandre, eller hva de har til felles.

## <a name="segment-overlap"></a>Segmentoverlapping

Analyse av segmentoverlapping viser hvor mange og hvilke kunder som er felles for to eller flere segmenter. For eksempel hvordan et segment med hyppige kunder overlapper med et segment som inneholder kunder som er fornøyd med servicen eller produktet.
Du kan også analysere hvordan overlappingen endres for bestemte attributter.

### <a name="run-an-overlap-analysis"></a>Kjøre en overlappingsanalyse

1. Gå til **Segmenter**, og velg kategorien **Innsikt (forhåndsversjon)**.

1. Velg **Ny**, og velg alternativet **Overlapping** i ruten **Velg innsiktstype**.

1. Velg segmentene av interesse, og velg **Neste**.

1. Hvis du vil, kan du velge ett eller flere felt av interesse for å analysere overlapping for alle mulige feltverdier og velge **Neste**.

1. Oppgi et navn for overlappingsanalysen, et valgfritt visningsnavn og en beskrivelse.

1. Velg **Lagre** for å starte analysen. Overlappingsanalysen er klar når statusen endres fra Oppdaterer til Vellykket.

### <a name="view-and-optimize-an-overlap-analysis"></a>Vise og optimalisere en overlappingsanalyse

1. Etter at du har fullført analysen, finner du mer informasjon om denne innsikten i **Segmenter** > **Innsikt (forhåndsversjon)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Innsiktsdetaljer om segmentoverlapping.":::

1. Velg en innsikt for å vise analyseresultatene:

   - Antall medlemmer som overlapper segmentene som er valgt for analyse.
   - Antall medlemmer som er inkludert i ett av segmentene, men ikke i resten av segmentene.
   - Hvis du valgte felt under konfigurasjon av overlappingsanalysen, finner du dem i de tilsvarende kategoriene. Du kan bruke rullegardinlisten for filter til å velge hvilket som helst interesseattributt, og tabellen nederst viser de tilsvarende dataene.

## <a name="segment-differentiators"></a>Segmentdifferensiatorer

Ved hjelp av segmentdifferensiatorer kan du finne ut hva som skiller et segment fra resten av kundene eller fra et annet segment. Velg et segment, og deretter identifiserer systemet profilattributter og mål som skiller det valgte segmentet.

### <a name="run-a-differentiator-analysis"></a>Kjøre en differensiatoranalyse

1. Gå til **Segmenter**, og velg kategorien **Innsikt (forhåndsversjon)**.

1. Velg **Ny**, og velg alternativet **Differensiatorer** i ruten **Velg innsiktstype**.

1. Velg segmentet du vil analysere, som **Primært segment**, og velg **Neste**.

1. Velg **Alle kunder** eller et **Sekundært segment** for å sammenligne hovedsegmentet med, og velg deretter **Neste**.

1. Hvis du vil, kan du velge ett eller flere felt av interesse for å fokusere analysen på bestemte attributter og deretter velge **Neste**.

1. Oppgi et navn for differensiatoranalysen, et valgfritt visningsnavn og en beskrivelse.

1. Velg **Lagre** for å starte analysen. Differensiatoranalysen er klar når statusen endres fra Oppdaterer til Vellykket.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Vise og optimalisere en differensiatoranalyse

1. Etter at du har fullført analysen, går du til **Segmenter** > **Innsikt (forhåndsversjon)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Innsiktsdetaljer om segmentdifferensiator.":::

1. Velg en innsikt for å vise analyseresultatene. En differensiatoranalyse inneholder to kategorier. Kategorien **Attributter** viser profilattributter vurdert som differensiatorer. Kategorien **Mål** viser differensiatorer. Hver kategori inkluderer følgende detaljer:

   - Rangert liste over differensiatorer, sortert etter differansepoengsum.
   - **Differansepoengsummen** for hver differensiator. Differansepoengsummen representerer graden av fifferanse for et attributt mellom to segmenter. Jo høyere differansepoengsum, jo mer forskjellig er attributtene mellom de to segmentene. Velg en poengsum for å åpne ruten **Differansepoengsum** med fordelingen av verdier for dette attributtet.

## <a name="manage-segment-insights"></a>Behandle segmentinnsikt

Gå til **Segmenter** > **Innsikt (forhåndsversjon)** for å vise segmentinnsikten og administrere den. Velg en segmentinnsikt for å vise tilgjengelige handlinger.

- **Vis** innsiktsanalysen
- **Rediger** innsikten for å endre egenskapene
- **Oppdater** innsikten for å kjøre analysen på nytt
- **Gi nytt navn** til innsikten
- **Slett** innsikten

[!INCLUDE [footer-include](includes/footer-banner.md)]
