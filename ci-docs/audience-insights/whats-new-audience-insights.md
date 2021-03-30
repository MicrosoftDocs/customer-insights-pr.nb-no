---
title: Nye og kommende funksjoner
description: Informasjon om nye funksjoner, forbedringer og feilrettinger.
ms.date: 03/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 96c0b871eeaaf0976e5c718f37f883f4410977dc
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598458"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Nyheter i funksjonaliteten for målgruppeinnsikt i Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Vi har gleden av å kunngjøre de nyeste oppdateringene! Denne artikkelen oppsummerer funksjoner i offentlig forhåndsversjon, generelle tilgjengelighetsforbedringer og funksjonsoppdateringer. Hvis du vil se de langsiktige funksjonsplanene, kan du se [Dynamics 365 og Power Platform-utgivelsesplanene](/dynamics365/release-plans/).

Du kan også se på følgende video for å finne ut mer om hvilke funksjoner som er planlagt de siste seks månedene.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Vi ruller ut oppdateringer for hver region. Enkelte områder kan se funksjoner før andre. Med mindre det er angitt noe annet, trenger du ikke å gjøre noe, og vi oppdaterer appen automatisk uten nedetid.

> [!TIP]
> For å sende inn og stemme på funksjonsforespørsler og produktforslag, går du til [ideportalen for Dynamics 365-apper](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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

  Administratorer kan kopiere miljøkonfigurasjoner til et nytt miljø i samme organisasjon. Denne funksjonen utvider Kopier miljø-funksjonaliteten for tilfeller der datakilder basert på en Common Data Service-datasjø eller en Common Data Model-mappe brukes.

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


## <a name="december-2020-updates"></a>Oppdateringer desember 2020

Oppdateringene i desember 2020 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="new-and-updated-features-in-december-2020"></a>Nye og oppdaterte funksjoner i desember 2020

#### <a name="data-enrichment"></a>Datasupplering

- **Forbedrede affinitetssuppleringer for merke og interesse**
  
  Vi har forenklet resultatene for tilknytning slik at de blir lettere å forstå og bruke. Du kan nå raskt identifisere kunder basert på hvor mye affinitet de har for et bestemt merke eller en bestemt interesse.

  I tillegg har vi lagt til nye konfigurasjonsalternativer for bedre å kontrollere hvordan du vil at kundeprofilene dine skal suppleres. 

  Hvis du vil ha mer informasjon, kan du se [Supplere kundeprofiler med merke- og interesseaffiniteter](enrichment-microsoft-graph.md).

- **Styre hvilke profiler som skal suppleres**

  Du kan nå bare supplere et delsett av kundeprofilene med alternativet for å velge en segmentenhet i stedet for standard kundeenhet. Opprett et segment med kundeprofilene du vil supplere, og velg det i suppleringskonfigurasjonen for kundedatasettet.
  Denne funksjonen er for øyeblikket bare tilgjengelig for suppleringer gitt av Experian og HERE Technologies. Vi skal snart aktivere denne muligheten for flere suppleringer.

  Hvis du vil ha mer informasjon, kan du se [Suppler kundeprofiler med demografi fra Experian](enrichment-experian.md) eller [Supplering av kundeprofiler med HERE Technologies](enrichment-here.md).

#### <a name="extensibility"></a>Utvidbarhet

- **Aktiver segmentene gjennom Autopilot**

  Eksporter segmenter til Autopilot, og bruk dem til markedsføringsformål. Hvis du vil ha mer informasjon, kan du se [Kobling for Autopilot (forhåndsversjon)](export-autopilot.md).

- **Aktiver segmentene gjennom SendGrid**

  Eksporter segmenter til SendGrid, og bruk dem til markedsføringsformål. Hvis du vil ha mer informasjon, kan du se [Kobling for SendGrid](export-sendgrid.md).

#### <a name="system-administration"></a>Systemadministrasjon

- **Oppdatert opplevelse av miljøadministrasjon**
  
  Du kan nå opprette, redigere, slette og tilbakestille miljøer direkte fra miljøvelgeren i apphodet. 
  
  I tillegg festes miljøet du bruker, øverst i miljøpanelet, slik at du ikke trenger å søke etter det lenger.

  Du finner mer informasjon under [Behandle miljøer](manage-environments.md).

## <a name="november-2020-updates"></a>Oppdateringer november 2020

Oppdateringene i november 2020 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="new-and-updated-features-in-november-2020"></a>Nye og oppdaterte funksjoner i november 2020

#### <a name="data-enrichment"></a>Datasupplering

- **Ta med dine egne suppleringsdata via egendefinert SFTP-import (Secure File Transfer Protocol)**
  
  Med egendefinert SFTP-import kan du supplere data som ikke trenger å gå gjennom dataforening. Finn ut mer om egendefinert SFTP-import.

  Hvis du vil ha mer informasjon, kan du se [Supplere kundeprofiler med egendefinerte data (forhåndsversjon)](enrichment-SFTP-custom-import.md).
 
- **Supplere kundedataene med stedsdata fra HERE Technologies**

  Ved hjelp av tjenester for datasupplering fra HERE Technologies kan du bygge et mer nøyaktig stedsforståelse av kundene med adressenormalisering, bredde- og lengdegradsuttrekking og så videre. Finn ut mer om supplering med HERE Technologies.

  Hvis du vil ha mer informasjon, kan du se [Supplering av kundeprofiler med HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Datasamling

- **Fleksibilitet til å aktivere dataprofilering på utvalgte enheter og felter fra lagringskontoen**

  Du kan angi hvilke dataenheter og felter fra en Common Data Model-mappe i Azure Data Lake-lagringskontoen du vil skal aktivere dataprofilering som en del av datainntaksprosessen.

  Hvis du vil ha mer informasjon, kan du se [Koble til en Common Data Model-mappe](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Utvidbarhet

- **Aktiver segmentene gjennom Google Ads**

  Eksporter segmenter fra Google Ads-målgruppelister, og bruk disse listene til å annonsere på Google Search, Google Display Network, YouTube og Gmail. Lær mer om aktivering av segmenter gjennom Google Ads.

  Hvis du vil ha mer informasjon, kan du se [Kobling for Google Ads](export-google-ads.md).

- **Aktiver segmentene gjennom Marketo**

  Eksporter segmenter til Marketo-målgrupper, og bruk disse målgruppene for markedsføringsautomatisering. Lær mer om aktivering av segmenter gjennom Marketo. 

  Hvis du vil ha mer informasjon, kan du se [Kobling for Marketo](export-marketo.md).

- **Aktiver segmentene gjennom DotDigital**

  Eksporter segmenter til DotDigital, og bruk dem til markedsføringsformål. Lær mer om aktivering av segmenter gjennom DotDigital. 

  Hvis du vil ha mer informasjon, kan du se [Kobling for DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Prognoser

- **Forutse transaksjonelt frafall**

  Ved hjelp av funksjonen for transaksjonelt frafallsprediksjon kan du, uten hjelp av en datatekniker, forutse sannsynligheten for at en kunde slutter å kjøpe produkter eller tjenester.  Ved hjelp av prediksjonspoengsummen kan du kombinere annen informasjon om kunder, for eksempel kundeverdi, for å skape segmenter med høy frafallsrisiko eller kunder med høy verdi. Bruk dette segmentet til å målrette kunder direkte ved hjelp av markedsføringsaktiviteter, kundestøtte og andre scenarier for å redusere frafallsrisikoen.
 
  Konfigurer definisjonen av frafall som et tidsbasert vindu som er spesifikt for virksomheten, og definer når kunder anses som frafalt. Et dagligforhandler kan for eksempel vurdere en kunde som frafalt hvis de ikke har kjøpt noe i løpet av de siste 30 dagene.
 
  Etter hvert som du fortsetter å opprette prediksjonen, vil vi veilede deg om hvilke data som kreves, og du kan tilordne data om virksomheten til felt som er nødvendige for å forutsi frafallet for kundene. Du kan også angi en tidsplan for å lære opp modellen på nytt basert på ny informasjon i systemet for å tilpasse den til endrede forretningssituasjoner.
 
  Hvis du vil ha mer informasjon, kan du se [Transaksjonell frafallsprediksjon (forhåndsversjon)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Systemadministrasjon

- **Tilbakestill miljøet**

  Tilbakestill alt i et miljø av en valgt forekomst for å starte på nytt.

  Hvis du vil ha mer informasjon, kan du se [Tilbakestille et eksisterende miljø](manage-environments.md#reset-an-existing-environment).


- **Koble til Azure Data Lake-lagringskontoen ved hjelp av en tjenestekontohaver**

  Skriv utdata til og les data fra lagringskontoen din ved hjelp av en Azure-tjenestekontohaver. Eksisterende koblinger til lagringskontoen kan fortsette å bruke kontonøkkelen. De har også et oppgraderingsalternativ for å bruke tjenestekontohaveren videre fremover. Nye tilkoblinger blir basert på godkjenningsmetoden via tjenestekontohaver for lagringskontoen.

  Hvis du vil ha mer informasjon, kan du se [Koble til en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver for målgruppeinnsikt](connect-service-principal.md).

## <a name="october-2020-updates"></a>Oktober 2020-oppdateringer

Oppdateringene i oktober 2020 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="new-and-updated-features-in-october-2020"></a>Nye og oppdaterte funksjoner i oktober 2020

#### <a name="extensibility"></a>Utvidbarhet

- **Eksporter til Mailchimp**

Eksporter segmenter til eksisterende målgruppelister i Mailchimp for å tilby en tilpasset e-postopplevelse til kundene.

Hvis du vil ha mer informasjon, kan du se [Kobling for Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Datasupplering

- **Deduplisere kildeoppføringene i en samsvarsenhet**

Angi dedupliseringsregler på enheter som brukes i samsvarsprosessen, for å identifisere duplikate oppføringer. Slå dem sammen i én oppføring, og koble alle kildeoppføringene til denne sammenslåtte oppføringen. Denne dedupliserte oppføringen brukes deretter i samsvarsprosessen på tvers av enheter.

Hvis du vil ha mer informasjon, kan du se [Definere deduplisering på en samsvarsenhet](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Systemadministrasjon

- **Orkestrering: Nytt oppdateringsalternativ under sammenslåing**

Frem til nå, da du kjørte sammenslåingsprosessen, kjørte systemet alle prosesser nedstrøms som er avhengige av sammenslåingen og påfølgende prosesser. Nå kan du kontrollere utdataene for sammenslåingsprosessen (den enhetlige kundeenheten) før du bruker dem i prosesser nedstrøms, for eksempel segmenter eller mål.
På sammenslåingssiden kan du nå velge å kjøre bare sammenslåingstrinnet og kjøre bare denne prosessen. Hvis du vil oppdatere alle prosessene nedstrøms også, kan du velge å kjøre sammenslåings- og nedstrømsprosessene. 

## <a name="september-2020-updates"></a>September 2020-oppdateringer

Oppdateringene i september 2020 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="new-and-updated-features-in-september-2020"></a>Nye og oppdaterte funksjoner i september 2020

#### <a name="activities"></a>Aktiviteter

- **Intelligent prediksjon av semantiske attributt**

Denne nye funksjonen forutsier de semantiske typene av inndataattributter som sendes til datasamlingsprosessen. Den bruker maskinlæringmodeller som forbedrer nøyaktigheten og sparer tid.

#### <a name="enrichments"></a>Suppleringer

- **Demografisupplering fra Experian**

Demografisuppleringen fra Experian er nå tilgjengelig i forhåndsversjon. Experian er en global leder innen forbruker- og forretningskredittrapportering og markedsføringstjenester. Ved hjelp [Experians datasuppleringstjenester](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) kan du bygge opp en dypere forståelse av kundene ved å supplere kundeprofilene med demografiske data, for eksempel husholdningsstørrelse, inntekt og så videre.

Hvis du vil bruke denne funksjonen, må du ha et aktivt Experian-abonnement.

Hvis du vil ha mer informasjon, kan du se [Supplere kundeprofiler med demografidata fra Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Systemadministrasjon

- **Oppgavedetaljer-ruten**

I ruten for oppgavedetaljer kan du se detaljer om oppgaver som systemet kjører. Det er en nyttig måte å identifisere problemer med konfigurasjonen og finne løsninger på.
Se gjennom feilmeldingene se hvordan du kan løse potensielle problemer.
 
- **Behandle informasjon lagt til på flere sider**

Denne forbedringen legger til informasjon om statusen for enhetene på siden **Enheter** og **Kunder**.
 
I tillegg kan du finne informasjon om fremdriften til prosesser, sammen med oppgavedetaljene, på begge disse sidene.

- **Forbedringer på systemstatussiden**

Vi har forbedret strukturen i statusdetaljtabellen i **System** > **Status** når du ser gjennom dataeksporter.
 
I tillegg er feil i **Detaljer**-kolonnen nå mer detaljerte og handlingsrettede. 
 
- **Avbryt gjenoppretter jobben tilbake til forrige tilstand**

Når du avbryter en oppgave, for eksempel i samsvarsprosessen, tilbakestilles den til den forrige tilstanden. Hvis for eksempel samsvarsprosessen ble fullført i går og du annullerer den i dag, tilbakestilles den til i gårsdagens tilstand.


## <a name="august-2020-updates"></a>Oppdateringer for august 2020

Oppdateringene i august 2020 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="new-and-updated-features-in-august-2020"></a>Nye og oppdaterte funksjoner i august 2020

#### <a name="data-unification"></a>Datasamling

- **Forbedret opplevelse for kartfasen under datasamling**

  Opplevelsen i kartfasen i datasamlingsprosessen gjør det mulig å velge enheter, attributter og definere semantikk på en mer sømløs måte.

  Endringene omfatter:
  
  - færre nødvendige samhandlinger for å legge til enheter og felt
  - forbedrede søkefunksjoner på kartsiden
  - visuell og enkel identifisering av den foreslåtte felttypen

#### <a name="enrichment"></a>Supplering

- **Supplering av interesseaffiniteter er tilgjengelig på flere markeder**

  Vi utvider tilgjengeligheten av supplering av interesseaffiniteter utover USA til fem andre markeder: Canada, Australia, Storbritannia, Frankrike og Tyskland. Med denne utvidelsen kan du supplere kundedataene med flere interesser som gjelder for disse markedene. Vi supplerer også kundeprofilene i disse markedene ved å bruke lokale rettighetsbeskyttede data fra Microsoft Graph.
  Hvis du vil ha mer informasjon, kan du se [Supplere kundeprofiler med merke- og interesseaffiniteter](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Oppdateringer i juli 2020

Oppdateringene i juli 2020 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="new-and-updated-features-in-july-2020"></a>Nye og oppdaterte funksjoner i juli 2020

#### <a name="extensibility"></a>Utvidbarhet

- **Power Automate-utløser for fullført samlingsprosess**

  Vi har utvidet utløserne våre for Power Automate og lar deg opprette en varsling eller en handling når en oppdatering av samlingsprosessen (tilordning, samsvar, sammenslåing) er fullført.    
  Hvis du vil ha mer informasjon, kan du se [Power Automate-kobling](export-power-automate.md)

#### <a name="enrichment"></a>Supplering

- **Supplering av merkeaffiniteter er tilgjengelig på flere markeder**

  Vi utvider tilgjengeligheten av supplering av merkeaffiniteter utover USA til fem andre markeder: Canada, Australia, Storbritannia, Frankrike og Tyskland. Med denne utvidelsen kan du supplere kundedataene med lokale merker i disse markedene. Vi supplerer også kundeprofilene i disse markedene ved å bruke lokale rettighetsbeskyttede data fra Microsoft Graph.
  Hvis du vil ha mer informasjon, kan du se [Supplere kundeprofiler med merke- og interesseaffiniteter](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Oppdateringer i juni 2020

Oppdateringene i juni 2020 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="new-and-updated-features-in-june-2020"></a>Nye og oppdaterte funksjoner i juni 2020

#### <a name="enrichment"></a>Supplering

- **Supplering av firmadata fra Leadspace**
  
  Definer felt i enhetlige kundeprofiler som brukes til å slå opp relaterte firmadata fra Leadspace. Når suppleringsprosessen er kjørt, får B2B-profiler flere attributter, blant annet firmastørrelse, sted, bransje og mer.    
  Dette samarbeidet gjør at du kan forbedre kvaliteten på dataene med inndata fra tredjepartstjenester. Hvis du vil bruke denne suppleringen, må du ha en lisens fra Leadspace for å få tilgang til B2B-firmadataene. Systemet vil bruke denne lisensen til å holde dataene dine supplert vedvarende.    
  Hvis du vil ha mer informasjon, kan du se [Supplering av firmaprofiler med Leadspace](enrichment-leadspace.md).

- **Side for suppleringshub**

  All tilgjengelig datasupplering fra første- og tredjepartsleverandører av supplering blir konfigurert på samme sted. Konfigurasjon av datasupplering er en sømløs opplevelse som administreres fra et felles sted.    
  Hvis du vil ha mer informasjon, kan du se [Supplering for kundeprofiler](enrichment-hub.md).

- **Separat supplering av merke- og interesseaffinitet**

  Merke- og interesseaffinitetene er nå tilgjengelige som to uavhengige suppleringer. Separate suppleringer gir deg fleksibiliteten til å konfigurere og administrere dem enkeltvis, avhengig av forretningskravene eller -behovene.    
  Hvis du vil ha mer informasjon, kan du se [Supplere kundeprofiler med merke- og interesseaffiniteter](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Utvidbarhet

- **Klikkbare URL-adresser for samlede aktiviteter i kundekorttillegget for Dynamics 365**

  De enhetlige aktivitetene i Kundekort-tillegget viser nå klikkbare URL-adresser hvis slike URL-adresser er definert under konfigurasjon av aktiviteter.    
  Hvis du vil ha mer informasjon, kan du se [Tilegg for kundekort](customer-card-add-in.md).

- **Merke- og interesseaffiniteter som er tilgjengelige i kundekorttillegget for Dynamics 365**

  En ny kontroll i kundekorttillegget for Dynamics 365 lar deg vise merke- og interessesuppleringer for kontaktene i Customer Engagement-apper i Dynamics 365.    
  Hvis du vil ha mer informasjon, kan du se [Tilegg for kundekort](customer-card-add-in.md).

- **Flere Power Automate-utløsere**

  Vi har utvidet utløserne våre for Power Automate og lagt til følgende utløsere:
  - Få en varsling eller utføre en handling når en automatisk fullstendig oppdatering (datakilder, samling, segmenter, mål, eksporter) fullføres
  - Definer en terskel for et forretningsmål. Du kan for eksempel opprette et varsel som sendes når den definerte grenseverdien er passert. I tillegg gir utløseren informasjon som gjør at du kan bygge mer komplekse arbeidsflyter i Power Automate.    
  Hvis du vil ha mer informasjon, kan du se [Power Automate-kobling](export-power-automate.md)

- **Eksportere til Facebook Annonseadministrasjon**
  
  Denne funksjonen gjør det mulig for deg å eksportere segmenter til Facebook-annonseadministrasjon. Segmenter eksporteres som egendefinerte målgrupper for å bruke enhetlige kundeprofiler i markedsføringskampanjer og annonser på Facebook. De egendefinerte målgruppene kan også brukes til å opprette kampanjer på Instagram via Facebook Annonseadministrasjon.    
  Hvis du vil ha mer informasjon, kan du se [Kobling for Facebook Annonseadministrasjon](export-facebook.md).

#### <a name="predictions"></a>Prediksjoner

- **Frafallsprediksjon for abonnement**

  Følg en veiledet opplevelse for å opprette frafallsprediksjon på abonnementsområder som skytjenester, kundemedlemskap og andre sektorer. 

  Med funksjonen for frafallsprediksjon for abonnement kan du forutsi sannsynligheten for at en kunde slutter å bruke abonnementsbaserte produkter eller tjenester, uten å ansette en dataforsker. Med prediksjonspoengsummen kan du kombinere annen informasjon om kundene for å opprette segmenter med høy frafallsrisiko. Ved hjelp av dette segmentet kan du direkte målrette kunder i markedsføring, kundestøtte og andre scenarier for å redusere risikoen for frafall for bestemte kunder for å øke omsetningen og redusere kostnadene.

  Du kan konfigurere definisjonen av frafall som et tidsbasert vindu som spesifikt gjelder virksomheten din. En videostrømmingsvirksomhet som har en månedlig abonnementsprosess, kan for eksempel regne en kunde for å ha frafalt etter 15 dager etter utløpet av abonnementet.

  Etter hvert som du fortsetter gjennom prediksjonen, veileder vi deg gjennom dataene som er nødvendige, og gjør at du kan tilordne data om virksomheten til felt som kreves for å forutsi frafall for kundene. Etter hvert som forretningsinformasjonen, kan du også angi en tidsplan for opplæring basert på ny informasjon i systemet for å tilpasse deg til forretningsforhold i endring.    
  Hvis du vil ha mer informasjon, kan du se [Frafallsprediksjon for abonnement (forhåndsversjon)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmenter

- **Søk etter lignende kunder**
  
  Finn lignende kunder i kundebasen ved å bruke kunstig intelligens. En maskinlæringsmodell med binær klassifisering tilordner en likhetspoengsum til kunder i det utvidede segmentet. Poengsummen er basert på likheten med kunder i kildesegmentet. Kundeprofiler legges til et nyopprettet segment avhengig av likhetspoengsummen.

  Den kalles speilmodellering i digital markedsføring og bruker en modell for kunstig intelligens for å hjelpe deg med å finne kunder som ligner på et annet segment av kundene, ved å ta hensyn til flere attributter. Det lar deg ikke bare velge attributtene, men lar deg også angi maksimalt antall kunder som skal være i dette nye segmentet. Modellen for kunstig intelligens beregner deretter likhetspoengsummen for hver kunde basert på de valgte attributtene, og finner kunder med den høyere gjennomsnittlige likhetspoengsummen. Det resulterende segmentet inneholder kunder som ligner på kunden i det opprinnelige segmentet.    
  Hvis du vil ha mer informasjon, kan du se [Lignende kunder](find-similar-customer-segments.md).

- **Segmentoverlapping og differensiatorer**

  Med segmentoverlapping kan du se hvor mange og hvilke kunder som er i to eller flere segmenter. Du kan for eksempel se hvordan et segment for storkunder overlapper med et segment for svært fornøyde kunder, eller hvordan et segment for frafallskunder overlapper med et segment for misfornøyde kunder. I tillegg kan du analysere hvordan overlappingen endres basert på et ekstra attributt du velger.

  Segmentdifferensiatorer viser hva som skiller ett segment fra resten av kundene eller fra et annet segment. Alt du trenger å gjøre, er å identifisere et segment, og dermed identifiserer systemet profilattributter og mål som skiller segmentet i form av en rangert liste med differensiatorer – fra den sterkeste differensiatoreren til den svakeste.    
  Hvis du vil ha mer informasjon, kan du se [Segmentinnsikt (forhåndsversjon)](segment-insights.md).

- **Segmentlevetid**
  
  Definer en tidsplan for å aktivere eller deaktivere et segment.    
  Hvis du vil ha mer informasjon, kan du se [Behandle eksisterende segmenter](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Mai 2020-oppdateringer

Oppdateringene i mai 2020 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="new-and-updated-features-in-may-2020"></a>Nye og oppdaterte funksjoner i mai 2020

#### <a name="data-ingestion"></a>Datainntak

- **Datainntak i sanntid: loggvisninger**

  Når du bruker API-et til å ta inn oppdateringer i sanntid, kan du se opptil 30 dager med samlet logg for disse oppdateringene. Du har tilgang til oppsamlingene av alle vellykkede eller mislykkede API-kall, inkludert utfallet, kildesystemet og andre nyttige metadata.    
  Se [Datainntak i sanntid](real-time-data-ingestion.md) for mer informasjon.

- **Datainntak i sanntid: profiloppdateringer**

  Denne utvidelsen av datainntak i sanntid gjør det mulig å se, i løpet av sekunder, endringer i bestemte brukerprofilfelt.    
  I tillegg til sanntidsfunksjonaliteten for aktiviteter støtter systemet oppdateringer med lav ventetid for profilfelt. Oppdateringer i sanntid for profilfelt har en utløpstid og er derfor ingen erstatning for planlagte oppdateringer.    
  Se [Datainntak i sanntid](real-time-data-ingestion.md) for mer informasjon.

#### <a name="extensibility"></a>Utvidbarhet

- **Oppdatert tidslinje og paginering i tillegget for kundekort**

  Tidslinjen for Kundekort-tillegget samsvarer med aktivitetstidslinjen. Pagineringen av tidslinjen er forbedret og viser opptil 50 aktiviteter samtidig. Den tillater også innlasting av flere aktiviteter på tidslinjen.    
  Hvis du vil ha mer informasjon, kan du se [Tilegg for kundekort](customer-card-add-in.md).

- **Power Automate-utløser for segmentendringer**

  Utløsere for Power Automate definerer hva du kan bygge en flyt fra. Ved hjelp av den nylig tillagte utløseren kan du definere en terskel for et segment. Du kan for eksempel opprette et varsel som sendes når den definerte grenseverdien er passert.    
  Hvis du vil ha mer informasjon, kan du se [Power Automate-kobling](export-power-automate.md).

- **Støtte for multi-instans for egendefinerte modeller**

  Konfigurer arbeidsflyter for egendefinerte modeller med en eb tjeneste for en annen Azure Machine Learning-leier. Du kan logge på Azure Machine Learning-leieren når du oppretter en ny arbeidsflyt for egendefinerte modeller. Denne funksjonaliteten er et tillegg til den eksisterende funksjonaliteten for integrering med din egen tilpassede Azure Machine Learning-webtjeneste.    
  Hvis du vil ha mer informasjon, kan du se [Egendefinerte maskinlæringsmodeller](custom-models.md).

#### <a name="segments"></a>Segmenter

- **Automatisering av enhetsbane**

  Når brukerne oppretter et segment, må de definere enhetsbanen. Denne funksjonen er et første trinn mot automatisering av enhetsbanedefinisjonen, slik at du kan fokusere på segmenteringskriteriene du har i tankene.    
  Hvis enheten du vil segmentere kundene mot, er direkte relatert til den enhetlige kundeenheten, trenger du ikke å definere enhetsbanen lenger. Hvis det er mer enn én mulig enhetsbane, må du imidlertid definere manuelt.

- **Handlinger på flere segmenter**
  
  Brukere kan velge flere segmenter og utføre handlinger på dem, for eksempel oppdatere segmentene, ved hjelp av ett enkelt klikk.    

- **Oppdatere segmenter**

  Brukere kan oppdatere ett enkelt segment eller bare velge de segmentene de vil oppdatere.    

  
- **Forbedringer i sammensatte segmenter**

  Brukere kan opprette, redigere og slette segmenter som er basert på andre segmenter. Et segment som for eksempel er konstruert på et annet segment, som ble konstruert i et tredje segment.    

- **Segment-listesiden**

  Den nye utformingen av siden med segmenter bruker et listeformat som lar deg vise flere segmenter samtidig. Et søkefelt er lagt til for å finne segmenter raskt. Brukere kan nå bruke handlinger, for eksempel nedlasting eller sletting, på flere segmenter samtidig. En ny trendopplevelse blir innført for raskt å identifisere betydelige endringer i segmenter.    
  Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).

#### <a name="system-administration"></a>Systemadministrasjon

- **Customer Insights tilgjengelig i Microsoft Dynamics 365 Online Government**

  Med flere og flere kanaler for samhandlinger er offentlige data spredt ut over et mylder av systemer, noe som medfører data i siloer og en fragmentert visning av informasjon om samhandlinger mellom borgere. Uten en fullstendig visning av alle borgernes samhandlinger på tvers av kanaler er det umulig for myndighetene å modernisere i stor skala. Microsoft går inn for å støtte teknologibehovene til myndighetene for å holde seg oppdatert med innbyggerens forventninger om konsistente og responsive opplevelser.    
  Med 2020 lanseringsbølge 1 vil Dynamics 365 Customer Insights være tilgjengelig for Government Community Cloud (GCC), som er et miljø som er bygd for å dekke de høyere overholdelsesbehovene til statlige myndigheter i USA. Byråer får en ensartet visning av innbyggerne og bruker forhåndsbygd kunstig intelligens til å utlede innsikt som forbedrer samhandlingen, gir de ansatte verktøy og omformer samfunn, samtidig som den reduserer IT-kompleksiteten og møter kravene til overholdelse og sikkerhetsstandarder i USA. Dynamics 365 Government tilfredsstiller de strenge kravene i USAs Federal Risk and Authorization Management Program (FedRAMP), noe som gjør det mulig for føderale byråer i USA å dra nytte av kostnadsbesparelsene og den strenge sikkerheten i Microsoft-skyen.

## <a name="april-2020-updates"></a>April 2020-oppdateringer

Oppdateringene i april 2020 inneholder flere funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="new-and-updated-features-in-april-2020"></a>Nye og oppdaterte funksjoner i april 2020

#### <a name="activities"></a>Aktiviteter

- **Tilordne aktivitetsenhet til standard aktivitetstype**
  
  Konfigurasjon og lagring av aktiviteter er for øyeblikket basert på en statisk utforming for å vise dem på en tidslinje. Den semantiske betydningen av aktiviteter, som har potensial for flere brukstilfeller i AI-modeller, er ikke fullstendig brukt for øyeblikket. Vi planlegger å gjøre aktivitetstidslinjen mer dynamisk, basert på aktivitetstypen og bedre semantisk forståelse av aktivitetene. Denne funksjonen har til hensikt å identifisere aktivitetstypen som definert i Common Data Model for en inkludert aktivitet.
  Hvis du vil ha mer informasjon, kan du se [Kundeaktiviteter](activities.md).

#### <a name="data-ingestion"></a>Datainntak

- **Datainntak i sanntid: aktiviteter**
  
  Datainntak i sanntid gir data øyeblikkelig for forbruk, helt til den påfølgende planlagte oppdateringen henter disse dataene fra datakilden.    
  Se [Datainntak i sanntid](real-time-data-ingestion.md) for mer informasjon.

- **Forbedringer i klargjøring av data**
  
  Lær mer om dataene som er innhentet i en enhet. Med datasammendraget kan du forstå datakvalitetsegenskapene som kan bidra til å utføre riktige handlinger.    
  Hvis du vil ha mer informasjon, kan du se [Utforske enhetsdata](entities.md#exploring-a-specific-entitys-data).

- **Hente inn analysedata fra Dynamics 365 med Common Data Service**
  
  Common Data Service er tilgjengelig som en måte å opprette datakilder på. Eksisterende Dynamics 365-kunder kan hente inn analytiske enheter fra Common Data Service til Customer Insights. Én enkelt datakilde kan bruke den samme administrerte Common Data Service-sjøen i et Customer Insights-miljø.    
  Hvis du vil ha mer informasjon, kan du se [Koble til data i en Common Data Service-administrert datasjø](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Utvidbarhet

- **Eksporter til LiveRamp**

  Aktiver dataene i LiveRamp® for å koble til over 500 plattformer på tvers av digitale og sosiale systemer og TV-økosystemer. Bruk dataene i LiveRamp til å målrette, hindre og tilpasse annonsekampanjer.    
  Hvis du vil ha mer informasjon, kan du se [LiveRamp&reg;-kobling](export-liveramp.md).

- **Teams-tillegg i Customer Insights**
  
  Roboten har oppslagsfunksjoner for enhetlige kundeprofiler. Det vises et kort med opptil 15 felt fra den resulterende kundeprofilen. Flere treff returnerer en liste over resultater der du kan velge en profil.    
  Hvis du vil ha mer informasjon, kan du se [Teams-ro bot for Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Mål

- **Mål-listesiden**
  
  Forbedringer på målsiden omfatter støtte for handlinger på ett enkelt mål og på flere mål samtidig. I tillegg finner du et søkefelt for å finne og spore mål raskt.    
  Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).

- **Forbedringer i sammensatte mål**
  
  Brukere kan opprette, redigere og slette mål som er basert på andre mål. Et mål som for eksempel er konstruert på et annet mal, som ble konstruert i et tredje mål.

#### <a name="segments"></a>Segmenter

- **En annen operator**
  
  Operatoren In-set tillater segmentering for kunder etter flere mulige strengverdier. Før denne operatoren ble lagt til, måtte du konstruere slike segmenter med flere OR-betingelser. Med In-set-operatoren kan du gjøre dette med én enkelt betingelse.    
  Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).

#### <a name="system-administration"></a>Systemadministrasjon

- **Kopiere konfigurasjonsinnstillinger til et nytt miljø**
  
  Kopier konfigurasjonen fra ett miljø til et annet. Når du oppretter et nytt miljø, kan du velge et eksisterende miljø som du vil kopiere konfigurasjonen fra. Vi støtter for øyeblikket datakilder, datasamkjøring, relasjoner, mål og segmenter som skal kopieres. Datakildelegitimasjon og faktiske data kopieres ikke.    
  Du finner mer informasjon under [Behandle miljøer](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]