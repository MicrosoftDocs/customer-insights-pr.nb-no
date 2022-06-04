---
title: Segmenter i Customer Insights
description: Oversikt over segmenter og hvordan du oppretter og administrerer dem.
ms.date: 03/30/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 9791e971387eb7db91ed7c4e4fe76552656013ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647066"
---
# <a name="segments-overview"></a>Oversikt over segmenter

Med segmenter kan du gruppere kunder basert på demografiske, transaksjonelle eller atferdsmessige attributter. Du kan bruke segmenter til å målrette kampanjer, salgsaktiviteter og kundestøttehandlinger slik at du oppnår forretningsmålene dine.

Kundeprofiler som samsvarer med filtrene i en segmentdefinisjon, kalles *medlemmer* av et segment. Enkelte [tjenestebegrensninger](/dynamics365/customer-insights/service-limits) gjelder.

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

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valgt segment med rullegardinliste med alternativer og tilgjengelige alternativer." lightbox="media/segments-selected-segment.png":::

Følgende handlinger er tilgjengelige når du velger et segment:

- **Vis** segmentdetaljene, inkludert medlemsantall, som viser en forhåndsvisning av segmentmedlemmer.
- **Last ned** listen over medlemmer som en .CSV-fil.
- **Rediger** segmentet for å endre egenskapene.
- **Opprett duplikat** av et segment. Du kan velge å redigere egenskapene med en gang, eller ganske enkelt lagre duplikatet.
- **Oppdater** segmentet slik at det inneholder de nyeste dataene.
- **Aktiver** eller **Deaktiver** segmentet. For inaktive segmenter finnes segmentdefinisjonen, men den inneholder ingen kunder ennå. Et aktivt segment ser etter kunder som samsvarer med segmentdefinisjonen. Hvis en [planlagt oppdatering](system.md#schedule-tab) er konfigurert, har inaktive segmenter **Status** oppført som **Hoppet over**, og dette tyder på at en oppdatering ikke ble forsøkt. Når et inaktivt segment blir aktivert, oppdateres det og tas med i planlagte oppdateringer.
  Du kan også bruke funksjonen **Planlegg senere** i rullegardinlisten **Aktiver/Deaktiver** for å angi en fremtidig dato og klokkeslett for acktivering og deaktivering av et bestemt segment.
- **[Finn lignende kunder](find-similar-customer-segments.md)** fra segmentet.
- **Gi nytt navn** til segmentet.
- **Merke** for å [administrere merker](work-with-tags-columns.md#manage-tags) for segmentet.
- **Last ned** listen over medlemmer som en .CSV-fil.
- **Behandle eksporter** for å se eksporter som er knyttet til segment, og administrere dem. [Finn ut mer om eksporter.](export-destinations.md)
- **Slett** segmentet.
- **Kolonner** for å [tilpasse kolonnene](work-with-tags-columns.md#customize-columns) som vises.
- **Filtrer** for å [filtrere på merker](work-with-tags-columns.md#filter-on-tags).
- **Søkenavn** for søk etter segmentnavn.

## <a name="refresh-segments"></a>Oppdatere segmenter

Du kan oppdatere alle segmenter samtidig ved å velge **Oppdater alle** på **Segmenter**-siden, eller du kan oppdatere ett eller flere segmenter når du velger dem, og deretter velge **Oppdater** fra alternativene. Du kan også konfigurere en regelmessig oppdatering under **Admin** > **System** > **Tidsplan**. Når en regelmessig oppdatering konfigureres, gjelder følgende regler:
- Alle segmenter av typen **Dynamisk** eller **Utvidelse** oppdateres automatisk med den angitte hyppigheten. Når oppdateringen er fullført, angir **Status** om det var problemer under oppdatering av segmentet. **Sist oppdaterte** viser et tidsstempel for den siste vellykkede oppdateringen. Hvis det oppstår en feil, velger du feilen for å vise detaljer om hva som har skjedd.
- Segmenter av typen **Statisk** *blir ikke* oppdatert automatisk. **Sist oppdatert** viser et tidsstempel for sist gang de statiske segmentene ble kjørt eller oppdatert manuelt.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

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


[!INCLUDE [footer-include](includes/footer-banner.md)]