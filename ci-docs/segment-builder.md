---
title: Opprett komplekse segmenter med segmentverktøyet
description: Bruk segmentverktøyet til å opprette komplekse kundesegmenter ved å gruppere dem basert på ulike attributter.
ms.date: 08/12/2022
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
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304761"
---
# <a name="create-complex-segments-with-segment-builder"></a>Opprett komplekse segmenter med segmentverktøyet

Definer komplekse filtre rundt enheten for enhetlig kunde eller enhetlig kontakt de relaterte enhetene. Hvert segment, etter at behandlingen er behandlet, oppretter et sett med kunde- eller kontaktoppføringer som du kan eksportere og utføre handlinger på.

> [!TIP]
> Segmenter basert på **individuelle kunder** inkluderer automatisk tilgjengelig kontaktinformasjon for segmentmedlemmer. Hvis du [samlet](data-unification.md) både forretningsforbindelser og kontakter i **forretningskontoer**, velger du om segmentet er basert på forretningsforbindelser eller forretningskontakter. Hvis du vil eksportere til et mål som forventer kontaktinformasjon, bruker du et segment med kontakter. Hvis du vil eksportere til et mål som forventer forretningsforbindelsesinformasjon, bruker du et segment med forretningsforbindelser.

## <a name="segment-builder"></a>Segmentverktøy

Bildet nedenfor illustrerer de ulike sidene ved segmentverktøyet. Det viser et segment som resulterer i en kundegruppe. Kundene bestilte varer i en bestemt tidsramme og samlet inn belønningspoeng eller brukte en bestemt sum penger.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementer i segmentverktøyet." lightbox="media/segment-builder-overview.png":::

1. Ordne segmentet med regler og underregler. Hver regel eller underregel består av betingelser. Kombiner betingelsene med logiske operatorer.

1. Velg [relasjonsbanen](relationships.md) mellom enheter som gjelder en regel. Relasjonsbanen avgjør hvilke attributter som kan brukes i en betingelse.

1. Administrer regler og underregler. Endre plasseringen av en regel eller slett den.

1. Legg til betingelser og bygg riktig nestingsnivå ved hjelp av underregler.

1. Bruk angitte operasjoner på tilkoblede regler.

1. Bruk attributtruten til å legge til tilgjengelige enhetsattributter eller opprette betingelser basert på attributter. Ruten viser listen over enheter og attributter, basert på den valgte relasjonsbanen, som er tilgjengelige for den valgte regelen.

1. Legg til betingelser basert på attributter i eksisterende regler og underregler, eller legg den til i en ny regel.

1. Angre og gjør om endringer når du bygger segmentet.

Eksemplet ovenfor illustrerer segmenteringsfunksjonen. Vi har definert et segment for kunder som kjøpte varer for minst $ 500 på nettet *og* er interessert i programvareutvikling.

## <a name="create-a-new-segment-with-segment-builder"></a>Opprett et nytt segment med segmentverktøyet

1. Gå til **Segmenter**.

1. Velg **Ny** > **Bygg din egen**. På siden for segmentverktøyet definerer eller skriver du regler. En regel består av ett eller flere betingelser som definerer et sett kunder.

   > [!NOTE]
   > For miljøer basert på forretningskontoer velger du **Nytt** > **Segment for forretningsforbindelser** eller **Segment for kontakter (forhåndsversjon)** basert på typen segment du vil opprette. Hvis et [forretningsforbindelseshierarki](relationships.md#set-up-account-hierarchies) er definert og du vil opprette regler for å filtrere ut data basert på relasjon mellom underordnet og overordnet, velger du **Vil du bruke hierarki? (forhåndsversjon)**, velger hierarkiet og deretter **Bruk**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Ruten Velg forretningsforbindelseshierarki for segment.":::

1. Velg **Rediger detaljer** ved siden av Segment uten tittel. Angi et navn for segmentet, og oppdater det foreslåtte **utdataentitetsnavnet** for segmentet. Du kan eventuelt legge til en beskrivelse og [merker](work-with-tags-columns.md#manage-tags) i segmentet.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialogboksen Rediger detaljer.":::

1. I **Regel1**-delen velger du et attributt for en enhet du vil filtrere kunder etter. Du kan velge attributter på to ulike måter:
   - Se gjennom listen over tilgjengelige enheter og attributter i ruten **Legg til i regel**, og velg ikonet **+** ved siden av attributtet du vil legge til. Velg om du vil legge til attributtet i en eksisterende regel eller bruke den til å opprette en ny regel.
   - Skriv inn navnet på attributtet i regeldelen for å vise samsvarende forslag.

1. Velg operatorene for å angi de samsvarende verdiene for betingelsen. Attributtet kan ha en av fire datatyper som verdi: numerisk, streng, dato eller boolsk. Avhengig av datatypen til attributtet, kan ulike operatorer angi betingelsen.

1. Velg **Legg til betingelse** for å legge til flere betingelser i en regel. Hvis du vil opprette en regel under den gjeldende regelen, velger du **Legg til underregel**.

1. Hvis en regel bruker andre enheter enn *Kunde*-enheten (eller *ContactProfile*-enheten for B2B), velger du **Angi relasjonsbane** for å tilordne den valgte enheten til enheten for enhetlig kunde. Hvis det bare finnes én mulig relasjonsbane, velger systemet den automatisk. Ulike [relasjonsbaner](relationships.md#relationship-paths) kan gi forskjellige resultater. Hver regel kan ha sin egen relasjonsbane.

   :::image type="content" source="media/relationship-path.png" alt-text="Mulig relasjonsbane ved oppretting av en regel basert på en enhet tilordnet til den enhetlige kundeenheten.":::

1. Hvis du har flere betingelser i en regel, velger du hvilken logisk operator som skal kobles til dem.  
   - **OG**-operator: Alle betingelser må oppfylles for å inkludere en oppføring i segmentet. Bruk dette alternativet når du definerer betingelser på tvers av forskjellige enheter.
   - **ELLER**-operator: En av betingelsene må oppfylles for å inkludere en oppføring i segmentet. Bruk dette alternativet når du definerer flere betingelser for samme enhet.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel med to OG-betingelser.":::

   Når du bruker ELLER-operatoren, må alle betingelser være basert på enheter som er inkludert i relasjonsbanen.

1. Opprett flere regler hvis du vil opprette ulike sett med kundeoppføringer. Kombiner grupper for å ta med kunder som kreves for forretningssaken. Hvis du ikke kan ta med en enhet i en regel på grunn av den angitte relasjonsbanen, oppretter du en ny regel for å velge attributter fra den.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Legg til en ny regel i et segment, og velg den angitte operatoren.":::

   1. Velg **Legg til regel**.
   1. Velg en av de angitte operatorer: **Union**, **Skjæringspunkt** eller **Unntatt**.

      - **Union** forener de to gruppene.
      - **Intersect** overlapper de to gruppene. Bare data som *er felles* for begge gruppene, forblir i den enhetlige gruppen.
      - **Bortsett fra** kombinerer de to gruppene. Bare data i gruppe A som *ikke er felles* for data i gruppe B, beholdes.

1. Utdataenheten inneholder som standard automatisk alle attributtene for kundeprofiler som samsvarer med de definerte filtrene. Når du bruker *ContactProfile*-enheten i B2B, inkluderes forretningsforbindelses-ID-en automatisk. Hvis et segment er basert på andre enheter enn *Kunde*-enheten, eller hvis du vil inkludere flere attributter fra *ContactProfile*, velger du **Prosjektattributter** for å legge til flere attributter fra disse enhetene i utdataenheten.
 
   Eksempel: Et segment er basert på en enhet som inneholder innkjøpsdata, som er relatert til *Kunde*-enheten. Segmentet ser etter alle kunder fra Spania som kjøpte varer i inneværende år. Du kan velge å føye til attributter som prisen på varer, eller innkjøpsdatoen i alle samsvarende kundeoppføringer i utdataenheten. Denne informasjonen kan være nyttig for å analysere årstidskorrelasjoner med de totale kostnadene.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Eksempel på beregnede attributter som er valgt i sideruten, som skal legges til i utdataenheten.":::
 
   Et eksempel på utdata for et segment basert på forretningskontoer med beregnede attributter for kontakter, kan se slik ut:

   |ID  |Kontonavn  |Omsetning  |Kontaktnavn  | Kontaktrolle|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100 000 | [Abbie Moss, Ruth Soto]  | [CEO, prosjektbehandling]

   > [!NOTE]
   > - **Anslå attributter** fungerer bare for enheter som har en én-til-mange-relasjon til *Kunde*- eller *ContactProfile*-enheten. Én kunde kan for eksempel ha flere abonnementer.
   > - Hvis attributtet du vil anslå, er mer enn én stasjon borte fra *Kunde* eller *ContactProfile*-enheten, som definert av relasjonen, må dette attributtet brukes i hver regel i segmentspørringen du bygger.
   > - Hvis attributtet du vil anslå, bare er én stasjon borte fra *Kunde*- eller *ContactProfile*-enheten, må ikke dette attributtet finnes i hver regel i segmentspørringen du bygger.
   > - **Beregnede attributter** beregner ved bruk av angitte operatorer.

1. Velg **Kjør** for å opprette segmentet. Velg **Lagre** hvis du vil beholde gjeldende konfigurasjon og kjøre segmentet senere. **Segmenter**-siden vises.

### <a name="segment-builder-tips"></a>Tips om segmentverktøyet

Husk følgende tips når du oppretter et segment ved hjelp av segmentverktøyet:

- Segmentverktøyet foreslår ikke gyldige verdier fra enheter når du angir operatorene for betingelsene. Du kan gå til **Data** > **Enheter** og laste ned enhetsdataene for å se hvilke verdier som er tilgjengelige.
- Betingelser basert på datoer gjør det enkelt å veksle mellom faste datoer og et flytende datointervall.
- Hvis du har flere regler for segmentet, har regelen du redigerer, en loddrett blå linje ved siden av seg.
- Du kan flytte regler og betingelser til andre steder i segmentdefinisjonen. Velg den loddrette ellipsen (&vellip;) ved siden av en regel eller betingelse, og velg hvordan og hvor den skal flyttes.
- Med **Angre** og **Gjør om**-kontrollene på kommandolinjen kan du rulle tilbake endringer.
- Når du har opprettet et segment , kan du [spore bruken av segmentet](segments.md#track-usage-of-a-segment) i noen segmenter.

## <a name="next-steps"></a>Neste trinn

[Eksporter et segment](export-destinations.md), og utforsk [kundekortintegreringen](customer-card-add-in.md) for å bruke segmenter i andre programmer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
