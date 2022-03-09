---
title: Kom i gang med målgruppeinnsiktsfunksjonen i Dynamics 365 Customer Insights
description: En oversikt over målgruppeinnsikt hjelpe ressurser med å komme raskt i gang.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 2776b2292560f9ea61a06d2b1b7bc7811d35c860
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353739"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Kom i gang med Dynamics 365 Customer Insights-målgruppeinnsiktsfunksjonen

Målgruppeinnsikt kan hjelpe deg med å få en dypere forståelse av kundene. Koble data fra forskjellige transaksjons-, virkemåte- og observasjonskilder for å opprette en 360-graders kundevisning. Bruk disse innsiktene til å drive kundeorienterte opplevelser og prosesser. Samle og forstå kunde data, og utnytt dataene for intelligent innsikt og handlinger.

## <a name="step-1-create-an-environment"></a>Trinn 1: Opprett et miljø

Du må først opprette et miljø å arbeide i. Hvis organisasjonen allerede har kjøpt en lisens, kan du se [Opprette et miljø](create-environment.md). Hvis du vil starte en prøveversjon for målgruppeinnsikt, kan du se [Konfigurere et prøveversjonsmiljø](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>Trinn 2: Utforsk målgruppeinnsikt

Første gang du logger på målgruppeinnsikt, kan du konfigurere innstillinger og utforske produktet.

1. [Logg på målgruppeinnsikt](https://home.ci.ai.dynamics.com) ved hjelp av Microsoft Azure Active Directory-brukerkontoen (AAD).

1. [Endre miljøet](manage-environments.md#switch-environments) for å se demonstrasjonsdata og [utforske målgruppeinnsikt](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Trinn 3: Innta, samle og konfigurer relasjoner for dataene

Enhetlige profiler er fundamentet for å få innsikt og handle ut fra dataene. Hent inn data fra ulike kilder, og kjør datasammenslåingsprosessen for å kombinere enhetlige profiler. Angi relasjoner mellom de innlagte enhetene bruker suppleringsfunksjoner for å legge til informasjon i profilene. 

1. Innhent data ved å opprette datakilder fra flere alternativer. Velg mellom [Power Query-koblinger](connect-power-query.md), en [Common Data Model-mappe](connect-common-data-model.md) eller [Microsoft Dataverse](/dynamics365/customer-insights/audience-insights/connect-dataverse-managed-lake). 

1. Kjør [datasammenslåingsprosessen](data-unification.md) ved å gå gjennom fasene for [tilordning](map-entities.md), [samsvar](match-entities.md) og [sammenslåing](merge-entities.md).

1. Gjør deg kjent med [enhetene systemet oppretter](entities.md), og opprett [relasjoner mellom de innlagte enhetene](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Trinn 4: Forbedre enhetlige profiler med prediksjoner, aktiviteter og tiltak

Med enhetlige profiler konfigurert kan du forbedre dataene og ytterligere øke informasjonen de gir.

1. Velg blant et utvidende bibliotek over suppleringsleverandører for å [supplere kundedataene](enrichment-hub.md).

1. Bruk [standardmodeller](predictions-overview.md) for å forutsi sannsynligheten for forventede inntekter eller forventede inntekter.

1. [Konfigurer aktiviteter](activities.md) basert på innhentede data og visualisere samhandlinger med kundene på en kronologisk tidslinje. 

1. [Bygg tiltak](measures.md) for å måle forretningsmålene og nøkkelindikatorene.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Trinn 5: Opprett segmenter og aktiver data ved hjelp av ulike eksportalternativer

Nå som dataene er fullført og inneholder et bredt utvalg av informasjon om kundene, er det på tide å lete etter måter å utføre handlinger på med de dataene. 

1. [Opprett segmenter](segments.md), delsett av kundebasen din, for å sikre at handlingene er relevante for kundene som er kontaktet.

1. Bla gjennom den utvidede katalogen over [eksportalternativer](export-destinations.md) der du kan bruke kundedata. Du kan for eksempel bruke data til å administrere kampanjer og kontaktpersoner ved hjelp av digital markedsføring.

1. Se gjennom integreringsalternativer, for eksempel med [direkte tilkobling til engasjementsinnsikt](../engagement-insights/integrate-audience-insights-engagement-insights.md) eller til andre Dynamics 365-apper med [Kundekort-tillegget](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]