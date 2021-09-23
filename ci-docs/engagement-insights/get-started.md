---
title: Kom i gang med engasjementsinnsiktfunksjonalitet
description: En oversikt over hjelperessurser for å komme raskt i gang.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494606"
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

1. Gjennomgå **vilkårene for bruk for engasjementsinnsikt (forhåndsversjon)** og **personvernerklæring**, og velg deretter **Utforsk demonstrasjonen** for å godta disse innstillingene.

1. Utforsk produktet ved hjelp av et sett med eksempeldata.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Trinn 3: Konfigurer et arbeidsområde og legg til kode på nettstedet

I et arbeidsområde kan du vise brukeraktivitet i sanntid og lagre og administrere rapporter. Legg til kode på nettstedet for å begynne å samle inn *hendelser*, aktivitetsdataene som kommer inn fra brukere.

1. [Opprett et arbeidsområde](create-workspace.md) og legg til medlemmer.

1. [Legg til kode på nettstedet](instrument-website.md) eller [mobilappen](developer-resources.md#capture-events-from-mobile-apps) for å se brukeraktiviteten som kommer inn i arbeidsområdet.

1. Vis en [sanntidsrapport](view-reports.md) som viser aktive brukere etter nettleser, enhet, operativsystem, plassering og språk. Du kan også opprette [egendefinerte rapporter](custom-reports.md) for å opprette dine egne visualiseringer.
    
## <a name="step-4-export-data-to-other-channels"></a>Trinn 4: Eksporter data til andre kanaler

Du kan opprette *begrensede hendelser* (en virtuell visning) av nettanalysedataene. Filtrer og eksporter deretter dataene til Azure Data Lake Storage. Du kan hente inn de eksporterte dataene som en datakilde. Hvis du vil ha mer informasjon, kan du se [Opprett en kobling mellom målgruppeinnsikt og engasjementsinnsikt](integrate-audience-insights-engagement-insights.md).

1. [Opprett begrensede hendelser](refined-events.md) for eksport.

1. [Eksporter dataene](export-events.md) til Data Lake Storage.

1. [Opprett en kobling mellom målgruppeinnsikt og engasjementsinnsikt](integrate-audience-insights-engagement-insights.md) for å dele data mellom de to funksjonene.

1. Finn ut hvordan du [sletter og eksporterer hendelsesdata som inneholder personlige opplysninger](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Trinn 5: Forbli tilkoblet

Vi setter pris på din aktive deltagelse og tar hensyn til alle relevante tilbakemeldinger i utviklingen av fremtidige utgivelser. Del tilbakemeldingen din og rapporter problemer i en av disse kanalene:
- [Samfunn](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Gi tilbakemelding](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Forespørsel om støtte](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
