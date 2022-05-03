---
title: Nye og kommende funksjoner
description: Informasjon om nye funksjoner, forbedringer og feilrettinger.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647246"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Nyheter i Dynamics 365 Customer Insights

Vi har gleden av å kunngjøre de nyeste oppdateringene! Denne artikkelen oppsummerer funksjoner i offentlig forhåndsversjon, generelle tilgjengelighetsforbedringer og funksjonsoppdateringer. Hvis du vil se de langsiktige funksjonsplanene, kan du se [Dynamics 365 og Power Platform-utgivelsesplanene](/dynamics365/release-plans/).

Vi ruller ut oppdateringer for hver region. Enkelte områder kan se funksjoner før andre. Med mindre det er angitt noe annet, trenger du ikke å gjøre noe, og vi oppdaterer appen automatisk uten nedetid.

> [!TIP]
> For å sende inn og stemme på funksjonsforespørsler og produktforslag går du til [ideportalen for Dynamics 365-apper](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


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

Hvis du vil ha mer informasjon, kan du se [Aktiver datadeling med Dataverse fra din egen Azure Data Lake Storage (forhåndsversjon)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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