---
title: Supplere kundeprofiler med data fra Microsoft
description: Bruk proprietære data fra Microsoft til å supplere kundedataene med merke- og interesseaffiniteter.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 51b150cbf5d9cfb3a5df42e680bcfa57ec5496cb
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617890"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Supplere kundeprofiler med merke- og interesseaffiniteter (forhåndsvisning)

Bruk proprietære data fra Microsoft til å supplere kundedataene med merke- og interesseaffiniteter. Disse affinitetene er basert på data fra personer med en lignende demografi til kundene dine. Ved hjelp av denne informasjonen kan du bedre forstå og segmentere kunder basert på deres affinitet til bestemte merker og interesser.

I målgruppeinnsikt går du til **Data** > **Supplering** for å [konfigurere og vise suppleringer](enrichment-hub.md).

Hvis du vil konfigurere merkeaffinitet som skal berikes, går du til kategorien **Utforsk** og velger **Suppler dataene** på **Merker**-flisen.

Hvis du vil konfigurere interesseaffinitet som skal berikes, går du til kategorien **Utforsk** og velger **Suppler dataene** på **Interesser**-flisen.

   > [!div class="mx-imgBorder"]
   > ![Fliser for merker og interesser.](media/BrandsInterest-tile-Hub.png "Fliser for merker og interesser")

## <a name="how-we-determine-affinities"></a>Slik avgjør vi affiniteter

Vi bruker Microsofts søkedata på Internett til å finne affiniteter for merker og interesser i ulike demografiske segmenter (definert av alder, kjønn eller sted). Det elektroniske søkevolumet for et merke eller en interesse avgjør hvor mye affinitet et demografisk segment, sammenlignet med andre segmenter, har til merket eller interessen.

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

Velg **Supplert enhet**, og velg kundedatasettet du vil supplere med firmadata fra Microsoft. Du kan velge kundeenheten for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.

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

> [!TIP]
> Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser. De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies). Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben. Når du har valgt **Se detaljer** for en av jobbens oppgaver, finner du ytterligere informasjon: behandlingstid, siste behandlingsdato og alle feil og advarsler knyttet til oppgaven.

## <a name="enrichment-results"></a>Resultater av supplering

Når du har kjørt suppleringsprosessen, går du til **Mine suppleringer** for å se du gjennom det totale antallet supplerte kunder, og en analyse over merker og interesser i de supplerte kundeprofilene.

:::image type="content" source="media/my-enrichments.png" alt-text="Forhåndsvisning av resultater etter kjøring av suppleringsprosessen.":::

Se gjennom de supplerte dataene ved å velge **Vis supplerte data** i diagrammet. Supplerte data for merker går til **BrandAffinityFromMicrosoft**-enheten. Data for interesser er i **InterestAffinityFromMicrosoft**-enheten. Du finner også disse enhetene oppført i gruppen **Supplering** i **Data** > **Enheter**.

Du vil se et diagram med antall forbedrede kundeprofiler over tid, og en forhåndsvisning av den supplerte enheten. Velg **Vis mer** i forhåndsvisningsflisen for å åpne den supplerte enheten.

## <a name="see-enrichment-data-on-the-customer-card"></a>Vise supplerte data på kundekortet

Merke- og interesseaffiniteter kan også vises på individuelle kundekort. Gå til **Kunder**, og velg en kundeprofil. På kundekortet finner du diagrammer for merker eller interesser som personer i kundens demografiske profil har affinitet for.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundekort med supplerte data.":::

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
