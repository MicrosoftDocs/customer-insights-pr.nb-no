---
title: Startside i målgruppeinnsikt
description: Kom i gang med å utforske appen på startsiden.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406521"
---
# <a name="create-a-new-environment"></a>Opprett et nytt miljø

## <a name="create-a-trial-environment"></a>Opprette et prøvemiljø

Du kan registrere deg for en prøveversjon på [registreringssiden for prøveversjon](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Prøveversjoner utløper etter 30 dager.

1. Velg alternativet for **Registrer deg for en gratis prøveversjon**, og velg **Registrer deg nå**.

1. Oppgi e-postadresse for jobb eller skole, og fortell oss mer om deg selv, og velg **Neste**.

1. Angi et **Navn** på det nye miljøet. 

1. Velg prøveversjonstype.

1. Velg **Område** for miljøet ditt.

1. Eksempel: For administratorer av en Dynamics 365-organisasjon: Velg **Avanserte innstillinger**, og angi URL-adressen til organisasjonen for å bruke prediksjonsfunksjoner som kundefrafall.

1. Velg **Opprett**. 

Når miljøet er opprettet, vil du se **Demo**-miljøet, som gjør det mulig å utforske appen med fiktive data. Du kan endre eksempeldataene, slik at de samsvarer med bransjen. Velg **Innstillinger**-ikonet i hodet, og velg **Demoinnstillinger**. Du kan også endre det visuelle temaet. 

Du [bytter til miljøet ](#change-between-environments) du opprettet under registreringsprosessen, slik at du kan arbeide med dine egne data.

## <a name="create-a-new-production-or-sandbox-environment"></a>Opprette et nytt produksjons- eller sandkassemiljø

Velg **Innstillinger**-ikonet i hodet i miljøet, og velg deretter **Nytt miljø**.

Følg fremgangsmåten som om du [oppretter et prøvemiljø](#create-a-trial-environment). Du får et tilleggsalternativ når du velger **Avanserte innstillinger**, for lagring av data i din egen Azure Data Lake. Angi kontonavn og kontonøkkel for å opprette en tilkobling til Azure Data Lake. Som standard lagres data i den Customer Insights-styrte datasjøen.

> [!IMPORTANT]
> Når du lagrer data i Azure Data Lake Storage, godtar du at dataene overføres til og lagres i den riktige geografiske plasseringen for denne Azure Storage-kontoen, som kan variere fra der dataene lagres i Dynamics 365 Customer Insights. [Finn ut mer om Microsofts klareringssenter.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Utforske startsiden

Du kan [få tilgang til Customer Insights-miljøet](https://home.ci.ai.dynamics.com/) på følgende URL-adresse: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Startside** siden viser en oversikt over kundebasen og nøkkelmetrikkverdier for å spore tilstanden til virksomheten.

> [!div class="mx-imgBorder"] 
> ![Innsikter på startside](media/home-page-insights.png "Innsikter på startside")

Under **Nylige segmenter** ser du grupper av kunder basert på demografiske, atferdsstyrte eller overførbare attributter som du har definert. [Ved å opprette segmenter](segments.md) kan du tilpasse forretningsaktivitetene bedre.

**Nylige mål** viser fliser med [mål](measures.md). Mål er KPI-er du har definert. For eksempel gjennomsnittlig sannsynlighet for kundefrafall eller gjennomsnittlig online-forbruk per kunde.

Delen **Siste suppleringer** viser resultatene av de suppleringskjøringene som nylig ble utført. Suppleringer legger til informasjon om kundebasen. Hvis du for eksempel forstår interessene og merker de har affinitet for. Denne informasjonen kan låses opp ved hjelp av funksjonene for [supplering](enrichment-microsoft-graph.md), etter å ha fullført fasene [tilordning](map-entities.md), [samsvar](match-entities.md) og [sammenslåing](merge-entities.md).

## <a name="change-between-environments"></a>Bytte mellom miljøer

Når du har opprettet og konfigurert [datakilder](data-sources.md), må du bytte fra et demonstrasjonsmiljø til et live-miljø. Ved hjelp av produksjonsmiljøet kan du jobbe med dine egne kundedata. Velg kontrollen **Miljø** øverst i høyre hjørne på siden for å endre miljøer.

> [!div class="mx-imgBorder"] 
> ![Bytt miljø](media/home-page-environment-switcher.png "Bytt miljø")

Administratorer kan opprette og administrere [flere miljøer](manage-environments.md). Det kan være nyttig å vedlikeholde mer enn ett miljø hvis organisasjonen for eksempel opererer internasjonalt og du må skille data og innsikt på forskjellige måter.

## <a name="next-step"></a>Neste trinn

Hvis du vil se din egen innsikt på startsiden, må du først [legge til datakilder](data-sources.md) og [samle](data-unification.md) dataene for å bygge kundeprofiler.
