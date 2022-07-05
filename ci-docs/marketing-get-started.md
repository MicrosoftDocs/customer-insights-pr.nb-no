---
title: Bruk enhetlige profiler i Dynamics 365 Marketing
description: Finn ut hvordan du integrerer enhetlige profiler og segmenter med Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054444"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>Bruk enhetlige kundeprofiler i Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) beriker kundeopplevelser og gjør at du kan organisere tilpassede reiser på tvers av alle berøringspunkter for å forsterke relasjoner og oppnå lojalitet. Dynamics 365 Marketing-appen fungerer sømløst med Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams og andre produkter, og lar deg ta raskere og bedre beslutninger ved å bruke data og kunstig intelligens.

Ved å koble Customer Insights-data til Marketing kan du gjøre følgende:

- Målrette mot enhetlige kundeprofiler og segmenter. Dette gjør det mulig for deg å engasjere hver kunde, uavhengig av plasseringen til kundens data.
- Baser dynamisk innhold (for eksempel tilpassede tokener) i e-poster, SMS og push-varsler på målinger som lojalitetsstatus, fornyelse av abonnementsdato, overordnet forretningsforbindelse eller andre målinger du har tatt opp i den enhetlige Customer Insights-profilen.
- Laste inn data fra Marketing til Customer Insights og kombinere den med kundedata fra andre kilder.
- Bruk verktøy for Customer Insights-datarensing, supplering og tilnærmet samsvar.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Bruk omfattende kundeprofiler i sanntidsmarkedsføring

Med sanntidsmarkedsføring kan du opprette [egendefinerte utløsere](/dynamics365/marketing/real-time-marketing-custom-triggers) som lanserer kundereiser basert på enhver kundehandling. Jo mer tilpassede dataene er, jo mer relevante og tilpassede blir reisene. Det er dette som gjør kombinasjon av Marketing og Customer Insights så kraftig. Du kan [samle data](data-unification.md) fra alle kilder og deretter bruke dem til å fylle på hypertilpassede kundereiser.

Finn ut mer: [Bruke Customer Insights-profiler og -segmenter i sanntidsmarkedsføring](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Bruk enhetlige segmenter med utgående kundereiser

Med Customer Insights kan du finjustere data fra mange kilder og kombinere dem i samlede kundesegmenter. Ved å [koble Customer Insights til utgående markedsføring](export-dynamics365-marketing.md) vil disse segmentene automatisk vises *og* oppdateres automatisk i kundereiseutformingen.

Finn ut mer: [Bruk segmenter fra Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Hent data fra din egen Azure Data Lake Storage

Du er ikke begrenset til skylagring hvis du vil bruke Customer Insights-data med Marketing. Hvis du allerede har din egen Azure Data Lake Storage opprettet, kan du koble til Customer Insights og deretter dele dataene med Marketing-appen på samme måte som med et skybasert oppsett.

Finn ut mer: [Aktiver datadeling med Dataverse fra din egen Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
