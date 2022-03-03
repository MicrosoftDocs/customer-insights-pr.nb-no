---
title: Customer Insights-enhetsskjemaer i Common Data Model
description: Arbeid med enheter i Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f0af2a6d8a90ff01ea9d4eeb29f34113261fd0d4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231051"
---
# <a name="entity-schemas-in-common-data-model"></a>Enhetsskjemaer i Common Data Model



[Common Data Model](/common-data-model/) er en deklarativ spesifikasjon og en definisjon av standardenheter som representerer vanlig brukte konsepter og aktiviteter på tvers av forretnings- og produktivitetsprogrammer. Denne modellen blir også utvidet til observasjonsmessige og analytiske data. Common Data Model tilbyr veldefinerte, modulbaserte og utvidbare forretningsenheter, som konto, forretningsenhet, sak, kontakt, kundeemne, salgsmulighet og produkt, samt samhandlinger med leverandører, arbeidere og kunder, for eksempel aktiviteter og servicenivåavtaler. Alle kan bygge på og utvide Common Data Model-definisjoner for å fange opp flere forretningsspesifikke ideer.

Denne delte datamodellen gjør det mulig for programmer og dataintegrerere å samarbeide enklere ved å gi en enhetlig definisjon av data. Common Data Model inneholder et rikholdig metadatasystem med standard enheter, relasjoner, hierarkier, egenskaper og mer. Den kommer fra Dynamics 365-apper og har åpen kildekode på GitHub med over 260 standard enheter. Et stort system av interne og eksterne partnere bidrar med bransjespesifikke konsepter for Common Data Model.

Flere systemer og plattformer implementerer Common Data Model i dag, inkludert Power BI-dataflyter og Azure Data Services. Det støttes allerede i Microsoft Dataverse, Dynamics 365, Power Apps, og Power BI og kommende Azure-datatjenester, som direkte påløper verdi i [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Customer Insights-enhetsskjemaer

For å opprette en 360-graders visning av kunden og gjøre Customer Insights-modeller tilgjengelige i Common Data Model for utvidelse, har vi publisert følgende enhetsskjemaer:

| Enhet | Beskrivelse |
|---------|---------|
|[Kundeaktivitet](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | En aktivitet som er utført av en bruker som har observasjonsmessig verdi for virksomheten. |
|[Kundeprofil](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | En person eller organisasjon som enten har utført, eller som har muligheten til å engasjere seg i, forretningsaktiviteter. |
|[Måldefinisjon](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definisjon av KPI-er partisjonert med null eller flere dimensjoner (for eksempel månedlige aktive brukere, samlet forbruk etter kunde, gjennomsnittlig kundeinnhentingskostnad) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definerer en gruppe medlemmer med vanlige egenskaper. |
|[Segmentmedlemskap](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Medlemmer som deltar i et gitt segment. |

Hvis du vil ha mer informasjon, kan du se dokumentasjonen om [Customer Insights-enhetsskjemaer i Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Vise enheter ved hjelp av enhetsnavigatoren for Common Data Model

Du kan vise enheter i [Common Data Model-enhetsnavigatoren](https://microsoft.github.io/CDM/). Velg en enhet i Insights Application-delen for å få listen over Customer Insights-enheter og deres definisjoner.
> [!div class="mx-imgBorder"]
> ![CDM-enhetsnavigator som viser Kundeaktivitet-enhet.](media/CDM-entity-navigator.png "CDM-enhetsnavigator som viser Kundeaktivitet-enhet")


[!INCLUDE[footer-include](../includes/footer-banner.md)]
