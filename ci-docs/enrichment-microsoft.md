---
title: Suppler kundeprofiler med merker og interessedata fra Microsoft (forhåndsversjon)
description: Bruk proprietære data fra Microsoft til å forbedre kundedataene med Andel av omtale.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081504"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Suppler kundeprofiler med merker og interessedata fra Microsoft (forhåndsversjon)

Bruk proprietære data fra Microsoft til å supplere kundedataene med merketiltrekning, interessetiltrekning og Andel av omtale. Disse tiltrekningene og Andel av omtale er basert på data fra personer med en lignende demografi som kundene dine. Denne informasjonen hjelper deg med å bedre forstå og segmentere kundene basert på deres tilknytninger eller Andel av omtale til bestemte merker og interesser.

## <a name="how-we-determine-affinities-and-sov"></a>Slik avgjør vi tilknytninger og Andel av omtale

Vi bruker Microsoft-søkedata på Internett til å finne tilknytninger og Andel av omtale for merker og interesser i ulike demografiske segmenter (definert av alder, kjønn eller sted). Det elektroniske søkevolumet for et merke eller en interesse danner grunnlaget for fastsettelse av tilknytningen eller Andel av omtale. Hver av dem har imidlertid ulike perspektiv for å forstå kundene.

- Affinitet er en sammenligning på tvers av demografiske segmenter. Du kan bruke denne informasjonen til å identifisere demografiske segmenter som har høyest affinitet for et bestemt merke eller en bestemt interesse sammenlignet med andre segmenter.

- Andel av omtale er en sammenligning på tvers av valgte merker eller interesser. Du kan bruke denne informasjonen til å identifisere hvilket merke eller hvilken interesse som har høyest Andel av omtale for et gitt demografisk segment, sammenlignet med andre merker eller interesser du valgte.

## <a name="affinity-level-and-score"></a>Affinitetsnivå og poengsum

For hver supplerte kundeprofil oppgir vi to relaterte verdier: affinitetsnivå og affinitetspoengsum. Disse verdiene hjelper deg med å bestemme hvor sterkt affiniteten er for den profilens demografiske segment, for et merke eller en interesse sammenlignet med andre demografiske segmenter.

*Affinitetsnivået* består av fire nivåer, og *affinitetspoengsummen* beregnes på en 100-punkts skala som tilordnes til affinitetsnivåene.

|Affinitetsnivå |Affinitetspoengsum  |
|---------|---------|
|Svært høyt     | 85–100       |
|Høy     | 70–84        |
|Middels     | 35–69        |
|Lav     | 1–34        |

Avhengig av detaljnivået du ønsker for å måle affiniteten, kan du bruke enten affinitetsnivå eller poengsum. Affinitetspoengsummen gir deg mer nøyaktig kontroll.

## <a name="share-of-voice-sov"></a>Andel av omtale

Vi beregner Andel av omtale på en 100-punktsskala. Det totale Andel av omtale-resultatet for alle merker eller interesser for hver supplerte kundeprofil utgjør opptil 100. I motsetning til affiniteter står Andel av omtale i forhold til merkene og interessene du velger. Andel av omtale-verdiene for "Microsoft" kan for eksempel være forskjellige hvis de valgte merkene er ('Microsoft', 'GitHub') versus ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Støttede land/områder

Vi støtter for øyeblikket følgende alternativer for land/område: Australia, Canada (engelsk), Frankrike, Tyskland, Storbritannia eller USA (engelsk).

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

   - Hvis du vil konfigurere merketiltrekning og Andel av omtale-supplering, velger **Suppler dataene** på **Merker**-flisen.

   - Hvis du vil konfigurere interessetiltrekning og Andel av omtale-supplering, velger **Suppler dataene** på **Interesser**-flisen.

   > [!div class="mx-imgBorder"]
   > ![Fliser for merker og interesser.](media/BrandsInterest-tile-Hub.png "Fliser for merker og interesser")

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Hvis du vil endre land eller område, velger du **Endre** ved siden av **Land/område**. Velg et [støttet land/område](#supported-countriesregions) i ruten **Innstillinger for land/område**, og velg **Bruk**.

   > [!NOTE]
   > Når du velger dine egne merker, gir systemet forslag basert på det valgte landet eller området. Når du velger en bransje, får du de mest relevante merkene eller interessene basert på det valgte landet eller området.

1. Velg opptil fem merker eller interesser ved å bruke ett av eller begge disse alternativene:

   - **Bransje**: Velg bransje fra rullegardinlisten, og velg deretter blant de viktigste merkene eller interessene for den bransjen.
   - **Velg dine egne**: Angi et merke eller en interesse som er relevant for organisasjonen din, og velg deretter blant forslagene som samsvarer. Hvis vi ikke viser et merke eller en interesse du leter etter, kan du sende oss tilbakemelding ved hjelp av **Foreslå**-koblingen.

1. Velg **Neste**, og se gjennom standardinnstillingene for supplering, og oppdater dem etter behov.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skjermbilde av vinduet for innstillinger for supplering.":::

1. Velg **Neste**.

1. Velg **Kundedatasett** og velg profilen eller segmentet du vil supplere med data fra Microsoft. *Kunde*-enheten supplerer alle kundeprofilene dine, mens segmentsuppleringer bare supplerer kundeprofiler i det segmentet.

1. Velg **Neste**.

1. Tildel feltene fra enheten for enhetlige kunder til Microsoft-dataene.

   > [!NOTE]
   > Minst attributtene Fødselsdato eller Kjønn kreves. Land/område og minst poststed (og delstat/provins) eller postnummer kreves. Vi anbefaler at fødselsdatoen konverteres til DateTime-type under datainntak. Den kan også være en streng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "åååå-MM-dd" eller "åååå-MM-ddTHH:mm:ss".

1. Velg **Neste** for å fullføre felttilordningen.

1. Angi et navn for suppleringen. **Navnet på utdataenhet** velges automatisk.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Side for å se gjennom og gi navn til interesser.":::

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

1. Velg **Kjør** for å starte suppleringsprosessen, eller lukk for å gå tilbake til siden **Suppleringer**.

   Ved supplering av profiler supplerer vi alle kundeprofiler som vi får data for de valgte merkene og interessene for, inkludert profiler som ikke finnes i det valgte landet eller området. Hvis du for eksempel valgte Tyskland, vil vi supplere profiler i USA hvis vi har data tilgjengelig for de valgte merkene og interessene i USA.

## <a name="view-enrichment-results"></a>Vis suppleringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Forhåndsvisning av resultater etter kjøring av suppleringsprosessen.":::

Resultatene inkluderer **Affinitetsnivå**- eller **Andel av omtale**-diagrammer.

Enhetene som opprettes fra suppleringene, vises under **suppleringsgruppen** i **Data** > **Enheter**. Supplerte data for varemerker går til **BrandAffinityFromMicrosoft**- og **BrandShareOfVoiceFromMicrosoft**-enhetene. Data for interesser er i enhetene **InterestAffinityFromMicrosoft** og **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Vise supplerte data på kundekortet

Andel av omtale for merke og interesse kan også vises på individuelle kundekort. Gå til **Kunder**, og velg en kundeprofil. På kundekortet finner du diagrammer for Andel av omtale-merket eller -interessen basert på personer i kundens demografiske profil.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundekort med supplerte data.":::

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
