---
title: Opprett enkle segmenter med hurtigsegmenter
description: Opprett enkle segmenter av kunder for å gruppere dem basert på forskjellige attributter.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171139"
---
# <a name="create-simple-segments-with-quick-segments"></a>Opprett enkle segmenter med hurtigsegmenter

Med hurtigsegmenter kan du bygge enkle segmenter med én operator raskt for raskere innsikt. Hurtigsegmenter støttes bare i miljøer for **enkeltkunder**.

## <a name="create-a-new-segment-with-quick-segments"></a>Opprett et nytt segment med hurtigsegmenter

1. Gå til **Segmenter**.

1. Velg **Ny** > **Opprett fra**.
   - Velg alternativet **Profiler** for å bygge et segment som er basert på den *enhetlige kundeenheten*.
   - Velg **Mål**-alternativet for å bygge et segment rundt mål du tidligere har opprettet.
   - Velg alternativet **Intelligens** for å bygge et segment rundt én av de utgående enhetene du genererte ved hjelp av funksjonene **Prediksjoner** eller **Egendefinerte modeller**.

1. I dialogboksen **Nytt hurtigsegment** velger du et attributt fra **Felt**-rullegardinlisten. Systemet gir ulike verdier basert på det du velger.
   - De 10 største kundeantallene vises for kategoriske felt. Velg en **Verdi** og deretter **Gå gjennom**.
   - For et numerisk attributt viser systemet hvilken attributtverdi som faller under hver kundepersentil. Velg en **Operator** og en **Verdi**, og velg deretter **Gå gjennom**.

1. Systemet gir en **Beregnet segmentstørrelse**. Velg om du vil generere segmentet du har definert, eller gå tilbake for å få velge et annet felt.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Navn og beregning for et hurtigsegment.":::

1. Angi et **navn** og **utdataenhetsnavn** for segmentet. Du kan eventuelt legge til [merker](work-with-tags-columns.md#manage-tags).

1. Velg **Lagre** for å opprette segmentet. **Segmenter**-siden vises.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Neste trinn

[Eksporter et segment](export-destinations.md), og utforsk [kundekortintegreringen](customer-card-add-in.md) for å bruke segmenter i andre programmer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
