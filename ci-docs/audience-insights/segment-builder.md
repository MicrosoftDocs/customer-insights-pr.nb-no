---
title: Opprett segmenter med segmentverktøyet
description: Opprett segmenter av kunder for å gruppere dem basert på forskjellige attributter.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494514"
---
# <a name="create-segments"></a>Opprett segmenter

Definer komplekse filtre rundt enheten for enhetlig kunde og de relaterte enhetene. Hvert segment, etter behandlingen, oppretter et sett med kundeoppføringer som du kan eksportere og utføre handlinger på. Segmenter administreres på **Segmenter**-siden. Du kan [opprette nye segmenter](#create-a-new-segment) ved hjelp av [segmentverktøyet](#segment-builder) eller [opprette hurtigsegmenter](#quick-segments) fra andre områder av appen.

## <a name="segment-builder"></a>Segmentverktøy

Bildet nedenfor illustrerer de ulike sidene ved segmentverktøyet. Det viser et segment som resulterer i en kundegruppe. Kundene bestilte varer i en bestemt tidsramme og samlet inn et antall belønningspoeng eller brukte en bestemt sum penger. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementer i segmentverktøyet." lightbox="media/segment-builder-overview.png":::

1 – Ordne segmentet med regler og underregler. Hver regel eller underregel består av betingelser. Kombiner betingelsene med logiske operatorer

2 – Velg [relasjonsbanen](relationships.md) mellom enheter som gjelder en regel. Relasjonsbanen avgjør hvilke attributter som kan brukes i en betingelse.

3 – Administrer regler og underregler. Endre plasseringen av en regel eller slett den.

4 – Legg til betingelser og bygg riktig nestingsnivå ved hjelp av underregler.

5 – Bruk angitte operasjoner på tilkoblede regler.

6 – Bruk attributtruten til å legge til tilgjengelige enhetsattributter eller opprette betingelser basert på attributter. Ruten viser listen over enheter og attributter, basert på den valgte relasjonsbanen, som er tilgjengelige for den valgte regelen.

7 – Legg til betingelser basert på attributter i eksisterende regler og underregler, eller legg den til i en ny regel.

8 – Angre og gjør om endringer når du bygger segmentet.

Eksemplet ovenfor illustrerer segmenteringsfunksjonen. Vi har definert et segment for kunder som kjøpte varer for minst $ 500 på nettet *og* er interessert i programvareutvikling.

## <a name="create-a-new-segment"></a>Opprett et nytt segment

Du kan opprette et nytt segment på flere måter. Denne delen beskriver hvordan du bygger ditt eget segment fra bunnen av. Du kan også opprette et *hurtigsegment* basert på eksisterende enheter eller bruke maskinlæringsmodeller til å få *foreslåtte segmenter*. Mer informasjon: [Oversikt over segmenter](segments.md).

Når du oppretter et segment, kan du lagre et utkast. Det blir lagret som et inaktivt segment og kan ikke aktiveres slik at det blir fullført med en gyldig konfigurasjon.

1. Gå til siden **Segmenter**.

1. Velg **Ny** > **Bygg din egen**.

1. På siden for segmentverktøyet definerer du den første regelen. En regel består av en eller flere betingelser og definerer et sett med kunder.

1. I **Regel1**-delen velger du et attributt for en enhet du vil filtrere kunder etter. Du kan velge attributter på to ulike måter: 
   - Se gjennom listen over tilgjengelige enheter og attributter i ruten **Legg til i regel**, og velg ikonet **+** ved siden av attributtet du vil legge til. Velg om du vil legge til attributtet i en eksisterende regel eller bruke den til å opprette en ny regel.
   - Skriv inn navnet på attributtet i regeldelen for å vise samsvarende forslag.

1. Velg operatorene for å angi de samsvarende verdiene for betingelsen. Attributtet kan ha en av fire datatyper som verdi: numerisk, streng, dato eller boolsk. Avhengig av datatypen til attributtet, kan ulike operatorer angi betingelsen. 

1. Velg **Legg til betingelse** for å legge til flere betingelser i en regel. Hvis du vil opprette en regel under den gjeldende regelen, velger du **Legg til underregel**.

1. Hvis en regel bruker andre enheter enn enheten *Kunde*, må du angi relasjonsbanen. Relasjonsbanen er nødvendig for å informere systemet om hvilke relasjoner du vil skal ha tilgang til den enhetlige kundeenheten. Velg **Angi relasjonsbanen** for å tilordne valgt enhet til den enhetlige kundeenheten. Hvis det bare finnes én mulig relasjonsbane, velger systemet den automatisk. Forskjellige relasjonsbaner kan gi forskjellige resultater. Hver regel kan ha sin egen relasjonsbane.

   :::image type="content" source="media/relationship-path.png" alt-text="Mulig relasjonsbane ved oppretting av en regel basert på en enhet tilordnet til den enhetlige kundeenheten.":::

   Enheten *eCommerce_eCommercePurchases* i skjermbildet har fire alternativer for å tilordne til enheten *Kunde*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Kunde
   - eCommerce_eCommercePurchases > Kunde
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Kunde
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Kunde Når du velger det siste alternativet, kan vi ta med attributter fra alle enhetene som er oppført, i reglebetingelsene. Vi vil sannsynligvis få færre resultater fordi de samsvarende kundeoppføringene må være en del av alle enheter. I dette eksemplet må de ha kjøpt varer via e-handel(*eCommerce_eCommercePurchases*), på et salgssted (*POS_posPurchases*) og delta i fordelsprogrammet (*loyaltyScheme_loyCustomers*). Når du velger det andre alternativet, kan vi bare velge attributter fra *eCommerce_eCommercePurchases* og enheten *Kunde*. Dette fører sannsynligvis til flere resulterende kundeprofiler.

1. Hvis du har flere betingelser i en regel, kan du velge hvilken logisk operator som skal kobles til dem.

   - **OG**-operator: Alle betingelser må oppfylles for å inkludere en oppføring i segmentet. Dette alternativet er svært nyttig når du definerer betingelser på tvers av forskjellige enheter.

   - **ELLER**-operator: En av betingelsene må oppfylles for å inkludere en oppføring i segmentet. Dette alternativet er svært nyttig når du definerer flere betingelser for samme enhet.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel med to OG-betingelser.":::

   Når du bruker ELLER-operatoren, må alle betingelser være basert på enheter som er inkludert i relasjonsbanen.

   1. Du kan opprette flere regler for å opprette forskjellige sett med kundeoppføringer. Du kan kombinere grupper for å inkludere kundene som kreves for forretningssaken. Velg **Legg til regel** for å opprette en ny regel. Hvis du ikke kan inkludere en enhet i en regel på grunn av den angitte relasjonsbanen, må du opprette en ny regel for å velge attributter fra skjemaet.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Legg til en ny regel i et segment, og velg den angitte operatoren.":::

   1. Velg en av de angitte operatorer: **Union**, **Skjæringspunkt** eller **Unntatt**.

   - **Union** forener de to gruppene.

   - **Intersect** overlapper de to gruppene. Bare data som *er felles* for begge gruppene, beholdes i den enhetlige gruppen.

   - **Bortsett fra** kombinerer de to gruppene. Bare data i gruppe A som *ikke er felles* med data i gruppe B, beholdes.

1. Som standard genererer segmenter utdataenheten som inneholder alle attributtene, til kundeprofiler som samsvarer med de definerte filtrene. Hvis et segment er basert på andre enheter enn *Kunde*-enheten, kan du legge til flere attributter fra disse enhetene i utdataenheten. Velg **Prosjektattributter** for å velge attributtene som skal legges til i utdataenheten.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Eksempel på beregnede attributter som er valgt i sideruten, som skal legges til i utdataenheten.":::
  
   Eksempel: Et segment er basert på en enhet som inneholder kjøpsdata, som er relatert til enheten *Kunde*. Segmentet ser etter alle kunder fra Spania som kjøpte varer i inneværende år. Du kan velge å føye til attributter som prisen på varene, eller innkjøpsdatoen i alle samsvarende kundeoppføringer i utdataenheten. Denne informasjonen kan være nyttig for å analysere årstidskorrelasjoner med de totale kostnadene.

   > [!NOTE]
   > - Beregnede attributter fungerer bare for enheter som har en én-til-mange-relasjon med kundeenheten. Én kunde kan for eksempel ha flere abonnementer.
   > - Du kan bare projisere attributter fra en enhet som brukes i hver regel for segmentspørring du bygger.
   > - Beregnede attributter beregner ved bruk av angitte operatorer.

1. Før du lagrer og kjører segmentet, velger du **Rediger detaljer** ved siden av segmentnavnet. Angi et navn for segmentet, og oppdater det foreslåtte **utdataentitetsnavnet** for segmentet. Du kan også legge til en beskrivelse i segmentet.

1. Velg **Kjør** for å lagre og behandle segmentet hvis alle krav er validert. Hvis ikke blir det lagret som et inaktivt segmentutkast.

1. Velg **Tilbake til Segmenter** for å gå tilbake til **Segmenter**-siden.

> [!TIP]
> - Segmentverktøyet foreslår ikke gyldige verdier fra enheter når du angir operatorene for betingelsene. Du kan gå til **Data** > **Enheter** og laste ned enhetsdataene for å se hvilke verdier som er tilgjengelige.
> - Betingelser basert på datoene gjør det enkelt å veksle mellom faste datoer og et flytende datointervall.
> - Hvis du har flere regler for segmentet, finner du en blå linje rundt regelen du redigerer.
> - Du kan flytte regler og betingelser til andre steder i segmentdefinisjonen. Velg [...] ved siden av en regel eller betingelse, og velg hvordan og hvor den skal flyttes.
> - Med kontrollene **Angre** og **Gjør om** på kommandolinjen kan du rulle tilbake endringer.

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

    > [!div class="mx-imgBorder"]
    > ![Navn og beregning for et hurtigsegment.](media/quick-segment-name.png "Navn og beregning for et hurtigsegment")

5. Angi et **Navn** for segmentet. Alternativt kan du angi et **Visningsnavn**.

6. Velg **Lagre** for å opprette segmentet.

7. Når segmentet er ferdig behandlet, kan du vise det på samme måte som et hvilket som helst segment du har opprettet.

## <a name="next-steps"></a>Neste trinn

[Eksporter et segment](export-destinations.md), og utforsk [kundekortintegreringen](customer-card-add-in.md) for å bruke segmenter i andre programmer.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
