---
title: Eksportere Customer Insights-data til LinkedIn-annonser
description: Finn ut hvordan du konfigurerer tilkoblingen og eksporterer til LinkedIn-annonser.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 948a7e980df5714034009c92282e78cf2bdcb231
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618303"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Eksportere segmenter til LinkedIn-annonser (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til LinkedIn-annonser for å opprette samsvarende målgrupper. Bruk de samsvarende målgruppene til firmamålretting og kontaktmålretting.

## <a name="prerequisites"></a>Forutsetninger

-   Du har en [LinkedIn Campaign Manager-konto](https://business.linkedin.com/marketing-solutions/ads) og tilhørende administratorlegitimasjon.
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Kundeprofiler i de eksporterte segmentene inneholder et felt med en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 100 000 kundeprofiler per eksport til LinkedIn Ads.
- Eksport til LinkedIn-annonser er begrenset til segmenter.
- Det kan ta opptil 10 minutter å eksportere 100 000 kundeprofiler til LinkedIn Ads. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Konfigurere tilkoblingen til LinkedIn-annonser

1. I målgruppeinnsikt går du til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **LinkedIn-annonser** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, er standarden administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi [konto-ID-en for LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Campaign Monitor.

1. Velg **Godkjenn med LinkedIn**, og angi legitimasjonen for administrator for LinkedIn Campaign Manager.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere en eksport hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra delen LinkedIn-annonse i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Velg om du vil eksportere data for å foreta [kontaktmålretting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) eller [firmamålretting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) på LinkedIn. 

1. I delen **Datasamsvar** for kontaktmålretting velger du minst ett felt som representerer kundens e-postadresse, Apple Ad-ID, Google Ad-ID, Google-bruker-ID eller for- og etternavn. Hvis du velger firmamålretting, velger du minst ett felt som representerer firmanavn, e-postdomene, URL-adresse for LinkedIn-side, aksjesymbol eller webområde. Du kan velge flere felt for å definere eksporten ytterligere. 

1. Velg segmentene du vil eksportere. De samsvarende målgruppene i LinkedIn Campaign Manager blir opprettet automatisk med navnet på segmentene du valgte å eksportere. Hvert segment fører til en egen samsvarende målgruppe. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for å overføre data til LinkedIn-annonser, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at LinkedIn-annonser oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Administratoren for Dynamics 365 Customer Insights kan fjerne dette eksportmålet når som helst for stoppe bruken av denne funksjonaliteten.
