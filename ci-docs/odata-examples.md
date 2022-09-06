---
title: OData-spørringsekseringer for API-er for Customer Insights
description: Vanlige eksempler på OData (Open Data Protocol) for å spørre API-ene for Customer Insights for å se gjennom data.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387214"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>OData-spørringsekseringer for API-er for Customer Insights

OData (Open Data Protocol) er en datatilgangsprotokoll som er bygd på kjerneprotokoller som HTTP. Den bruker allment aksepterte metoder som REST for Internett. Det finnes ulike typer biblioteker og verktøy som kan brukes til å bruke OData-tjenester.

For å bygge dine egne implementeringer basert på [API-er for Customer Insights](apis.md) går du gjennom noen ofte forespurte eksempelspørringer.

Endre spørringseksemplene slik at de fungerer i målmiljøene:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` der {instanceId} er GUID for Customer Insights-miljøet du vil spørre om. Du kan bruke [ListAllInstances-operasjonen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) til å finne {InstanceId} du har tilgang til.
- {CID}: GUID for en enhetlig kundeoppføring. Eksempel: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identifikator for primærnøkkelen for en kundeoppføring i en datakilde. Eksempel: `CNTID_1002`
- {DSname}: Streng med enhetsnavnet for en datakilde som blir innlagt i Customer Insights. Eksempel: `Website_contacts`.
- {SegmentName}: Streng med utdataenhetsnavnet for et segment i Customer Insights. Eksempel: `Male_under_40`.

## <a name="customer"></a>Kunde

Eksempelspørringer for *Kunde*-enheten.

|Spørringstype |Eksempel  | Merk  |
|---------|---------|---------|
|Enkelt kunde-ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternativ nøkkel    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternative nøkler beholdes i enhet for enhetlige kunder       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|om    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternativ nøkkel + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Søk  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Returnerer de ti beste resultatene for en søkestreng      |
|Segmentmedlemskap  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Returnerer et antall rader for serienummer fra segmenteringsenheten.      |
|Segmentmedlemskap for en kunde | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Returnerer kundeprofilen hvis de er medlem i gitt segment     |

## <a name="unified-activity"></a>Enhetlig aktivitet

Eksempelspørringer for *UnifiedActivity*-enheten.

|Spørringstype |Eksempel  | Merk  |
|---------|---------|---------|
|Aktivitet for CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Viser aktiviteter for en bestemt kundeprofil |
|Aktivitetstidsramme    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktiviteter for en kundeprofil i en tidsramme       |
|Aktivitetstype    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivitet etter visningsnavn     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Aktivitetssortering    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Sorter aktiviteter stigende eller synkende       |
|Aktivitet utvidet fra segmentmedlemskap  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Andre eksempler

Eksempelspørringer for andre enheter.

|Spørringstype |Eksempel  | Merk  |
|---------|---------|---------|
|Mål for CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Supplerte merker for CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Supplerte interesser for CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + utvid     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Ikke støttede OData-spørringer

Følgende spørringer støttes ikke av Customer Insights:

- `$filter` på inntatte kildeenheter. Du kan bare kjøre $filter-spørringer på systemenheter som Customer Insights oppretter.
- `$expand` fra en `$search`-spørring. Eksempel: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` fra `$select` hvis bare et delsett av attributter er valgt. Eksempel: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand`-supplerte varemerker eller interessetilknytninger for en gitt kunde. Eksempel: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Spørring av utdataenheter for prediksjonsmodell gjennom alternativ nøkkel. Eksempel: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
