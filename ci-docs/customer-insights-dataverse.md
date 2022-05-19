---
title: Customer Insights-data i Microsoft Dataverse
description: Bruk Customer Insights-enheter som tabeller i Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741377"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbeide med Customer Insights-data i Microsoft Dataverse

Med Customer Insights kan du gjøre utdataenheter tilgjengelige i [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Denne integreringen gjør det enkelt å dele data og å utvikle basert på en tilnærming med lite eller ingen kode. [Utdataenhetene](#output-entities) er tilgjengelige som tabeller i et Dataverse-miljø. Du kan bruke dataene for et hvilket som helst annet program basert på Dataverse-tabeller. Disse tabellene muliggjør scenarioer som automatiske arbeidsflytprosesser via Power Automate eller bygging av apper med Power Apps. Den nåværende implementeringen støtter i hovedsak oppslag der data fra de tilgjengelige Customer Insights-enhetene kan hentes for en gitt kunde-ID.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Knytte et Dataverse-miljø til Customer Insights

**Eksisterende organisasjon**

Administratorer kan konfigurere Customer Insights for å [bruke et eksisterende Dataverse-miljø](create-environment.md) når de oppretter et Customer Insights-miljø. Ved å oppgi nettadressen til Dataverse-miljøet legges den ved det nye Customer Insights-miljøet. Customer Insights og Dataverse-miljøer må driftes i samme område. 

Hvis du ikke vil bruke et eksisterende Dataverse-miljø, oppretter systemet et nytt miljø for Customer Insights-dataene i leieren. 

> [!NOTE]
> Hvis organisasjonene allerede bruker Dataverse i leieren, er det viktig å huske at [oppretting av Dataverse-miljøet styres av en administrator](/power-platform/admin/control-environment-creation). Hvis du for eksempel konfigurerer et nytt Customer Insights-miljø med organisasjonskontoen din og administratoren har deaktivert opprettingen av Dataverse-prøvemiljøer for alle unntatt administratorer, kan du ikke opprette et nytt prøvemiljø.
> 
> Dataverse-prøveversjonsmiljøene som opprettes i Customer Insights, har 3 GB lagringsplass, som ikke teller mot den samlede kapasiteten leieren er berettiget til. Betalte abonnementer får Dataverse-rettighet til 15 GB til database og 20 GB til fillagring.

**Ny organisasjon**

Hvis du oppretter en ny organisasjon når du konfigurerer Customer Insights, oppretter systemet automatisk et nytt Dataverse-miljø i organisasjonen for deg.

## <a name="output-entities"></a>Utdataenheter

Noen utdataenheter fra Customer Insights er tilgjengelige som tabeller i Dataverse. Delene nedenfor beskriver det forventede skjemaet for disse tabellene.

- [Kundeprofil](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Supplering](#enrichment)
- [Prediksjon](#prediction)
- [Segmentmedlemskap](#segment-membership)


### <a name="customerprofile"></a>Kundeprofil

Denne tabellen inneholder den enhetlige kundeprofilen fra Customer Insights. Skjemaet for en enhetlig kundeprofil avhenger av enhetene og attributtene som brukes i datasamlingsprosessen. Et kundeprofilskjema inneholder vanligvis et delsett av attributtene fra [Common Data Model-definisjonen av CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

AlternateKey-tabellen inneholder nøklene til enhetene som var med i foreningsprosessen.

|Column  |Type  |Beskrivelse  |
|---------|---------|---------|
|DataSourceName    |String         | Navnet på datakilden. Eksempel: `datasource5`        |
|EntityName        | String        | Navnet på enheten i Customer Insights. Eksempel: `contact1`        |
|AlternateValue    |String         |Alternativ ID som er tilordnet til kunde-ID-en. Eksempel: `cntid_1078`         |
|KeyRing           | Tekst på flere linjer        | JSON-verdi  </br> Eksempel: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | ID for den enhetlige kundeprofilen.         |
|AlternateKeyId     | GUID         |  Deterministisk GUID for AlternateKey basert på msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Eksempel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Denne tabellen inneholder aktiviteter av brukere som er tilgjengelige i Customer Insights.

| Column            | Type        | Beskrivelse                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Kundeprofil-ID                                                                      |
| ActivityId        | String      | Intern ID for kundeaktiviteten (primærnøkkel)                                       |
| SourceEntityName  | String      | Navnet på kildeenheten                                                                |
| SourceActivityId  | String      | Primærnøkkel fra kildeenheten                                                       |
| ActivityType      | String      | Semantisk aktivitetstype eller navn på egendefinert aktivitet                                        |
| ActivityTimeStamp | DATETIME    | Aktivitetstidsstempel                                                                      |
| Stilling             | String      | Tittelen eller navnet på aktiviteten                                                               |
| Beskrivelse       | String      | Aktivitetsbeskrivelse                                                                     |
| Nettadresse               | String      | Kobling til en ekstern nettadresse som er spesifikk for aktiviteten                                         |
| SemanticData      | JSON-streng | Omfatter en liste over nøkkelverdipar for semantiske tilordningsfelt som er spesifikke for aktivitetstypen |
| RangeIndex        | String      | Unix-tidsstempel som brukes til å sortere aktivitetstidslinjen og spørringer vedrørende gyldig intervall |
| mydynci_unifiedactivityid   | GUID | Intern ID for kundeaktiviteten (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Denne tabellen inneholder utdataene for mål basert på kundeattributter.

| Column             | Type             | Beskrivelse                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Kundeprofil-ID        |
| Mål           | JSON-streng      | Omfatter en liste over nøkkelverdipar for målnavn og -verdier for gitt kunde | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Kundeprofil-ID |


### <a name="enrichment"></a>Supplering

Denne tabellen inneholder utdataene for suppleringsprosessen.

| Column               | Type             |  Beskrivelse                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Kundeprofil-ID                                 |
| EnrichmentProvider   | String           | Navnet på leverandøren av suppleringen                                  |
| EnrichmentType       | String           | Type supplering                                      |
| Verdier               | JSON-streng      | Liste over attributter produsert av suppleringsprosessen |
| msdynci_enrichmentid | GUID             | Deterministisk GUID generert fra msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prediksjon

Denne tabellen inneholder utdataene til modellprediksjonene.

| Column               | Type        | Beskrivelse                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Kundeprofil-ID                                  |
| ModelProvider        | String      | Navnet på leverandøren av modellen                                      |
| Modell                | String      | Modellnavn                                                |
| Verdier               | JSON-streng | Liste over attributter produsert av modellen |
| msdynci_predictionid | GUID        | Deterministisk GUID generert fra msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmentmedlemskap

Denne tabellen inneholder informasjon om segmentmedlemskap for kundeprofilene.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Kundeprofil-ID        |
| SegmentProvider      | String       | Appen som publiserer segmentene.      |
| SegmentMembershipType | String       | Type kunde for denne segmentmedlemskapsoppføringen. Støtter flere typer, for eksempel Kunde, Kontakt eller Konto. Standard: Kunde  |
| Segmenter       | JSON-streng  | Liste over unike segmenter kundeprofilen er medlem av      |
| msdynci_identifier  | String   | Unik identifikator for segmentmedlemskapsoppføringen. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministisk GUID generert fra `msdynci_identifier`          |
