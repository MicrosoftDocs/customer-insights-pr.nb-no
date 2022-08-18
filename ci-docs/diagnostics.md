---
title: Eksporter diagnoselogger (forhåndsversjon)
description: Finn ut hvordan du sender logger til Microsoft Azure Monitor.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245937"
---
# <a name="export-diagnostic-logs-preview"></a>Eksporter diagnoselogger (forhåndsversjon)

Videresend logger fra Customer Insights med Azure Monitor. Med Azure Monitor-ressurslogger kan du overvåke og sende logger til [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), eller strømme dem til [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Customer Insights sender følgende hendelseslogger:

- **Overvåkingshendelser**
  - **APIEvent** – aktiverer endringssporing via Dynamics 365 Customer Insights-brukergrensesnittet.
- **Driftshendelser**
  - **WorkflowEvent** – gjør det mulig å konfigurere [datakilder](data-sources.md), [samle](data-unification.md), [supplere](enrichment-hub.md) og [eksportere](export-destinations.md) data til andre systemer. Disse trinnene kan utføres enkeltvis (for eksempel utløse én enkelt eksport). De kan også kjøre iverksatt (for eksempel dataoppdatering fra datakilder som utløser samlingsprosessen, noe som vil trekke inn suppleringer og eksportere dataene til et annet system). Du finner mer informasjon i [WorkflowEvent-skjemaet](#workflow-event-schema).
  - **APIEvent** – sender alle API-kall til kunder-forekomsten til Dynamics 365 Customer Insights. Du finner mer informasjon i [APIEvent-skjemaet](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Konfigurere diagnoseinnstillingene

### <a name="prerequisites"></a>Forutsetning

- Et aktivt [Azure-abonnement](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Administrator](permissions.md#admin)-tillatelser i Customer Insights.
- [Bidragsyter og Brukertilgangsadministrator](/azure/role-based-access-control/role-assignments-portal) på målressursen i Azure. Ressursen kan være en Azure Data Lake Storage-konto, et Azure-hendelsessenter eller et Azure Log Analytics-arbeidsområde. Denne tillatelsen er nødvendig når du konfigurerer diagnoseinnstillinger i Customer Insights, men den kan endres etter at installasjonen er fullført.
- [Målkrav](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) for Azure Storage, Azure-hendelseshub eller Azure Log Analytics er oppfylt.
- Minst **leser**-rollen på ressursgruppen som ressursen tilhører.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Konfigurere diagnostisering med Azure Monitor

1. I Customer Insights går du til **Admin** > **System**, og deretter velger du fanen **Diagnose**.

1. Velg **Legg til mål**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Diagnostikktilkobling.":::

1. Angi et navn i feltet **Navn på diagnosemål**.

1. Velg **ressurstypen** (lagringskonto, hendelsessenter eller logganalyse).

1. Velg **abonnementet**, **ressursgruppen** og **ressursen** for målressursen. Se [Konfigurasjon i målressursen](#configuration-on-the-destination-resource) hvis du vil ha tillatelses- og logginformasjon.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til system** for å koble til målressursen. Loggene vises i målet etter 15 minutter hvis API-en er i bruk og genererer hendelser.

## <a name="configuration-on-the-destination-resource"></a>Konfigurasjon på målressursen

Avhengig av hvilken ressurstype du velger, gjelder skjer følgende endringer automatisk:

### <a name="storage-account"></a>Storage account

Tjenestekontohaveren for Customer Insights får tillatelsen **Bidragsyter for lagringskonto** for den valgte ressursen og oppretter to beholdere under det valgte navneområdet:

- `insight-logs-audit` inneholder **overvåkingshendelser**
- `insight-logs-operational` inneholder **driftshendelser**

### <a name="event-hub"></a>Hendelsessenter

Tjenestekontohaveren for Customer Insights får tillatelsen **Azure Event Hubs-dataeier** for den valgte ressursen og oppretter to hendelseshuber under det valgte navneområdet:

- `insight-logs-audit` inneholder **overvåkingshendelser**
- `insight-logs-operational` inneholder **driftshendelser**

### <a name="log-analytics"></a>Logganalyse

Tjenestekontohaveren for Customer Insights-tjenesten får tillatelsen **Bidragsyter for logganalyse** for ressursen. Loggene er tilgjengelige under **Logger** > **Tabeller** > **Loggbehandling** på det valgte Log Analytics-arbeidsområdet. Utvid **Loggbehandling**-løsningen og finn `CIEventsAudit` og `CIEventsOperational`-tabellene.

- `CIEventsAudit` inneholder **overvåkingshendelser**
- `CIEventsOperational` inneholder **driftshendelser**

Under **Spørringer**-vinduet utvider du **Spor endringer**-løsningen og finner eksempelspørringene ved å søke etter `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Fjern et diagnosemål

1. Gå til **Administrator** > **System**, og velg fanen **Diagnose**.

1. Velg diagnosemålet i listen.

   > [!TIP]
   > Når du fjerner målet, stoppes videresending av loggen, men ressursen slettes ikke i Azure-abonnementet. Hvis du vil slette ressursen i Azure, velger du koblingen i **Handlinger**-kolonnen for å åpne Azure Portal for den valgte ressursen og sletter den der. Slett deretter diagnosemålet.

1. I **Handlinger**-kolonnen velger du **Slett**-ikon.

1. Bekreft slettingen for å fjerne målet og stoppe videresending av loggen.

## <a name="log-categories-and-event-schemas"></a>Loggkategorier og hendelsesskjemaer

For øyeblikket støttes [API-hendelser](apis.md) og arbeidsflythendelser, og følgende kategorier og skjemaer gjelder.
Loggskjemaet følger det vanlige [Azure Monitor-skjemaet](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorier

Customer Insights inneholder to kategorier:

- **Overvåkingshendelser**: [API-hendelser](#api-event-schema) for å spore konfigurasjonsendringene for tjenesten. `POST|PUT|DELETE|PATCH`-operasjoner går inn i denne kategorien.
- **Driftshendelser**: [API-hendelser](#api-event-schema) eller [arbeidsflythendelser](#workflow-event-schema) som genereres under bruk av tjenesten.  For eksempel `GET` forespørsler eller utføringshendelser for en arbeidsflyt.

## <a name="event-schemas"></a>Hendelsesskjemaer

API-hendelser og arbeidsflythendelser har en felles struktur, men med noen få forskjeller. Du finner mer informasjon i [API-hendelsesskjema](#api-event-schema) eller [arbeidsflytskjema](#workflow-event-schema).

### <a name="api-event-schema"></a>API-hendelsesskjema

| Felt             | DataType  | Obligatorisk/valgfritt | Description       | Eksempel        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Tidsstempel | Kreves          | Timestamp til hendelsen (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Kreves          | ResourceId for forekomsten som utsendte hendelsen         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Kreves          | Navnet på operasjonen som representeres av denne hendelsen.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Kreves          | Loggkategorien for hendelsen. Enten `Operational` eller `Audit`. Alle POST/PUT/PATCH/DELETE HTTP-forespørsler er merket med `Audit`, alt annet med `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Kreves          | Statusen for hendelsen. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Valgfritt          | Resultstatus for hendelsen. Hvis operasjonen tilsvarer et REST-API-kall, er det HTTP-statuskoden.        | `200`             |
| `durationMs`      | Lang      | Valgfritt          | Varighet for operasjonen i millisekunder.     | `133`     |
| `callerIpAddress` | String    | Valgfritt          | IP-adresse for oppringer hvis operasjonen samsvarer med et API-kall som kommer fra en allmenn tilgjengelig IP-adresse.                                                 | `144.318.99.233`         |
| `identity`        | String    | Valgfritt          | JSON-objekt som beskriver identiteten til brukeren eller programmet som gjorde operasjonen.       | Se [Identitet](#identity-schema)-delen.     |  
| `properties`      | String    | Valgfritt          | JSON-objekt med flere egenskaper for den bestemte kategorien av hendelser.      | Se [Egenskaper](#api-properties-schema)-delen.    |
| `level`           | String    | Kreves          | Alvorsgradsnivå for hendelsen.    | `Informational`, `Warning`, `Error` eller `Critical`.           |
| `uri`             | String    | Valgfritt          | URI for absolutt forespørsel.    |               |

#### <a name="identity-schema"></a>Identitetsskjema

`identity`-JSON-objektet har følgende struktur

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Felt                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Tilordnet rolle for brukeren eller appen. Du finner mer informasjon i [brukertillatelser](permissions.md).                                     |
| `Authorization.RequiredRoles` | Obligatoriske roller for å utføre operasjonen. `Admin`-rollen har tillatelse til å utføre alle operasjoner.                                                    |
| `Claims`                      | Krav til brukeren eller app, JSON Web Token (JWT). Krevegenskaper varierer per organisasjon, og Azure Active Directory-konfigurasjonen. |

#### <a name="api-properties-schema"></a>API-egenskapsskjema

[API-hendelser](apis.md) har følgende egenskaper.

| Felt                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Alltid `ApiEvent`, merker logghendelsen som API-hendelse.                                                                 |
| `properties.userAgent`       | Nettleseragent som sender forespørselen eller `unknown`.                                                                        |
| `properties.method`          | HTTP-metode: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relativ bane til forespørselen.                                                                                          |
| `properties.origin`          | URI som angir hvor en Fetch kommer fra eller `unknown`.                                                                  |
| `properties.operationStatus` | `Success` for HTTP-statuskode < 400 <br> `ClientError` for HTTP-statuskode < 500 <br> `Error` for HTTP-status >= 500 |
| `properties.tenantId`        | Organisasjons-ID                                                                                                        |
| `properties.tenantName`      | Navnet på organisasjonen.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId for oppringeren.                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Skjema for arbeidsflythendelse

Arbeidsflyten inneholder flere trinn. [Hente inn datakilder](data-sources.md), [forene](data-unification.md), [supplere](enrichment-hub.md) og [eksportere](export-destinations.md) data. Alle disse trinnene kan kjøres individuelt eller orkestrert med følgende prosesser.

#### <a name="operation-types"></a>Operasjonstyper

| OperationType     | Grupper                                     |
| ----------------- | ----------------------------------------- |
| Inntak         | [Datakilder](data-sources.md)           |
| DataPreparation   | [Datakilder](data-sources.md)           |
| Tilordne               | [Datasamling](data-unification.md)   |
| Treff             | [Datasamling](data-unification.md)   |
| Flett             | [Datasamling](data-unification.md)   |
| ProfileStore      | [Kundeprofiler](customer-profiles.md) |
| Søk            | [Kundeprofiler](customer-profiles.md) |
| Aktivitet          | [Aktiviteter](activities.md)                  |
| AttributeMeasures | [Segmenter og mål](segments.md)      |
| EntityMeasures    | [Segmenter og mål](segments.md)      |
| Mål          | [Segmenter og mål](segments.md)      |
| Segmentering      | [Segmenter og mål](segments.md)      |
| Supplering        | [Supplering](enrichment-hub.md)                                          |
| Intelligens      | [Prediksjoner](predictions-overview.md)                                          |
| AiBuilder         | [Prediksjoner](predictions-overview.md)                                          |
| Innsikt          | [Prediksjoner](predictions-overview.md)                                          |
| Export            | [Eksporter](export-destinations.md)                                          |
| ModelManagement   | [Prediksjoner](custom-models.md)                                           |
| Relasjon      | [Datasamling](relationships.md)                                           |

#### <a name="field-description"></a>Feltbeskrivelse

| Felt           | DataType  | Obligatorisk/valgfritt | Description                                                                                                                                                   | Eksempel                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Tidsstempel | Kreves          | Timestamp til hendelsen (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Kreves          | ResourceId for forekomsten som utsendte hendelsen.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Kreves          | Navnet på operasjonen som representeres av denne hendelsen. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Se [Operasjonstyper](#operation-types) for referanse. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Kreves          | Loggkategorien for hendelsen. Alltid `Operational` for arbeidsflythendelser                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Kreves          | Statusen for hendelsen. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Lang      | Valgfritt          | Varighet for operasjonen i millisekunder.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Valgfritt          | JSON-objekt med flere egenskaper for den bestemte kategorien av hendelser.                                                                                        | Se underdelen [Arbeidsflytegenskaper](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Kreves          | Alvorsgradsnivå for hendelsen.                                                                                                                                  | `Informational`, `Warning` eller `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Arbeidsflytegenskaper-skjema

Arbeidsflythendelser har følgende egenskaper.

| Felt              | Workflow | Oppgave | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ja      | Ja  | Alltid `WorkflowEvent`, merker logghendelsen som arbeidsflythendelse.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ja      | Ja  | Identifikator for arbeidsflytkjøringen. Alle arbeidsflyt- og oppgavehendelser i arbeidsflytkjøringen har samme `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ja      | Ja  | Identifikator for operasjonen, se [Operasjonstyper](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Ja      | No   | Bare arbeidsflyt. Antall oppgaver arbeidsflyten utløser.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ja      | No   | Valgfritt. Bare arbeidsflythendelser. Azure Active Directory [objectId for brukeren](/azure/marketplace/find-tenant-object-id#find-user-object-id) som utløste arbeidsflythendelsen, se også `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ja      | No   | `full` eller `incremental` oppdater.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ja      | No   | `OnDemand` eller `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ja      | No   | `Running` eller `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ja      | Ja  | UTC-timestamp `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ja      | Ja  | UTC-timestamp `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ja      | Ja  | UTC-timestamp `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ja      | Ja  | Customer Insights `instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Ja  | - For OperationType = `Export` er identifikatoren GUIDen for eksportkonfigurasjonen. <br> - For OperationType = `Enrichment` er det GUID-en for suppleringen <br> - For OperationType `Measures` og `Segmentation` er identifikatoren enhetsnavnet. |
| `properties.friendlyName`                    | No       | Ja  | Brukervennlig navn på eksporten eller enheten som behandles.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ja  | Valgfritt. Feilmelding med flere detaljer.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ja  | Valgfritt. Bare for OperationType `Export`. Identifiserer typen eksport. Hvis du vil ha mer informasjon, kan du se [Oversikt over eksportmål](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ja  | Valgfritt. Bare for OperationType `Export`. Inneholder en liste over konfigurerte enheter i eksporten.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ja  | Valgfritt. Bare for OperationType `Export`. Detaljert melding for eksporten.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ja  | Valgfritt. Bare for OperationType `Segmentation`. Angir totalt antall medlemmer som segmentet har.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
