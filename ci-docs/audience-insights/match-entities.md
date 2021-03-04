---
title: Samsvare enheter for dataforening
description: Samsvar enheter for å opprette enhetlige kundeprofiler.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267490"
---
# <a name="match-entities"></a>Samsvare enheter

Når du har fullført tilordningsfasen, er du klar til å samsvare med enhetene. Samsvarfasen angir hvordan du kombinerer datasettene til et enhetlig kundeprofildatasett. Samsvarsfasen krever minst [to tilordnede enheter](map-entities.md).

## <a name="specify-the-match-order"></a>Angi samsvarsrekkefølgen

Gå til **Data** > **Samle** > **Samsvar**, og velg **Angi ordre** for å starte samsvarsfasen.

Hvert treff forener to eller flere enheter i én enhet, samtidig som hver unike kundeoppføring beholdes. I det følgende eksemplet valgte vi tre entiteter: **ContactCSV: TestData** som **Primær**-enhet, **WebAccountCSV: TestData** som **Enhet 2** og **CallRecordSmall: TestData** som **Enhet 3**. Diagrammet over utvalgene illustrerer hvordan samsvarsrekkefølgen blir utført.

> [!div class="mx-imgBorder"]
> ![Redigere datasamsvarsrekkefølgen](media/configure-data-match-order-edit-page.png "Redigere datasamsvarsrekkefølgen")
  
**Primær**-enheten samsvarer med **Enhet 2**. Datasettet som er et resultat av det første samsvaret, samsvarer med **Enhet 3**.
I dette eksemplet har vi bare valgt to treff, men systemet kan støtte flere.

> [!IMPORTANT]
> Enheten du velger som **Primær**-enhet, fungerer som grunnlag for det enhetlige hoveddatasettet. Flere enheter som velges under samsvarsfasen, blir lagt til i enheten. Samtidig betyr det ikke at den enhetlige enheten skal inneholde *alle* dataene som er inkludert i enheten.
>
> Det er to hensyn som kan hjelpe deg med å velge enhetshierarkiet:
>
> - Hvilken enhet vurderer du å ha de mest fullstendige og pålitelige dataene om kundene?
> - Har enheten du nettopp identifiserte, attributter som også deles av andre enheter (for eksempel navn, telefonnummer eller e-postadresse)? Hvis ikke velger du den andre pålitelige enheten.

Velg **Ferdig** for å lagre samsvarsrekkefølgen.

## <a name="define-rules-for-your-first-match-pair"></a>Definere regler for det første samsvarsparet

Når du har angitt samsvarsrekkefølgen, vises de definerte samsvarene på siden for **Samsvar**. Flisene øverst på skjermen er tomme til du kjører samsvarsbestillingen.

> [!div class="mx-imgBorder"]
> ![Definere regler](media/configure-data-match-need-rules.png "Definere regler")

Advarselen **Trenger regler** antyder at ingen samsvarsregel er definert for et samsvarspar. Samsvarsregler angir logikken som et bestemt enhetspar skal samsvares etter.

1. Hvis du vil definere den første regelen, åpner du ruten **Regeldefinisjon** ved å velge den tilsvarende samsvarsraden i samsvarstabellen (1) og deretter velge **Opprett ny regel** (2).

   > [!div class="mx-imgBorder"]
   > ![Opprett ny regel](media/configure-data-match-new-rule2.png "Opprett ny regel")

2. I ruten **Rediger regel** konfigurerer du betingelsene for regelen. Hver betingelse representeres av to rader som inkluderer obligatoriske valg.

   > [!div class="mx-imgBorder"]
   > ![Ny regelrute](media/configure-data-match-new-rule-condition.png "Ny regelrute")

   Enhet/felt (første) – Et attributt som skal brukes til samsvar fra første samsvarsparenhet. Eksempler kan inneholde et telefonnummer eller en e-postadresse. Velg et attributt som sannsynligvis vil være unikt for kunden.

   > [!TIP]
   > Unngå samsvar på grunnlag av aktivitetstypeattributter. Hvis et attributt for eksempel ser ut til å være en aktivitet, kan det være et dårlig vilkår å samsvare etter.  

   Enhet/felt (andre) – Et attributt som skal brukes til samsvar fra andre samsvarsparenhet.

   Normaliser – **Normaliseringsmetode**: Ulike normaliseringsalternativer er tilgjengelige for de valgte attributtene. For eksempel fjerne tegnsetting eller fjerne mellomrom

   For organisasjonsnavnnormalisering (forhåndsvisning) kan du også velge **Type (Telefon, Navn, Adresse, Organisasjon)**

   > [!div class="mx-imgBorder"]
   > ![Normalisering – B2B](media/match-normalization-b2b.png "Normalisering – B2B")

   Presisjonsnivå – Presisjonsnivået som skal brukes for denne betingelsen. Angivelse av et presisjonsnivå for en samsvarsbetingelse kan ha to typer: **Grunnleggende** og **Egendefinert**.  
   - Grunnleggende: Gir deg fire alternativer som du kan velge mellom: Lav, Middels, Høy og Nøyaktig. Velg **Nøyaktig** hvis du bare vil at oppføringer som samsvarer med 100 prosent, skal samsvare. Velg ett av de andre nivåene for å samsvare oppføringer som ikke er 100 prosent identiske.
   - Egendefinert: Bruk glidebryteren for å definere den egendefinerte prosentandelen som oppføringer må samsvare med, eller angi en verdi i feltet **Egendefinert**. Systemet samsvarer bare med oppføringer som overstiger denne terskelen som kombinert samsvarspar. Verdiene på glidebryteren er mellom 0 og 1. 0,64 representerer dermed 64 prosent.

3. Velg **Ferdig** for å lagre regelen.

### <a name="add-multiple-conditions"></a>Legge til flere betingelser

Hvis du vil at enhetene skal samsvares bare hvis flere betingelser er oppfylt, legger du til flere betingelser som er koblet ved hjelp av en AND-operator.

1. Velg **Legg til betingelse** i ruten **Rediger regel**. Du kan også slette betingelser ved å velge Fjern-knappen ved siden av en eksisterende betingelse.

2. Velg **Ferdig** for å lagre regelen.

## <a name="add-multiple-rules"></a>Legge til flere regler

Hver betingelse gjelder for ett enkelt par med attributter, mens regler representerer sett med betingelser. Hvis du vil at enhetene skal samsvares av forskjellige attributtsett, kan du legge til flere regler.

1. I Målgruppeinnsikt går du til **Data** > **Samle** > **Samsvar**.

2. Velg enheten du vil oppdatere, og velg **Legg til regler**.

3. Følg fremgangsmåten som beskrevet i [Definere regler for det første samsvarsparet](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Regelrekkefølgen er viktig. Samsvarsalgoritmen prøver å samsvare basert på den første regelen, og fortsetter til den andre regelen hvis ingen treff ble identifisert under den første regelen.

## <a name="define-deduplication-on-a-match-entity"></a>Definere deduplisering på en samsvarsenhet

Sammen med angivelse av regler for kryssenhetssamsvar som beskrevet i delene ovenfor, kan du også angi regler for deduplisering. *Deduplisering* er en prosess. Den identifiserer duplikatoppføringer, slår dem sammen til én oppføring og kobler alle kildeoppføringene til denne flettede oppføringen med alternative ID-er til den flettede oppføringen.

Når en deduplisert oppføring er identifisert, blir denne oppføringen brukt i samsvarsprosessen på tvers av enheter. Deduplisering implementeres på enhetsnivå og kan brukes på alle enheter som brukes i samsvarsprosessen.

### <a name="add-deduplication-rules"></a>Legge til dedupliseringsregler

1. I Målgruppeinnsikt går du til **Data** > **Samle** > **Samsvar**.

1. I delen **Sammenslåtte duplikater** velger du **Angi enheter**.

1. I delen **Innstillinger for sammenslåing** velger du enhetene du vil bruke deduplisering på.

1. Angi hvordan du vil slå sammen duplikatoppføringer, og velg ett av tre alternativer for sammenslåing:
   - *Mest fylte*: Identifiserer oppføringen med de mest fylte attributtene som vinneroppføringen. Dette er standardalternativet for sammenslåing.
   - *Nyeste*: Identifiserer vinneroppføringen, basert på den nyeste oppføringen. Krever en dato eller et numerisk felt for å definere den nyeste.
   - *Minst nylig*: Identifiserer vinneroppføringen, basert på den minst nye oppføringen. Krever en dato eller et numerisk felt for å definere den nyeste.
 
   > [!div class="mx-imgBorder"]
   > ![Trinn 1 for dedupliseringsregler](media/match-selfconflation.png "Trinn 1 for dedupliseringsregler")
 
1. Når enhetene er valgt og innstillingen for sammenslåing er angitt, velger du **Opprett ny regel** for å definere regler for deduplisering på enhetsnivå.
   - **Velg felt** viser alle tilgjengelige felt fra den enheten som du vil deduplisere kildedata for.
   - Angi normaliserings- og presisjonsinnstillinger på lignende måte som angitt i kryssenhetssamsvaret.
   - Du kan definere flere betingelser ved å velge **Legg til betingelse**.
 
   > [!div class="mx-imgBorder"]
   > ![Trinn 2 for dedupliseringsregler](media/match-selfconflation-rules.png "Trinn 2 for dedupliseringsregler")

  Du kan opprette flere dedupliseringsregler for en enhet. 

1. Når du kjører samsvarsprosessen, grupperes oppføringene nå basert på betingelsene som er definert i dedupliseringsreglene. Når du har gruppert oppføringene, brukes sammenslåingspolicyen til å identifisere vinneroppføringen.

1. Denne vinneroppføringen sendes deretter videre til samsvar på tvers av enheter sammen med de ikke-vinnende oppføringer (for eksempel alternative ID-er) for å forbedre den samsvarende kvaliteten.

1. Eventuelle egendefinerte samsvars regler som er definert for å alltid og aldri samsvare, overstyr dedupliseringsregler. Hvis en dedupliseringsregel identifiserer samsvarende oppføringer, og en egendefinert samsvarsregel er angitt til aldri å samsvare med disse oppføringene, samsvares ikke disse to oppføringene.

1. Når du har kjørt samsvarsprosessen, vises dedupliseringsstatistikken.
   
> [!NOTE]
> Det er ikke obligatorisk å angi dedupliseringsregler. Hvis ingen slike regler er konfigurert, brukes reglene som er angitt av systemet. De skjuler alle oppføringer som deler samme verdikombinasjon (identisk treff) fra primærnøkkelen og feltene i samsvarende regler i én enkelt oppføring, før enhetsdataene sendes til samsvar mellom enheter for forbedret ytelse og systemtilstand.

## <a name="run-your-match-order"></a>Kjøre samsvarsrekkefølgen

Når du har definert samsvarsreglene, inkludert samsvar på tvers av enheter og dedupliseringsregler, kan du kjøre samsvarsordren. På siden **Samsvar** velger **Kjør** for å starte prosessen. Det kan ta litt tid å fullføre samsvarsalgoritmen. Du kan ikke endre egenskapene på siden **Samsvar** før samsvarsprosessen er fullført. Du finner den enhetlige kundeprofilenheten som ble opprettet på siden **Enheter**. Den enhetlige kundeenheten kalles **ConflationMatchPairs : CustomerInsights**.

Hvis du vil gjøre flere endringer og kjøre trinnet på nytt, kan du annullere et samsvar som pågår. Velg teksten **Oppdaterer...**, og velg **Avbryt jobb** nederst i sideruten som vises.

Når samsvarsprosessen er fullført, endres teksten **Oppdaterer ...** til **Vellykket**, og du kan bruke alle funksjonene på siden på nytt.

Den første samsvarsprosessen fører til at det opprettes en hoveddataenhet. Alle påfølgende samsvar fører til en utvidelse av enheten.

> [!TIP]
> Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser. De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies). Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben. Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.

## <a name="deduplication-output-as-an-entity"></a>Dedupliseringsutdata som en enhet
I tillegg til den enhetlige hovedenheten som er opprettet som en del av samsvarende tverrenhet, genererer dedupliseringsprosessen også en ny enhet for hver enhet fra samsvarsrekkefølgen for å identifisere de dedupliserte oppføringene. Disse enhetene kan finnes sammen med **ConflationMatchPairs:CustomerInsights** i **System**-delen på **Enheter**-siden med navnet **Deduplication_Datasource_Entity**.

En utdataenhet for deduplisering inneholder følgende informasjon:
- ID-er/nøkler
  - Hovednøkkelfelt og alternativt ID-felt. Feltet for alternative ID-er består av alle de alternative ID-ene som er identifisert for en oppføring.
  - Feltet Deduplication_GroupId viser gruppen eller klyngen som identifiseres i en enhet, som grupperer alle lignende oppføringer basert på de angitte dedupliseringsfeltene. Dette brukes til systembehandlingsformål. Hvis det ikke er angitt noen regler for manuell deduplisering og systemdefinerte dedupliseringsregler gjelder, kan det hende du ikke finner dette feltet i utdataenheten for deduplisering.
  - Deduplication_WinnerId: Dette feltet inneholder vinner-ID-en fra de identifiserte gruppene eller klyngene. Hvis Deduplication_WinnerId er den samme som primærnøkkelverdien for en oppføring, betyr det at oppføringen er vinneroppføringen.
- Felter brukes til å definere dedupliseringsreglene.
- Feltene Regel og Poengsum for å angi hvilke av dedupliseringsreglene som ble brukt, og poengsummen som ble returnert av den samsvarende algoritmen.

## <a name="review-and-validate-your-matches"></a>Se gjennom og validere samsvarene

Evaluer kvaliteten på samsvarsparene og begrens det:

- På siden **Samsvar** finner du to fliser som viser innledende innsikt om dataene.

  - **Unike kunder**: Viser antall unike profiler som systemet identifiserte.
  - **Samsvarte oppføringer**: Viser antall samsvar på tvers av alle samsvarsparene.

- I tabellen **Samsvar rekkefølge** kan du vurdere resultatene av hvert samsvarspar ved å sammenligne antallet oppføringer som ble levert fra denne samsvarsparenheten, mot prosentandelen av vellykkede samsvarte oppføringer.

- I delen **Regler** for en enhet i tabellen for **Samsvar rekkefølge** finner du prosentandelen av samsvarende oppføringer på regelnivået. Ved å velge tabellsymbolet ved siden av en regel kan du vise alle disse oppføringene på regelnivået. Vi anbefaler at du gjennomgår et delsett av oppføringene for å kontrollere at de ble riktig samsvart.

- Eksperimenter med forskjellige presisjonsterskler rundt betingelsene for å identifisere den optimale verdien.

  1. Velg ellipsen (...) for den samsvarsparregelen du vil eksperimentere med, og velg **Rediger**.

  2. Velg betingelsen du vil eksperimentere med. Hvert vilkår representeres av én rad i ruten **Samsvarsregel**.

  3. Hva du vil se på siden **Forhåndsvisning av vilkår**, avhenger av hvilket presisjonsnivå du har valgt for en betingelse. Finn antall samsvarende og ikke-samsvarende oppføringer for den valgte betingelsen.

     Få en rik forståelse av virkningene av forskjellige grensenivåer. Du kan sammenligne hvor mange oppføringer som samsvares under hvert terskelnivå, og vise oppføringene under hvert alternativ. Velg hver av flisene, og se gjennom dataene i tabelldelen.

## <a name="optimize-your-matches"></a>Optimalisere treffene

Øk kvaliteten ved å konfigurere noen av samsvarsparameterne på nytt:

- **Endre samsvarsrekkefølgen** ved å velge **Rediger** og endre feltene for samsvarsrekkefølge.

  > [!div class="mx-imgBorder"]
  > ![Redigere datasamsvarsrekkefølgen](media/configure-data-match-order-edit.png "Redigere datasamsvarsrekkefølgen")

- **Endre rekkefølgen på reglene** hvis du definerer flere regler. Du kan endre rekkefølgen på reglene for samsvar ved å velge **Flytt opp** og **Flytt ned** i samsvarsregelrutenettet.

  > [!div class="mx-imgBorder"]
  > ![Endre regelrekkefølge](media/configure-data-change-rule-order.png "Endre regelrekkefølge")

- **Dupliser reglene** hvis du har definert en samsvarsregel og vil opprette en liknende regel med endringer. Dette gjør du ved velge **Dupliser**.

  > [!div class="mx-imgBorder"]
  > ![Duplisere en regel](media/configure-data-duplicate-rule.png "Duplisere en regel")

- **Deaktiver en regel** for å beholde en samsvarsregel når den utelates fra den samsvarende prosessen.

  > [!div class="mx-imgBorder"]
  > ![Deaktiver en regel](media/configure-data-deactivate-rule.png "Deaktiver en regel")

- **Rediger reglene** ved å velge symbolet **Rediger**. Du kan gjøre følgende endringer:

  - Endre attributter for en betingelse: Velg nye attributter innenfor den bestemte betingelsesraden.
  - Endre terskelen for en betingelse: Juster presisjonsglidebryteren.
  - Endre normaliseringsmetoden for en betingelse: Oppdater normaliseringsmetoden.

## <a name="specify-your-custom-match-records"></a>Spesifisere de egendefinerte samsvarsoppføringene

Du kan spesifisere vilkårene som bestemte oppføringer alltid skal samsvare med eller aldri samsvare med. Disse reglene kan lastes opp samlet i samsvarsprosessen.

1. Velg alternativet **Egenfinert samsvar** på skjermen **Samsvar rekkefølge**.

   > [!div class="mx-imgBorder"]
   > ![Opprette et egendefinert samsvar](media/custom-match-create.png "Opprette et egendefinert samsvar")

2. Hvis du ikke har noen opplastede enheter, vises en ny dialogboks for **Egendefinert samsvar** som krever at du fyller ut noen detaljer. Hvis du har angitt disse detaljene tidligere, går du til trinn 8.

   > [!div class="mx-imgBorder"]
   > ![Dialogboksen Nytt egendefinert samsvar](media/custom-match-new-dialog-box.png "Dialogboksen Nytt egendefinert samsvar")

3. Velg **Fyll ut malen** for å få en malfil som kan angi hvilke oppføringer fra hvilke enheter som alltid skal samsvare eller aldri samsvare. Du må fylle ut oppføringene for "alltid samsvar" og "aldri samsvar" i to forskjellige filer.

4. Malen inneholder felt for å angi enheten og primærnøkkelverdiene for enheten som skal brukes i det egendefinerte samsvaret. Hvis du for eksempel vil at primærnøkkelen 12345 fra salgsenheten alltid skal samsvare med primærnøkkel 34567 fra kontaktenheten, må du angi følgende:
    - Entity1: Salg
    - Entity1Key: 12345
    - Entity2: Kontakt
    - Entity2Key: 34567

   Den samme malfilen kan angi egendefinerte samsvarsoppføringer fra flere enheter.
   
   Hvis du vil angi egendefinert samsvar for deduplisering for en enhet, angir du samme enhet som både Enhet1 og Enhet2 og angir de forskjellige primærnøkkelverdiene.

5. Når du har lagt til alle overstyringene du vil bruke, lagrer du malfilen.

6. Gå til **Data** > **Datakilder**, og hent inn malfilene som nye enheter. Når de er lagt inn, kan du bruke dem til å angi samsvarskonfigurasjonen.

7. Etter at du har lastet opp filene og enhetene er tilgjengelige, velger du alternativet **Egendefinert samsvar** på nytt. Du vil se alternativer for å angi enhetene du vil inkludere. Velg de påkrevde enhetene på rullegardinmenyen.

   > [!div class="mx-imgBorder"]
   > ![Egendefinerte samsvarsoverstyringer](media/custom-match-overrides.png "Egendefinerte samsvarsoverstyringer")

8. Velg enhetene du vil bruke for **Samsvar alltid** og **Samsvar aldri**, og velg **Ferdig**.

9. Velg **Lagre** på siden **Samsvar** for den egendefinerte samsvarskonfigurasjonen du nettopp konfigurerte.

10. Velg **Kjør** på siden **Samsvar** for å starte den samsvarsprosessen, og den egendefinerte samsvarskonfigurasjonen trer i kraft. Alle systemsamsvarsregler overstyres av konfigurasjonssettet.

11. Når samsvaret er fullført, kan du kontrollere enheten **ConflationMatchPair** for å bekrefte at overstyringene brukes i sammenslåingssamsvarene.

## <a name="next-step"></a>Neste trinn

Når du har fullført samsvarsprosessen for minst ett samsvarspar, kan du løse mulige konflikter i dataene ved å gå gjennom emnet [**Slå sammen**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]