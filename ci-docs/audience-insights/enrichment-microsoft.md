---
title: Supplere kundeprofiler med data fra Microsoft
description: Bruk proprietære data fra Microsoft til å forbedre kundedataene med Andel av omtale.
ms.date: 11/11/2021
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
ms.openlocfilehash: 77972475c9a448186cee3b1b62eeda7b1996edfc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355341"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Supplere kundeprofiler med tilknytninger og Andel av omtale (forhåndsversjon)

Bruk proprietære data fra Microsoft til å supplere kundedataene med merketiltrekning, interessetiltrekning og Andel av omtale. Disse tiltrekningene og Andel av omtale er basert på data fra personer med en lignende demografi som kundene dine. Denne informasjonen hjelper deg med å bedre forstå og segmentere kundene basert på deres tilknytninger eller Andel av omtale til bestemte merker og interesser.

I målgruppeinnsikt går du til **Data** > **Supplering** for å [konfigurere og vise suppleringer](enrichment-hub.md).

Hvis du vil konfigurere merketiltrekning og Andel av omtale-supplering, går du til kategorien **Oppdag** og velger **Suppler dataene** på **Merker**-flisen.

Hvis du vil konfigurere interessetiltrekning og Andel av omtale-supplering, går du til kategorien **Oppdag** og velger **Suppler dataene** på **Interesser**-flisen.

   > [!div class="mx-imgBorder"]
   > ![Fliser for merker og interesser.](media/BrandsInterest-tile-Hub.png "Fliser for merker og interesser")

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

Hvis du vil velge et land eller en region, åpner du **Merkesupplering** eller **Interessesupplering** og velger **Endre** ved siden av **Land/område**. Velg et alternativ i ruten **Innstillinger for land/område**, og velg **Bruk**.

### <a name="implications-related-to-country-selection"></a>Implikasjoner knyttet til valg av land

- Når du [velger dine egne merker](#define-your-brands-or-interests), gir systemet forslag basert på det valgte landet eller området.

- Når du [velger en bransje](#define-your-brands-or-interests), får du de mest relevante merkene eller interessene basert på det valgte landet eller området.

- Ved [supplering av profiler](#refresh-enrichment) supplerer vi alle kundeprofiler som vi får data for de valgte merkene og interessene for, inkludert profiler som ikke finnes i det valgte landet eller området. Hvis du for eksempel valgte Tyskland, vil vi supplere profiler i USA hvis vi har data tilgjengelig for de valgte merkene og interessene i USA.

## <a name="configure-enrichment"></a>Konfigurere supplering

En veiledet opplevelse hjelper deg gjennom konfigurasjonen av suppleringene. 

### <a name="define-your-brands-or-interests"></a>Definer merker og interesser

Velg opptil fem merker eller interesser ved å bruke ett av eller begge disse alternativene:

- **Bransje**: Velg bransje fra rullegardinlisten, og velg deretter blant de viktigste merkene eller interessene for den bransjen.
- **Velg dine egne**: Angi et merke eller en interesse som er relevant for organisasjonen din, og velg deretter blant forslagene som samsvarer. Hvis vi ikke viser et merke eller en interesse du leter etter, kan du sende oss tilbakemelding ved hjelp av **Foreslå**-koblingen.

### <a name="review-enrichment-preferences"></a>Se gjennom innstillinger for supplering

Se gjennom standardinnstillingene for supplering, og oppdater dem etter behov.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skjermbilde av vinduet for innstillinger for supplering.":::

### <a name="select-entity-to-enrich"></a>Velg enhet som skal suppleres

Velg **Supplert enhet**, og velg datasettet du vil bruke supplere med data fra Microsoft. Du kan velge kundeenheten for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.

### <a name="map-your-fields"></a>Tilordne feltene

Tilordne felter fra enheten for enhetlige kunder for å definere det demografiske segmentet du vil at systemet skal bruke til supplering av kundedataene. Tilordne land/område og minst attributtene Fødselsdato eller Kjønn. I tillegg må du tilordne minst én by (og delstat/område) eller ett postnummer. Velg **Rediger** for å definere tilordningen av feltene, og velg **Bruk** når du er ferdig. Velg **Lagre** for å fullføre felttilordningen.

Følgende formater og verdier støttes (det skilles ikke mellom små og store bokstaver i verdier):

- **Fødselsdato**: Vi anbefaler at fødselsdatoen konverteres til en DateTime-type under datainntak. Den kan også være en streng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "åååå-MM-dd" eller "åååå-MM-ddTHH:mm:ss".
- **Kjønn**: hann, hunn, ukjent.
- **Postnummer**: Femsifrede postnumre for USA, standard postnummer alle andre steder.
- **Sted**: Navn på poststed på engelsk.
- **Delstat/område**: Forkortelse på to bokstaver for USA og Canada. Forkortelse på to eller tre bokstaver for Australia. Gjelder ikke for Frankrike, Tyskland eller Storbritannia.
- **Land/område**:

  - US: Amerikas forente stater, De forente stater, USA, US, Amerika
  - CA: Canada, CA
  - GB: Storbritannia, UK, Great Britain, GB, Det forente kongerike Storbritannia og Nord-Irland, United Kingdom of Great Britain
  - AU: Australia, AU, Commonwealth of Australia
  - FR: Frankrike, FR, Republikken Frankrike
  - DE: Tyskland, German, Deutschland, Allemagne, DE, Forbundsrepublikken Tyskland, Republic of Germany

## <a name="review-and-name-the-enrichment"></a>Se gjennom og gi navn til suppleringen

Til slutt får du se gjennom informasjonen og angi et navn for suppleringen.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Side for å se gjennom og gi navn til interesser.":::

## <a name="refresh-enrichment"></a>Oppdatere supplering

Kjør suppleringen etter å ha konfigurert merker, interesser og felttilordningen for demografi. Hvis du vil starte prosessen, velger du **Kjør** på siden for merke- eller interessekonfigurasjon. I tillegg kan du la systemet kjøre suppleringen automatisk som en del av en planlagt oppdatering.

Avhengig av størrelsen på kundedataene kan det ta flere minutter å fullføre en supplering.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultater av supplering

Når du har kjørt suppleringsprosessen, går du til **Mine suppleringer** for å se du gjennom det totale antallet supplerte kunder, og en analyse over merker og interesser i de supplerte kundeprofilene.

:::image type="content" source="media/my-enrichments.png" alt-text="Forhåndsvisning av resultater etter kjøring av suppleringsprosessen.":::

Du finner et diagram med antall supplerte kundeprofiler over tid, og forhåndsvisninger av de supplerte enhetene. Se gjennom de supplerte dataene ved å velge **Se mer** i diagrammene **Affinitetsnivå** eller **Andel av omtale**. Supplerte data for varemerker går til **BrandAffinityFromMicrosoft**- og **BrandShareOfVoiceFromMicrosoft**-enhetene. Data for interesser er i enhetene **InterestAffinityFromMicrosoft** og **InterestShareOfVoiceFromMicrosoft**. Du finner også disse enhetene oppført i gruppen **Supplering** i **Data** > **Enheter**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Vise supplerte data på kundekortet

Andel av omtale for merke og interesse kan også vises på individuelle kundekort. Gå til **Kunder**, og velg en kundeprofil. På kundekortet finner du diagrammer for Andel av omtale-merket eller -interessen basert på personer i kundens demografiske profil.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundekort med supplerte data.":::

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
