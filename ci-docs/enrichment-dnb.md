---
title: Suppler firmaprofiler med Dun & Bradstreet (forhåndsversjon)
description: Generell informasjon om tredjepartssuppleringen for Dun & Bradstreet.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237916"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Suppler firmaprofiler med Dun & Bradstreet (forhåndsversjon)

Dun & Bradstreet tilbyr kommersielle data, analyse og innsikt for virksomheter. Den gjør det mulig for kunder med enhetlige kundeprofiler for selskaper å berike dataene sine. Suppleringer omfatter attributter, som DUNS-nummer, selskapsstørrelse, sted, bransje og mye mer.

## <a name="prerequisites"></a>Forutsetning

- En aktiv [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights)-lisens.
- [Enhetlige kundeprofiler](customer-profiles.md) for firmaer.
- Et Dun & Bradstreet-[prosjekt](#set-up-your-dun--bradstreet-project) er konfigurert.
- En Dun & Bradstreet-[tilkobling](connections.md) er [konfigurert](#configure-a-connection-for-dun--bradstreet) av en administrator.

## <a name="set-up-your-dun--bradstreet-project"></a>Konfigurer Dun & Bradstreet-prosjektet

Som lisensiert bruker av Dun & Bradstreet kan du konfigurere et prosjekt i [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Logg på [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Du henter legitimasjon ved å [gjenopprette passordet](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Last ned [csv-malfilen](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) som skal brukes til å tildele Customer Insights-felter til de tilsvarende feltene i Dun & Bradstreet.

1. Last opp filen i trinnet **Last opp data** i Dun & Bradstreet-prosjektopprettelsesopplevelsen.

1. Velg de vannrette prikkene under den relevante **kilden** i det nyopprettede Dun & Bradstreet-prosjektet for å vise de tilgjengelige alternativene.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Skjermbilde av prikker i et Dun & Bradstreet-prosjekt.":::

1. Velg **Hent S3-detaljer**. Lagre denne informasjonen på et trygt sted. Du må [konfigurere tilkoblingen for suppleringen](#configure-a-connection-for-dun--bradstreet) i Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Skjermbilde av valg av S3-informasjon i et Dun & Bradstreet-prosjekt.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurer en tilkobling for Dun & Bradstreet

Du må være en [administrator](permissions.md#admin) i Customer Insights og ha legitimasjon fra Dun & Bradstreet Connect.

1. Velg **Legg til tilkobling** når du konfigurerer en suppleringen, eller gå til **Administrator** > **Tilkoblinger**, og velg **Konfigurer** på Dun & Bradstreet-flisen.

1. Skriv inn et navn for tilkoblingen.

1. Angi gyldig legitimasjon for Dun & Bradstreet og Dun & Bradstreet-prosjektdetaljer *Område, Slipp mappebane og Slipp mappenavn*. Du [får denne informasjonen](#set-up-your-dun--bradstreet-project) fra Dun & Bradstreet-prosjektet.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Bekreft** for å validere konfigurasjonen, og velg deretter **Lagre**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Ruten for Dun & Bradstreet-tilkoblingskonfigurasjon.":::

## <a name="supported-countries-or-regions"></a>Støttede land eller områder

Vi støtter for øyeblikket følgende alternativer for land/område: Canada (engelsk) eller USA (engelsk).

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på **firmadataene** for Dun & Bradstreet-flisen.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Skjermbilde av Dun & Bradstreet-flisen.":::

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Velg tilkoblingen og bekreft. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Velg **Neste**.

1. Velg **Kundedatasett** og velg profilen eller segmentet du vil supplere med firmadata fra Dun & Bradstreet. *Kunde*-enheten supplerer alle kundeprofilene dine, mens segmentsuppleringer bare supplerer kundeprofiler i det segmentet.

1. Definer hvilken type felter fra de enhetlige profilene som skal brukes for samsvarende firmadata fra Dun & Bradstreet. Minst ett av feltene **Navn og adresse**, **Telefon** eller **E-post** er obligatorisk.

1. Velg **Neste**

1. Tildel feltene til firmadataene fra Dun & Bradstreet. Feltene **DUNS-nummer** eller **Navn på firma-** og **Land** er obligatoriske.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Felttildelingsrute for Dun & Bradstreet.":::

1. Velg **Neste** for å fullføre felttilordningen.

1. Angi et **Navn** for suppleringen og **Utdataenhetsnavn**.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

1. Velg **Kjør** for å starte suppleringsprosessen, eller lukk for å gå tilbake til siden **Suppleringer**.

## <a name="view-enrichment-results"></a>Vis suppleringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
