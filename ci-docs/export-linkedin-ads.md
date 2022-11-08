---
title: Eksportere segmenter til LinkedIn-annonser (forhåndsversjon)
description: Finn ut hvordan du konfigurerer tilkoblingen og eksporterer til LinkedIn-annonser.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 06eb915e352ad545f95e96e6108be0f81f43a451
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725320"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Eksportere segmenter til LinkedIn-annonser (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til LinkedIn-annonser for å opprette samsvarende målgrupper. Bruk de samsvarende målgruppene til firmamålretting og kontaktmålretting.

## <a name="prerequisites"></a>Forutsetning

- En [LinkedIn Campaign Manager-konto](https://business.linkedin.com/marketing-solutions/ads) og tilsvarende administratorlegitimasjon.
- En [LinkedIn Campaign Manager-konto-ID](https://www.linkedin.com/help/lms/answer/a424270).
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- De eksporterte segmentene trenger minst ett bestemt felt, avhengig av om du velger [kontaktmålretting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) eller [firmamålretting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) på LinkedIn. De mulige feltene vises i trinnet **Datasamsvar** når du [konfigurerer eksporten](#configure-an-export).

## <a name="known-limitations"></a>Kjente begrensninger

- Private Link kombinert med Bring your own storage (BYOS) støttes ikke.
- Opptil 100 000 kundeprofiler per eksport til LinkedIn Ads, som kan ta opptil 10 minutter å fullføre.
- Bare segmenter. Et segment må inneholde minst 300 unike profiler.

## <a name="set-up-connection-to-linkedin-ads"></a>Konfigurer tilkobling til LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **LinkedIn Ads**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi LinkedIn Campaign Manager-konto-ID-en.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Godkjenn med LinkedIn**, og angi legitimasjonen for administrator for LinkedIn Campaign Manager.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra delen LinkedIn-annonse i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg om du vil eksportere data for å foreta [kontaktmålretting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) eller [firmamålretting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) på LinkedIn.

1. I delen **Datasamsvar** for kontaktmålretting velger du minst ett felt som representerer kundens e-postadresse, Apple Ad-ID, Google Ad-ID, Google-bruker-ID eller for- og etternavn. Hvis du velger firmamålretting, velger du minst ett felt som representerer firmanavn, e-postdomene, URL-adresse for LinkedIn-side, aksjesymbol eller webområde.

1. Legg eventuelt til felter for å definere eksporten ytterligere. Velg **Legg til attributt** for å tilordne disse feltene.

1. Velg segmentene du vil eksportere. De samsvarende målgruppene i LinkedIn Campaign Manager blir opprettet automatisk med navnet på segmentene du valgte å eksportere. Hvert segment fører til en egen samsvarende målgruppe.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
