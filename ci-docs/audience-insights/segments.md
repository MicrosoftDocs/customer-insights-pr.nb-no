---
title: Opprette og behandle segmenter
description: Opprett segmenter av kunder for å gruppere dem basert på forskjellige attributter.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270368"
---
# <a name="create-and-manage-segments"></a>Opprette og behandle segmenter

Med segmenter kan du gruppere kunder basert på demografiske, transaksjonelle eller atferdsmessige attributter. Du kan bruke segmenter til å målrette kampanjer, salgsaktiviteter og kundestøttehandlinger slik at du oppnår forretningsmålene dine.

Du kan definere komplekse filtre rundt kundeprofilenheten og de relaterte enhetene. Hvert segment, etter behandlingen, oppretter et sett med kundeoppføringer som du kan eksportere og utføre handlinger på. Enkelte [tjenestebegrensninger](service-limits.md) gjelder.

Med mindre noe annet er angitt, er alle segmenter **dynamiske segmenter**, som oppdateres etter en regelmessig tidsplan.

Eksemplet nedenfor viser bruken av segmenteringsfunksjonaliteten. Vi har definert et segment for kunder som har bestilt varer for minst USD 500 i løpet av de siste 90 dagene *og* som var involvert i en kundeservicesamtale som ble videresendt.

> [!div class="mx-imgBorder"]
> ![Flere grupper](media/segmentation-group1-2.png "Flere grupper")

## <a name="create-a-new-segment"></a>Opprett et nytt segment

Segmenter administreres på **Segmenter**-siden.

1. I Målgruppeinnsikt går du til **Segmenter**-siden.

2. Velg **Ny** > **Tomt segment**.

3. Velg ruten **Nytt segment**, gå til en segmenttype og angi et **Navn**.

   Du kan eventuelt angi et visningsnavn og en beskrivelse som hjelper deg med å identifisere segmentet.

4. Velg **Neste** for å gå til siden for **Segmentverktøy**, der du definerer en gruppe. En gruppe er et sett med kunder.

5. Velg enheten som inkluderer attributtet du vil segmentere etter.

6. Velg attributtet du vil segmentere etter. Dette attributtet kan ha en av fire verdityper: numerisk, streng, dato eller boolsk.

7. Velg en operator og en verdi for det valgte attributtet.

   > [!div class="mx-imgBorder"]
   > ![Egendefinert gruppefilter](media/customer-group-numbers.png "Gruppefilter for kunde")

   |Antall |Definisjon  |
   |---------|---------|
   |1     |Entity          |
   |2     |Attributt          |
   |3    |Operator         |
   |4    |Verdi         |

8. Hvis enheten er koblet til den enhetlige kundeenheten via [relasjoner](relationships.md), må du definere relasjonsbanen for å opprette et gyldig segment. Legg til enhetene fra relasjonsbanen til du kan velge **Kunde: CustomerInsights**-enheten fra rullegardinlisten. Velg deretter **Alle oppføringer** for hver betingelse.

   > [!div class="mx-imgBorder"]
   > ![Relasjonsbane under opprettelse av segment](media/segments-multiple-relationships.png "Relasjonsbane under opprettelse av segment")

9. Velg **Lagre** for å lagre segmentet. Segmentet blir lagret og behandlet hvis alle kravene valideres. Hvis ikke blir det lagret som et utkast.

10. Velg **Tilbake til Segmenter** for å gå tilbake til **Segmenter**-siden.

## <a name="manage-existing-segments"></a>Behandle eksisterende segmenter

På siden **Segmenter** kan du vise alle lagrede segmenter og administrere dem.

Hvert segment representeres av en rad som inneholder tilleggsinformasjon om segmentet.

Du kan sortere segmentene i en kolonne ved å velge kolonneoverskriften.

Bruk **Søk**-boksen øverst i høyre hjørne til å filtrere segmentene.

> [!div class="mx-imgBorder"]
> ![Alternativer for å behandle et eksisterende segment](media/segments-selected-segment.png "Alternativer for å behandle et eksisterende segment")

Følgende handling er tilgjengelig når du velger et segment:

- **Vis** segmentdetaljene, inkludert medlemsantall, som viser en forhåndsvisning av segmentmedlemmer.
- **Rediger** segmentet for å endre egenskapene.
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

## <a name="download-and-export-segments"></a>Laste ned og eksportere segmenter

Du kan laste ned segmentene til en CSV-fil eller eksportere dem til Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Laste ned segmenter til en CSV-fil

1. I Målgruppeinnsikt går du til **Segmenter**-siden.

2. Velg en ellipse i flisen i et bestemt segment.

3. Velg **Last ned som CSV** fra rullegardinlisten for handlinger.

### <a name="export-segments-to-dynamics-365-sales"></a>Eksporter segmenter til Dynamics 365 Sales

Før du eksporterer segmenter til Dynamics 365 Sales, må en administrator [opprette eksportmålet](export-destinations.md) for Dynamics 365 Sales.

1. I Målgruppeinnsikt går du til **Segmenter**-siden.

2. Velg en ellipse i flisen i et bestemt segment.

3. Velg **Legg til i** fra rullegardinlisten for handlinger, og velg eksportmålet du vil sende dataene til.

## <a name="draft-mode-for-segments"></a>Kladdemodus for segmenter

Hvis ikke alle krav til å behandle et segment er oppfylt, kan du lagre segmentet som et utkast og få tilgang til det fra siden **Segmenter**.

Det blir lagret som et inaktivt segment, og kan ikke aktiveres det før det er gyldig.

## <a name="add-more-conditions-to-a-group"></a>Legge til flere betingelser i en gruppe

Hvis du vil legge til flere betingelser i en gruppe, kan du bruke to logiske operatorer:

- **AND**-operator: Begge betingelser må oppfylles som en del av segmentprosessen. Dette alternativet er svært nyttig når du definerer betingelser på tvers av forskjellige enheter.

- **OR**-operator: En av betingelsene må oppfylles som en del av segmenteringsprosessen. Dette alternativet er svært nyttig når du definerer flere betingelser for samme enhet.

   > [!div class="mx-imgBorder"]
   > ![OR-operator der begge betingelser må oppfylles](media/segmentation-either-condition.png "OR-operator der begge betingelser må oppfylles")

Det er for øyeblikket mulig å neste en **OR**-operator under en **AND**-operator, men ikke motsatt.

## <a name="combine-multiple-groups"></a>Kombinere flere grupper

Hver gruppe produserer et bestemt sett med kunder. Du kan kombinere disse gruppene slik at de inneholder kundene som kreves for forretningssaken.

1. I Målgruppeinnsikt går du til **Segmenter**-siden og velger et segemtn.

2. Velg **Legg til gruppe**.

   > [!div class="mx-imgBorder"]
   > ![Legg til gruppe i kundegruppe](media/customer-group-add-group.png "Legg til gruppe i kundegruppe")

3. Velg én av følgende sett operatorer: **Union**, **Skjæringspunkt** eller **Unntatt**.

   > [!div class="mx-imgBorder"]
   > ![Legg til union i kundegruppe](media/customer-group-union.png "Legg til union i kundegruppe")

   Velg en angitt operator for å definere en ny gruppe. Lagre forskjellige grupper for å avgjøre hvilke data som beholdes:

   - **Union** forener de to gruppene.

   - **Intersect** overlapper de to gruppene. Bare data som *er felles* for begge gruppene, beholdes i den enhetlige gruppen.

   - **Bortsett fra** kombinerer de to gruppene. Bare data i gruppe A som *ikke er felles* med data i gruppe B, beholdes.

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

## <a name="quick-segments"></a>Hurtigsegmenter

I tillegg til segmentverktøyet finnes det en annen bane for oppretting av segmenter. Med hurtigsegmenter kan du bygge enkle segmenter (med én enkelt operator) raskt og med direkte innsikt.

1. På **Segmenter**-siden velger du **Ny** > **Hurtigopprett fra**.

   - Velg alternativet **Profiler** for å bygge et segment som er basert på den enhetlige kundeenheten.
   - Velg alternativet **Mål** for å bygge et segment rundt hver av Kundeattributt-måltypene du tidligere har opprettet på **Mål**-siden.
   - Velg alternativet **Intelligens** for å bygge et segment rundt én av de utgående enhetene du genererte ved hjelp av funksjonene **Prediksjoner** eller **Egendefinerte modeller**.

2. I dialogboksen **Nytt hurtigsegment** velger du et attributt fra **Felt**-rullegardinlisten.

3. Systemet gir noe ekstra innsikt som hjelper deg med å lage bedre segmenter av kundene.
   - Vi viser de 10 største kundeantallene for kategoriske felt. Velg en **Verdi** og deretter **Gå gjennom**.

   - For et numerisk attributt vil systemet vise hvilken attributtverdi som faller under hver kundepersentil. Velg en **Operator** og en **Verdi**, og velg deretter **Gå gjennom**.

4. Systemet gir deg en **Beregnet segmentstørrelse**. Du kan velge om du vil generere segmentet du har definert, eller først gå til det igjen for å få en annen segmentstørrelse.

    > [!div class="mx-imgBorder"]
    > ![Navn og beregning for et hurtigsegment](media/quick-segment-name.png "Navn og beregning for et hurtigsegment")

5. Angi et **Navn** for segmentet. Alternativt kan du angi et **Visningsnavn**.

6. Velg **Lagre** for å opprette segmentet.

7. Når segmentet er ferdig behandlet, kan du vise det på samme måte som et hvilket som helst segment du har opprettet.

I følgende scenarioer anbefaler vi å bruke segmentverktøyet i stedet for den anbefalte segmentfunksjonen:

- Opprette segmenter med filtre i kategorifelt der operatoren er forskjellig fra **Is**-operatoren
- Opprette segmenter med filtre på numeriske felt der operatoren er forskjellig fra operatorene **Mellom**, **Større enn** og **Mindre enn**
- Opprette segmenter med filtre på datotype-felt

## <a name="next-steps"></a>Neste trinn

[Eksporter et segment](export-destinations.md) og utforsk [Kundekort](customer-card-add-in.md) og [Koblinger](export-power-bi.md) for å få innsikt på kundenivået.


[!INCLUDE[footer-include](../includes/footer-banner.md)]