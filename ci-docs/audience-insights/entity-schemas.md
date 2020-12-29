---
title: Customer Insights-enhetsskjemaer i Common Data Model
description: Arbeid med enheter i Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2cf01029ef6b64fe566022d09ce65bca3603189c
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643920"
---
# <a name="entity-schemas-in-common-data-model"></a>Enhetsskjemaer i Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) er en deklarativ spesifikasjon og en definisjon av standardenheter som representerer vanlig brukte konsepter og aktiviteter på tvers av forretnings- og produktivitetsprogrammer. Denne modellen blir også utvidet til observasjonsmessige og analytiske data. Common Data Model tilbyr veldefinerte, modulbaserte og utvidbare forretningsenheter, som konto, forretningsenhet, sak, kontakt, kundeemne, salgsmulighet og produkt, samt samhandlinger med leverandører, arbeidere og kunder, for eksempel aktiviteter og servicenivåavtaler. Alle kan bygge på og utvide Common Data Model-definisjoner for å fange opp flere forretningsspesifikke ideer.

Denne delte datamodellen gjør det mulig for programmer og dataintegrerere å samarbeide enklere ved å gi en enhetlig definisjon av data. Common Data Model inneholder et rikholdig metadatasystem med standard enheter, relasjoner, hierarkier, egenskaper og mer. Den kommer fra Dynamics 365-apper og har åpen kildekode på GitHub med over 260 standard enheter. Et stort system av interne og eksterne partnere bidrar med bransjespesifikke konsepter for Common Data Model.

Flere systemer og plattformer implementerer Common Data Model i dag, inkludert Power BI-dataflyter og Azure Data Services. Den er allerede støttet i Common Data Service Dynamics 365, Power Apps, Power BI og kommende Azure Data Services, og gir direkte verdi mot [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Customer Insights-enhetsskjemaer

For å opprette en 360-graders visning av kunden og gjøre Customer Insights-modeller tilgjengelige i Common Data Model for utvidelse, har vi publisert følgende enhetsskjemaer:

| Enhet | Beskrivelse |
|---------|---------|
|[Kundeaktivitet](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | En aktivitet som er utført av en bruker som har observasjonsmessig verdi for virksomheten. |
|[Kundeprofil](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | En person eller organisasjon som enten har utført, eller som har muligheten til å engasjere seg i, forretningsaktiviteter. |
|[Måldefinisjon](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definisjon av KPI-er partisjonert med null eller flere dimensjoner (for eksempel månedlige aktive brukere, samlet forbruk etter kunde, gjennomsnittlig kundeinnhentingskostnad) |
|[Segment](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definerer en gruppe medlemmer med vanlige egenskaper. |
|[Segmentmedlemskap](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Medlemmer som deltar i et gitt segment. |

Hvis du vil ha mer informasjon, kan du se dokumentasjonen om [Customer Insights-enhetsskjemaer i Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Vise enheter ved hjelp av enhetsnavigatoren for Common Data Model

Du kan vise enheter i [Common Data Model-enhetsnavigatoren](https://microsoft.github.io/CDM/). Velg knappen **Last inn fra GitHub!** , og naviger til **foundationCommon** > **crmCommon** > **løsninger** > **customerInsights**, der du finner en liste over Customer Insights-enheter og definisjoner.
> [!div class="mx-imgBorder"]
> ![CDM-enhetsnavigator som viser Kundeaktivitet-enhet](media/CDM-entity-navigator.png "CDM-enhetsnavigator som viser Kundeaktivitet-enhet")
