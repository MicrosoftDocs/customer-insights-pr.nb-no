---
title: Nye og kommende funksjoner
description: Informasjon om nye funksjoner, forbedringer og feilrettinger.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988932"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Nyheter i funksjonaliteten for målgruppeinnsikt i Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Vi har gleden av å kunngjøre de nyeste oppdateringene! Denne artikkelen oppsummerer funksjoner i offentlig forhåndsversjon, generelle tilgjengelighetsforbedringer og funksjonsoppdateringer. Hvis du vil se de langsiktige funksjonsplanene, kan du se [Dynamics 365 og Power Platform-utgivelsesplanene](/dynamics365/release-plans/).

Vi ruller ut oppdateringer for hver region. Enkelte områder kan se funksjoner før andre. Med mindre det er angitt noe annet, trenger du ikke å gjøre noe, og vi oppdaterer appen automatisk uten nedetid.

> [!TIP]
> For å sende inn og stemme på funksjonsforespørsler og produktforslag, går du til [ideportalen for Dynamics 365-apper](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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

- **Eksporter segmenter til RollWorks** Vi har utvidet eksportmålene til å inkludere RollWorks. Du kan nå eksportere segmenter fra Customer Insights til RollWorks-målgrupper og bruke dem som basislinje for B2B-reklame.    
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




[!INCLUDE[footer-include](../includes/footer-banner.md)]