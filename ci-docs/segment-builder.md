---
title: Opprett segmenter med segmentverktøyet
description: Opprett segmenter av kunder for å gruppere dem basert på forskjellige attributter.
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
ms.openlocfilehash: c8e9e4976ade36c1c3c4f688a667b329bfde6e3e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647077"
---
# <a name="create-segments"></a>Opprett segmenter

Definer komplekse filtre rundt enheten for enhetlig kunde og de relaterte enhetene. Hvert segment, etter behandlingen, oppretter et sett med kundeoppføringer som du kan eksportere og utføre handlinger på. Segmenter administreres på **Segmenter**-siden. Du kan [opprette nye segmenter](#create-a-new-segment) ved hjelp av segmentverktøyet eller [opprette hurtigsegmenter](#quick-segments) fra andre områder av appen.

> [!TIP]
> - Hurtigsegmenter støttes bare i miljøer for **enkeltkunder**.
> - Segmenter basert på **individuelle kunder** inkluderer automatisk tilgjengelig kontaktinformasjon for segmentmedlemmer. I miljøer for **forretningsforbindelser** er segmenter basert på forretningsforbindelser (selskaper eller datterselskaper). Hvis du vil inkludere kontaktinformasjon i et segment, bruker du funksjonen **Prosjektattributter** i segmentverktøyet. Kontroller at kontaktdataene er [tilordnet semantisk til ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping)-enheten.

## <a name="segment-builder"></a>Segmentverktøy

Bildet nedenfor illustrerer de ulike sidene ved segmentverktøyet. Det viser et segment som resulterer i en kundegruppe. Kundene bestilte varer i en bestemt tidsramme og samlet inn belønningspoeng eller brukte en bestemt sum penger.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementer i segmentverktøyet." lightbox="media/segment-builder-overview.png":::

1. Ordne segmentet med regler og underregler. Hver regel eller underregel består av betingelser. Kombiner betingelsene med logiske operatorer

1. Velg [relasjonsbanen](relationships.md) mellom enheter som gjelder en regel. Relasjonsbanen avgjør hvilke attributter som kan brukes i en betingelse.

1. Administrer regler og underregler. Endre plasseringen av en regel eller slett den.

1. Legg til betingelser og bygg riktig nestingsnivå ved hjelp av underregler.

1. Bruk angitte operasjoner på tilkoblede regler.

1. Bruk attributtruten til å legge til tilgjengelige enhetsattributter eller opprette betingelser basert på attributter. Ruten viser listen over enheter og attributter, basert på den valgte relasjonsbanen, som er tilgjengelige for den valgte regelen.

1. Legg til betingelser basert på attributter i eksisterende regler og underregler, eller legg den til i en ny regel.

1. Angre og gjør om endringer når du bygger segmentet.

Eksemplet ovenfor illustrerer segmenteringsfunksjonen. Vi har definert et segment for kunder som kjøpte varer for minst $ 500 på nettet *og* er interessert i programvareutvikling.

## <a name="create-a-new-segment"></a>Opprett et nytt segment

Du kan opprette et nytt segment på flere måter. Denne delen beskriver hvordan du bygger ditt eget segment fra bunnen av. Du kan også opprette et *hurtigsegment* basert på eksisterende enheter eller bruke maskinlæringsmodeller til å få *foreslåtte segmenter*. Hvis du vil ha mer informasjon, kan du gå til [Segmentoversikt](segments.md).

Når du oppretter et segment, kan du lagre et utkast. I fasen utkast lagres et segment som et inaktivt segment. Når du fullfører segmentkonfigurasjonen, kjører du den for å aktivere segmentet. Du kan også **Aktivere** et segment fra siden **Alle segmenter**.

1. Gå til siden **Segmenter**.

1. Velg **Ny** > **Bygg din egen**.

1. På siden for segmentverktøyet definerer eller skriver du regler. En regel består av ett eller flere betingelser som definerer et sett kunder.

1. I **Regel1**-delen velger du et attributt for en enhet du vil filtrere kunder etter. Du kan velge attributter på to ulike måter:
   - Se gjennom listen over tilgjengelige enheter og attributter i ruten **Legg til i regel**, og velg ikonet **+** ved siden av attributtet du vil legge til. Velg om du vil legge til attributtet i en eksisterende regel eller bruke den til å opprette en ny regel.
   - Skriv inn navnet på attributtet i regeldelen for å vise samsvarende forslag.

1. Velg operatorene for å angi de samsvarende verdiene for betingelsen. Attributtet kan ha en av fire datatyper som verdi: numerisk, streng, dato eller boolsk. Avhengig av datatypen til attributtet, kan ulike operatorer angi betingelsen. For segmenter med forretningskontoer er to spesielle operatorer tilgjengelige for å inkludere potensielle hierarkier mellom de integrerte forretningsforbindelsene. Bruk *underordnet av*- og *overordnet for*-operatoren til å inkludere relaterte forretningsforbindelser.

1. Velg **Legg til betingelse** for å legge til flere betingelser i en regel. Hvis du vil opprette en regel under den gjeldende regelen, velger du **Legg til underregel**.

1. Hvis en regel bruker andre enheter enn enheten *Kunde*, må du angi relasjonsbanen. Relasjonsbanen er nødvendig for å informere systemet om hvilke relasjoner du vil skal ha tilgang til den enhetlige kundeenheten. Velg **Angi relasjonsbanen** for å tilordne valgt enhet til den enhetlige kundeenheten. Hvis det bare finnes én mulig relasjonsbane, velger systemet den automatisk. Forskjellige relasjonsbaner kan gi forskjellige resultater. Hver regel kan ha sin egen relasjonsbane.

   :::image type="content" source="media/relationship-path.png" alt-text="Mulig relasjonsbane ved oppretting av en regel basert på en enhet tilordnet til den enhetlige kundeenheten.":::

   Enheten *eCommerce_eCommercePurchases* i skjermbildet har fire alternativer for å tilordne til enheten *Kunde*:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Kunde
   - eCommerce_eCommercePurchases > Kunde
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Kunde
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Kunde Når du velger det siste alternativet, kan vi ta med attributter fra alle enhetene som er oppført, i reglebetingelsene. Vi får sannsynligvis færre resultater fordi de samsvarende kundeoppføringene må være en del av alle enheter. I dette eksemplet må de ha kjøpt varer via e-handel(*eCommerce_eCommercePurchases*) på et salgssted (*POS_posPurchases*) og delta i fordelsprogrammet (*loyaltyScheme_loyCustomers*). Når du velger det andre alternativet, kan vi bare velge attributter fra *eCommerce_eCommercePurchases* og enheten *Kunde*. Dette fører sannsynligvis til flere resulterende kundeprofiler.

1. Hvis du har flere betingelser i en regel, kan du velge hvilken logisk operator som skal kobles til dem.  
   - **OG**-operator: Alle betingelser må oppfylles for å inkludere en oppføring i segmentet. Dette alternativet er svært nyttig når du definerer betingelser på tvers av forskjellige enheter.
   - **ELLER**-operator: En av betingelsene må oppfylles for å inkludere en oppføring i segmentet. Dette alternativet er svært nyttig når du definerer flere betingelser for samme enhet.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel med to OG-betingelser.":::

   Når du bruker ELLER-operatoren, må alle betingelser være basert på enheter som er inkludert i relasjonsbanen.

   - Du kan opprette flere regler for å opprette forskjellige sett med kundeoppføringer. Du kan kombinere grupper for å inkludere kundene som kreves for forretningssaken. Velg **Legg til regel** for å opprette en ny regel. Hvis du ikke kan inkludere en enhet i en regel på grunn av den angitte relasjonsbanen, må du opprette en ny regel for å velge attributter fra skjemaet.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Legg til en ny regel i et segment, og velg den angitte operatoren.":::

   - Velg en av de angitte operatorer: **Union**, **Skjæringspunkt** eller **Unntatt**.

      - **Union** forener de to gruppene.
      - **Intersect** overlapper de to gruppene. Bare data som *er felles* for begge gruppene, forblir i den enhetlige gruppen.
      - **Bortsett fra** kombinerer de to gruppene. Bare data i gruppe A som *ikke er felles* for data i gruppe B, beholdes.

1. Som standard genererer segmenter utdataenheten som inneholder alle attributtene, til kundeprofiler som samsvarer med de definerte filtrene. Hvis et segment er basert på andre enheter enn *Kunde*-enheten, kan du legge til flere attributter fra disse enhetene i utdataenheten. Velg **Prosjektattributter** for å velge attributtene som skal legges til i utdataenheten.

   > [!IMPORTANT]
   > For segmenter som er basert på forretningsforbindelser, må detaljer om én eller flere kontakter for hver konto fra enheten *ContactProfile* inkluderes i segmentet for å tillate at dette segmentet aktiveres eller eksporteres til mål som krever kontaktinformasjon. Hvis du vil ha mer informasjon om *ContactProfile*-enheten, kan du se [Semantiske tilordninger](semantic-mappings.md).
   > Et eksempel på utdata for et segment basert på forretningskontoer med beregnede attributter for kontakter, kan se slik ut:
   >
   > |ID  |Kontonavn  |Omsetning  |Kontaktnavn  | Kontaktrolle|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 000 | [Abbie Moss, Ruth Soto]  | [CEO, prosjektbehandling]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Eksempel på beregnede attributter som er valgt i sideruten, som skal legges til i utdataenheten.":::
  
   Eksempel: Et segment er basert på en enhet som inneholder innkjøpsdata, som er relatert til *Kunde*-enheten. Segmentet ser etter alle kunder fra Spania som kjøpte varer i inneværende år. Du kan velge å føye til attributter som prisen på varene, eller innkjøpsdatoen i alle samsvarende kundeoppføringer i utdataenheten. Denne informasjonen kan være nyttig for å analysere årstidskorrelasjoner med de totale kostnadene.

   > [!NOTE]
   > - **Prosjektattributter** fungerer bare for enheter som har en én-til-mange-relasjon med kundeenheten. Én kunde kan for eksempel ha flere abonnementer.
   > - Hvis attributtet du vil prosjektere, er mer enn én stasjon borte fra *Kunde*-enheten, som definert av relasjonen, må dette attributtet brukes i hver regel i segmentspørringen du bygger.
   > - Hvis attributtet du vil prosjektere, bare er én stasjon borte fra *Kunde*-enheten, må ikke dette attributtet finnes i hver regel i segmentspørringen du bygger.
   > - **Beregnede attributter** beregner ved bruk av angitte operatorer.

1. Velg **Rediger detaljer** ved siden av Segment uten tittel. Angi et navn for segmentet, og oppdater det foreslåtte **utdataentitetsnavnet** for segmentet. Du kan eventuelt legge til en beskrivelse og [merker](work-with-tags-columns.md#manage-tags) i segmentet.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialogboksen Rediger detaljer.":::

1. Velg **Kjør** for å lagre segmentet, aktiver det, og begynn å behandle segmentet basert på alle regler og betingelser. Ellers lagres det som et inaktivt segment.

1. Velg **Tilbake til Segmenter** for å gå tilbake til **Segmenter**-siden.

1. Som standard opprettes segmentet som et dynamisk segment. Det betyr at segmentet oppdateres under systemoppdateringer. Hvis du vil [stoppe den automatiske oppdateringen](segments.md#manage-existing-segments), velger du segmentet og velger alternativet **Gjør statisk**. Statiske segmenter kan [oppdateres manuelt](segments.md#refresh-segments) når som helst.

> [!TIP]
> - Segmentverktøyet foreslår ikke gyldige verdier fra enheter når du angir operatorene for betingelsene. Du kan gå til **Data** > **Enheter** og laste ned enhetsdataene for å se hvilke verdier som er tilgjengelige.
> - Betingelser basert på datoene gjør det enkelt å veksle mellom faste datoer og et flytende datointervall.
> - Hvis du har flere regler for segmentet, har regelen du redigerer, en loddrett blå linje ved siden av seg.
> - Du kan flytte regler og betingelser til andre steder i segmentdefinisjonen. Velg [...] ved siden av en regel eller betingelse, og velg hvordan og hvor den skal flyttes.
> - Med **Angre** og **Gjør om**-kontrollene på kommandolinjen kan du rulle tilbake endringer.

## <a name="quick-segments"></a>Hurtigsegmenter

Med hurtigsegmenter kan du bygge enkle segmenter med én operator raskt for raskere innsikt.

1. Velg **Ny** > **Opprett fra** på siden **Segment**.
   - Velg alternativet **Profiler** for å bygge et segment som er basert på den *enhetlige kundeenheten*.
   - Velg **Mål**-alternativet for å bygge et segment rundt mål du tidligere har opprettet.
   - Velg alternativet **Intelligens** for å bygge et segment rundt én av de utgående enhetene du genererte ved hjelp av funksjonene **Prediksjoner** eller **Egendefinerte modeller**.

2. I dialogboksen **Nytt hurtigsegment** velger du et attributt fra **Felt**-rullegardinlisten.

3. Systemet gir deg mer innsikt som hjelper deg med å opprette bedre segmenter av kundene.
   - Vi viser de 10 største kundeantallene for kategoriske felt. Velg en **Verdi** og deretter **Gå gjennom**.
   - For et numerisk attributt vil systemet vise hvilken attributtverdi som faller under hver kundepersentil. Velg en **Operator** og en **Verdi**, og velg deretter **Gå gjennom**.

4. Systemet gir deg en **Beregnet segmentstørrelse**. Du kan velge om du vil generere segmentet du har definert, eller først gå til det igjen for å få en annen segmentstørrelse.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Navn og beregning for et hurtigsegment.":::

5. Angi et **navn** og **utdataenhetsnavn** for segmentet. Du kan eventuelt legge til [merker](work-with-tags-columns.md#manage-tags).

6. Velg **Lagre** for å opprette segmentet.

7. Når segmentet er ferdig behandlet, kan du vise det på samme måte som et hvilket som helst segment du har opprettet.

## <a name="next-steps"></a>Neste trinn

[Eksporter et segment](export-destinations.md), og utforsk [kundekortintegreringen](customer-card-add-in.md) for å bruke segmenter i andre programmer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
