---
title: Nyheter i Dynamics 365 Customer Insights
description: Informasjon om nye funksjoner, forbedringer og feilrettinger.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: acba06cba5fb5cbf0bca5aeb30b603003555fc32
ms.sourcegitcommit: 3ab8f1c0ba5874095a19f0b6367b9a4432f72ed1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409369"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Nyheter i Dynamics 365 Customer Insights

Vi har gleden av å kunngjøre de nyeste oppdateringene! Denne artikkelen oppsummerer funksjoner i offentlig forhåndsversjon, generelle tilgjengelighetsforbedringer og funksjonsoppdateringer. Hvis du vil se de langsiktige funksjonsplanene, kan du se [Dynamics 365 og Power Platform-utgivelsesplanene](/dynamics365/release-plans/).

Vi ruller ut oppdateringer for hver region. Enkelte områder kan se funksjoner før andre. Med mindre det er angitt noe annet, trenger du ikke å gjøre noe, og vi oppdaterer appen automatisk uten nedetid.

> [!TIP]
> For å sende inn og stemme på funksjonsforespørsler og produktforslag går du til [ideportalen for Dynamics 365-apper](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="august-2022-updates"></a>Oppdateringer for august 2022

Oppdateringene i august 2022 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="contact-unification-in-b-to-b-environments"></a>Kontaktsamling i B-til-B-miljøer

B-til-B-miljøer i Customer Insights støtter nå en forbedret dataforordningsopplevelse.

Du kan nå samle kontakter i tillegg til forretningsforbindelser for å få en fullstendig visning av forretningskontaktene. Enhetlige kontakter er knyttet til enhetlige forretningsforbindelser og vises nå på kundekortene. 

Hvis du vil ha mer informasjon, kan du se [Opprette en enhetlig kontaktprofil](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Opprette og eksportere segmenter basert på enhetlige kontakter

Takket være den nye kontaktforeningen kan du opprette segmenter med kontakter ved hjelp av vilkår fra kontakter, forretningsforbindelser eller begge deler. Disse segmentene kan eksporteres for aktivering i andre tjenester.

Hvis du vil ha mer informasjon, kan du se [Oversikt over eksporter](export-destinations.md).

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>Distribusjonsområder justert med Microsoft Dataverse

Når du oppretter et nytt Customer Insights-miljø, kan du velge området der du vil at tjenesten skal distribueres og driftes. Vi har oppdatert områdevalget slik at det justeres med Microsoft Dataverse og Power Platform.

Du kan nå enkelt velge samme område som det eksisterende Microsoft Dataverse-miljøet eller Azure Data Lake-lagringskontoen (hvis du velger dette alternativet), avhengig av tilgjengeligheten til Customer Insights i dette området.

Hvis du vil ha mer informasjon, kan du se [Opprett et nytt miljø](create-environment.md) og [Produkttilgjengelighet etter geografisk område](https://dynamics.microsoft.com/availability-reports/).

## <a name="july-2022-updates"></a>Oppdateringer i juli 2022

Oppdateringene i juli 2022 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="export-to-moengage"></a>Eksporter til MoEngage

Eksporter segmenter av enhetlige kundeprofiler til MoEngage, og bruk dem til e-postmarkedsføring i MoEngage.

Hvis du vil ha mer informasjon, kan du se [Eksportere segmenter til MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>SSH-støtte for SFTP-baserte eksporter

Velg om du vil godkjenne via SSH eller brukernavn/passord for tilkoblinger til SFTP-eksportmål.

Hvis du vil ha mer informasjon, kan du se [Eksporter data til SFTP-verter](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Tilpass erfaringer med data om kjente og ukjente brukere

Det er ikke noen ny utfordring å administrere kundedata, men det blir stadig vanskeligere etter hvert som brukere navigerer blant de ulike digitale kanalene varemerker tilbyr. En bruker som er kjent (godkjent) i én kanal, blir ukjent (ikke godkjent) i en annen hvis vedkommende ikke er logget på. Problemet er ofte at ikke godkjente (ukjente) brukere ikke har en felles ID. Den kunne ha blitt brukt til å knytte sammen meningsfulle attributter for profiler og generere enhetlige kundeprofiler. Customer Insights bidrar til å løse dette problemet ved å hente inn data fra sporingsmetoder på kildesystemene.

Hvis du vil ha mer informasjon, kan du se [Tilpass opplevelsene dine med data om kjente og ukjente brukere](unknown-to-known.md).

## <a name="june-2022-updates"></a>Oppdateringer i juni 2022

Oppdateringene i juni 2022 omfatter nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Oppdatert brukeropplevelse for datakilder og datainntak

Import av data fra en rekke ulike datakilder er fundamentet for konsolidering av kundedataene i Dynamics 365 Customer Insights. Vi har oppdatert brukeropplevelsen for import og tilkobling av datakilder. Denne oppdateringen fokuserer på å gjøre det enklere å hente inn data i Customer Insights.

Hvis du vil ha mer informasjon, kan du se [Oversikt over datakilder](data-sources.md).

### <a name="export-to-inmobi"></a>Eksporter til InMobi

InMobi hjelper varemerker å forstå, identifisere, engasjere og skaffe kunder. Du kan eksportere segmenter og andre data til InMobi-tjenesten via Azure Blob Storage-kontoer.

Hvis du vil ha mer informasjon, kan du se [Eksporter til InMobi (forhåndsversjon)](export-inmobi.md).

### <a name="lockbox-support-in-customer-insights"></a>Støtte for Lockbox i Customer Insights

Customer Lockbox har et grensesnitt for å se gjennom og godkjenne (eller avvise) datatilgangsforespørsler. Disse forespørslene oppstår når datatilgang til kundedata er nødvendig for å avslutte en kundestøttesak.

Hvis du vil ha mer informasjon, kan du se [Få sikker tilgang til kundedata med Customer Lockbox (forhåndsversjon)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Koble til dataene ved hjelp av Azure Private Link

Azure Private Link gjør at Customer Insights kan kobles til Azure Data Lake Storage-kontoen din over et privat endepunkt i det virtuelle nettverket. For data i en lagringskonto, som ikke er eksportert for offentlig Internett, kan Private Link aktivere tilkoblingen til det begrensede nettverket.

Hvis du vil ha mer informasjon, kan du se [Bruk Private Link i Customer Insights](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Mai 2022-oppdateringer

Oppdateringene i mai 2022 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="updated-data-unification-experience"></a>Oppdatert datasamlingsfunksjon

 Med datasamling kan du samle datakilder som en gang var spredt, til ett enkelt hoveddatasett som gir en enhetlig visning av dataene. Data kan forenes for én enkelt enhet eller flere enheter. Først [velger du enheter og kildefelter](map-entities.md), [fjerner dupliserte oppføringer](remove-duplicates.md), angir regler for [samsvarende betingelser](match-entities.md) og definerer hvilke [felter som skal inkluderes i de enhetlige kundeprofilene](merge-entities.md).

Hvis du vil ha mer informasjon, kan du se [Oversikt over datasamling](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Oppdatert startside i Customer Insights

**Start** veileder deg gjennom konfigureringsprosessen for nøkkelfunksjoner og gir en oversikt over segmenter, mål og suppleringsdata. Vi har oppdatert opplevelsen for å gi deg mer relevant informasjon med et raskt blikk.

Hvis du vil ha mer informasjon, kan du se [Utforsk Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>Spor bruk av et segment

Du kan nå [spore bruken av et segment](segments.md#track-usage-of-a-segment) i apper, som er basert på den samme Dataverse-organisasjonen som er koblet til Customer Insights. For [Customer Insights-segmenter som brukes i kundereiser for Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) informerer systemet deg om bruken av dette segmentet.

### <a name="export-to-criteo"></a>Eksporter til Criteo

Criteo er en nettplattform som hjelper brukere med å administrere digital reklame. Du kan nå eksportere segmenter for enhetlige kundeprofiler til å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Criteo.

Hvis du vil ha mer informasjon, kan du se [Eksporter segmenter til Criteo (forhåndsversjon)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Finjustert dokumentasjonsstruktur for oppretting av miljø

Vi har revidert hjelpedokumentene som er relatert til oppretting og administrasjon av miljøer i Customer Insights. Artiklene er nå gruppert under Miljøer-noden i innholdsfortegnelsen. De omstrukturerte artiklene gir mer veiledning for de ulike måtene å konfigurere miljøer på og har en klarere struktur. Hvis du har tilbakemeldinger du vil dele, kan du gi oss beskjed via kontrollene mot slutten av hjelpeartiklene.

Hvis du vil ha mer informasjon, kan du se [Veiledning: Opprett et nytt miljø](create-environment.md).

## <a name="april-2022-updates"></a>April 2022-oppdateringer

Oppdateringene i april 2022 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet-supplering (forhåndsversjon)

Dun & Bradstreet tilbyr kommersielle data, analyse og innsikt for virksomheter. Den gjør det mulig for kunder med enhetlige kundeprofiler for selskaper å berike dataene sine. Suppleringer omfatter attributter, som DUNS-nummer, selskapsstørrelse, sted, bransje og mye mer.

Hvis du vil ha mer informasjon , kan du se [Supplement for firmaprofiler med Dun & Bradstreet (forhåndsversjon)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Definer måltypen ved oppretting av et nytt mål

Nå kan du skille mellom mål for individuelle profiler og tiltak i hele virksomheten. Selv om forretningstiltak vises på hjemmesiden for Customer Insights, vises kundetiltak i de detaljerte kundevisningene.

Hvis du vil ha informasjon, kan du se [Bruk måleverktøyet til å opprette mål fra bunnen av](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Konsolidering av Customer Insights-dokumentasjon

Vi har revidert dokumentasjonsartiklene og fjernet omtaler av funksjoner for engasjementsinnsikt og målgruppeinnsikt. Fremover vil vi konsekvent henvise til produktnavnet Customer Insights når vi skriver om kjernefunksjonene i programmet. Denne endringen fører også til betydelig omstrukturering av innholdsfortegnelsen, nettadressestrukturen og filbanene i den underliggende dokumentlageret. Alle bokmerkene eller eksisterende koblinger fortsetter å fungere, og omdirigeres til de oppdaterte nettadressene.

Hvis du vil fortelle oss hvordan du oppfatter denne endringen eller ser noe som ikke fungerer som forventet, kan du fortelle oss det ved å [sende inn tilbakemelding for denne siden](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Mars 2022-oppdateringer

Oppdateringene i mars 2022 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec-supplering (forhåndsversjon)

LiveRamp gir identitetsløsning og konsolidering av kundedata. Du kan tilordne personlige identifikatorer i kundedataene til AbiliTec-identitetsgrafen og motta AbiliTec-ID-er. Deretter kan du bruke disse IDene til bedre forening av kundedataene.

Hvis du vil ha mer informasjon, kan du se [Suppler kundeprofiler med identitetsdata fra LiveRamp (forhåndsversjon)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organiser segmenter og mål med merker og filtre

Hvis organisasjonen din vedlikeholder mange segmenter eller tiltak, kan det noen ganger være en utfordring å finne den rette. Med denne nye funksjonen kan du organisere lister ved hjelp av merker og kolonner. Det hjelper deg med å finne data raskt og enkelt og tilpasse visningene.

For mer informasjon kan du se [Jobb med merker og kolonner](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Aktiver datadeling med Dataverse når du bruker din egen lagringskonto

Hvis miljøet bruker Azure Data Lake Storage til å lagre Customer Insights-data, krever aktivering av datadeling med Microsoft Dataverse litt ekstra konfigurasjon.
Tidligere kunne du bare aktivere datadeling med Dataverse da dataene ble lagret i den administrerte datasjøen.

Hvis du vil ha mer informasjon, kan du se [Aktiver datadeling med Dataverse fra din egen Azure Data Lake Storage (forhåndsversjon)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nye eksportmål: Iterable og Braze

Vi fortsetter å utvide økosystemet for eksportmål med nye tilkoblinger. Du kan nå eksportere segmenter til Iterable og Braze for å bruke aktiveringstjenestene deres.

Hvis du vil ha mer informasjon, kan du se [Eksporter segmenter til Iterable (forhåndsversjon)](export-iterable.md) og [Eksporter segmenter til Braze (forhåndsversjon)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Forbedringer i eksport av Marketo og Google Ads

Endring av API-er i tilkoblede tjenester fører til at oppdateringer for koblinger kjører pålitelig og problemfritt. Vi har gitt ut noen oppdateringer for eksportene til Marketo- og Google Ads-tjenester:

- Google Ads: Den nye versjonen av eksportkoblingen for Google Ads forenkler godkjenningsopplevelsen og gjør det nå mulig å opprette nye Google Ads-målgrupper automatisk. 
- Marketo: Den nye versjonen av Marketo-eksportkoblingen gir støtte for Marketo-ID-en slik at du kan unngå dataduplisering, oppdatere eksisterende oppføringer og opprette nye oppføringer i Marketo. 

## <a name="february-2022-updates"></a>Oppdateringer februar 2022

Oppdateringene i februar 2022 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="general-availability-for-prediction-models"></a>Generell tilgjengelighet for prediksjon modeller

Standard prediksjonmodeller, inklusive **abonnementsfrafall**, **transaksjonsfrafall** og **Verdi for kundelevetid (CLV)**. blir allment tilgjengelige som en del av Customer Insights. 

Hvis du vil ha mer informasjon, kan du se [Oversikt over prediksjon](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Ny datakilde: Integrasjon med Azure Synapse Analytics (forhåndsversjon)

Azure Synapse Analytics er en bedriftsanalysetjeneste som akselererer tid til innsikt på tvers av datalagre og stordatasystemer.

Organisasjoner som allerede bruker Azure Synapse Analytics, kan legge inn dataene i Customer Insights. 

Hvis du vil ha mer informasjon, kan du se [Koble til en Azure Synapse-datakilde (forhåndsversjon)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp-supplering (forhåndsversjon)

LiveRamp gir identitetsløsning og konsolidering av kundedata. Du kan tilordne personlige identifikatorer i kundedataene til AbiliTec-identitetsgrafen og motta AbiliTec-ID-er. Deretter kan du bruke disse IDene til bedre forening av kundedataene.

Hvis du vil ha mer informasjon, kan du se [Suppler kundeprofiler med identitetsdata fra LiveRamp (forhåndsversjon)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Supplering for datakilder (forhåndsversjon)

Bruk data fra kilder som Microsoft og andre partnere til å forbedre kundedataene før dataforeningen. Datakildesupplering bidrar til å gi høyere datafullstendighet og -kvalitet som kan bidra til å oppnå bedre resultater når dataene samles.

Hvis du vil ha mer informasjon, kan du se [Supplering for datakilder (forhåndsversjon)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Endre eier av miljø

Selv om flere brukere kan ha administratortillatelser i Customer Insights, er bare én bruker eieren av et miljø. En forbedret opplevelse gjør det mulig å endre eiere av et miljø og kreve eierskap hvis en tidligere eier har sluttet i organisasjonen. 

Hvis du vil ha mer informasjon, kan du se [Endre eieren av et miljø](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Prosess for dataforberedelse viser årsaken til skadede oppføringer

Dataforberedelse viser nå årsaken til at alle felter med skadede data blir skadet. Informasjonen gis på det individuelle oppføringsnivået for enkel identifisering. 

Hvis du vil ha mer informasjon, kan du se [Skadede datakilder](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Slutten av forhåndsversjon for rapporteringsfunksjoner i engasjementsinnsiktsfunksjonen

Forhåndsversjonen av engasjementsinnsiktsfunksjonen i Dynamics 365 Customer Insights ble avsluttet 15. februar 2022.  
Denne endringen betyr at Customer Insights-prøveopplevelsen ikke lenger omfatter muligheten til å opprette trakter eller annen rapporteringsfunksjonalitet.

Vi inviterer deg til å utforske og evaluere de mange andre funksjonene i [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), Microsofts kundedataplattform (CDP).    
 
I en overføringsperiode har eksisterende forhåndsversjonsdeltakere fremdeles tilgang til noen forhåndsversjonsfunksjoner:

- Få kode til å instrumentere et nettsted eller en mobilapp 
- Se hendelser og hendelsesegenskaper 
- Forbedre enhetlige profiler med registrerte og finjusterte hendelser for å dra full nytte av alle kundedataene
  
I løpet av overføringsperioden strømmes registrerte hendelser fremdeles til den tilkoblede Data Lake. Når denne funksjonaliteten er deaktivert, stoppes datadeling, og det sendes ingen nye hendelser til det tilkoblede lageret.
Kontakt Microsoft-kontoteamet ditt direkte hvis du har spørsmål til avslutningen av forhåndsversjonsfunksjonen. Kontoteamet holder deg oppdatert om kommende lanseringer. 

## <a name="january-2022-updates"></a>Januar 2022-oppdateringer

Oppdateringene i januar 2022 inkluderer nye funksjoner, ytelsesoppgraderinger og feilrettinger.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Sentimentanalyse for tilbakemelding fra kunder

Customer Insights gir en ny AI-dreven funksjon for å syntetisere kundesentiment og identifisere bestemte forretningsaspekter som salgsmuligheter for målrettede forbedringer. Ved å analysere de skriftlige tilbakemeldingene fra kundene kan du få nøyaktig innsikt til lave kostnader. Sentimentanalyse som drives av NLP-modeller (Natural Language Processing) som genererer to utledede innsikter for hver kunde-ID. En sentimentpoengsum (på –5 til 5) og en liste over aktuelle forretningsaspekter. 

Hvis du vil ha mer informasjon, kan du se [Analysere sentiment i tilbakemeldinger fra kunder (forhåndsversjon)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]