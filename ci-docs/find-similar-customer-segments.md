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
ms.openlocfilehash: d58b2e424fd81ad691db4b2576bdf5655038ed89
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054813"
---
# <a name="find-similar-customers-with-ai-preview"></a>Finn lignende kunder med kunstig intelligens (forhåndsversjon)

Denne funksjonen gjør det mulig for deg å finne lignende kunder i kundebasen ved hjelp av kunstig intelligens. Du må ha minst ett opprettet segment for å bruke denne funksjonen. Ved å utvide kriteriene for et eksisterende segment kan du finne kunder som ligner på dette segmentet.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Finn lignende kunder* bruker automatiske metoder til å evaluere data og lage prognoser basert på dataene, og kan derfor brukes som en metode for profilering, slik denne termen defineres av EUs personvernforordning ("GDPR"). Kundens bruk av denne funksjonen til å behandle data kan være underlagt GDPR eller andre lover eller bestemmelser. Du er ansvarlig for å sikre at bruken av Dynamics 365 Customer Insights, inkludert prognoser, samsvarer med alle gjeldende lover og bestemmelser, inkludert lover som er relatert til personvern, personlige data, biometriske data, databeskyttelse og konfidensialitet for kommunikasjon.

## <a name="finding-similar-customers"></a>Finne lignende kunder

1. Gå til **Segmenter** og velg segmentet du vil basere det nye segmentet på. Dette er *kildesegmentet*.

1. På handlingslinjen velger du **Finn lignende kunder**.

1. Se gjennom det foreslåtte navnet på det nye segmentet, og endre det hvis det er nødvendig.

1. Du kan eventuelt legge til [merker](work-with-tags-columns.md#manage-tags) i det nye segmentet.

1. Se gjennom feltene som definerer det nye segmentet. Disse feltene definerer grunnlaget for når systemet skal prøve å finne lignende kunder i kildesegmentet. Systemet velger anbefalte felt som standard.
  Felt som kan redusere modellytelsen betydelig, blir automatisk utelatt:
  
   - Felt med følgende datatyper: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Felt med en kardinalitet (antall elementer i et felt) under 2 eller over 30

1. Velg om du vil inkludere **alle kunder** eller bare kunder i et **spesifikt eksisterende segment** i det nye segmentet.

1. Som standard foreslår systemet en inkludering på bare 20 % av målgruppestørrelsen i utdataene. Rediger denne terskelen etter behov. Hvis du øker terskelen, reduseres presisjonen.

1. Inkluder kunder i kildesegmentet ved å merke av for **Inkluder medlemmer fra kildesegmentet i tillegg til kunder med lignende attributter**.

1. Velg **Kjør** nederst på siden for å starte en binær klassifiseringsoppgave (en metode for maskinlæring) som analyserer datasettet.

## <a name="view-the-similar-segment"></a>Vise det lignende segmentet

Etter at du har behandlet det lignende segmentet, finner du det nye segmentet som vises på **Segmenter**-siden.

> [!div class="mx-imgBorder"]
> ![Segmentet Lignende kunder.](media/expanded-segment.png "Segmentet Lignende kunder")

Velg **Vis** på handlingslinjen for å åpne segmentdetaljene. Denne visningen inneholder informasjon om resultatfordelingen på tvers av [likhetsresultater](#about-similarity-scores). Du finner også likhetspoengsummene i **Forhåndsvisning av segmentmedlemmer**.

## <a name="use-the-output-of-a-similar-segment"></a>Bruke utdataene for et lignende segment

Du kan [arbeide med utdataene fra et lignende segment](segments.md) som du gjør med andre segmenter. Du kan for eksempel eksportere segmentet eller bygge et mål.

## <a name="refresh-and-edit-a-similar-segment"></a>Oppdatere og redigere et lignende segment

Hvis du vil oppdatere et lignende segment, velger du det på **Segmenter**-siden og velger **Oppdater** på handlingslinjen.

Når du redigerer et lignende segment, behandles dataene på nytt. Det tidligere opprettede segmentet blir oppdatert med oppdaterte data.
Hvis du vil redigere et lignende segment, velger du det på **Segmenter**-siden og velger **Rediger** på handlingslinjen. Ta i bruk endringene, og velg **Kjør** for å starte behandlingen.

## <a name="delete-a-similar-segment"></a>Slette et lignende segment

Slett segmentet på **Segmenter**-siden og velg **Slett** på handlingslinjen. Bekreft deretter slettingen.

## <a name="about-similarity-scores"></a>Likhetsresultater

Maskinlæringsmodellen for binær klassifisering tilordner en poengsum til kunder i det lignende segmentet. Poengsummen er basert på likheten med kunder i kildesegmentet.

- Likhetsresultater under 0,55 er kunder som systemet har klassifisert som *ikke lik* kunder i kildesegmentet
- Likhetsresultater mellom 0,55 og 0,7 klassifiseres som *ligner litt*
- Likhetsresultater mellom 0,7 og 0,85 klassifiseres som *ligner*
- Likhetsresultater mellom 0,85 og 1 er kunder som systemet har klassifisert som *svært like*

Kunder med likhetsresultater under 0,4, tas ikke med i modellutdataene. Systemet betrakter ikke de som like nok kildesegmentet.

[!INCLUDE [footer-include](includes/footer-banner.md)]
