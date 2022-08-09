---
title: Finn lignende kunder med kunstig intelligens (forhåndsversjon) (inneholder video)
description: Finn lignende kundesegmenter med kunstig intelligens.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170739"
---
# <a name="find-similar-customers-with-ai-preview"></a>Finn lignende kunder med kunstig intelligens (forhåndsversjon)

Finn lignende kunder i kundebasen ved å bruke kunstig intelligens. Du må ha minst ett segment opprettet for å bruke denne funksjonen. Når du utvider kriteriene for et eksisterende segment, blir det enklere å finne kunder som ligner på dette segmentet.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Søk etter lignende kunder* bruker automatiske metoder til å evaluere data og lage prediksjoner basert på dataene. Den kan derfor brukes som en metode for profilering, slik denne termen er definert i EUs personvernforordning (GDPR). Kundens bruk av denne funksjonen til å behandle data kan være underlagt GDPR eller andre lover eller bestemmelser. Du er ansvarlig for å sikre at bruken av Dynamics 365 Customer Insights, inkludert prognoser, samsvarer med alle gjeldende lover og bestemmelser, inkludert lover som er relatert til personvern, personlige data, biometriske data, databeskyttelse og konfidensialitet for kommunikasjon.

## <a name="find-similar-customers"></a>Søk etter lignende kunder

1. Gå til **Segmenter** og velg segmentet du vil basere det nye segmentet på. Dette er *kildesegmentet*.

1. Velg **Søk etter lignende kunder**.

1. Se gjennom det foreslåtte navnet på det nye segmentet, og endre det hvis det er nødvendig.

1. Du kan eventuelt legge til [merker](work-with-tags-columns.md#manage-tags) i det nye segmentet.

1. Se gjennom feltene som definerer det nye segmentet. Disse feltene definerer grunnlaget for når systemet skal prøve å finne lignende kunder i kildesegmentet. Systemet velger anbefalte felter som standard. Legg til flere felter om nødvendig.
  Felt som kan redusere modellytelsen betydelig, blir automatisk utelatt:
  
   - Felt med følgende datatyper: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Felt med en kardinalitet (antall elementer i et felt) under 2 eller over 30

1. Velg om du vil ta med **Alle kunder** unntatt kildesegmentet eller bare kunder i et **annet segment** i det nye segmentet.

1. Som standard foreslår systemet en inkludering på bare 20 % av målgruppestørrelsen i utdataene. Rediger denne terskelen etter behov. Hvis du øker terskelen, reduseres presisjonen.

1. Inkluder kunder i kildesegmentet ved å merke av for **Inkluder medlemmer fra kildesegmentet i tillegg til kunder med lignende attributter**.

1. Velg **Kjør** nederst på siden for å starte en [binær klassifiseringsoppgave](#about-similarity-scores) (en metode for maskinlæring) som analyserer datasettet.

## <a name="view-the-similar-segment"></a>Vise det lignende segmentet

Etter at du har behandlet det lignende segmentet, finner du det nye segmentet på **Segmenter**-siden med typen **Utvidelse**.

Velg **Vis** for å vise resultatfordelingen på tvers av [likhetsresultater](#about-similarity-scores) og likhetspoengsummer under **Forhåndsvisning av segmentmedlemmer**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segmentet Lignende kunder.":::

## <a name="manage-a-similar-segment"></a>Administrer et lignende segment

[Arbeid med og administrer et lignende segment](segments.md#manage-existing-segments) som du gjør med andre segmenter. Du kan for eksempel eksportere segmentet eller bygge et mål.

Rediger, oppdater, gi nytt navn til, last ned og slett et lignende segment. Når du redigerer et lignende segment, behandles dataene på nytt. Det tidligere opprettede segmentet blir oppdatert med oppdaterte data.

## <a name="about-similarity-scores"></a>Likhetsresultater

Maskinlæringsmodellen for binær klassifisering tilordner en poengsum til kunder i det lignende segmentet. Poengsummen er basert på likheten med kunder i kildesegmentet.

- Likhetsresultater under 0,55 er kunder som systemet har klassifisert som *ikke lik* kunder i kildesegmentet
- Likhetsresultater mellom 0,55 og 0,7 klassifiseres som *ligner litt*
- Likhetsresultater mellom 0,7 og 0,85 klassifiseres som *ligner*
- Likhetsresultater mellom 0,85 og 1 er kunder som systemet har klassifisert som *svært like*

Kunder med likhetsresultater under 0,4, tas ikke med i modellutdataene. Systemet betrakter ikke de som like nok kildesegmentet.

[!INCLUDE [footer-include](includes/footer-banner.md)]
