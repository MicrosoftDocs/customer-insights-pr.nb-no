---
title: Customer Insights-data i Microsoft Dataverse
description: Bruk Customer Insights-enheter som tabeller i Microsoft Dataverse.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9855ff6908001dd18bc19a286fc56620d0a127e5
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645230"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbeide med Customer Insights-data i Microsoft Dataverse

Med Customer Insights kan du gjøre utdataenheter tilgjengelige i [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Denne integreringen gjør det enkelt å dele data og å utvikle basert på en tilnærming med lite eller ingen kode. Utdataenhetene blir tilgjengelige som tabeller i Dataverse. Disse tabellene muliggjør scenarioer som [automatiske arbeidsflyter via Power Automate](/power-automate/getting-started), [modelldrevne apper](/powerapps/maker/model-driven-apps/) og [lerretsapper](/powerapps/maker/canvas-apps/) via Power Apps. Du kan bruke dataene for ethvert annet program som er basert på Dataverse-tabeller. Den gjeldende implementeringen støtter i hovedsak oppslag der data fra de tilgjengelige enhetene for målgruppeinnsikt kan hentes for en gitt kunde-ID.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Knytte et Dataverse-miljø til Customer Insights

**Organisasjoner med eksisterende Dataverse-miljøer**

Organisasjoner som allerede bruker Dataverse, kan [bruke et av de eksisterende Dataverse-miljøene sine](create-environment.md) når en administrator konfigurerer målgruppeinnsikt. Når du oppgir nettadressen til Dataverse-miljøet, knyttes det til det nye miljøet for målgruppeinnsikt. Customer Insights og Dataverse-miljøer må driftes i samme område for å sikre best mulig ytelse.

**Ny organisasjon**

Hvis du oppretter en ny organisasjon når du konfigurerer Customer Insights, får du automatisk et nytt Dataverse-miljø.

> [!NOTE]
> Hvis organisasjonene allerede bruker Dataverse i leieren, er det viktig å huske at [opprettelse av Dataverse-miljøet styres av en administrator](/power-platform/admin/control-environment-creation.md). Hvis du for eksempel konfigurerer et nytt miljø for målgruppeinnsikt med organisasjonskontoen din og administratoren har deaktivert opprettelse av Dataverse-prøveversjonsmiljøer for alle unntatt administratorer, kan du ikke opprette et nytt prøveversjonsmiljø.
> 
> Dataverse-prøveversjonsmiljøene som opprettes i Customer Insights, har 3 GB lagringsplass, som ikke teller mot den samlede kapasiteten leieren er berettiget til. Betalte abonnementer får Dataverse-rettighet til 15 GB til database og 20 GB til fillagring.

## <a name="output-entities"></a>Utdataenheter

Noen utdataenheter fra målgruppeinnsikt er tilgjengelige som tabeller i Dataverse. Delene nedenfor beskriver det forventede skjemaet for disse tabellene.

- [Kundeprofil](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Supplering](#enrichment)
- [Prediksjon](#prediction)


### <a name="customerprofile"></a>Kundeprofil

Denne tabellen inneholder den enhetlige kundeprofilen fra Customer Insights. Skjemaet for en enhetlig kundeprofil avhenger av enhetene og attributtene som brukes i sammenslåingsprosessen. Et kundeprofilskjema inneholder vanligvis et delsett av attributtene fra [Common Data Model-definisjonen av CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

AlternateKey-tabellen inneholder nøklene til enhetene som var med i foreningsprosessen.

|Column  |Type  |Beskrivelse  |
|---------|---------|---------|
|DataSourceName    |String         | Navnet på datakilden. Eksempel: `datasource5`        |
|EntityName        | String        | Navnet på enheten i målgruppeinnsikt. Eksempel: `contact1`        |
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
