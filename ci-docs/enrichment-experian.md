---
title: Supplere kundeprofiler med demografi fra Experian (forhåndsvisning)
description: Generell informasjon om tredjeparts Experian-supplering.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053033"
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

1. Gå gjennom og gi ditt samtykke til [Datapersonvern og -samsvar](#data-privacy-and-compliance) ved å velge **Jeg er enig**.

1. Velg **Bekreft** for å validere konfigurasjonen, og velg deretter **Lagre**.

### <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du gjør det mulig for Dynamics 365 Customer Insights å overføre data til Experian, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data som personlige data. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Experian oppfyller personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732). Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på **Demografi** fra Experian-flisen.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian-flis på oversiktssiden for supplering.":::

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Velg tilkoblingen. Kontakt en administrator hvis en slik ikke er tilgjengelig.

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
