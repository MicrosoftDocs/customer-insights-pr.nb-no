---
title: Supplering for firmaprofiler med Dun & Bradstreet
description: Generell informasjon om tredjepartssuppleringen for Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755412"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Supplering for firmaprofiler med Dun & Bradstreet (forhåndsversjon)

Dun & Bradstreet tilbyr kommersielle data, analyse og innsikt for virksomheter. Den gjør det mulig for kunder med enhetlige kundeprofiler for selskaper å berike dataene sine. Suppleringer omfatter attributter, som DUNS-nummer, selskapsstørrelse, sted, bransje og mye mer.

## <a name="prerequisites"></a>Krav

Følgende forutsetninger må være oppfylt for at du skal konfigurere Dun & Bradstreet-suppleringen:

- Du må ha en aktiv [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights)-lisens.
- Du har [enhetlige kundeprofiler](customer-profiles.md) for selskaper.
- En Dun & Bradstreet-[tilkobling](connections.md) konfigureres av en administrator. Du kan opprette den hvis du har [administratortillatelser](permissions.md#admin) og legitimasjon fra Dun & Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>Konfigurer Dun & Bradstreet-prosjektet

Som lisensiert bruker av Dun & Bradstreet kan du konfigurere et prosjekt i [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. Logg på [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Du henter legitimasjon ved å [gjenopprette passordet](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Last ned [csv-malfilen](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) som skal brukes til å tildele Customer Insights-felter til de tilsvarende feltene i Dun & Bradstreet.

1. Last opp filen i trinnet **Last opp data** i Dun & Bradstreet-prosjektopprettelsesopplevelsen.

1. Velg de vannrette prikkene under den relevante **kilden** i det nyopprettede Dun & Bradstreet-prosjektet for å vise de tilgjengelige alternativene.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Skjermbilde av prikker i et Dun & Bradstreet-prosjekt.":::

1. Velg **Hent S3-detaljer**. Lagre denne informasjonen på et trygt sted. Du må [konfigurere tilkoblingen for suppleringen](#configure-a-connection-for-dun--bradstreet) i Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Skjermbilde av valg av S3-informasjon i et Dun & Bradstreet-prosjekt.":::

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**.

1. Velg **Suppler dataene mine** på Dun & Bradstreet-flisen, og velg **Kom i gang**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Skjermbilde av Dun & Bradstreet-flisen.":::

1. Velg en [tilkobling](connections.md) fra rullegardinlisten. Kontakt en administrator hvis ingen tilkobling er tilgjengelig. Hvis du er en administrator, kan du opprette en tilkobling. Velg **Legg til tilkobling** og velg **Dun & Bradstreet**.

1. Velg **Koble til Dun & Bradstreet** for å bekrefte tilkoblingen.

1. Velg **Neste**, og velg **Kundedatasett** du vil bruke til å supplere med firmadata fra Dun & Bradstreet. Du kan velge **Kunde**-enheten for å supplere alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere samlede kundeprofiler i det segmentet.

1. Velg **Neste**, og definer hvilken type felter fra de enhetlige profilene som brukes til å se etter samsvarende firmadata fra Dun & Bradstreet. Feltene **DUNS-nummer** eller **Navn på firma-** og **Land** er obligatoriske. Landfeltet støtter [landkoder med to eller tre bokstaver](https://www.iso.org/iso-3166-country-codes.html), landnavn på engelsk, landnavn på morsmål og telefonprefiks. Følgende er vanlige landvarianter:

- USA: United States of America, United States, USA, Amerika.
- CA: Canada.
- GB: Storbritannia, UK, Great Britain, GB, Det forente kongerike Storbritannia og Nord-Irland, United Kingdom of Great Britain.
- AU: Australia, Commonwealth of Australia.
- FR: Frankrike, Republikken Frankrike.
- DE: Tyskland, tysk, Deutschland, Allemagne, Federal Republic of Germany, Republikken Tyskland.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Felttildelingsrute for Dun & Bradstreet.":::

1. Velg **Neste** for å fullføre felttilordningen.

1. Angi et navn for suppleringen, og velg **Lagre supplering** etter at du har sett gjennom valgene.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurer en tilkobling for Dun & Bradstreet

Du må være en administrator for å konfigurere tilkoblinger. Velg **Legg til tilkobling** når du konfigurerer en suppleringen, *eller* gå til **Administrator** > **Tilkoblinger**, og velg **Konfigurer** på Dun & Bradstreet-flisen.

1. Velg **Kom i gang**.

1. Skriv inn et navn på tilkoblingen i **Visningsnavn**-boksen.

1. Angi gyldig legitimasjon for Dun & Bradstreet og Dun & Bradstreet-prosjektdetaljer *Område, Slipp mappebane og Slipp mappenavn*. Du [får denne informasjonen](#setting-up-your-dun--bradstreet-project) fra Dun & Bradstreet-prosjektet.

1. Gå gjennom og gi ditt samtykke til **Datapersonvern og -samsvar** ved å velge **Jeg er enig**.

1. Velg **Bekreft** for å validere konfigurasjonen.

1. Velg **Lagre** etter at verifiseringen er fullført.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Ruten for Dun & Bradstreet-tilkoblingskonfigurasjon.":::

## <a name="enrichment-results"></a>Resultater av supplering

Etter at du har oppdatert suppleringen, kan du gå gjennom de nylig supplerte firmadataene under [Mine suppleringer](enrichment-hub.md). Du kan finne tidspunktet for siste oppdatering og antall supplerte profiler.

Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Dun & Bradstreet, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Dun & Bradstreet oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.

[!INCLUDE[footer-include](includes/footer-banner.md)]
