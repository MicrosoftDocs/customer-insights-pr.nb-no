---
title: Komme i gang med Dynamics 365 Customer Insights
description: En oversikt over Customer Insights hjelper ressurser med å komme raskt i gang.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: ce0336c4bf853bc81ec01c45410169a63b69eb03
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304623"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Komme i gang med Dynamics 365 Customer Insights

Customer Insights kan hjelpe deg med å få en dypere forståelse av kundene. Koble data fra forskjellige transaksjons-, virkemåte- og observasjonskilder for å opprette en 360-graders kundevisning. Bruk disse innsiktene til å drive kundeorienterte opplevelser og prosesser. Samle og forstå kunde data, og utnytt dataene for intelligent innsikt og handlinger.

## <a name="step-1-create-an-environment"></a>Trinn 1: Opprett et miljø

Opprett først et miljø å arbeide i. Hvis organisasjonen allerede har kjøpt en lisens, kan du se [Opprette et miljø](create-environment.md). Hvis du vil starte en prøveversjon for Customer Insights, kan du se [Konfigurer et prøvemiljø](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Trinn 2: Utforsk Customer Insights

Første gang du logger på Customer Insights, konfigurerer du innstillinger og utforsker produktet.

1. [Logg på Customer Insights](https://home.ci.ai.dynamics.com) ved hjelp av Microsoft Azure Active Directory-brukerkontoen (AAD).

1. Endre miljøet for å se demonstrasjonsdata og [utforske Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Trinn 3: Innta, samle og konfigurer relasjoner for dataene

Enhetlige profiler er fundamentet for å få innsikt og handle ut fra dataene. Hent inn data fra ulike kilder, og kjør datasammenslåingsprosessen for å kombinere enhetlige profiler. Angi relasjoner mellom de registrerte enhetene, og bruk suppleringsfunksjoner for å legge til informasjon i profilene.

1. Innhent data ved å opprette datakilder fra flere alternativer. Velg mellom [Azure Data Lake Storage, inkludert Common Data Model](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md) eller [Power Query-tilkoblinger](connect-power-query.md).

1. Kjør [datasamlingsprosessen](data-unification.md) ved å identifisere [kildefeltene](map-entities.md), fjerne [duplikater](remove-duplicates.md), [samsvarende betingelser](match-entities.md) og [samle felter](merge-entities.md).

1. Gjør deg kjent med [enhetene systemet oppretter](entities.md), og opprett [relasjoner mellom de innlagte enhetene](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Trinn 4: Forbedre enhetlige profiler med prediksjoner, aktiviteter og tiltak

Med enhetlige profiler konfigurert kan du forbedre dataene og ytterligere øke informasjonen de gir.

1. Velg blant et utvidende bibliotek over suppleringsleverandører for å [supplere kundedataene](enrichment-hub.md).

1. Bruk [standardmodeller](predictions-overview.md) for å forutsi sannsynligheten for forventede inntekter eller forventede inntekter.

1. [Konfigurer aktiviteter](activities.md) basert på innhentede data og visualisere samhandlinger med kundene på en kronologisk tidslinje.

1. [Bygg tiltak](measures.md) for å måle forretningsmålene og nøkkelindikatorene.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Trinn 5: Opprett segmenter og aktiver data ved hjelp av ulike eksportalternativer

Nå som dataene er fullført og inneholder et bredt utvalg av informasjon om kundene, kan du lete etter måter å utføre handlinger på.

1. [Opprett segmenter](segments.md), delsett av kundebasen din, for å sikre at handlingene er relevante for kundene som er kontaktet.

1. Bla gjennom den utvidede katalogen over [eksportalternativer](export-destinations.md) der du kan bruke kundedata. Du kan for eksempel bruke data til å administrere kampanjer og kontaktpersoner ved hjelp av digital markedsføring.

1. Se gjennom integreringsalternativer, for eksempel for andre Dynamics 365-apper med [Kundekort-tillegget](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
