---
title: Arbeide med Customer Insights-data i Microsoft Dataverse
description: Lær hvordan du kobler til Customer Insights og Microsoft Dataverse og forstå utdataenhetene som eksporteres til Dataverse.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153416"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbeide med Customer Insights-data i Microsoft Dataverse

Med Customer Insights kan du gjøre utdataenheter tilgjengelige som [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Denne integreringen gjør det enkelt å dele data og å utvikle basert på en tilnærming med lite eller ingen kode. [Utdataenhetene](#output-entities) er tilgjengelige som tabeller i et Dataverse-miljø. Du kan bruke dataene for et hvilket som helst annet program basert på Dataverse-tabeller. Disse tabellene muliggjør scenarioer som automatiske arbeidsflytprosesser via Power Automate eller bygging av apper med Power Apps.

Når du kobler til Dataverse-miljøet, kan du også [samle inn data fra lokale datakilder ved å bruke Power Platform-dataflyter og -gatewayer](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Forutsetning

- Customer Insights og Dataverse-miljøer må driftes i samme område.
- Du må ha en global administrator-rolle i Dataverse-miljøet. Kontroller om dette [Dataverse-miljøet er tilknyttet](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) bestemte sikkerhetsgrupper, og kontroller at du er lagt til i disse sikkerhetsgruppene.
- Ingen andre Customer Insights-miljø er allerede tilknyttet Dataverse-miljøet du vil koble til. Lær hvordan du [fjerner en eksisterende tilkobling til et Dataverse-miljø ](#remove-an-existing-connection-to-a-dataverse-environment).
- Et Microsoft Dataverse-miljø kan bare kobles til én enkelt lagringskonto. Den gjelder bare hvis du konfigurerer miljøet til å [bruke Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Rettighet til Dataverse-lagringskapasitet

Et abonnement på Customer Insights gir deg rett til ekstra kapasitet for organisasjonens eksisterende [Dataverse-lagringskapasitet](/power-platform/admin/capacity-storage). Tilleggskapasiteten avhenger av antall profiler du bruker i abonnementet.

**Eksempel:**

La oss si at du får 15 GB databaselagring og 20 GB fillagring per 100 000 kundeprofiler. Hvis abonnementet omfatter 300 000 kundeprofiler, blir den totale lagringskapasiteten 45 GB (3 x 15 GB) databaselagring og 60 GB fillagring (3 x 20 GB). Hvis du har et B2B-abonnement med 30 000 kontoer, blir den totale lagringskapasiteten 45 GB (3 x 15 GB) databaselagring og 60 GB fillagring (3 x 20 GB).

Loggkapasiteten er ikke trinnvis og fast for organisasjonen.

Hvis du vil ha detaljert informasjon om rettigheter til lagringskapasitet, kan du se [Veiledning om lisenser for Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Koble et Dataverse-miljø til Customer Insights

Trinnet **Microsoft Dataverse** lar deg koble Customer Insights til Dataverse-miljøet mens du [oppretter et Customer Insights-miljø](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datadeling med Microsoft Dataverse automatisk aktivert for netto nye miljøer":::

Administratorer kan konfigurere Customer Insights til å koble til et eksisterende Dataverse-miljø. Når du angir nettadressen i Dataverse-miljøet, kobles den til det nye Customer Insights-miljøet. Etter at du har opprettet tilkoblingen mellom Customer Insights og Dataverse, lar du være å endre organisasjonsnavnet for Dataverse-miljøet. Navnet på organisasjonen brukes i nettadressen til Dataverse, og et endret navn bryter tilkoblingen til Customer Insights.

Hvis du ikke vil bruke et eksisterende Dataverse-miljø, oppretter systemet et nytt miljø for Customer Insights-dataene i leieren. [Power Platform-administratorer kan styre hvem som kan opprette miljøer](/power-platform/admin/control-environment-creation). Når du konfigurerer et nytt Customer Insights-miljø og administratoren har deaktivert opprettingen av Dataverse-miljøer for alle unntatt administratorer, kan det hende du ikke kan opprette et nytt miljø.

**Aktiver datadeling** med Dataverse ved å merke av for datadeling.

Hvis du bruker din egen Data Lake Storage-konto, må du også ha **tillatelsesidentifikatoren** . Hvis du vil ha mer informasjon om hvordan du får tilgangsidentifikatoren, kan du se gjennom følgende del.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktivere datadeling med Dataverse fra din egen Azure Data Lake Storage (forhåndsversjon)

Aktivering av datadeling med Microsoft Dataverse når miljøet [bruker din egen Azure Data Lake Storage-konto](own-data-lake-storage.md), trenger litt ekstra konfigurasjon. Brukeren som konfigurerer Customer Insights-miljøet, må minst ha tillatelsene **Storage Blob Data-leser** på *CustomerInsights*-beholderen i Azure Data Lake Storage-kontoen.

1. Opprett to sikkerhetsgrupper i Azure-abonnementet – én **Leser**-sikkerhetsgruppe og én **Bidragsyter**-sikkerhetsgruppe, og angi Microsoft Dataverse-tjenesten som eier for begge sikkerhetsgruppene.
2. Administrer tilgangskontrollisten (ACL) i CustomerInsights-beholderen på lagringskontoen via disse sikkerhetsgruppene. Legg til Microsoft Dataverse-tjenesten og eventuelle Dataverse-baserte forretningsprogrammer som Dynamics 365 Marketing i  **Leser**-sikkerhetsgruppen med **skrivebeskyttede** tillatelser. Legg *bare* til Customers Insights-programmet i **Bidrag**-sikkerhetsgruppen for å gi **lese- og skrive**-tillatelser til å skrive profiler og innsikt.

### <a name="limitations"></a>Begrensninger

Det er to begrensninger når du bruker Dataverse med din egen Azure Data Lake Storage-konto:

- Det finnes én-til-én-tildeling mellom en Dataverse-organisasjon og en Azure Data Lake Storage-konto. Når en Dataverse-organisasjon er koblet til en lagringskonto, kan den ikke koble til en annen lagringskonto. Denne begrensningen hindrer at en Dataverse ikke fyller ut flere lagringskontoer.
- Datadeling fungerer ikke hvis et oppsett av Azure Private Link er nødvendig for å få tilgang til Azure Data Lake Storage-kontoen din fordi den er bak en brannmur. Dataverse støtter for øyeblikket ikke tildelingen til private endepunkter via Private Link.

### <a name="set-up-powershell"></a>Konfigurer PowerShell

Hvis du vil kjøre PowerShell-skriptene, må du først konfigurere PowerShell i henhold til dette.

1. Installer den nyeste versjonen av [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. Velg Windows-tasten på tastaturet på PC-en, søk etter **Windows PowerShell**, og velg **Kjør som administrator**.
   1. I PowerShell-vinduet som åpnes, skriver du inn `Install-Module AzureAD`.
2. Importer tre moduler.
    1. I PowerShell-vinduet angir du `Install-Module -Name Az.Accounts` og følger trinnene.
    1. Gjenta for `Install-Module -Name Az.Resources` og `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Konfigurasjonstrinn

1. Last ned de to PowerShell-skriptene du må kjøre fra teknikerens [GitHub-repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Du må ha *leieradmin*-tilgang for å kjøre dette PowerShell-skriptet.
       - Dette PowerShell-skriptet oppretter to sikkerhetsgrupper på Azure-abonnementet. Ett for lesergruppe og et annet for bidragsytergruppe, og vil gjøre Microsoft Dataverse-tjenesten til eier for begge disse sikkerhetsgruppene.
       - Kjør dette PowerShell-skriptet i Windows PowerShell ved å angi Azure-abonnements-IDen som inneholder Azure Data Lake Storage. Åpne PowerShell-skriptet i et redigeringsprogram for å se gjennom tilleggsinformasjon og logikken som er implementert.
       - Lagre begge ID-verdiene for sikkerhetsgruppe som genereres av dette skriptet, fordi vi skal bruke dem i skriptet `ByolSetup.ps1`.

        > [!NOTE]
        > Oppretting av sikkerhetsgrupper kan deaktiveres for leieren. I det tilfellet kreves det en manuell konfigurasjon og Azure AD-administratoren må [aktivere oppretting av sikkerhetsgrupper](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Du må ha tillatelsene for *Eier av Storage Blob Data* på lagringskonto-/beholdernivå for å kjøre dette skriptet, ellers opprettes det et skript for deg. Rolletilordningen kan fjernes manuelt etter at skriptet er kjørt.
        - Dette PowerShell-skriptet legger til den nødvendige rollebaserte tilgangskontrollen for Microsoft Dataverse-tjenesten og eventuelle Dataverse-baserte forretningsprogrammer. Den oppdaterer også tilgangskontrollisten (ACL) i CustomerInsights-beholderen for sikkerhetsgruppene som opprettes med skriptet `CreateSecurityGroups.ps1`. Bidragsyteregruppen har også *RWX* tillatelse og lesergruppen har bare *r-x*-tillatelse.
        - Kjør dette PowerShell-skriptet i Windows PowerShell ved å angi Azure-abonnement-ID-en som inneholder Azure Data Lake Storage, lagringskontonavnet, ressursgruppenavnet og ID-verdier for leser og bidragsyter-sikkerhetsgruppe. Åpne PowerShell-skriptet i et redigeringsprogram for å se gjennom tilleggsinformasjon og logikken som er implementert.
        - Kopier utdatastrengen etter at skriptet er kjørt. Utdatastrengen ser slik ut: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Angi utdatastrengen som kopieres ovenfor, i **Tillatelsesidentifikator**-feltet i miljøkonfigurasjonstrinnet for Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurasjonsalternativer for å aktivere datadeling fra din egen Azure Data Lake Storage med Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Fjern en eksisterende tilkobling til et Dataverse-miljø

Når du kobler til et Dataverse-miljø, vises feilmeldingen **Denne CDS-organisasjonen er allerede knyttet til en annen Customer Insights-forekomst**, betyr at Dataverse-miljøet allerede er brukt i et Customer Insights-miljø. Du kan fjerne den eksisterende tilkoblingen som en global administrator i Dataverse-miljøet. Det kan ta noen timer før endringene fylles ut.

1. Gå til [Power Apps](https://make.powerapps.com).
1. Velg miljøet fra miljøvelgeren.
1. Gå til **Løsninger**
1. Avinstaller eller slett løsningen kalt **Dynamics 365 Customer Insights-tillegg for kundekort (forhåndsvisning)**.

OR

1. Åpne Dataverse-miljøet.
1. Gå til **Avanserte innstillinger** > **Løsninger**.
1. Avinstaller **CustomerInsightsCustomerCard**-løsningen.

Hvis fjerningen av tilkoblingen mislykkes på grunn av avhengigheter, må du også fjerne avhengighetene. Hvis du vil ha mer informasjon, kan du se [Fjerning av avhengigheter](/power-platform/alm/removing-dependencies).

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

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
