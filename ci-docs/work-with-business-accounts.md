---
title: Komme i gang med forretningskontoer som primær målgruppe
description: Lær om forretningskontoer som primær målgruppe Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: f16c8ad50ed290562fa9f223a3e8c86228e5331e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647000"
---
# <a name="work-with-business-accounts"></a>Arbeide med forretningskontoer

Dynamics 365 Customer Insights gjør det mulig å konfigurere miljøet for ulike primære målgrupper: enkeltforbrukere (B-til-C) og forretningskontoer (B-til-B). I B-til-C-scenarioer er dataene sentrert rundt enkeltpersoner. For B-til-B er primær målgruppe kontoer – organisasjoner eller firmaer – og kontakter. Denne artikkelen hjelper deg med å komme i gang med et miljø for forretningskontoer. Den viser forskjellene for funksjonsområdene i Customer Insights, avhengig av miljøfokuset. Hvis du vil ha mer informasjon om forskjeller, kan du se gjennom dokumentene i funksjonsområdene. 

## <a name="create-an-environment-for-business-accounts"></a>Opprette et miljø for forretningskontoer

Administratorer kan [opprette et miljø i en eksisterende organisasjon](create-environment.md). Et trinn i prosessen med å opprette et nytt miljø ber administratorer om den primære målgruppen for miljøet. I tilfelle det er den første konfigurasjonen etter å ha kjøpt en lisens, hjelper en veiledet opplevelse med opprettelsen av det første miljøet.

Deretter kan du [legge inn data](data-sources.md) for forretningskontoer og relaterte kontakter som datakilder fra alle støttede kilder.

Når dataene er slått sammen [angir du forretningsforbindelseshierarkier](relationships.md#set-up-account-hierarchies) som en del av relasjonskonfigurasjonen. Du kan også [konfigurere semantiske tilordninger](semantic-mappings.md) for å koble kontakt- og forretningsforbindelsesenheter. 

## <a name="switch-between-primary-target-audience"></a>Veksle mellom primære målgrupper

Hvis organisasjonen vedlikeholder miljøer for individuelle kunder og forretningskontoer, kan du bruke veksleren i den venstre ruten til å velge primær målgruppe.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Veksler for å endre primær målgruppe mellom individuelle kunder og forretningskontoer.":::

## <a name="supported-feature-areas"></a>Støttede funksjonsområder

- [Aktiviteter](activities.md): Støtte for forretningsforbindelser og relaterte kontakter for å opprette aktiviteter og vise dem på en tidslinje.
- [Relasjoner](relationships.md): Aktivitetsveiviseren hjelper deg med å opprette relasjoner mellom enhetene, slik at visningen for forretningsforbindelsen kan vise alle aktiviteter fra kontakter. Kontaktpersoner kan drille opp for å se kontaktvisning, og hierarkier kan brukes for aktivetetsaggregasjoner for forretningsforbindelser.
- [Mål](measures.md): Støtter mål som er opprettet fra målbyggeverktøy med én beregning. En valgfri innstilling tillater opprulling av underordnede forretningsforbindelser når du oppretter mål.
- [Segmenter](segments.md): Støtter segmenter som opprettes fra bunnen av med segmentbyggeverktøyet. Nye operatorer tillater innlemmelse av forretningsforbindelseshierarki når de bygger segmenter.
- [Datainntak](data-sources.md): Alle funksjonene i dette området er de samme for forretningskontoer og individuelle kunder.
- [Dataforening](data-unification.md): Alle funksjonene i dette området er de samme for forretningskontoer og individuelle kunder.
- [Supplering](enrichment-hub.md): Noen suppleringstyper er bare tilgjengelige for individuelle kundescenarioer, mens andre bare er tilgjengelige for forretningskontoer.
- [Prognoser og standardmodeller](predictions-overview.md): Prediksjon for transaksjonsfrafall inneholder ytterligere trinn for forretningskontoer. Andre prognoser er bare tilgjengelige for enkeltkunder.
- [Aktivering og eksport](export-destinations.md): Eksporter er tilgjengelige for forretningskontoer og individuelle kunder. Noen eksporter krever ekstra konfigurasjon og kontaktinformasjon som beregnes i de underliggende segmentene for å være gyldig for forretningskontoer.
- [Systeminnstillinger](system.md) og [brukeradministrasjon](permissions.md): Alle funksjonene i dette området er de samme for forretningskontoer og individuelle kunder.
