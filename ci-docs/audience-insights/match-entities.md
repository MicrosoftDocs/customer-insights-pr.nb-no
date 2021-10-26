---
title: Samsvare enheter for dataforening
description: Samsvar enheter for å kombinere datasett og opprette enhetlige kundeprofiler.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
ms.openlocfilehash: 67e17495fa6da1cfac7ee4ee165e798364f6cb27
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648220"
---
# <a name="match-entities"></a>Samsvare enheter

Samsvarfasen angir hvordan du kombinerer datasettene til et enhetlig kundeprofildatasett. Etter å ha fullført [tilordningstrinnet](map-entities.md) i dataforeningsprosessen, er du klar til å samsvare enhetene. Samsvarsfasen krever minst to tilordnede enheter.

Samsvarssiden består av tre deler: 
- Nøkkelmåledata som oppsummerer antall samsvarte oppføringer
- Samsvarsrekkefølge og regler for samsvar på tvers av enheter
- Regler for deduplisering av samsvarsenheter

## <a name="specify-the-match-order"></a>Angi samsvarsrekkefølgen

Gå til **Data** > **Samle** > **Samsvar**, og velg **Angi ordre** for å starte samsvarsfasen.

Hvert samsvar forener to eller flere enheter i én konsolidert enhet. Samtidig beholdes de unike kundeoppføringene. Vi valgte for eksempel to enheter: **eCommerce:eCommerceContacts** som den primære enheten og **LoyaltyScheme:loyCustomers** som en sekundær enhet. Rekkefølgen til enhetene angir i hvilken rekkefølge systemet prøver å samsvare oppføringene.

:::image type="content" source="media/match-page.png" alt-text="Skjermbilde av Samsvar-siden i Unify-området i dataforeningsprosessen.":::
  
Den primære enheten *eCommerce:eCommerceContacts* samsvares med den neste enheten *LoyaltyScheme:loyCustomers*. Datasettet som er et resultat av det første samsvarstrinnet, samsvares med den påfølgende enheten hvis du har flere enn to enheter.

> [!IMPORTANT]
> Enheten du velger som primær enhet, fungerer som grunnlag for det enhetlige profildatasettet. Flere enheter som velges under samsvarsfasen, blir lagt til i enheten. Dette betyr ikke at den enhetlige enheten vil inkludere *alle* dataene som er inkludert i denne enheten.
>
> Det er to hensyn som kan hjelpe deg med å velge enhetshierarkiet:
>
> - Velg enheten med de mest fullstendige og pålitelige profildataene om kundene som den primære enheten.
> - Velg en enhet som har flere attributter felles med andre enheter (for eksempel navn, telefonnummer eller e-postadresse) som den primære enhet.

Når du har angitt samsvarsrekkefølgen, ser du de definerte samsvarsparene i delen **Detaljer om samsvarende oppføringer** under **Data** > **Samle** > **Samsvar**. Nøkkelmåledataene vil være tomme til samsvarsprosessen er fullført.

## <a name="define-rules-for-match-pairs"></a>Definer regler for samsvarspar

Samsvarsregler angir logikken som et bestemt enhetspar skal samsvares etter.

Advarselen **Trenger regler** ved siden av et enhetsnavn antyder at ingen samsvarsregel er definert for et samsvarspar. 

:::image type="content" source="media/match-rule-add.png" alt-text="Skjermbilde av delen Detaljer om samsvarende oppføringer med kontroll for å legge til regler uthevet.":::

1. Velg **Legg til regler** under en enhet i delen **Detaljer om samsvarende oppføringer** for å definere samsvarsregler.

1. I ruten **Opprett regel** konfigurerer du betingelsene for regelen.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Skjermbilde av en åpnet samsvarsregel med betingelser lagt til.":::

   - **Enhet/felt (første rad)**: Velg en relatert enhet og et attributt for å angi en oppføringsegenskap som sannsynligvis er unik for en kunde. For eksempel et telefonnummer eller en e-postadresse. Unngå samsvar etter attributter av aktivitetstypen. En kjøps-ID samsvarer for eksempel sannsynligvis ikke med andre oppføringstyper.

   - **Enhet/felt (andre rad)**: Velg et attributt som er relatert til attributtet for enheten som er angitt i den første raden.

   - **Normaliser**: Velg blant følgende normaliseringsalternativer for de valgte attributtene. 
     - Mellomrom: Fjerner alle mellomrom. *Hello   World* blir *HelloWorld*.
     - Symboler: Fjerner alle symboler og spesialtegn. *Head&Shoulder* blir *HeadShoulder*.
     - Tekst til små bokstaver: Konverterer alle tegn til små bokstaver. *BARE STORE BOKSTAVER og Store forbokstaver* blir *bare store bokstaver og store forbokstaver*.
     - Unicode til ASCII: Konverterer Unicode-notasjon til ASCII-tegn. */u00B2* blir *2*.
     - Tall: Konverterer andre tallsystemer, for eksempel romertall, til arabiske tall. *VIII* blir *8*.
     - Semantiske typer: Standardiserer navn, titler, telefonnumre, adresser osv. 

   - **Presisjon:** Angir presisjonsnivået som skal brukes for denne betingelsen. 
     - **Grunnleggende**: Velg mellom *Lav*, *Middels*, *Høy* og *Nøyaktig*. Velg **Nøyaktig** hvis du bare vil at oppføringer som samsvarer med 100 prosent, skal samsvare. Velg ett av de andre nivåene for å samsvare oppføringer som ikke er 100 prosent identiske.
     - **Egendefinert:** Angi en prosentandel som oppføringer må samsvare med. Systemet samsvarer bare oppføringer som passerer denne terskelen.

1. Oppgi et **Navn** for regelen.

1. [Legg til flere betingelser](#add-conditions-to-a-rule), eller velg **Fullført** for å fullføre regelen.

1. Du kan eventuelt [legge til flere regler](#add-rules-to-a-match-pair).

1. Velg **Lagre** for å ta i bruk endringene.

### <a name="add-conditions-to-a-rule"></a>Legg til betingelser for en regel

Hvis du vil samsvare enheter bare hvis attributter oppfyller flere betingelser, legger du til flere betingelser i en samsvarsregel. Betingelser er koblet til en logisk OG-operator og kjøres derfor bare hvis alle betingelser er oppfylt.

1. Gå til **Data** > **Samle** > **Samsvar**, og velg **Rediger** for regelen du vil legge til betingelser for.

1. Velg **Legg til betingelse** i ruten **Rediger regel**.

1. Velg **Ferdig** for å lagre regelen.

### <a name="add-rules-to-a-match-pair"></a>Legg til regler i et samsvarspar

Samsvarsregler representerer sett med betingelser. Hvis du vil samsvare enheter etter betingelser basert på flere attributter, kan du legge til flere regler.

1.  Gå til **Data** > **Samle** > **Samsvar**, og velg **Legg til regel** for enheten du vil legge til regler for.

2. Følg fremgangsmåten i [Definer regler for samsvarspar](#define-rules-for-match-pairs).

> [!NOTE]
> Rekkefølgen av regler er viktig. Den samsvarende algoritmen prøver å samsvare på grunnlag av den første regelen, og fortsetter til den andre regelen bare hvis ingen treff ble identifisert med den første regelen.

### <a name="change-the-entity-order-in-match-rules"></a>Endre enhetsrekkefølgen i samsvarsregler

Du kan endre rekkefølgen på enheter for samsvarsregler for å endre rekkefølgen de behandles i. Regler som er i konflikt på grunn av en endret ordre, blir fjernet. Du må opprette regler som er fjernet, på nytt med en oppdatert konfigurasjon.

1. Gå til **Data** > **Samle** > **Samsvar**, og velg **Rediger**.

1. I **Rediger regel**-ruten velger du **Flytt opp/ned**-kontrollen eller drar og slipper enheter for å endre rekkefølgen.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Alternativer for å endre rekkefølgen enheter behandles i, i samsvarsfasen.":::

1. Velg **Ferdig** for å lagre regelen.

## <a name="define-deduplication-on-a-match-entity"></a>Definere deduplisering på en samsvarsenhet

I tillegg til [samsvarsregler på tvers av enheter](#define-rules-for-match-pairs) kan du også angi dedupliseringsregler. *Deduplisering* er en annen prosess ved samsvar av oppføringer. Den identifiserer duplikatoppføringer og slår dem sammen til én oppføring. Kildeoppføringer kobles til den flettede oppføringen med alternative ID-er.

Dedupliserte oppføringer brukes i samsvarsprosessen på tvers av enheter. Deduplisering skjer for enkeltenheter og kan konfigureres for hver enhet som brukes i samsvarspar.

Det er ikke obligatorisk å angi dedupliseringsregler. Hvis ingen slike regler er konfigurert, brukes reglene som er angitt av systemet. De kombinerer alle oppføringene i én enkelt oppføring før de sender enhetsdataene til samsvar på tvers av enheter for å forbedre ytelsen.

### <a name="add-deduplication-rules"></a>Legge til dedupliseringsregler

1. Gå til **Data** > **Samle** > **Samsvar**.

1. I delen **Sammenslåtte duplikater** velger du **Angi enheter**. Hvis regler for deduplisering allerede er opprettet, velger du **Rediger**.

1. I ruten **Innstillinger for sammenslåing** velger du enhetene du vil kjøre deduplisering på.

1. Angi hvordan du vil kombinere duplikatoppføringer, og velg ett av tre alternativer:
   - **Mest fylte**: Identifiserer oppføringen med de mest utfylte attributtfeltene som vinneroppføringen. Dette er standardalternativet for sammenslåing.
   - **Nyeste**: Identifiserer vinneroppføringen, basert på den nyeste oppføringen. Krever en dato eller et numerisk felt for å definere den nyeste.
   - **Minst nylig**: Identifiserer vinneroppføringen, basert på den minst nye oppføringen. Krever en dato eller et numerisk felt for å definere den nyeste.
 
   > [!div class="mx-imgBorder"]
   > ![Trinn 1 for dedupliseringsregler.](media/match-selfconflation.png "Trinn 1 for dedupliseringsregler")
 
1. Når enhetene er valgt og innstillingen for sammenslåing er angitt, velger du **Legg til regel** for å definere regler for deduplisering på enhetsnivå.
   - **Velg felt** viser alle tilgjengelige felter fra enheten. Velg feltet du vil søke etter duplikater for. Velg felter som sannsynligvis er unike for hver enkelt kunde. For eksempel en e-postadresse eller en kombinasjon av navn, poststed og telefonnummer.
   - Angi normaliserings- og presisjonsinnstillingene.
   - Definer flere betingelser ved å velge **Legg til betingelse**.
 
   > [!div class="mx-imgBorder"]
   > ![Trinn 2 for dedupliseringsregler.](media/match-selfconflation-rules.png "Trinn 2 for dedupliseringsregler")

  Du kan opprette flere dedupliseringsregler for en enhet. 

1. Når du kjører samsvarsprosessen, grupperes oppføringene nå basert på betingelsene som er definert i dedupliseringsreglene. Når du har gruppert oppføringene, brukes sammenslåingspolicyen til å identifisere vinneroppføringen.

1. Denne vinneroppføringen sendes deretter videre til samsvar på tvers av enheter sammen med de ikke-vinnende oppføringer (for eksempel alternative ID-er) for å forbedre den samsvarende kvaliteten.

1. Eventuelle egendefinerte samsvarsregler som er definert, overskriver dedupliseringsregler. Hvis en dedupliseringsregel identifiserer samsvarende oppføringer, og en egendefinert samsvarsregel er angitt til aldri å samsvare med disse oppføringene, samsvares ikke disse to oppføringene.

1. Når du har [kjørt samsvarsprosessn](#run-the-match-process), vises dedupliseringsstatistikken i flisene med nøkkelmåledata.

### <a name="deduplication-output-as-an-entity"></a>Dedupliseringsutdata som en enhet

Dedupliseringsprosessen oppretter en ny enhet for hver enhet fra samsvarsparene for å identifisere de dedupliserte oppføringene. Disse enhetene kan finnes sammen med **ConflationMatchPairs:CustomerInsights** i **System**-delen på **Enheter**-siden med navnet **Deduplication_DataSource_Entity**.

En utdataenhet for deduplisering inneholder følgende informasjon:
- ID-er/nøkler
  - Hovednøkkelfelt og alternativt ID-felt. Feltet for alternative ID-er består av alle de alternative ID-ene som er identifisert for en oppføring.
  - Feltet Deduplication_GroupId viser gruppen eller klyngen som identifiseres i en enhet, som grupperer alle lignende oppføringer basert på de angitte dedupliseringsfeltene. Det brukes til systembehandlingsformål. Hvis det ikke er angitt noen regler for manuell deduplisering og systemdefinerte dedupliseringsregler gjelder, kan det hende du ikke finner dette feltet i utdataenheten for deduplisering.
  - Deduplication_WinnerId: Dette feltet inneholder vinner-ID-en fra de identifiserte gruppene eller klyngene. Hvis Deduplication_WinnerId er den samme som primærnøkkelverdien for en oppføring, betyr det at oppføringen er vinneroppføringen.
- Felter brukes til å definere dedupliseringsreglene.
- Feltene Regel og Poengsum for å angi hvilke av dedupliseringsreglene som ble brukt, og poengsummen som ble returnert av den samsvarende algoritmen.
   
## <a name="run-the-match-process"></a>Kjør samsvarsprosessen

Med konfigurerte samsvarsregler, inkludert samsvar på tvers av enheter og dedupliseringsregler, kan du kjøre samsvarsprosessen. 

Gå til **Data** > **Samle** > **Samsvar**, og velg **Kjør** for å starte prosessen. Det tar litt tid å fullføre den samsvarende algoritmen, og du kan ikke endre konfigurasjonen før den er fullført. Hvis du vil gjøre endringer, kan du avbryte kjøringen. Velg statusen for jobben, og velg **Avbryt jobb** i ruten **Fremdriftsdetaljer**.

Du finner resultatet av en vellykket kjøring, enheten for enhetlig kundeprofil, på **Enheter**-siden. Enheten for enhetlig kunde kalles **Kunder** i **Profiler**-delen. Det første vellykkede samsvarskjøringen oppretter den enhetlige *Kunde*-enheten. Alle påfølgende samsvarskjøringer utvider enheten.

> [!TIP]
> Når du har kjørt samsvarsprosessen, velger du prosessstatusen for å åpne ruten **Oppgavedetaljer**. Den gir en oversikt over behandlingstiden, den siste behandlingsdatoen og alle feil og advarsler som er knyttet til oppgaven. Velg **Se detaljer** for å se hvilke enheter som deltok i samsvarsprosessen, hvilke regler som ble brukt på dem, og om oppdateringene ble publisert på riktig måte.  
> Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser. De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Neddrillingsbane for å komme til å behandle detaljer fra aktivitetsstatuskoblingen.":::

## <a name="review-and-validate-your-matches"></a>Se gjennom og validere samsvarene

Gå til **Data** > **Samle** > **Samsvar** for å evaluere kvaliteten på samsvarsparene, og finjuster dem om nødvendig.

Flisene på toppen av siden viser nøkkelmåledata som oppsummerer antall samsvarte oppføringer og duplikater.

:::image type="content" source="media/match-KPIs.png" alt-text="Beskjært skjermbilde av nøkkelmåledataene på Samsvar-siden med tall og detaljer.":::

- **Unike kildeoppføringer** viser antall individuelle kildeoppføringer som ble behandlet i siste samsvarskjøring.
- **Samsvarende og ikke-samsvarende oppføringer** uthever hvor mange unike oppføringer som gjenstår etter behandling av samsvarsreglene.
- **Bare samsvarende oppføringer** viser bare antall treff på tvers av alle samsvarsparene.

Du kan vurdere resultatene av hvert samsvarspar og tilhørende regler i tabellen **Detaljer om samsvarende oppføringer**. Sammenligne antallet oppføringer som kom fra et samsvarspar, med prosentandelen oppføringer som samsvarte.

Gå gjennom reglene for et samsvarspar for å se prosentandelen for oppføringer som samsvarer, på regelnivå. Velg ellipsen (...), og velg deretter **Forhåndsvisning av samsvar** for å vise alle disse oppføringene på regelnivå. Vi anbefaler at du ser på noen oppføringer for å kontrollere at de samsvarte riktig.

Prøv ulike presisjonsgrenser for betingelser for å finne den optimale verdien.

  1. Velg ellipsen (...) for regelen du vil eksperimentere med, og velg **Rediger**.

  2. Endre presisjonsverdiene i betingelsene du vil revidere.

  3. Velg **Forhåndsvisning** for å se antallet samsvarende og ikke-samsvarende oppføringer for den valgte betingelsen.

## <a name="manage-match-rules"></a>Administrer samsvarsregler

Du kan omkonfigurere og finjustere de fleste av samsvarsparameterne.

:::image type="content" source="media/match-rules-management.png" alt-text="Skjermbilde av rullegardinmenyen med alternativer for samsvarsregel.":::

- **Endre rekkefølgen på reglene** hvis du definerer flere regler. Du kan endre rekkefølgen på samsvarsreglene ved å velge alternativene **Flytt opp** og **Flytt ned** ellerr ved å dra og slippe.

- **Endre regelbetingelser** ved å velge **Rediger** og velge forskjellige felter.

- **Deaktiver en regel** for å beholde en samsvarsregel når den utelates fra den samsvarende prosessen.

- **Dupliser reglene** hvis du har definert en samsvarsregel, og hvis du vil opprette en lignende regel med endringer, velger du **Duplikat**.

- **Slett en regel** ved å velge **Slett**-symbolet.

## <a name="specify-custom-match-conditions"></a>Angi egendefinerte samsvarsbetingelser

Du kan spesifisere vilkårene som bestemte oppføringer alltid skal samsvare med eller aldri samsvare med. Disse reglene kan lastes opp for å overstyre standard samsvarsprosess. Hvis det for eksempel er en Ola Nordmann I og Ola Nordmann II i oppføringene, kan det hende at systemet samsvarer dem som én person. Ved hjelp av egendefinerte samsvarsregler kan du angi at profilene deres refererer til forskjellige personer. 

1. Gå til **Data** > **Samle** > **Samsvar**, og velg **Egendefinert samsvar** i delen **Detaljer om samsvarende oppføringer**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Skjermbilde av delen Samsvarsregler med Egendefinert samsvar-kontrollen uthevet.":::

1. Hvis du ikke har angitt noen egendefinerte samsvarsregler, vises en ny **Egendefinert samsvar**-rute med flere detaljer.

1. Velg **Fyll ut malen** for å få en malfil som kan angi hvilke oppføringer fra hvilke enheter som alltid skal samsvare eller aldri samsvare. Du må fylle ut oppføringene for "alltid samsvar" og "aldri samsvar" i to forskjellige filer.

1. Malen inneholder felt for å angi enheten og primærnøkkelverdiene for enheten som skal brukes i det egendefinerte samsvaret. Hvis du for eksempel vil at primærnøkkelen *12345* fra *Salg*-enheten alltid skal samsvare med primærnøkkelen *34567* fra *Kontakt*-enheten, fyller du ut malen:
    - Entity1: Salg
    - Entity1Key: 12345
    - Entity2: Kontakt
    - Entity2Key: 34567

   Den samme malfilen kan angi egendefinerte samsvarsoppføringer fra flere enheter.
   
   Hvis du vil angi egendefinert samsvar for deduplisering for en enhet, angir du samme enhet som både Enhet1 og Enhet2 og angir de forskjellige primærnøkkelverdiene.

1. Når du har lagt til alle overstyringene du vil bruke, lagrer du malfilen.

1. Gå til **Data** > **Datakilder**, og hent inn malfilene som nye enheter. Når de er lagt inn, kan du bruke dem til å angi samsvarskonfigurasjonen.

1. Etter at du har lastet opp filene og enhetene er tilgjengelige, velger du alternativet **Egendefinert samsvar** på nytt. Du vil se alternativer for å angi enhetene du vil inkludere. Velg de nødvendige enhetene på rullegardinmenyen.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Skjermbilde av dialogen for å velge overstyringer for et egendefinert samsvarsscenario.":::

1. Velg enhetene du vil bruke for **Samsvar alltid** og **Samsvar aldri**, og velg **Ferdig**.

1. Velg **Lagre** på **Samsvar**-siden for å bruke den egendefinerte samsvarskonfigurasjonen.

1. Velg **Kjør** på **Samsvar**-siden for å starte samsvarsprosessen. Andre angitte samsvarsregler overstyres av den egendefinerte samsvarskonfigurasjonen.

> [!TIP]
> Gå til **Data** > **Enheter**, og gå gjennom **ConflationMatchPair**-enheten for å bekrefte at overstyringene er brukt.

## <a name="next-step"></a>Neste trinn

Når du har fullført samsvarsprosessen for minst ett samsvarspar, kan du løse mulige konflikter i dataene ved å gå gjennom emnet [**Slå sammen**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
