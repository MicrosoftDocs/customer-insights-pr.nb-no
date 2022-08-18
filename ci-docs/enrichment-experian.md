---
title: Supplere kundeprofiler med demografi fra Experian (forhåndsvisning)
description: Generell informasjon om tredjeparts Experian-supplering.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238008"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Supplere kundeprofiler med demografi fra Experian (forhåndsvisning)

Experian er en global leder innen kredittrapportering og markedsføringstjenester for forbruker og selskap. Med Experian-datasuppleringstjenester kan du bygge en dypere forståelse av kundene ved å berike kundeprofilene med demografiske data som størrelsen på kunden, inntekter og annet.

## <a name="supported-countriesregions"></a>Støttede land/områder

Vi støtter for øyeblikket bare supplering av kundeprofiler i USA.

## <a name="prerequisites"></a>Forutsetning

- Et aktivt Experian-abonnement. Hvis du vil ha et abonnement, [kontakter du Experian](https://www.experian.com/marketing-services/contact) direkte. [Finn ut mer om Experian-datasupplering](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- En Experian-[tilkobling](connections.md) er [konfigurert](#configure-the-connection-for-experian) av en administrator.

- Experian-bruker-ID, parts-ID og modellnummer for den SSH-aktiverte ST-kontoen (Secure Transport) som Experian opprettet for deg.

## <a name="configure-the-connection-for-experian"></a>Konfigurere tilkoblingen for Experian

Du må være en [administrator](permissions.md#admin) i Customer Insights og ha en Experian-klient-ID, parts-ID og modellnummer.

1. Velg **Legg til tilkobling** når du konfigurerer en supplering eller gå til **Administrator** > **Tilkoblinger**, og velg **Konfigurer** på Experian-flisen.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian-tilkoblingskonfigurasjonsruten.":::

1. Skriv inn et navn på tilkoblingen og en gyldig bruker-ID, parts-ID og modellnummer for Experian Secure Transport-kontoen.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Bekreft** for å validere konfigurasjonen, og velg deretter **Lagre**.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på **Demografi** fra Experian-flisen.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian-flis på oversiktssiden for supplering.":::

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Velg tilkoblingen. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Velg **Neste**.

1. Velg **Kundedatasett** og velg profilen eller segmentet du vil supplere med demografiske data fra Experian. *Kunde*-enheten supplerer alle kundeprofilene dine, mens segmentsuppleringer bare supplerer kundeprofiler i det segmentet.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. Definer hvilken type felter fra de enhetlige profilene som skal brukes for samsvarende demografiske data fra Experian. Minst ett av feltene **Navn og adresse**, **Telefon** eller **E-post** er obligatorisk. Hvis du vil ha høyere samsvarsnøyaktighet, legger du til andre felter. Velg **Neste**.

1. Tildel feltene til demografiske data fra Experian.

1. Velg **Neste** for å fullføre felttilordningen.

1. Angi et **Navn** for suppleringen og **Utdataenhetsnavn**.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

1. Velg **Kjør** for å starte suppleringsprosessen, eller lukk for å gå tilbake til siden **Suppleringer**.

## <a name="view-enrichment-results"></a>Vis suppleringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antall kunder supplert av feltet** gir en neddrilling i dekningen av hvert supplerte felt.

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
