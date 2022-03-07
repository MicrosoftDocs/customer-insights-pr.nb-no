---
title: Berike med tredjeparts supplering fra Experian
description: Generell informasjon om tredjeparts supplering fra Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597799"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Supplere kundeprofiler med demografidata fra Experian (forhåndsversjon)

Experian er en global leder innen forbruker- og forretningskredittrapportering og markedsføringstjenester. Ved hjelp Experians datasuppleringstjenester kan du bygge opp en dypere forståelse av kundene ved å supplere kundeprofilene med demografiske data, for eksempel husholdningsstørrelse, inntekt og så videre.

## <a name="prerequisites"></a>Forutsetninger

For å konfigurere Experian må følgende forutsetninger være oppfylt:

- Du har et aktivt Experian-abonnement. Hvis du vil ha et abonnement, [kontakter du Experian](https://www.experian.com/marketing-services/contact) direkte. [Finn ut mer om Experian-datasupplering](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Du har bruker-ID, part-ID og modellnummer for SSH-aktivert ST-konto (Secure Transport) som Experian opprettet for deg.
- Du har [administratortillatelser](permissions.md#administrator) tillatelser i målgruppeinnsikt.

## <a name="configuration"></a>Konfigurasjon

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på Experian-flisen.

   > [!div class="mx-imgBorder"]
   > ![Experian-flis](media/experian-tile.png "Experian-flis")

1. Velg **Start**, og angi bruker-ID, part-ID og modellnummer for Experian Secure Transport-kontoen. Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**. Bekreft alle inndata ved å velge **Bruk**.

## <a name="map-your-fields"></a>Tilordne feltene

1.  Velg **Legg til data**, og velg **kundedatasettet** du vil supplere med demografiske data fra Experian. Du kan velge **kundeenheten** for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.

1. Velg nøkkelidentifikatorene fra **Navn og Adresse**, **E-post** eller **Telefon** for å sende til Experian for identitetsløsning.

   > [!TIP]
   > Flere nøkkel-ID-attributter som sendes til Experian, vil sannsynligvis gi en høyere samsvarsrate.

1. Velg **Neste**, og tilordne de tilsvarende attributtene fra den enhetlige kundeenheten for de valgte nøkkel-ID-feltene.

1. Velg **Legg til attributt** for å tilordne eventuelle tilleggsattributter du ønsker å sende til Experian.

1.  Velg **Lagre** for å fullføre felttilordningen.

    > [!div class="mx-imgBorder"]
    > ![Experian-felttilordning](media/experian-field-mapping.png "Experian-felttilordning")

## <a name="enrichment-results"></a>Resultater av supplering

Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen. Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab). Behandlingstiden avhenger av størrelsen på kundedataene og suppleringsprosessene som er satt opp for kontoen din av Experian.

Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**. I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.

Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.

## <a name="next-steps"></a>Neste trinn

Bygg på toppen av de supplerte kundedataene. Opprett [segmenter](segments.md), [mål](measures.md) og til og med [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Experian, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Experian oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]