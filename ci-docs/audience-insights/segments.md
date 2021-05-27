---
title: Segmenter i målgruppeinnsikt
description: Oversikt over segmenter og hvordan du oppretter og administrerer dem.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034024"
---
# <a name="segments-overview"></a>Oversikt over segmenter

Med segmenter kan du gruppere kunder basert på demografiske, transaksjonelle eller atferdsmessige attributter. Du kan bruke segmenter til å målrette kampanjer, salgsaktiviteter og kundestøttehandlinger slik at du oppnår forretningsmålene dine.

Kundeprofiler som samsvarer med filtrene i en segmentdefinisjon, kalles *medlemmer* av et segment. Enkelte [tjenestebegrensninger](service-limits.md) gjelder.

## <a name="create-a-new-segment"></a>Opprett et nytt segment

Du kan opprette et nytt segment på flere måter: 

- Komplekst segment med segmentverktøyet: [Tomt segment](segment-builder.md#create-a-new-segment)
- Enkle segmenter med én operator: [Hurtigsegment](segment-builder.md#quick-segments)
- AI-drevne måter å finne lignende kunder på: [Lignende kunder](find-similar-customer-segments.md)
- AI-drevne forslag basert på mål eller attributter: [Foreslåtte segmenter for å forbedre tiltak](suggested-segments.md)
- Forslag basert på aktiviteter: [Foreslåtte segmenter basert på kundeaktivitet](suggested-segments-activity.md)

## <a name="get-insights-on-existing-segments"></a>Få innsikt i eksisterende segmenter

Oppdag ytterligere informasjon om de eksisterende segmentene ved hjelp av [Segmentinnsikt](segment-insights.md). Finn ut hva som skiller to segmenter fra hverandre, eller hva de har til felles.

## <a name="find-similar-customers"></a>Søk etter lignende kunder

Finn kunder som ligner på medlemmene i et valgt segment, ved hjelp av kunstig intelligens. Hvis du vil ha mer informasjon, kan du se [lignende kunder ](find-similar-customer-segments.md).

## <a name="manage-existing-segments"></a>Behandle eksisterende segmenter

Gå til **Segmenter**-siden for å vise alle lagrede segmenter og behandle dem.

Hvert segment representeres av en rad som inneholder tilleggsinformasjon om segmentet.

> [!div class="mx-imgBorder"]
> ![Alternativer for å behandle et eksisterende segment](media/segments-selected-segment.png "Alternativer for å behandle et eksisterende segment")

Følgende handling er tilgjengelig når du velger et segment:

- **Vis** segmentdetaljene, inkludert medlemsantall, som viser en forhåndsvisning av segmentmedlemmer.
- **Rediger** segmentet for å endre egenskapene.
- **Opprett duplikat** av et segment. Du kan velge å redigere egenskapene med en gang, eller ganske enkelt lagre duplikatet.
- **Oppdater** segmentet slik at det inneholder de nyeste dataene.
- **Aktiver** eller **Deaktiver** segmentet. Segmenter har to mulige tilstander – aktive eller inaktive. Disse tilstandene er nyttige når du redigerer et segment. For inaktive segmenter finnes segmentdefinisjonen, men den inneholder ingen kunder ennå. Når du aktiverer et segment, endres statusen fra inaktiv til aktiv, og den begynner å se etter kunder som samsvarer med segmentdefinisjonen. Hvis en [planlagt oppdatering](system.md#schedule-tab) er konfigurert, har inaktive segmenter **Status** oppført som **Hoppet over**, og dette tyder på at en oppdatering ikke ble forsøkt. Når et inaktivt segment blir aktivert, oppdateres det og tas med i planlagte oppdateringer.
  Du kan også bruke funksjonen **Planlegg senere** i rullegardinlisten **Aktiver/Deaktiver** for å angi en fremtidig dato og klokkeslett for acktivering og deaktivering av et bestemt segment.
- **Gi nytt navn** til segmentet.
- **Last ned** listen over medlemmer som en .CSV-fil.
- **Legg til**-alternativet sender listen over kunde-ID-er i segmentet til behandling i et annet program.
- **Slett** segmentet.

## <a name="refresh-segments"></a>Oppdatere segmenter

Du kan oppdatere alle segmenter samtidig ved å velge **Oppdater alle** på **Segmenter**-siden, eller du kan oppdatere ett eller flere segmenter når du velger dem, og deretter velge **Oppdater** fra alternativene. Du kan også konfigurere en regelmessig oppdatering under **Admin** > **System** > **Tidsplan**.

> [!TIP]
> Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser. De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies). Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben. Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.

## <a name="view-processing-history-and-segment-members"></a>Vis behandlingslogg og segmentmedlemmer

Du kan vise konsoliderte data om et segment ved å se gjennom detaljene.

På siden **Segmenter** velger du segmentet du vil se gjennom.

Den øvre delen av siden inneholder et trendgraf som visualiserer endringer i medlemsantall. Beveg pekeren over datapunkter for å se medlemsantallet på en bestemt dato.

Du kan oppdatere tidsrammen for visualiseringen.

> [!div class="mx-imgBorder"]
> ![Tidsintervall for segment](media/segment-time-range.png "Tidsintervall for segment")

Den nedre delen inneholder en liste over medlemmene i segmentet.

> [!NOTE]
> Felt som vises i listen, er basert på attributtene til enhetene i segmentet.
>
>Listen er en forhåndsvisning av de samsvarende segmentmedlemmene og viser de første 100 oppføringene av segmentet, slik at du raskt kan evaluere det og se gjennom definisjonene hvis det er nødvendig. Hvis du vil vise alle samsvarende oppføringer, må du [eksportere segmentet](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
