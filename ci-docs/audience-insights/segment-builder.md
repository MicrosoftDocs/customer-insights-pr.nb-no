---
title: Opprette og behandle segmenter
description: Opprett segmenter av kunder for å gruppere dem basert på forskjellige attributter.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a19661abea42618ef1848110c05d635a925c68f
ms.sourcegitcommit: c45b094072cbe3fbf61d1e9e7d220e1f29ffebd0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/29/2021
ms.locfileid: "6685474"
---
# <a name="create-and-manage-segments"></a>Opprette og behandle segmenter

> [!IMPORTANT]
> Det er flere endringer som rulles ut til segmentopprettingsopplevelsen i september 2021: 
> - Segmentbyggeren vil se litt annerledes ut med nye elementer og en forbedret brukerflyt.
> - Nye datetime-operatorer og en forbedret datovelger aktiveres i segmentbyggeren.
> - Du kan legge til eller fjerne betingelser og regler fra segmenter. 
> - Nestede regler som starter med en OR-betingelse, blir tilgjengelige. Du trenger ikke lenger en AND-betingelse på det ytterste laget.
> - En siderute for å velge attributter vil være tilgjengelig hele tiden.
> - Et alternativ for å velge enhetsrelasjonsbaner.
> For å prøve den nye segmentbyggeren må du send en e-post med emnet Be om å aktivere den nye segmentbyggeren til å cihelp [at] microsoft.com. Inkluder navnet på organisasjonen og ID-en til sandkassemiljøet.

Definer komplekse filtre rundt enheten for enhetlig kunde og de relaterte enhetene. Hvert segment, etter behandlingen, oppretter et sett med kundeoppføringer som du kan eksportere og utføre handlinger på. Segmenter administreres på **Segmenter**-siden. 

Eksemplet nedenfor viser bruken av segmenteringsfunksjonaliteten. Vi har definert et segment for kunder som har bestilt varer for minst USD 500 i løpet av de siste 90 dagene *og* som var involvert i en kundeservicesamtale som ble videresendt.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Skjermbilde av grensesnittet for segmentverktøyet med to grupper som angir et kundesegment.":::

## <a name="create-a-new-segment"></a>Opprett et nytt segment

Du kan opprette et nytt segment på flere måter. Denne delen beskriver hvordan du oppretter et *tomt segment* fra bunnen av. Du kan også opprette et *hurtigsegment* basert på eksisterende enheter eller bruke maskinlæringsmodeller til å få *foreslåtte segmenter*. Mer informasjon: [Oversikt over segmenter](segments.md).

Når du oppretter et segment, kan du lagre et utkast. Det blir lagret som et inaktivt segment og kan ikke aktiveres slik at det blir fullført med en gyldig konfigurasjon.

1. Gå til siden **Segmenter**.

1. Velg **Ny** > **Tomt segment**.

1. Velg en segmenttype i ruten **Ny segment**:

   - **Dynamiske segmenter** [oppdateres](segments.md#refresh-segments) i en regelmessig tidsplan.
   - **Statiske segmenter** kjører én gang når du oppretter den.

1. Angi et **navn på utdataenheten** for segmentet. Du kan eventuelt angi et visningsnavn og en beskrivelse som hjelper deg med å identifisere segmentet.

1. Velg **Neste** for å gå til siden for **Segmentverktøy**, der du definerer en gruppe. En gruppe er et sett med kunder.

1. Velg enheten som inkluderer attributtet du vil segmentere etter.

1. Velg attributtet du vil segmentere etter. Dette attributtet kan ha en av fire verdityper: numerisk, streng, dato eller boolsk.

1. Velg en operator og en verdi for det valgte attributtet.

   > [!div class="mx-imgBorder"]
   > ![Egendefinert gruppefilter.](media/customer-group-numbers.png "Gruppefilter for kunde")

   |Antall |Definisjon  |
   |---------|---------|
   |1     |Entity          |
   |2     |Attributt          |
   |3    |Operatør         |
   |4    |Verdi         |

   1. Hvis du vil legge til flere betingelser i en gruppe, kan du bruke to logiske operatorer:

      - **AND**-operator: Begge betingelser må oppfylles som en del av segmentprosessen. Dette alternativet er svært nyttig når du definerer betingelser på tvers av forskjellige enheter.

      - **OR**-operator: En av betingelsene må oppfylles som en del av segmenteringsprosessen. Dette alternativet er svært nyttig når du definerer flere betingelser for samme enhet.

      > [!div class="mx-imgBorder"]
      > ![OR-operator der begge betingelser må oppfylles.](media/segmentation-either-condition.png "OR-operator der begge betingelser må oppfylles")

      Det er for øyeblikket mulig å neste en **OR**-operator under en **AND**-operator, men ikke motsatt.

   1. Hver gruppe samsvarer til et sett med kunder. Du kan kombinere grupper for å inkludere kundene som kreves for forretningssaken.    
   Velg **Legg til gruppe**.

      > [!div class="mx-imgBorder"]
      > ![Legg til gruppe i kundegruppe.](media/customer-group-add-group.png "Legg til gruppe i kundegruppe")

   1. Velg en av de angitte operatorer: **Union**, **Skjæringspunkt** eller **Unntatt**.

   > [!div class="mx-imgBorder"]
   > ![Legg til union i kundegruppe.](media/customer-group-union.png "Legg til union i kundegruppe")

   - **Union** forener de to gruppene.

   - **Intersect** overlapper de to gruppene. Bare data som *er felles* for begge gruppene, beholdes i den enhetlige gruppen.

   - **Bortsett fra** kombinerer de to gruppene. Bare data i gruppe A som *ikke er felles* med data i gruppe B, beholdes.

1. Hvis enheten er koblet til den enhetlige kundeenheten via [relasjoner](relationships.md), må du definere relasjonsbanen for å opprette et gyldig segment. Legg til enhetene fra relasjonsbanen til du kan velge **Kunde: CustomerInsights**-enheten fra rullegardinlisten. Deretter velger du **Alle oppføringer** for hvert trinn.

   > [!div class="mx-imgBorder"]
   > ![Relasjonsbane under opprettelse av segment.](media/segments-multiple-relationships.png "Relasjonsbane under opprettelse av segment")

1. Som standard genererer segmenter en utdataenhet som inneholder alle attributter for kundeprofiler som samsvarer med de definerte filtrene. Hvis et segment er basert på andre enheter enn *Kunde*-enheten, kan du legge til flere attributter fra disse enhetene i utdataenheten. Velg **Prosjektattributter** for å velge attributtene som skal legges til i utdataenheten.  
  
   Eksempel: Et segment er basert på en enhet som inneholder kundeaktivitetsdata som er relatert til *Kunde*-enheten. Segmentet ser etter alle kunder som har ringt til brukerstøtteavdelingen i løpet av de siste 60 dagene. Du kan velge å tilføye samtalevarighet og antall samtaler til alle samsvarende kundeoppføringer i utdataenheten. Denne informasjonen kan være nyttig for å sende en e-post med nyttige koblinger til artikler i elektronisk hjelp og vanlige spørsmål til kunder som ofte har ringt.

   > [!NOTE]
   > - Beregnede attributter fungerer bare for enheter som har en én-til-mange-relasjon med kundeenheten. Én kunde kan for eksempel ha flere abonnementer.
   > - Du kan bare prosjektere attributter fra en enhet som brukes i hver gruppe med segmentspørringer du bygger.
   > - Beregnede attributter beregner ved bruk av angitte operatorer.

1. Velg **Lagre** for å lagre segmentet. Segmentet blir lagret og behandlet hvis alle kravene valideres. Hvis ikke blir det lagret som et utkast.

1. Velg **Tilbake til Segmenter** for å gå tilbake til **Segmenter**-siden.



## <a name="quick-segments"></a>Hurtigsegmenter

Med hurtigsegmenter kan du bygge enkle segmenter med én operator raskt for raskere innsikt.

1. Velg **Ny** > **Opprett fra** på siden **Segment**.

   - Velg alternativet **Profiler** for å bygge et segment som er basert på den *enhetlige kundeenheten*.
   - Velg **Mål**-alternativet for å bygge et segment rundt mål du tidligere har opprettet.
   - Velg alternativet **Intelligens** for å bygge et segment rundt én av de utgående enhetene du genererte ved hjelp av funksjonene **Prediksjoner** eller **Egendefinerte modeller**.

2. I dialogboksen **Nytt hurtigsegment** velger du et attributt fra **Felt**-rullegardinlisten.

3. Systemet gir noe ekstra innsikt som hjelper deg med å lage bedre segmenter av kundene.
   - Vi viser de 10 største kundeantallene for kategoriske felt. Velg en **Verdi** og deretter **Gå gjennom**.

   - For et numerisk attributt vil systemet vise hvilken attributtverdi som faller under hver kundepersentil. Velg en **Operator** og en **Verdi**, og velg deretter **Gå gjennom**.

4. Systemet gir deg en **Beregnet segmentstørrelse**. Du kan velge om du vil generere segmentet du har definert, eller først gå til det igjen for å få en annen segmentstørrelse.

    > [!div class="mx-imgBorder"]
    > ![Navn og beregning for et hurtigsegment.](media/quick-segment-name.png "Navn og beregning for et hurtigsegment")

5. Angi et **Navn** for segmentet. Alternativt kan du angi et **Visningsnavn**.

6. Velg **Lagre** for å opprette segmentet.

7. Når segmentet er ferdig behandlet, kan du vise det på samme måte som et hvilket som helst segment du har opprettet.

## <a name="next-steps"></a>Neste trinn

[Eksporter et segment](export-destinations.md) og utforsk [Kundekort](customer-card-add-in.md) og [Koblinger](export-power-bi.md) for å få innsikt på kundenivået.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
