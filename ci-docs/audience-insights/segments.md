---
title: Segmenter i målgruppeinnsikt
description: Oversikt over segmenter og hvordan du oppretter og administrerer dem.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 740d293b21f43b50201f23fcba109318823ef3af
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978071"
---
# <a name="segments-overview"></a>Oversikt over segmenter

Med segmenter kan du gruppere kunder basert på demografiske, transaksjonelle eller atferdsmessige attributter. Du kan bruke segmenter til å målrette kampanjer, salgsaktiviteter og kundestøttehandlinger slik at du oppnår forretningsmålene dine.

Kundeprofiler som samsvarer med filtrene i en segmentdefinisjon, kalles *medlemmer* av et segment. Enkelte [tjenestebegrensninger](service-limits.md) gjelder.

## <a name="create-a-new-segment"></a>Opprett et nytt segment

Du kan opprette et nytt segment på flere måter: 

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

- Komplekst segment med segmentbygger: [Bygg din egen](segment-builder.md#create-a-new-segment) 
- Enkle segmenter med én operator: [Hurtigsegment](segment-builder.md#quick-segments) 
- AI-drevne måter å finne lignende kunder på: [Lignende kunder](find-similar-customer-segments.md) 
- AI-drevne forslag basert på mål eller attributter: [Foreslåtte segmenter for å forbedre tiltak](suggested-segments.md) 
- Forslag basert på aktiviteter: [Foreslåtte segmenter basert på kundeaktivitet](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

- Komplekst segment med segmentbygger: [Bygg din egen](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Behandle eksisterende segmenter

Gå til **Segmenter**-siden for å vise alle lagrede segmenter og behandle dem.

Hvert segment representeres av en rad som inneholder tilleggsinformasjon om segmentet.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valgt segment med rullegardinliste med alternativer og tilgjengelige alternativer.":::

Følgende handling er tilgjengelig når du velger et segment:

- **Vis** segmentdetaljene, inkludert medlemsantall, som viser en forhåndsvisning av segmentmedlemmer.
- **Rediger** segmentet for å endre egenskapene.
- **Opprett duplikat** av et segment. Du kan velge å redigere egenskapene med en gang, eller ganske enkelt lagre duplikatet.
- **Oppdater** segmentet slik at det inneholder de nyeste dataene.
- **Aktiver** eller **Deaktiver** segmentet. Segmenter har to mulige tilstander – aktive eller inaktive. Disse tilstandene er nyttige når du redigerer et segment. For inaktive segmenter finnes segmentdefinisjonen, men den inneholder ingen kunder ennå. Når du aktiverer et segment, endres statusen fra inaktiv til aktiv, og den begynner å se etter kunder som samsvarer med segmentdefinisjonen. Hvis en [planlagt oppdatering](system.md#schedule-tab) er konfigurert, har inaktive segmenter **Status** oppført som **Hoppet over**, og dette tyder på at en oppdatering ikke ble forsøkt. Når et inaktivt segment blir aktivert, oppdateres det og tas med i planlagte oppdateringer.
  Du kan også bruke funksjonen **Planlegg senere** i rullegardinlisten **Aktiver/Deaktiver** for å angi en fremtidig dato og klokkeslett for acktivering og deaktivering av et bestemt segment.
- **Gi nytt navn** til segmentet.
- **Last ned** listen over medlemmer som en .CSV-fil.
- **Behandle eksporter** for å se eksporter som er knyttet til segment, og administrere dem. [Finn ut mer om eksporter.](export-destinations.md)
- **Slett** segmentet.

## <a name="refresh-segments"></a>Oppdatere segmenter

Du kan oppdatere alle segmenter samtidig ved å velge **Oppdater alle** på **Segmenter**-siden, eller du kan oppdatere ett eller flere segmenter når du velger dem, og deretter velge **Oppdater** fra alternativene. Du kan også konfigurere en regelmessig oppdatering under **Admin** > **System** > **Tidsplan**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Eksportere segmenter

Du kan eksportere et segment fra segmentsiden eller [eksportsiden](export-destinations.md). 

1. Gå til siden **Segmenter**.

1. Velg **Vis mer [...]** for segmentet du vil eksportere.

1. Velg **Behandle eksporter** fra rullegardinlisten over handlinger.

1. Siden **Eksporter (forhåndsversjon) for segmentet** åpnes. Du kan se alle konfigurerte eksporter gruppert etter om de inneholder gjeldende segment eller ikke.

   1. Hvis du vil legge til det valgte segmentet i en eksport, **Rediger** den respektive eksporten for å velge det tilsvarende segmentet, og deretter lagrer du. I miljøer for enkeltkunder kan du i stedet velge eksporten fra listen og velge **Legg til segment** for å oppnå samme resultat.

   1. Hvis du vil opprette en ny eksport med det valgte segmentet, velger du **Legg til eksport**. Hvis du vil ha mer informasjon om hvordan du oppretter eksporter, kan du se [Konfigurere en ny eksport](export-destinations.md#set-up-a-new-export).

1. Velg **Tilbake** for å gå tilbake til hovedsiden for segmenter.

## <a name="view-processing-history-and-segment-members"></a>Vis behandlingslogg og segmentmedlemmer

Du kan vise konsoliderte data om et segment ved å se gjennom detaljene.

På siden **Segmenter** velger du segmentet du vil se gjennom.

Den øvre delen av siden inneholder et trendgraf som visualiserer endringer i medlemsantall. Beveg pekeren over datapunkter for å se medlemsantallet på en bestemt dato.

Du kan oppdatere tidsrammen for visualiseringen.

> [!div class="mx-imgBorder"]
> ![Tidsintervall for segment.](media/segment-time-range.png "Tidsintervall for segment")

Den nedre delen inneholder en liste over medlemmene i segmentet.

> [!NOTE]
> Felt som vises i listen, er basert på attributtene til enhetene i segmentet.
>
>Listen er en forhåndsvisning av de samsvarende segmentmedlemmene og viser de første 100 oppføringene av segmentet, slik at du raskt kan evaluere det og se gjennom definisjonene hvis det er nødvendig. Hvis du vil vise alle samsvarende oppføringer, må du [eksportere segmentet](export-destinations.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)] 
