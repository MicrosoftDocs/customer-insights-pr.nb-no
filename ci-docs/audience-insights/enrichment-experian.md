---
title: Berikelse med tredjeparts supplering fra Experian
description: Generell informasjon om tredjeparts Experian-supplering.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: efa26fa82a950063e074a4ab930ed95383c55334
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376704"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Supplere kundeprofiler med demografi fra Experian (forhåndsvisning)

Experian er en global leder innen kredittrapportering og markedsføringstjenester for forbruker og selskap. Med Experian-datasuppleringstjenester kan du bygge en dypere forståelse av kundene ved å berike kundeprofilene med demografiske data som størrelsen på kunden, inntekter og annet.

## <a name="prerequisites"></a>Forutsetninger

Følgende forutsetninger må være oppfylt for at du skal kunne konfigurere Experian:

- Du må ha et aktivt abonnement på Experian. Hvis du vil ha et abonnement, [kontakter du Experian](https://www.experian.com/marketing-services/contact) direkte. [Finn ut mer om Experian-datasupplering](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- En Experian-tilkobling er allerede konfigurert av en administrator, *eller* du har [administrator](permissions.md#admin)-tillatelser. Du må også ha bruker-ID, parts-ID og modellnummer for den SSH-aktiverte ST-kontoen (Secure Transport) som Experian har opprettet for deg.

## <a name="supported-countriesregions"></a>Støttede land/områder

Vi støtter for øyeblikket bare supplering av kundeprofiler i USA.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på Experian-flisen.

   > [!div class="mx-imgBorder"]
   > ![Experian-flis.](media/experian-tile.png "Experian tile")
   > 

1. Velg en [tilkobling](connections.md) fra rullegardinlisten. Kontakt en administrator hvis ingen tilkobling er tilgjengelig. Hvis du er en administrator, kan du opprette en tilkobling ved å velge **Legg til tilkobling** og velge Experian fra rullegardinlisten. 

1. Velg **Koble til Experian** for å bekrefte valget av tilkobling.

1.  Velg **Neste**, og velg **Kundedatasettet** du vil supplere ned demografiske data fra Experian. Du kan velge **kundeenheten** for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. Velg **Neste**, og definer hvilken type felt fra de enhetlige profilene som skal brukes til å se etter samsvarende demografiske data fra Experian. Minst ett av feltene **Navn og adresse**, **Telefon** eller **E-post** er obligatorisk. Hvis du vil ha høyere nøyaktighet for treff, kan du legge til opptil to andre felt. Dette valget påvirker tilordningsfeltene du har tilgang til i neste trinn.

    > [!TIP]
    > Flere nøkkelidentifikatorattributter som sendes til Experian, gir sannsynligvis høyere samsvarsrate.

1. Velg **Neste** for å starte felttilordningen.

1. Definer hvilken felt fra de enhetlige profilene som skal brukes til å se etter samsvarende demografiske data fra Experian. Obligatoriske felt er merket.

1. Angi et navn for suppleringen og et navn for utdataenheten.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

## <a name="configure-the-connection-for-experian"></a>Konfigurere tilkoblingen for Experian 

Du må være en administrator for å konfigurere tilkoblinger. Velg **Legg til tilkobling** når du konfigurerer en supplering *eller* gå til **Administrator** > **Tilkoblinger**, og velg **Konfigurer** på Experian-flisen.

1. Velg **Komme i gang**.

1. Skriv inn et navn på tilkoblingen i **Visningsnavn**-boksen.

1. Angi gyldig bruker-ID, part-ID og modellnummer for Experian ST-kontoen.

1. Gå gjennom og gi ditt samtykke til **Datapersonvern og -samsvar** ved å velge **Jeg er enig**.

1. Velg **Bekreft** for å validere konfigurasjonen.

1. Velg **Lagre** etter at verifiseringen er fullført.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian-tilkoblingskonfigurasjonsruten.":::

## <a name="enrichment-results"></a>Resultater av supplering

Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen. Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab). Behandlingstiden avhenger av størrelsen på kundedataene og suppleringsprosessene som er konfigurert for forretningsforbindelsen din etter Experian.

Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**. I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.

Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du gjør det mulig for Dynamics 365 Customer Insights å overføre data til Experian, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data som personlige data. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Experian oppfyller personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
