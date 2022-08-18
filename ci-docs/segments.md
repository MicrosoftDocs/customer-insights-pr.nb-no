---
title: Oversikt over segmenter
description: Oversikt over segmenter og hvordan du oppretter og administrerer dem.
ms.date: 05/20/2022
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
ms.openlocfilehash: 195a7c733f047c24f9f47a151c1cb623fe34d055
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246305"
---
# <a name="segments-overview"></a>Oversikt over segmenter

Med segmenter kan du gruppere kunder basert på demografiske, transaksjonelle eller atferdsmessige attributter. Du kan bruke segmenter til å målrette kampanjer, salgsaktiviteter og kundestøttehandlinger slik at du oppnår forretningsmålene dine.

Kundeprofiler som samsvarer med filtrene i en segmentdefinisjon, kalles *medlemmer* av et segment. Enkelte [tjenestebegrensninger](/dynamics365/customer-insights/service-limits) gjelder.

## <a name="create-a-segment"></a>Opprett et segment

Velg hvordan du vil opprette et segment, basert på målgruppen.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

- Komplekse segmenter med segmentbygger: [Bygg din egen](segment-builder.md)
- Enkle segmenter med én operator: [Hurtigsegment](segment-quick.md)
- KI-drevne måter å finne lignende kunder på: [Lignende kunder](find-similar-customer-segments.md)
- KI-drevne forslag basert på mål eller attributter: [Foreslåtte segmenter basert på mål](suggested-segments.md)
- Forslag basert på aktiviteter: [Foreslåtte segmenter basert på kundeaktivitet](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

- Enkle eller komplekse segmenter med segmentbygger: [Bygg din egen](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Behandle eksisterende segmenter

Gå til **Segmenter**-siden for å vise segmentene du opprettet, statusen og tilstanden deres, antall medlemmer og sist gang dataene ble oppdatert. Du kan sortere listen over segmenter etter en hvilken som helst kolonne, eller du kan bruke søkefeltet til å finne segmentet du vil administrere.

Velg et segment for å vise tilgjengelige handlinger.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valgt segment med rullegardinliste med alternativer og tilgjengelige alternativer." lightbox="media/segments-selected-segment.png":::

- [**Vis**](#view-segment-details) segmentdetaljene, inkludert medlemsantallstrend og en forhåndsvisning av segmentmedlemmer.
- **Last ned** listen over medlemmer som en .CSV-fil.
- **Rediger** segmentet for å endre egenskapene.
- **Opprett duplikat** av et segment. Du kan velge å redigere egenskapene med én gang, eller lagre duplikatet.
- [**Oppdater**](#refresh-segments) segmentet slik at det inneholder de nyeste dataene.
- **Aktiver** eller **Deaktiver** segmentet. Inaktive segmenter blir ikke oppdatert under en [planlagt oppdatering](schedule-refresh.md) og har **Status** oppført som **Hoppet over**, som tyder på at en oppdatering ikke ble forsøkt. Aktive segmenter oppdateres basert på typen deres: statisk eller dynamisk.
- Angi **Gjør statisk** eller **Gjør dynamisk** for segmenttypen. Statiske segmenter må oppdateres manuelt. Dynamiske segmenter oppdateres automatisk under systemoppdateringer.
- [**Finn lignende kunder**](find-similar-customer-segments.md) fra segmentet.
- **Gi nytt navn** til segmentet.
- **Merke** for å [administrere merker](work-with-tags-columns.md#manage-tags) for segmentet.
- [**Behandle eksporter**](#export-segments) for å se eksportrelaterte segmenter og administrere dem. [Finn ut mer om eksporter.](export-destinations.md)
- **Slett** segmentet.
- **Kolonner** for å [tilpasse kolonnene](work-with-tags-columns.md#customize-columns) som vises.
- **Filtrer** for å [filtrere på merker](work-with-tags-columns.md#filter-on-tags).
- **Søkenavn** for søk etter segmentnavn.

## <a name="view-segment-details"></a>Vis segmentdetaljer

På **Segmenter**-siden velger du et segment for å vise behandlingsloggen og segmentmedlemmene.

Den øvre delen av siden inneholder et trendgraf som visualiserer endringer i medlemsantall. Beveg pekeren over datapunkter for å se medlemsantallet på en bestemt dato. Endre tidsrammen for visualiseringen.

:::image type="content" source="media/segment-time-range.png" alt-text="Tidsintervall for segment.":::

Den nedre delen inneholder en liste over medlemmene i segmentet.

> [!NOTE]
> Felt som vises i listen, er basert på attributtene til enhetene i segmentet.
>
>Listen er en forhåndsvisning av de samsvarende segmentmedlemmene og viser de første 100 oppføringene av segmentet, slik at du raskt kan evaluere det og se gjennom definisjonene hvis det er nødvendig. Hvis du vil vise alle samsvarende oppføringer, [eksporterer du segmentet](export-destinations.md).

## <a name="refresh-segments"></a>Oppdatere segmenter

Segmenter kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov. Hvis du vil oppdatere ett eller flere segmenter, velger du dem og velger **Oppdater**.

Hvis du vil [planlegge en automatisk oppdatering](schedule-refresh.md), går du til **Administrator** > **System** > **Plan**. Følgende regler gjelder:

- Alle segmenter av typen **Dynamisk** eller **Utvidelse** oppdateres automatisk med den angitte hyppigheten. Når oppdateringen er fullført, angir **Status** om det var problemer under oppdatering av segmentet. **Sist oppdaterte** viser et tidsstempel for den siste vellykkede oppdateringen. Hvis det oppstår en feil, velger du feilen for å vise detaljer om hva som har skjedd.
- Segmenter av typen **Statisk** *blir ikke* oppdatert automatisk. **Sist oppdatert** viser et tidsstempel for sist gang det statiske segmentet ble kjørt eller oppdatert manuelt.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Eksportere segmenter

Eksporter segmenter til andre apper for å bruke dataene videre. Eksporter et segment fra segmentsiden eller [eksportsiden](export-destinations.md).

1. Gå til **Segmenter**-siden og velg segmentet du vil eksportere.

1. Velg **Behandle eksporter**. Siden **Eksporter (forhåndsversjon) for segmentet** åpnes. Vis alle konfigurerte eksporter gruppert etter om de inneholder gjeldende segment eller ikke.

   1. Hvis du vil legge til det valgte segmentet i en eksport, **Rediger** den respektive eksporten for å velge det tilsvarende segmentet, og deretter lagrer du. I miljøer for enkeltkunder velger du eksporten fra listen og velger **Legg til segment** for å oppnå samme resultat.

   1. Hvis du vil opprette en ny eksport med det valgte segmentet, velger du **Legg til eksport**. Hvis du vil ha mer informasjon om hvordan du oppretter eksporter, kan du se [Konfigurere en ny eksport](export-destinations.md#set-up-a-new-export).

1. Velg **Tilbake** for å gå tilbake til hovedsiden for segmenter.

## <a name="track-usage-of-a-segment"></a>Spor bruk av et segment

Hvis du bruker segmenter i apper som er basert på den samme Microsoft Dataverse-organisasjonen som er koblet til Customer Insights, kan du spore bruken av et segment. For [Customer Insights-segmenter som brukes i kundereiser for Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) informerer systemet deg om bruken av dette segmentet.

Når du redigerer et segment som brukes i Customer Insights-miljøet eller i en kundereise i Marketing, informerer et banner i [segmentverktøyet](segment-builder.md) deg om avhengighetene. Inspiser avhengighetsdetaljene direkte fra banneret, eller velg **Bruk** i segmentverktøyet.

Ruten **Segmentbruk** viser detaljene om bruken av dette segmentet i Dataverse-baserte apper. For segmenter som brukes i kundereiser, finner du en kobling du kan bruke til å inspisere reisen i Marketing der dette segmentet brukes. Hvis du har tilgang til Marketing-appen, kan du vise flere detaljer der.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Sideruten med detaljer om segmentbruken i segmentverktøyet.":::

Systemet informerer deg om bruken av et sporet segment når du prøver å slette det. Hvis segmentet du er i ferd med å slette, brukes i en kundereise i Marketing, stoppes denne reisen for alle brukerne i segmentet. Hvis reisen er en del av en markedsføringskampanje, påvirker slettingen selve kampanjen. Du kan imidlertid fremdeles slette segmentet til tross for advarslene.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialogboksen for å bekrefte segmentsletting når et segment brukes i et Dataverse-program.":::

### <a name="supported-apps"></a>Støttede apper

Bruk spores for øyeblikket i følgende Dataverse-baserte apper:

- [Kundereiser i Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
