---
title: Nye og kommende funksjoner
description: Informasjon om nye funksjoner, forbedringer og feilrettinger.
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: e501df8701493a1c5b83c4d06da3a73fd226165f
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673869"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Nyheter i funksjonaliteten for målgruppeinnsikt i Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Vi har gleden av å kunngjøre de nyeste oppdateringene! Denne artikkelen oppsummerer funksjoner i offentlig forhåndsversjon, generelle tilgjengelighetsforbedringer og funksjonsoppdateringer. Hvis du vil se de langsiktige funksjonsplanene, kan du se [Dynamics 365 og Power Platform-utgivelsesplanene](/dynamics365/release-plans/).

Vi ruller ut oppdateringer for hver region. Enkelte områder kan se funksjoner før andre. Med mindre det er angitt noe annet, trenger du ikke å gjøre noe, og vi oppdaterer appen automatisk uten nedetid.

> [!TIP]
> For å sende inn og stemme på funksjonsforespørsler og produktforslag, går du til [ideportalen for Dynamics 365-apper](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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