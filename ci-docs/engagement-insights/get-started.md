---
title: Kom i gang med engasjementsinnsiktfunksjonalitet
description: En oversikt over hjelperessurser for å komme raskt i gang.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3505c15c4319c8cc8823bcd89d3b8adc944a87dd
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623689"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Kom i gang med Dynamics 365 Customer Insights-engasjementsinnsiktfunksjonalitet (offentlig forhåndsversjon)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med engasjementsinnsiktfunksjonen kan du samle inn og måle kundeatferd på nettstedet ditt. Den integreres med målgruppeinnsiktsfunksjonen slik at du kan se omfattende atferdsanalyse i sanntid ved siden av rapporter for kundeprofiler. Koblingene i denne artikkelen hjelper deg med å konfigurere og sette opp miljøet raskt.

## <a name="step-1-review-prerequisites"></a>Trinn 1: Gå gjennom kravene

Først må du ha en aktiv Microsoft Azure Active Directory-brukerkonto (AAD). Les deretter artiklene nedenfor før du konfigurerer arbeidsområdet for engasjementsinnsikt.

- Se gjennom og godta [vilkår for bruk](terms-of-service.md) med Microsoft.  
- Les artikkelen [Administrer informasjonskapsler og brukersamtykke](user-consent-storage.md). Deretter evaluerer du om du må oppdatere varselet om brukersamtykke. Hvis du tidligere ikke hadde noen ikke-viktige informasjonskapsler, må du sannsynligvis oppdatere områdepolicyen.
- Se gjennom [ordlisten](glossary.md) for å få en rask innføring i viktige termer og konsepter.

## <a name="step-2-explore-engagement-insights"></a>Trinn 2: Utforsk engasjementsinnsikt

Første gang du går til engasjementsinnsikt, kan du konfigurere innstillinger, se gjennom policyer og utforske mulighetene.

1. Logg på [funksjonsportalen for engasjementsinnsikt](https://home.ci.ai.dynamics.com/app/engagement-insights) ved hjelp av Microsoft AAD-brukerkontoen (skole- eller jobbkontoen).

1. Velg område, og merk av i avmerkingsboksen hvis du vil registrere deg for å motta e-postoppdateringer og tilbud.

1. Gjennomgå **vilkårene for bruk** for engasjementsinnsikt (forhåndsversjon) og **personvernerklæring**, og velg deretter **Utforsk demonstrasjonen** for å godta disse innstillingene.

1. Utforsk produktet ved hjelp av et sett med eksempeldata.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Trinn 3: Konfigurere et arbeidsområde og opprette rapporter

I et arbeidsområde kan du vise brukeraktivitet i sanntid og lagre og administrere rapporter. Legg til kode på nettstedet for å begynne å samle inn *hendelser*, aktivitetsdataene som kommer inn fra brukere.

1. [Opprett et arbeidsområde](create-workspace.md) og legg til medlemmer.

1. Legg til kode på [nettstedet](instrument-website.md) eller [mobilappen](developer-resources.md#capture-events-from-mobile-apps) for å se brukeraktiviteten som kommer inn i arbeidsområdet.

1. Vis en [sanntidsrapport](view-reports.md) som viser aktive brukere etter nettleser, enhet, operativsystem, plassering og språk. Du kan også opprette [egendefinerte rapporter](custom-reports.md) for å opprette dine egne visualiseringer.

1. Opprett [dimensjoner](dimensions.md) for å sortere besøkende etter nye og returnerende brukere, [metrikkverdier](metrics.md) for å gjøre brukeratferden bedre å forstå, og [segmenter](segments.md) for å identifisere delsett av besøkende basert på kjennetegn eller interaksjon med nettstedet.
    
## <a name="step-4-export-data-to-other-channels"></a>Trinn 4: Eksporter data til andre kanaler

Du kan opprette *begrensede hendelser* (en virtuell visning) av nettanalysedataene. Filtrer og eksporter deretter dataene til Azure Data Lake Storage. Du kan hente inn de eksporterte dataene som en datakilde.

1. [Opprett begrensede hendelser](refined-events.md) for eksport.

1. [Eksporter dataene](export-events.md) til Azure Data Lake Storage.

1. [Opprett en kobling mellom målgruppeinnsikt og engasjementsinnsikt](integrate-audience-insights-engagement-insights.md) for å dele data mellom de to funksjonene.

1. [Gjenkjenne webhendelser fra tidligere godkjente brukere](unknown-to-known.md) med **ukjent til kjent**-funksjonen.

1. Finn ut hvordan du [sletter og eksporterer hendelsesdata som inneholder personlige opplysninger](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Trinn 5: Opprette og administrere traktrapporter

En traktrapport samler inn informasjon om trinnene som inntreffer i løpet av en kundereise via nettstedet ditt eller mobilappen. I tillegg til å opprette standardprofilrapporter og egendefinerte rapporter, kan du opprette en traktrapport for å identifisere baner kundene bruker før de foretar et kjøp. 

1. [Opprett en traktrapport](funnel-reports.md) for å informere avgjørelser og identifisere områder for optimalisering og prosessforbedringer.

1. Opprett traktrapporter på tvers av kanaler når du har instrumentert mobilappen med engasjementinnsikt [Android-SDK](get-started-android.md) eller [iOS SDK](get-started-ios.md).

1. Bruk [traktinnsikt](funnel-reports.md#funnel-insights) til å få bedre innsikt i kundeatferd om trinnene i traktrapporten.
 
## <a name="step-6-stay-connected"></a>Trinn 6: Forbli tilkoblet

Vi setter pris på din aktive deltagelse og tar hensyn til alle relevante tilbakemeldinger i utviklingen av fremtidige utgivelser. Del tilbakemeldingen din og rapporter problemer i en av disse kanalene:
- [Samfunn](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Gi tilbakemelding](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Forespørsel om støtte](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
