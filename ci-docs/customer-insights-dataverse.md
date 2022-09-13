---
title: Arbeide med Customer Insights-data i Microsoft Dataverse
description: Lær hvordan du kobler til Customer Insights og Microsoft Dataverse og forstå utdataenhetene som eksporteres til Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424321"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbeide med Customer Insights-data i Microsoft Dataverse

Med Customer Insights kan du gjøre utdataenheter tilgjengelige i [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Denne integreringen gjør det enkelt å dele data og å utvikle basert på en tilnærming med lite eller ingen kode. [Utdataenhetene](#output-entities) er tilgjengelige som tabeller i et Dataverse-miljø. Du kan bruke dataene for et hvilket som helst annet program basert på Dataverse-tabeller. Disse tabellene muliggjør scenarioer som automatiske arbeidsflytprosesser via Power Automate eller bygging av apper med Power Apps.

Når du kobler til Dataverse-miljøet, kan du også [samle inn data fra lokale datakilder ved å bruke Power Platform-dataflyter og -gatewayer](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Forutsetning

- Customer Insights og Dataverse-miljøer må driftes i samme område.
- En global administratorrolle konfigurert i Dataverse-miljøet. Kontroller om dette [Dataverse-miljøet er tilknyttet](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) bestemte sikkerhetsgrupper, og kontroller at du er lagt til i disse sikkerhetsgruppene.
- Ingen andre Customer Insights-miljøer er allerede tilknyttet Dataverse-miljøet du vil koble til. Lær hvordan du [fjerner en eksisterende tilkobling til et Dataverse-miljø ](#remove-an-existing-connection-to-a-dataverse-environment).
- Et Microsoft Dataverse-miljø som er koblet til én lagringskonto hvis du konfigurerer miljøet slik at det [bruker Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Rettighet til Dataverse-lagringskapasitet

Et abonnement på Customer Insights gir deg rett til ekstra kapasitet for organisasjonens eksisterende [Dataverse-lagringskapasitet](/power-platform/admin/capacity-storage). Tilleggskapasiteten avhenger av antall profiler du bruker i abonnementet.

**Eksempel:**

La oss si at du får 15 GB databaselagring og 20 GB fillagring per 100 000 kundeprofiler. Hvis abonnementet omfatter 300 000 kundeprofiler, er den totale lagringskapasiteten 45 GB (3 x 15 GB) databaselagring og 60 GB fillagring (3 x 20 GB). Hvis du har et B2B-abonnement med 30 000 kontoer, er den totale lagringskapasiteten 45 GB (3 x 15 GB) databaselagring og 60 GB fillagring (3 x 20 GB).

Loggkapasiteten er ikke trinnvis og fast for organisasjonen.

Hvis du vil ha detaljert informasjon om rettigheter til lagringskapasitet, kan du se [Veiledning om lisenser for Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Koble et Dataverse-miljø til Customer Insights

Trinnet **Microsoft Dataverse** lar deg koble Customer Insights til Dataverse-miljøet mens du [oppretter et Customer Insights-miljø](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datadeling der Microsoft Dataverse aktiveres automatisk for nye miljøer":::

1. Oppgi nettadressen til Dataverse-miljøet, eller la den være tom for å få en opprettet for deg.

   > [!NOTE]
   > Etter at du har opprettet tilkoblingen mellom Customer Insights og Dataverse, lar du være å endre organisasjonsnavnet for Dataverse-miljøet. Navnet på organisasjonen brukes i nettadressen til Dataverse, og et endret navn bryter tilkoblingen til Customer Insights.

   [Power Platform-administratorer kan styre hvem som kan opprette nye Dataverse-miljøer](/power-platform/admin/control-environment-creation). Hvis du prøver å konfigurere et nytt Customer Insights-miljø og ikke kan det, kan det hende at administratoren har deaktivert opprettelsen av Dataverse-miljøer for alle unntatt administratorer.

1. Hvis du bruker din egen Data Lake Storage-konto:
   1. Velg **Aktiver datadeling** med Dataverse.
   1. Angi **Tillatelsesidentifikator**. For å hente tillatelsesidentifikatoren [aktiverer du datadeling med Dataverse fra din egen Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktivere datadeling med Dataverse fra din egen Azure Data Lake Storage (forhåndsversjon)

På [din egen Azure Data Lake Storage-konto](own-data-lake-storage.md) kontrollerer du at brukeren som konfigurerer Customer Insights-miljøet har minst tillatelsen **Storage Blob Data Reader** i beholderen `customerinsights` på lagringskontoen.

### <a name="limitations"></a>Begrensninger

- Det er bare én-til-én-tilordning mellom en Dataverse-organisasjon og en Azure Data Lake Storage-konto. Når en Dataverse-organisasjon er koblet til en lagringskonto, kan den ikke koble til en annen lagringskonto. Denne begrensningen hindrer at Dataverse fyller flere lagringskontoer.
- Datadeling fungerer ikke hvis et oppsett av Azure Private Link er nødvendig for å få tilgang til Azure Data Lake Storage-kontoen din fordi den er bak en brannmur. Dataverse støtter for øyeblikket ikke tildelingen til private endepunkter via Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Konfigurer sikkerhetsgrupper i din egen Azure Data Lake Storage

1. Opprett to sikkerhetsgrupper i Azure-abonnementet – én **Leser**-sikkerhetsgruppe og én **Bidragsyter**-sikkerhetsgruppe, og angi Microsoft Dataverse-tjenesten som eier for begge sikkerhetsgruppene.

1. Administrer tilgangskontrollisten (ACL) i beholderen `customerinsights` på lagringskontoen via disse sikkerhetsgruppene.
   1. Legg til Microsoft Dataverse-tjenesten og eventuelle Dataverse-baserte forretningsprogrammer som Dynamics 365 Marketing i  **Leser**-sikkerhetsgruppen med **skrivebeskyttede** tillatelser.
   1. Legg *bare* til Customers Insights-programmet i **Bidrag**-sikkerhetsgruppen for å gi **lese- og skrive**-tillatelser til å skrive profiler og innsikt.

### <a name="set-up-powershell"></a>Konfigurer PowerShell

Konfigurer PowerShell for å kjøre PowerShell-skript.

1. Installer den nyeste versjonen av [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. Velg Windows-tasten på tastaturet på PC-en, søk etter **Windows PowerShell**, og velg **Kjør som administrator**.
   1. I PowerShell-vinduet som åpnes, skriver du inn `Install-Module AzureAD`.

1. Importer tre moduler.
   1. I PowerShell-vinduet angir du `Install-Module -Name Az.Accounts` og følger trinnene.
   1. Gjenta for `Install-Module -Name Az.Resources` og `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Kjør PowerShell-skript, og hent tillatelsesidentifikatoren

1. Last ned de to PowerShell-skriptene du må kjøre fra teknikerens [GitHub-repo](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Krever leieradministratortillatelser.
   - `ByolSetup.ps1`: Krever Storage Blob-dataeiertillatelser på lagringskonto-/beholdernivået. Dette skriptet oppretter tillatelsen for deg. Rolletilordningen kan fjernes manuelt etter at skriptet er kjørt.

1. Kjør `CreateSecurityGroups.ps1` i Windows PowerShell ved å angi Azure-abonnements-ID-en som inneholder Azure Data Lake Storage. Åpne PowerShell-skriptet i et redigeringsprogram for å se gjennom tilleggsinformasjon og den implementerte logikken.

   Dette skriptet oppretter to sikkerhetsgrupper i Azure-abonnementet: én for lesergruppen og en annen for bidragsytergruppen. Microsoft Dataverse-tjenesten er eieren av begge disse sikkerhetsgruppene.

1. Lagre begge ID-verdiene for sikkerhetsgruppe som genereres av dette skriptet, for å bruke dem i skriptet `ByolSetup.ps1`.

   > [!NOTE]
   > Oppretting av sikkerhetsgrupper kan deaktiveres for leieren. I det tilfellet kreves det en manuell konfigurasjon og Azure AD-administratoren må [aktivere oppretting av sikkerhetsgrupper](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Kjør dette `ByolSetup.ps1` i Windows PowerShell ved å angi Azure-abonnement-ID-en som inneholder Azure Data Lake Storage, lagringskontonavnet, ressursgruppenavnet og ID-verdier for sikkerhetsgruppene for leser og bidragsyter. Åpne PowerShell-skriptet i et redigeringsprogram for å se gjennom tilleggsinformasjon og den implementerte logikken.

   Dette skriptet legger til den nødvendige rollebaserte tilgangskontrollen for Microsoft Dataverse-tjenesten og eventuelle Dataverse-baserte forretningsprogrammer. Den oppdaterer også tilgangskontrollisten (ACL) i beholderen `customerinsights` for sikkerhetsgruppene som opprettes med skriptet `CreateSecurityGroups.ps1`. Bidragsytergruppen får *rwx*-tillatelse, og lesergruppen får bare *r-x*-tillatelse.

1. Kopier utdatastrengen som ser slik ut: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Angi den kopierte utdatastrengen i **Tillatelsesidentifikator**-feltet i miljøkonfigurasjonstrinnet for Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurasjonsalternativer for å aktivere datadeling fra din egen Azure Data Lake Storage med Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Fjern en eksisterende tilkobling til et Dataverse-miljø

Når du kobler til et Dataverse-miljø, vises feilmeldingen **Denne CDS-organisasjonen er allerede knyttet til en annen Customer Insights-forekomst**, betyr at Dataverse-miljøet allerede er brukt i et Customer Insights-miljø. Du kan fjerne den eksisterende tilkoblingen som en global administrator i Dataverse-miljøet. Det kan ta noen timer før endringene fylles ut.

1. Gå til [Power Apps](https://make.powerapps.com).
1. Velg miljøet fra miljøvelgeren.
1. Gå til **Løsninger**.
1. Avinstaller eller slett løsningen kalt **Dynamics 365 Customer Insights-tillegg for kundekort (forhåndsvisning)**.

OR

1. Åpne Dataverse-miljøet.
1. Gå til **Avanserte innstillinger** > **Løsninger**.
1. Avinstaller **CustomerInsightsCustomerCard**-løsningen.

Hvis fjerningen av tilkoblingen mislykkes på grunn av avhengigheter, må du også fjerne avhengighetene. Hvis du vil ha mer informasjon, kan du se [Fjerning av avhengigheter](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Utdataenheter

Noen utdataenheter fra Customer Insights er tilgjengelige som tabeller i Dataverse. Delene nedenfor beskriver det forventede skjemaet for disse tabellene.

- [Kundeprofil](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Supplering](#enrichment)
- [Prediksjon](#prediction)
- [Segmentmedlemskap](#segment-membership)

### <a name="customerprofile"></a>Kundeprofil

Denne tabellen inneholder den enhetlige kundeprofilen fra Customer Insights. Skjemaet for en enhetlig kundeprofil avhenger av enhetene og attributtene som brukes i datasamlingsprosessen. Et kundeprofilskjema inneholder vanligvis et delsett av attributtene fra [Common Data Model-definisjonen av CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Når det gjelder B2B-scenarioet, inneholder kundeprofilen samlede forretningsforbindelser, og skjemaet inneholder vanligvis et delsett av attributtene fra [Common Data Model-definisjonen av forretningsforbindelse](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

En ContactProfile inneholder samlet informasjon om en kontakt. Kontakter er [enkeltpersoner som er tilordnet til en forretningsforbindelse](data-unification-contacts.md) i et B2B-scenario.

| Kolonne                       | Type                | Bekrivelse     |
| ---------------------------- | ------------------- | --------------- |
|  BirthDate            | Date/klokkeslett       |  Fødselsdatoen til kontakten               |
|  City                 | Tekst |  Poststedet i kontaktadressen               |
|  ContactId            | Tekst |  ID-en for kontaktprofilen               |
|  ContactProfileId     | Unik identifikator   |  GUID for kontakten               |
|  CountryOrRegion      | Tekst |  Land/område i kontaktadressen               |
|  CustomerId           | Tekst |  ID-en for forretningsforbindelsen kontakten er tilordnet til               |
|  EntityName           | Tekst |  Enheten som data kommer fra                |
|  FirstName            | Tekst |  Fornavnet til kontakten               |
|  Gender               | Tekst |  Kontaktens kjønn               |
|  ID                   | Tekst |  Deterministisk GUID basert på `Identifier`               |
|  Identifier           | Tekst |  Intern ID for kontaktprofilen: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Tekst |  Stillingstittelen til kontakten               |
|  LastName             | Tekst |  Etternavnet til kontakten               |
|  PostalCode           | Tekst |  Postnummeret i kontaktadressen               |
|  PrimaryEmail         | Tekst |  E-postadressen til kontakten               |
|  PrimaryPhone         | Tekst |  Telefonnummeret til kontakten               |
|  StateOrProvince      | Tekst |  Delstaten eller området i kontaktadressen               |
|  StreetAddress        | Tekst |  Gate i kontaktadressen               |

### <a name="alternatekey"></a>AlternateKey

AlternateKey-tabellen inneholder nøklene til enhetene som var med i foreningsprosessen.

|Column  |Type  |Bekrivelse  |
|---------|---------|---------|
|DataSourceName    |Tekst         | Navnet på datakilden. Eksempel: `datasource5`        |
|EntityName        | Tekst        | Navnet på enheten i Customer Insights. Eksempel: `contact1`        |
|AlternateValue    |Tekst         |Alternativ ID som er tilordnet til kunde-ID-en. Eksempel: `cntid_1078`         |
|KeyRing           | Tekst        | JSON-verdi  </br> Eksempel: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Tekst        | ID for den enhetlige kundeprofilen.         |
|AlternateKeyId     | Unik identifikator        |  Deterministisk GUID for AlternateKey basert på `Identifier`      |
|Identifier |   Tekst      |   `DataSourceName|EntityName|AlternateValue`  </br> Eksempel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Denne tabellen inneholder aktiviteter av brukere som er tilgjengelige i Customer Insights.

| Kolonne            | Type        | Bekrivelse                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Tekst      | Kundeprofil-ID                                                                      |
| ActivityId        | Tekst      | Intern ID for kundeaktiviteten (primærnøkkel)                                       |
| SourceEntityName  | Tekst      | Navnet på kildeenheten                                                                |
| SourceActivityId  | Tekst      | Primærnøkkel fra kildeenheten                                                       |
| ActivityType      | Tekst      | Semantisk aktivitetstype eller navn på egendefinert aktivitet                                        |
| ActivityTimeStamp | Date/klokkeslett    | Aktivitetstidsstempel                                                                      |
| Title             | Tekst      | Tittelen eller navnet på aktiviteten                                                               |
| Description       | Tekst      | Aktivitetsbeskrivelse                                                                     |
| URL               | Tekst      | Kobling til en ekstern nettadresse som er spesifikk for aktiviteten                                         |
| SemanticData      | Tekst | Omfatter en liste over nøkkelverdipar for semantiske tilordningsfelt som er spesifikke for aktivitetstypen |
| RangeIndex        | Tekst      | Unix-tidsstempel som brukes til å sortere aktivitetstidslinjen og spørringer vedrørende gyldig intervall |
| UnifiedActivityId   | Unik identifikator | Intern ID for kundeaktiviteten (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Denne tabellen inneholder utdataene for mål basert på kundeattributter.

| Kolonne             | Type             | Bekrivelse                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Tekst           | Kundeprofil-ID        |
| Measures           | Tekst      | Omfatter en liste over nøkkelverdipar for målnavn og -verdier for gitt kunde |
| Identifier | Tekst           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Unik identifikator     | Kundeprofil-ID |

### <a name="enrichment"></a>Supplering

Denne tabellen inneholder utdataene for suppleringsprosessen.

| Column               | Type             |  Bekrivelse                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Tekst           | Kundeprofil-ID                                 |
| EnrichmentProvider   | Tekst           | Navnet på leverandøren av suppleringen                                  |
| EnrichmentType       | Tekst           | Type supplering                                      |
| Values               | Tekst      | Liste over attributter produsert av suppleringsprosessen |
| EnrichmentId | Unik identifikator            | Deterministisk GUID generert fra `Identifier` |
| Identifier   | Tekst           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prediksjon

Denne tabellen inneholder utdataene til modellprediksjonene.

| Kolonne               | Type        | Bekrivelse                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Tekst      | Kundeprofil-ID                                  |
| ModelProvider        | Tekst      | Navnet på leverandøren av modellen                                      |
| Model                | Tekst      | Modellnavn                                                |
| Values               | Tekst | Liste over attributter produsert av modellen |
| PredictionId | Unik identifikator       | Deterministisk GUID generert fra `Identifier` |
| Identifier   | Tekst      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmentmedlemskap

Denne tabellen inneholder informasjon om segmentmedlemskap for kundeprofilene.

| Kolonne        | Type | Bekrivelse                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Tekst       | Kundeprofil-ID        |
| SegmentProvider      | Tekst       | Appen som publiserer segmentene.      |
| SegmentMembershipType | Tekst       | Type kunde for denne segmentmedlemskapsoppføringen. Støtter flere typer, for eksempel Kunde, Kontakt eller Konto. Standard: Kunde  |
| Segments       | Tekst  | Liste over unike segmenter kundeprofilen er medlem av      |
| Identifier  | Tekst   | Unik identifikator for segmentmedlemskapsoppføringen. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Unik identifikator      | Deterministisk GUID generert fra `Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
