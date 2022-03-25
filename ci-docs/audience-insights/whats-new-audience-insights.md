---
title: Nye og kommende funksjoner
description: Informasjon om nye funksjoner, forbedringer og feilrettinger.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 9195770255bd798636b9532d6e1ca928345b3708
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376474"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Nyheter i funksjonaliteten for målgruppeinnsikt i Dynamics 365 Customer Insights

Vi har gleden av å kunngjøre de nyeste oppdateringene! Denne artikkelen oppsummerer funksjoner i offentlig forhåndsversjon, generelle tilgjengelighetsforbedringer og funksjonsoppdateringer. Hvis du vil se de langsiktige funksjonsplanene, kan du se [Dynamics 365 og Power Platform-utgivelsesplanene](/dynamics365/release-plans/).

Vi ruller ut oppdateringer for hver region. Enkelte områder kan se funksjoner før andre. Med mindre det er angitt noe annet, trenger du ikke å gjøre noe, og vi oppdaterer appen automatisk uten nedetid.

> [!TIP]
> For å sende inn og stemme på funksjonsforespørsler og produktforslag går du til [ideportalen for Dynamics 365-apper](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="february-2022-updates"></a>Oppdateringer februar 2022

Oppdateringene i februar 2022 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="general-availability-for-prediction-models"></a>Generell tilgjengelighet for prediksjon modeller

Standard prediksjonmodeller, inklusive **abonnementsfrafall**, **transaksjonsfrafall** og **Verdi for kundelevetid (CLV)**. blir allment tilgjengelige som en del av Customer Insights. 

Hvis du vil ha mer informasjon, kan du se [Oversikt over prediksjon](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Ny datakilde: Integrasjon med Azure Synapse Analytics (forhåndsversjon)

Azure Synapse Analytics er en bedriftsanalysetjeneste som akselererer tid til innsikt på tvers av datalagre og stordatasystemer.

Hvis organisasjonen din allerede bruker avanserte analysefunksjoner i Azure Synapse Analytics og lagrer utdataene i Data Lake, kan du enkelt legge inn disse dataene i Customer Insights. Hvis du vil ha mer informasjon, kan du se [Koble til en Azure Synapse-datakilde (forhåndsversjon)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp-supplering (forhåndsversjon)

LiveRamp gir deterministiske frakoblede identitetsløsning og konsolidering av kundedata. Du kan tilordne personlige identifikatorer i kundedataene til AbiliTec-identitetsgrafen og motta AbiliTec-ID-er. Deretter kan du bruke disse IDene til bedre forening av kundedataene.

Hvis du vil ha mer informasjon, kan du se [Suppler kundeprofiler med identitetsdata fra LiveRamp (forhåndsversjon)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Supplering for datakilder (forhåndsversjon)

Bruk data fra kilder som Microsoft og andre partnere til å forbedre kundedataene før dataforeningen. Datakildesupplering bidrar til å gi høyere datafullstendighet og -kvalitet som kan bidra til å oppnå bedre resultater når dataene samles.

Hvis du vil ha mer informasjon, kan du se [Supplering for datakilder (forhåndsversjon)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Endre eier av miljø

Selv om flere brukere kan ha administratortillatelser i Customer Insights, er bare én bruker eieren av et miljø. En forbedret opplevelse gjør det mulig å endre eiere av et miljø og kreve eierskap hvis en tidligere eier har sluttet i organisasjonen. 

Hvis du vil ha mer informasjon, kan du se [Endre eieren av et miljø](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Prosess for dataforberedelse viser årsaken til skadede oppføringer

Prosessen med dataklargjøring viser nå årsaken til at alle felt med skadede data er på det individuelle oppføringsnivået, for enkel identifisering. 

Hvis du vil ha mer informasjon, kan du se [Skadede datakilder](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Slutten av forhåndsversjon for rapporteringsfunksjoner i engasjementsinnsiktsfunksjonen

Forhåndsversjonen av engasjementsinnsiktsfunksjonen i Dynamics 365 Customer Insights ble avsluttet 15. februar 2022.  
Denne endringen betyr at Customer Insights-prøveopplevelsen ikke lenger omfatter muligheten til å opprette trakter eller annen rapporteringsfunksjonalitet.

Vi inviterer deg til å utforske og evaluere de mange andre funksjonene i [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), Microsofts kundedataplattform (CDP).    
 
I en overføringsperiode har eksisterende forhåndsversjonsdeltakere fremdeles tilgang til noen forhåndsversjonsfunksjoner:

- Få kode til å instrumentere et nettsted eller en mobilapp 
- Se hendelser og hendelsesegenskaper 
- Forbedre enhetlige profiler med registrerte og finjusterte hendelser for å dra full nytte av alle kundedataene
  
I løpet av overføringsperioden strømmes registrerte hendelser fremdeles til den tilkoblede Data Lake. Når denne funksjonaliteten er deaktivert, stoppes datadeling mellom engasjementsinnsikt og målgruppeinnsikt, og det sendes ingen nye hendelser til det tilkoblede lageret.
Kontakt Microsoft-kontoteamet ditt direkte hvis du har spørsmål til avslutningen av forhåndsversjonsfunksjonen. Kontoteamet holder deg oppdatert om kommende lanseringer. 

## <a name="january-2022-updates"></a>Januar 2022-oppdateringer

Oppdateringene i januar 2022 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Sentimentanalyse for tilbakemelding fra kunder

Customer Insights gir en ny AI-dreven funksjon for å syntetisere kundesentiment og identifisere bestemte forretningsaspekter som salgsmuligheter for målrettede forbedringer. Ved å analysere de skriftlige tilbakemeldingene fra kundene kan du få nøyaktig innsikt til lave kostnader. Sentimentanalyse som drives av NLP-modeller (Natural Language Processing) som genererer to utledede innsikter for hver kunde-ID. En sentimentpoengsum (på –5 til 5) og en liste over aktuelle forretningsaspekter. 

Hvis du vil ha mer informasjon, kan du se [Analysere sentiment i tilbakemeldinger fra kunder (forhåndsversjon)](sentiment-analysis.md).


## <a name="december-2021-updates"></a>Oppdateringer desember 2021

Oppdateringene i desember 2021 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Videresend Customer Insights-logger til Azure Monitor

Customer Insights gir direkte integrasjon med Azure Monitor. Denne funksjonen inkluderer hendelser for sporing av endringer og driftshendelser. Med Azure Monitor-ressurslogger kan du overvåke og sende logger til Azure Storage, Azure Log Analytics, eller strømme dem til Azure Event Hubs.

Hvis du vil ha mer informasjon, kan du se [Logg videresending i Dynamics 365 Customer Insights med Azure Monitor (forhåndsversjon)](diagnostics.md).

### <a name="enrich-customer-profiles-with-engagement-data"></a>Supplere kundeprofiler med engasjementsdata

Bruk data fra Microsoft Office 365 til å forbedre kundekontoprofilene dine med innsikt i engasjementer gjennom Office 365-apper. Engasjementsdataene består av e-post og møteaktivitet, som samles på kontonivå. For eksempel antall e-poster fra en forretningsforbindelse eller antall møter med forretningsforbindelsen. Ingen data om enkeltbrukere deles. Denne suppleringen er tilgjengelig i følgende regioner: Storbritannia, Europa og Nord-Amerika.

Hvis du vil ha mer informasjon, kan du se [Suppler kundeprofiler med engasjementsdata (forhåndsversjon)](enrichment-office.md).

### <a name="advanced-data-unification-features"></a>Avanserte funksjoner for datasamling

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Aktiver konfliktløsningspolicyer på individuelt attributtnivå

Når du dedupliserer kundeoppføringer i en enhet, er det ikke sikkert du trenger å velge en fullstendig oppføring som vinner. Nå kan du slå sammen de beste feltene fra forskjellige oppføringer basert på regler for hvert attributt. Du kan for eksempel velge å beholde den nyeste e-postadressen OG den mest fullstendige adressen fra forskjellige oppføringer. 

Du kan nå definere separate fletteregler for enkeltattributter når du dedupliserer og slår sammen oppføringer i én enkelt enhet. Tidligere kunne du bare velge én enkelt fletteregel (holde oppføringer basert på fullføring av besøksdata), og denne regelen ble brukt på oppføringsnivå for alle attributter. Det er ikke ideelt når noen av dataene du vil beholde, finnes i oppføring A og andre gode data som finnes i oppføring B.

Hvis du vil ha mer informasjon, kan du se [Definere deduplisering på en samsvarsenhet](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="custom-rules-for-matching"></a>Egendefinerte regler for samsvar

Noen ganger må du angi et unntak fra generelle regler for IKKE å samsvare oppføringer. Dette kan skje når flere enkeltpersoner deler nok informasjon slik at systemet samsvarer med dem som én enkelt person. Eksempler på dette kan være etternavn, bo i samme by og dele fødselsdato.

Unntak sikrer at ukorrekt datasamling kan løses i foreningsreglene. Du kan legge til flere unntak i en regel.

Hvis du vil ha mer informasjon, kan du se [Legg til unntak i en regel](match-entities.md#add-exceptions-to-a-rule).

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Tilby ytterligere konfliktløsningspolicyer og aktiver gruppering av attributter

Med denne funksjonen kan du behandle en gruppe felter som én enkelt enhet. Hvis oppføringene for eksempel inneholder feltene Adresse1, Adresse2, Poststed og Postnummer. Vi vil sannsynligvis ikke slå sammen Adresse2 for en annen oppføring, da det kan tenkes at det vil gjøre dataene mer fullstendige.

Du kan nå kombinere en gruppe med relaterte felter og bruke én enkelt flettepolicy på gruppen. 

Hvis du vil ha mer informasjon, kan du se [Kombinere en gruppe felter](merge-entities.md#combine-a-group-of-fields).


## <a name="november-2021-updates"></a>Oppdateringer november 2021

Oppdateringene i november 2021 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="segment-membership-now-available-in-dataverse"></a>Segmentmedlemskap er nå tilgjengelig i Dataverse

Informasjon om segmentmedlemskap for kundeprofiler er nå tilgjengelig i Dataverse sammen med kundeprofiler og innsikt. Dynamics 365-handlingsapper og modelldrevne apper kan bruke disse dataene for å slå opp detaljer om segmentmedlemskap for en gitt kunde.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Aktiviteter støtter detaljer på kontaktnivå for forretningsforbindelser

Du kan nå konfigurere, vise og filtrere aktiviteter for kontakter på tidslinjene for forretningsforbindelsesaktiviteten, slik at det blir en bedre forståelse av hvilke forretningsforbindelseskontakter som deltok i bestemte aktiviteter.

## <a name="october-2021-updates"></a>Oktober 2021-oppdateringer

Oppdateringene i oktober 2021 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="b-to-b"></a>B-til-B

Fra og med oktober 2021 kan du arbeide med forretningsforbindelser og deres relaterte kontaktpersoner i Customer Insights. Før var appen for det meste skreddersydd til individuelle forbrukere. Flere funksjonsområder ble oppdatert for å støtte B-til-B-scenarier i tillegg til en ny miljøtype. Hvis du vil ha en oversikt over støttede B-til-B-funksjoner, kan du se [Arbeide med forretningskontoer i målgruppeinnsikt](work-with-business-accounts.md).

Avsnittene nedenfor fremhever noen av de viktigste områdene som ble tilpasset for å støtte forretningskontoer og individuelle forbrukere.

#### <a name="export-segments-based-on-business-accounts"></a>Eksportere segmenter basert på forretningsforbindelser

Alle segmenteksporter i målgruppeinnsikt er tilgjengelige i konteksten for forretningskontoer. De fleste segmenteksporter krever at ekstra konfigurasjon og [kontaktinformasjon projiseres](segment-builder.md#create-a-new-segment) i de underliggende segmentene for å være gyldige for forretningskontoer. Hvis du vil ha mer informasjon, kan du se [Eksportere segmenter](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Bruke LinkedIn Ads-eksporten med forretningskontoer

LinkedIn Ads-eksporten er nå tilgjengelig for kontakt- og firmamålretting i forbindelse med forretningskontoer. Når du velger firmamålretting som hovedfokus for LinkedIn-eksporten, kan du eksportere segmenter som er bygd på forretningsforbindelser, uten å måtte projisere kontaktinformasjon. Hvis du vil ha mer informasjon, kan du gå til dokumentene om [LinkedIn Ads-eksport](export-linkedin-ads.md) og forskjellen mellom [kontaktmålretting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) og [firmamålretting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Opprette tiltak basert på forretningskontoer og hierarkiet

Måleverktøyet lar deg opprette mål i forretningskontoer og eventuelt bruke hierarkiinformasjonen. Hierarkiinformasjon brukes til å beregne en måling på tvers av en forretningsforbindelse og alle de relaterte underordnede forretningsforbindelsene. Du kan for eksempel opprette målinger som total omsetning for hver gruppe forretningsforbindelser identifisert av hierarkiet. Hvis du vil ha mer informasjon, kan du se [Definere og behandle mål](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Opprette segmenter basert på forretningsforbindelser og hierarkiet

Med segmentverktøyet kan du opprette segmenter med forretningsforbindelser som eventuelt inneholder kontaktinformasjon for hver forretningsforbindelse i et segment. Hvis du har opprettet et kontohierarki, kan du bruke informasjon om forretningsforbindelseshierarkiet i opprettingen av segmenter. Hvis du vil ha mer informasjon, kan du se [Opprette et nytt segment](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Beholde forretningsforbindelsene med grundig innsikt i tendensen deres

Prediksjonsmodellen for kundefrafall støtter nå også forretningsforbindelser. Du kan evaluere risikoen for at frafall ikke bare for en forretningsforbindelse, men for en kombinasjon av en forretningsforbindelse og en produkt- eller servicekategori som de kjøper fra deg. Dette tillegget hjelper deg med å forstå om det er mer sannsynlig at en forretningsforbindelse slutter å kjøpe fra deg generelt eller bare for en bestemt kategori av varer eller tjenester. For ytterligere å hjelpe deg med å bruke denne AI-modellen viser den også årsaker til at en forretningsforbindelse sannsynligvis kommer til å frafalle. Hvis du vil ha mer informasjon, kan du se [Prediksjon for transaksjonsfrafall (forhåndsversjon)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Vise kontaktpersoner for en forretningsforbindelse i kundevisning

Hvis forretningsforbindelser tilordnes til relaterte forretningsforbindelser, viser Customer Insights-appen disse relaterte kontaktene som en del av visningen for kundedetaljer. Hvis du vil ha mer informasjon, kan du se [Kundeprofiler](customer-profiles.md).


## <a name="september-2021-updates"></a>September 2021-oppdateringer

Oppdateringene i september 2021 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="activities"></a>Aktiviteter

- **Forbedringer på tidslinje for aktivitet** Vi har utvidet filtrene for aktivitetstidslinjen for kundeprofiler. I tillegg kan du bruke den nye filterruten til å filtrere etter aktivitetstype og dato. Datoer kan filtreres ved hjelp av forskjellige betingelser. Hvis du vil ha mer informasjon, kan du se [Vise tidslinjer for aktiviteter i kundeprofiler](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relasjoner

- **Relasjon med flere mellomstasjoner** Bruk relasjoner med flere mellomstasjoner når du konfigurerer aktiviteter og definerer relasjoner mellom enheter. Relasjoner med mellomstasjoner bruker en mellomliggende enhet til å koble sammen to enheter. Når du konfigurerer en aktivitet, kan du bruke en relasjon med flere mellomstasjoner til å koble aktivitetsenheten til en mellomliggende enhet og deretter til en kundeenhet. Du kan kombinere relasjoner med flere mellomstasjoner med relasjoner med flere baner. For mer informasjon, se [Relasjon med flere mellomstasjoner](relationships.md#multi-hop-relationship).

- **Relasjon med flere baner** Bruk relasjoner med flere baner når du konfigurerer aktiviteter og definerer relasjoner mellom enheter. Relasjoner med flere baner relaterer en kildeenhet til mer enn én enhet. Når du konfigurerer en aktivitet, kan du bruke en relasjon med flere baner til å koble aktivitetsenheten til mer enn én kundeenhet. Du kan kombinere relasjoner med flere baner med relasjoner med flere mellomstasjoner. For mer informasjon, se [Relasjon med flere baner](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Oppdateringer for august 2021

Oppdateringene i juli og august 2021 inkluderer en ny funksjon, ytelsesoppgraderinger og feilrettinger.

### <a name="extensibility"></a>Utvidbarhet

- **Eksporter segmenter til Kalviyo** Vi har utvidet [eksportdestinasjonene våre til å inkludere Klaviyo](export-klaviyo.md). Du kan nå eksportere segmenter for å opprette kampanjer, utføre e-postmarkedsføring og bruke bestemte kundegrupper med Kalviyo. 


## <a name="june-2021-updates"></a>Oppdateringer i juni 2021

Oppdateringene i juni 2021 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="data-ingestion"></a>Datainntak

- **Forbedrede fremdriftsoppdateringer for dataforening** Du kan nå vise mer detaljerte, forbedrede dynamiske statusoppdateringer i trinnene for [datasammenslåingsprosessen](data-unification.md). Med denne funksjonen kan du holde oversikt over den detaljerte fremdriften for å forstå prosessflyten og iverksette tiltak hvis et trinn trenger oppmerksomhet.

### <a name="extensibility"></a>Utvidbarhet

- **Eksporter segmenter og andre data til Salesforce Marketing Cloud** Vi har utvidet eksportdestinasjonene våre til å inkludere [Salesforce Marketing Cloud](export-salesforce.md). Du kan nå eksportere segmenter og andre typer data til Salesforce Marketing Cloud gjennom en merket SFTP-eksport. Dataimport kan automatiseres fullstendig i Salesforce og brukes til å opprette mer effektive markedsføringskampanjer.  
 
- **Eksporter segmenter til ActiveCampaign** Vi har utvidet eksportdestinasjonene våre til å inkludere [Aktiv kampanje](export-active-campaign.md). Du kan nå eksportere segmenter for å generere kampanjer, kjøre e-postmarkedsføring og arbeide med bestemte kundegrupper i ActiveCampaign.
 
- **Eksporter segmenter til Sendinblue** Vi har utvidet eksportdestinasjonene våre til å inkludere [Sendinblue](export-sendinblue.md). Du kan nå eksportere segmenter for å generere kampanjer, kjøre e-postmarkedsføring og arbeide med bestemte kundegrupper med Sendinblue.
 
### <a name="ux-updates"></a>UX-oppdateringer 

- **Side for nye og forbedrede kunder og profildetaljer** Vi har redesignet Kunder-siden og profildetaljsidene for forbedret brukeropplevelse og bedre ytelse. Med disse endringene kan du vise, sortere, søke etter og filtrere kunder. Filtre er nå representert i nettadressen for å dele søkeresultatene sømløst med andre brukere. Søkeresultater kan også lagres som et segment.    
  Detaljsiden for kundeprofiler grupperer nå data i ulike underavsnitt, for eksempel demografiske data, ID-er og andre profilattributter for forbedret lesbarhet. Andre deler på profildetaljsiden er nå mer interaktive. Aktivitetsdelen tillater for eksempel nå filtrering og sortering.


## <a name="may-2021-updates"></a>Mai 2021-oppdateringer

Oppdateringene i mai 2021 omfatter flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="data-ingestion"></a>Datainntak

- **Vis eller endre metadata eller enhetsdefinisjon når du knytter til data fra Azure Data Lake Storage** Du kan nå vise og redigere metadata eller enhetsdefinisjon i målgruppeinnsikt når du knytter til data fra en Common Data Model-mappe i Azure Data Lake Storage. Denne funksjonen gir tilbakemelding, modellvalidering og feilkontroll i sanntid. Den gjør at du kan redigere både model.json og manifest.json sømløst.

### <a name="extensibility"></a>Utvidbarhet

- **Forbedrede segmenteksporter, egendefinert tidsplan og duplisering** Du kan nå [se alle eksporter for et bestemt segment](export-destinations.md#view-exports-and-export-details) i en liste. Denne nye visningen hjelper deg å styre hvordan et bestemt segment brukes, og å tilpasse eksisterende eller opprette nye rapporter.    
  Du kan [definere egendefinerte oppdateringsplaner](export-destinations.md#schedule-and-run-exports) for individuelle eksporter eller flere eksporter samtidig. Hittil har alle eksporter blitt kjørt med hver systemoppdatering.    
  Du kan nå starte basert på en eksisterende rapport for å spare litt tid, i stedet for å opprette en ny eksport fra grunnen av.

- **Eksporter segmenter til Microsoft Advertising** Vi har utvidet eksportmålene til å omfatte Microsoft Advertising. Opprett Customer Match-målgrupper på Microsoft Advertising med de enhetlige kundeprofildataene, og bruk disse målgruppene i reklamekampanjene dine. Hvis du vil ha mer informasjon, kan du se [Eksporter segmenter til Microsoft Advertising](export-microsoft-advertising.md).

- **Eksporter segmenter til LinkedIn-annonser** Vi har utvidet eksportmålene våre slik at de omfatter LinkedIn-annonser, og gjør at du kan låse opp kontaktmålretting samt firmamålretting via LinkedIn ved å eksportere de enhetlige kundeprofildataene. Hvis du vil ha mer informasjon, kan du se [Eksportere segmenter til LinkedIn-annonser](export-linkedin-ads.md).


- **Eksporter segmenter til Omnisend** Vi har utvidet eksportmålene til å omfatte Omnisend. Bruk segmentene som er opprettet i målgruppeinnsikt, til å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Omnisend. Hvis du vil ha mer informasjon, kan du se [Eksportere segmenter til Omnisend](export-omnisend.md).

### <a name="predictions"></a>Prediksjoner

- **Brukbarhetsrapport for inndata** Brukbarhetsrapporten for inndata byr på en konsolidert visning av feilene og advarslene som de bruksklare prediksjonene kan generere. Den gir også anbefalinger om hvordan du kan forbedre modellytelsen.    
  Rapporten er tilgjengelig etter at en modell har fullført opplæringsprosessen. Den opprettes for hver modell separat, uavhengig av om den ble fullført eller ikke.
  Denne funksjonen er for øyeblikket bare tilgjengelig for modellen for transaksjonsfrafall. Hvis du vil ha mer informasjon, kan du se [Brukbarhetsrapport for inndata](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relasjoner

- **Relasjonsvisualisering** Visningen for relasjonsvisualisering gjør at du kan se alle eksisterende relasjoner mellom enheter og kardinaliteten deres. Relasjoner er nå organisert i grupper: brukeropprettede relasjoner, systemrelasjoner og arvede relasjoner. Du kan også eksportere en visning som et bilde. Hvis du vil ha mer informasjon, kan du se [Vise relasjoner](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>April 2021-oppdateringer

Oppdateringene i april 2021 inkluderer flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="data-unification"></a>Datasamling
 
- **Forbedret sammenslåingsopplevelse for dataforening**    
  
   Vi har nå en forbedret brukeropplevelse i sammenslåingskonfigurasjonen for dataforeningsprosessen. Endringene inkluderer intuitiv rekkefølge av de sammenslåtte feltene og detaljert statistikk om kombinerte felter og enkeltdatabasefelter.

- **Ordne enheten på nytt og konfigurer alle kildeoppføringer i kundeenheten**  
      
   Du kan nå endre rekkefølgen på og fjerne enheter fra en eksisterende sammensettingsplan i dataforeningsprosessen. Det gir fleksibilitet til å endre rekkefølgen på enhetene i samsvarsprosessen i henhold til forretningsbehov. I tillegg inkluderer vi alle oppføringer som ikke samsvarer, i den endelige *kundeenheten*, som gjør det mulig for dem å definere datasettdefinisjonen for kundeprofilen.

### <a name="enrichments"></a>Suppleringer

 - **Ny supplering: Forbedrede adresser**    
  
   Det er en glede å introdusere en ny supplering for å forbedre adressene i kundedataene. Adresser i dataene kan være ustrukturerte, ufullstendige eller feil. Denne funksjonen bruker Microsofts modeller til å normalisere og forbedre adressene i Common Data Model-formatet for bedre nøyaktighet og innsikt.
 
   Hvis du vil ha mer informasjon, kan du se [Supplering av kundeprofiler med forbedrede adresser](enrichment-enhanced-addresses.md).

- **Veiledet konfigurasjonsopplevelse for suppleringer**    
  
   Vi har sett på konfigurasjonsopplevelsen for suppleringer på nytt med enkel, veiledet opplevelse. Du har nå en tydelig trinnvis prosess for å opprette og redigere suppleringer.
 
   I tillegg har vi separert konfigurasjonen av tilkoblinger for tredjepartssuppleringer for å gjøre det mulig at den samme tilkoblingen kan brukes av flere suppleringer. Bare administratorer kan konfigurere nye tilkoblinger, men de opprettede tilkoblingene er tilgjengelige for både administratorer og bidragsytere.    

   Hvis du vil ha mer informasjon, kan du se [Oversikt over tilkoblinger](connections.md).

- **Flere suppleringer av samme type**    
  
   Nå tillater vi at brukere oppretter og administrerer flere suppleringer av samme suppleringstype. Du kan for eksempel nå opprette to separate adressesuppleringer for å supplere to forskjellige kundesegmenter. Grensene gjelder for hvor mange suppleringer av samme type som kan opprettes, og varierer avhengig av suppleringstypen.
  
   Hvis du vil ha mer informasjon, kan du se [Supplering for kundeprofiler](enrichment-hub.md).

## <a name="march-2021-updates"></a>Mars 2021-oppdateringer

Oppdateringene i mars 2021 inkluderer flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="activities"></a>Aktiviteter

- **Aktivitetsveiviser og semantiske typer**

   Vi har forbedret og oppdatert erfaringen med aktivitetstilordning for å veilede og forenkle opprettingen av aktivitetstilordning. I denne nye opplevelsen får brukerne en veiledet opplevelse som hjelp til å fullføre hvert trinn i prosessen. På aktivitetstilordningstrinnet, i tillegg til å velge fra mange aktivitetstyper, kan brukeren velge å semantisk tilordne data for *Abonnement* og/eller *SalesOrderLine* til bransjestandardskjemaer, som kan brukes for nedstrømsforbruk.   

   Hvis du vil ha mer informasjon, kan du se [Kundeaktiviteter](activities.md).

### <a name="data-ingestion"></a>Datainntak

- **Koble til lokale datakilder ved hjelp av Power Platform-dataflyter og -gatewayer** Vi vil gjerne kunngjøre forhåndsversjonen av Power Platform-dataflyter og lokal tilkobling ved hjelp av gatewayer i Customer Insights med et tilknyttet Power Platform- eller Dataverse-miljø. Alle nye datakilder som er opprettet i et Customer Insights-miljø med et koblet Dataverse-miljø, bruker som standard Power Platform-dataflyter med lokal datatilkobling og et rikt sett med koblinger og transformasjonsfunksjoner.

### <a name="extensibility"></a>Utvidbarhet

- **Eksporter organisert i tilkoblinger og eksporter** Vi har endret navnet på **Eksportmål**-siden til **Tilkoblinger** og lagt til en egen side for **Eksporter**. Som en del av denne oppdateringen vil vi gjøre eksisterende eksporter om til par av en tilkobling og en eksport ved hjelp av tilkoblingen. Administratorer har nå tydeligere oversikt over utgående data på **Tilkoblinger**-siden. Alle brukerroller har tilgang til **Eksporter**-siden, men bare administratorer kan velge å tillate bidragsytere å redigere bestemte eksporter med delte tilkoblinger.     
  Hvis du vil ha mer informasjon, kan du se [Oversikt over tilkoblinger](connections.md) og [Oversikt over eksporter](export-destinations.md).

- **Eksporter segmenter til Campaign Monitor** Vi har utvidet eksportmålene til å inkludere Campaign Monitor. Du kan nå eksportere segmenter fra Customer Insights til Campaign Monitor-lister og bruke dem som basislinje for markedsføringskampanjene.    
   Hvis du vil ha mer informasjon, kan du se [Eksportere til Campaign Monitor](export-campaign-monitor.md).

- **Eksporter segmenter til Constant Contact** Vi har utvidet eksportmålene til å inkludere Constant Contact. Du kan nå eksportere segmenter fra Customer Insights til Constant Contact-lister og bruke dem som basislinje for markedsføringskampanjene.   
   Hvis du vil ha mer informasjon, kan du se [Eksportere til Constant Contact](export-constant-contact.md).

- **Eksporter segmenter til RollWorks** Vi har utvidet eksportmålene til å inkludere RollWorks. Du kan nå eksportere segmenter fra Customer Insights til RollWorks-målgrupper og bruke dem som grunnlinje for B-til-B-annonseringen.    
   Hvis du vil ha mer informasjon, kan du se [Eksportere til RollWorks](export-rollworks.md).

- **Eksporter segmenter til Snapchat** Vi har utvidet eksportmålene til å inkludere Snapchat. Du kan nå eksportere segmenter fra Customer Insights til Snapchat-målgrupper og bruke dem som basislinje for reklame.     
   Hvis du vil ha mer informasjon, kan du se [Eksportere til Snapchat](export-snapchat.md).

### <a name="predictions"></a>Prediksjoner

- **Bruk produktfiltre i prediktive produktanbefalinger** Vi har lagt til muligheten til å bruke produktfiltre i produktanbefalingsmodellen. Du kan nå opprette en prediksjon som bare bruker et delsett av produktene.    
   Hvis du vil ha mer informasjon, kan du se [Konfigurere produktfiltre](predict-product-recommendation.md#configure-product-filters).

- **Opprette segmenter fra modellprediksjoner** Vi har lagt til en rask måte å opprette segmenter på ved hjelp av resultatene av en prediksjonsmodell. På siden for modellresultater kan du enkelt opprette et nytt segment ved å velge det nye **Opprett segment**-alternativet.    
  Hvis du vil ha mer informasjon, kan du se [Opprette et segment basert på en prediksjonsmodell](prediction-based-segment.md).

- **Forklaringer på produktanbefalinger** Vi har lagt til informasjon om nøkkelfaktorene som AI-modellen har lært, for å generere produktanbefalinger og i hvilken grad disse faktorene bidrar til produktanbefalingene. Denne informasjonen legges til i skjermbildet for modellresultater.    
   Hvis du vil ha mer informasjon, kan du se [Gå gjennom en prediksjonsstatus og resultater](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Oppdateringer februar 2021

Oppdateringene i februar 2021 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

#### <a name="extensibility"></a>Utvidbarhet

- **Eksporter segmenter til AdRoll**

  Vi har utvidet eksportmålene til å inkludere AdRoll. Du kan nå eksportere segmenter fra Customer Insights til AdRoll-målgrupper og bruke dem som utgangspunkt for annonseringen. Hvis du vil ha mer informasjon, kan du se [Kobling for AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmenter
 
- **Dupliser et segment**
  
  Hvis du vil opprette et nytt segment basert på et eksisterende, kan du duplisere et segment og redigere det dupliserte segmentet for å finjustere det ytterligere. 

- **Legg til flere attributter i et segment**

  Du kan nå inkludere attributter i segmentutdataene, selv om disse attributtene ikke er en del av kundeprofilen. Du kan for eksempel inkludere abonnements-ID-er i et segment, selv om det er en del av abonnementsenheten som har en M:1-relasjon med kundeenheten. Så lenge attributtet tilhører en enhet som er relatert til kundeenheten, kan du nå inkludere disse attributtene.  

#### <a name="predictions"></a>Prediksjoner

- **Opprett prediktive produktanbefalinger**

  Det å forstå hva kunder er interessert i å kjøpe, er et av de første trinnene som kreves for å forbedre omsetningen og bygge kundelojalitet ved hjelp av tilpassing og engasjement. Ved å gi anbefalinger for produkter som ikke er innrettet etter kundens interesser, kan du skape en følelse av distansering mellom kunden og bedriften, og til slutt begrense den totale potensielle inntekten og opplevelsen for en kunde. 

  Ved hjelp av dine egne data kan du nå lage prognoser for hvilke produkter kundene sannsynligvis vil kjøpe i fremtiden. Hvis du vil ha mer informasjon, kan du se [Produktanbefalingsprediksjon](predict-product-recommendation.md).

#### <a name="system-administration"></a>Systemadministrasjon

- **Kopier miljø støtter flere typer datakilder**

  Administratorer kan kopiere miljøkonfigurasjoner til et nytt miljø i samme organisasjon. Denne funksjonen utvider kopieringsmiljøfunksjonaliteten for tilfeller der datakilder basert på en administrert Microsoft Dataverse-datasjø eller en Common Data Model-mappe brukes.

## <a name="january-2021-updates"></a>Januar 2021-oppdateringer

Oppdateringene i januar 2021 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

#### <a name="extensibility"></a>Utvidbarhet

- **Utvidet funksjonalitet og forbedret ytelse for SFTP-eksport** Du kan nå eksportere alle utdataenheter fra Customer Insights til en SFTP-vert. Tidligere var eksport begrenset til segmentenheter. I tillegg gir ytelsen av SFTP-eksporten mer datavolum på kortere tid, avhengig av ytelsen til SFTP-verten.    
  Hvis du vil ha mer informasjon, kan du se [Kobling for SFTO (forhåndsversjon)](export-sftp.md).  

#### <a name="segments"></a>Segmenter

- **Maskinlæringsbaserte foreslåtte segmenter for å forbedre måledata** Det finnes en ny måte å oppdage og opprette segmenter på. Systemet bruker en modell for kunstig intelligens til å foreslå segmenter som kan bidra til å forbedre en KPI (mål) du allerede sporer. Vi viser omfanget av innflytelse på attributter som du velger, på et mål eller et annet hovedattributt. Denne informasjonen hjelper deg med å finne potensielle segmenter som presenterer salgsmuligheter.    
  Hvis du vil ha mer informasjon, kan du se [Foreslåtte segmenter (forhåndsversjon)](suggested-segments.md).

#### <a name="data-unification"></a>Datasamling

- **Forbedret samsvarsopplevelse** I området for dataforening ble samsvarsopplevelsen oppdatert. Den lar deg konfigurere og vise samsvarsreglene, inkludert detaljert statistikk for å forklare mer om hvordan samsvar fungerer. Det finnes alternativer for å deaktivere en samsvarsregel, slik at den ikke lenger er aktiv, samtidig som du beholder konfigurasjonen, drar og slipper samsvarsregler og mer.
  Hvis du vil ha mer informasjon, kan du se [Samsvarsenheter](match-entities.md).

- **Dedupliseringsutdata fra samsvarsprosessen er tilgjengelige fordi en enhet** Dedupliseringsprosess som sendes fra samsvarsprosessen skrives nå til en separat enhet for videre analyse. Denne enheten består av feltene som brukes i dedupliseringsprosessen og vinneroppføringen og de tilhørende alternative oppføringene som slås sammen med vinneroppføringen.
  Hvis du vil ha mer informasjon, kan du se [Dedupliseringsutdata som en enhet](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Systemadministrasjon

- **Del data sømløst til Microsoft Dataverse** Du kan nå dele Customer Insights-utdata med Microsoft Dataverse-programmer ved hjelp av Microsoft Dataverse-administrert datasjø. Når du har knyttet et Dataverse-miljø til Customer Insights, kan du aktivere datadeling.
  Du finner mer informasjon under [Behandle miljøer](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]