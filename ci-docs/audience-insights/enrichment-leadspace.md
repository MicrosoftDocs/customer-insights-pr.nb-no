---
title: Supplering av firmaprofiler med tredjeparts supplering fra Leadspace
description: Generell informasjon om tredjeparts supplering fra Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597661"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Supplering av firmaprofiler med Leadspace (forhåndsversjon)

Leadspace er et datavitenskapsfirma som tilbyr en B2B-kundedataplattform. Den gjør det mulig for kunder med enhetlige kundeprofiler for selskaper å berike dataene sine. Suppleringer omfatter ekstra attributter, for eksempel selskapsstørrelse, sted, bransje og mer.

## <a name="prerequisites"></a>Forutsetninger

Følgende forutsetninger må være oppfylt for at du skal kunne konfigurere Leadspace:

- Du har en aktiv Leadspace-lisens og en "permanent nøkkel" (henvist til som **Leadspace-token**). Kontakt [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direkte for detaljer om produktet.
- Du har [administratortillatelser](permissions.md#administrator).
- Du har [enhetlige kundeprofiler](customer-profiles.md) for selskaper.

## <a name="configuration"></a>Konfigurasjon

1. I Målgruppeinnsikt går du til **Data** > **Supplering**.

1. Velg **Suppler dataene** på Leadspace-flisen.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skjermbilde av Leadspace-flisen.":::

1. Velg **Kom i gang**, og angi deretter et aktivt **Leadspace-token** (permanent nøkkel). Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**. Bekreft begge inndataene ved å velge **Koble til Leadspace**.

1. Velg **Tilordne data**, og velg datasettet du vil supplere med selskapsdata fra Leadspace. Du kan velge *kundeenheten* for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Velg mellom kundeprofil og segmentsupplering.":::

1. Klikk på **Neste**, og definer hvilke felt fra de enhetlige profilene som skal brukes til å søke etter samsvarende firmadata fra Leadspace. Feltet **Navn på selskap** feltet er obligatorisk. For høyere nøyaktighet kan opptil to andre felter, **Selskapets nettsted** og **Selskapssted**, legges til.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Tilordningsrute i Leadspace-felt.":::
   
1. Velg **Bruk** for å fullføre felttilordningen.

1. Velg **Kjør** for å supplere firmaprofilene. Hvor lang tid en supplering tar, avhenger av antallet enhetlige kundeprofiler.

## <a name="enrichment-results"></a>Resultater av supplering

Etter at du har oppdatert suppleringen, kan du gå gjennom de nylig supplerte firmadataene under [Mine suppleringer](enrichment-hub.md). Du kan finne tidspunktet for siste oppdatering og antall supplerte profiler.

Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.

Hvis du vil ha mer informasjon, kan du se [API-er for Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Neste trinn

Bygg på toppen av de supplerte kundedataene. Opprett [segmenter](segments.md), [mål](measures.md) og til og med [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Leadspace, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Leadspace oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]