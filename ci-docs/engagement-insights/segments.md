---
title: Vise og opprette segmenter
description: Hvordan du oppretter, redigerer og sletter segmenter, og hvor du bruker dem.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: f6bba645a78173fb00dc75e6080f2aeda0b5a143
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623599"
---
# <a name="view-and-create-segments"></a>Vise og opprette segmenter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med segmenter kan du identifisere delsett av besøkende basert på kjennetegn eller samhandlinger med nettstedet. Med segmenter kan du bruke filtre og analysere delsettene. Analysen kan hjelpe deg å undersøke og reagere på trender i virksomheten. 

:::image type="content" source="media/segments-page.png" alt-text="Skjermbilde av programmet for engasjementsinnsikt, der listen over eksisterende segmenter i et arbeidsområde vises.":::

## <a name="view-segments"></a>Vise segmenter

1. Gå til **Data** i venstre navigasjonsrute. 

1. Velg **Segmenter**-fanen for å vise en liste over alle segmenter i arbeidsområdet. 

## <a name="create-a-segment"></a>Opprett et segment

Segmenter består av regler og betingelser som er koblet til logiske operatorer. Betingelser bruker filtre på en valgt dimensjon. Hvert segment kan bruke opptil fem dimensjoner.

Følgende eksempel viser et segment med to betingelser i en regel. Det filtrerer alle nettstedshendelser der nettleseren er Chrome og operativsystemet er iOS eller Android.

:::image type="content" source="media/segment-sample.png" alt-text="Eksempelsegmenter med to betingelser i en regel for å filtrere etter nettstedshendelser.":::

Denne delen beskriver hvordan du oppretter et *tomt segment* fra bunnen av.

1. Gå til **Data** > **Segmenter**.

1. Velg **Nytt segment**.

1. I **Ressursbibliotek** velger du (+) ved siden av attributtet du vil filtrere etter. For øyeblikket kan du bare opprette segmenter basert på dimensjoner.

   :::image type="content" source="media/create-new-segment.png" alt-text="Opprett et nytt segment.":::

1. Velg en operator og en verdi for det valgte attributtet i **Regel**-delen. Følgende operasjoner støttes ikke.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Velg en operator for det nye segmentet.":::

   - **er**: krever nøyaktig treff for å ta med verdier. Bruker **er lik** for én verdi eller **noen av** for å ta med flere verdier.
   - **er ikke**: krever nøyaktig treff for å utelate verdier. Bruker **er lik** for én verdi eller **noen av** for å ta med flere verdier.
   - **begynner med**: en streng som de samsvarende verdiene begynner med.
   - **slutter med**: en streng som de samsvarende verdiene slutter med.
   - **inneholder**: en streng i samsvarende verdier.

1. Hvis du vil legge til flere betingelser for en gruppe, kan du bruke logiske operatorer. Beregnede attributter beregner ved bruk av angitte operatorer.
   - **AND**-operator: Begge betingelser må oppfylles som en del av segmentprosessen. Dette alternativet er svært nyttig når du definerer betingelser på tvers av forskjellige enheter.
   - **OR**-operator: En av betingelsene må oppfylles som en del av segmenteringsprosessen. Dette alternativet er svært nyttig når du definerer flere betingelser for samme enhet.

1. Velg **Lagre**, og gi segmentet et navn. 

Segmentet vises på **Segmenter**-siden, og du kan bruke det på alle rapporter og trakter i arbeidsområdet.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Bruke et segment på en rapport eller trakt

Du kan bruke segmenter på en rapport eller trakt for å filtrere dem basert på betingelsene i segmentet. Du kan imidlertid ikke bruke segmenter på bruksrapporter i sanntid.

:::image type="content" source="media/segment-reports-filter.png" alt-text="En sidevisningsrapport med en utvidet rullegardinliste for å velge hvilke segmenter som skal brukes.":::

Åpne rapporten eller trakten for å bruke et segment. Velg **+ Legg til betingelse**, og velg **Filtrer etter segment**. Velg segmentet du vil bruke, fra listen. Segmentet brukes på rapporten. Hvis et diagram ikke støtter segmentet, vises det en feil. Hvis du vil ha mer informasjon, kan du se [Opprette og behandle traktrapporter](funnel-reports.md).
 
Du kan bruke *opptil tre segmenter* på en rapport eller trakt.

## <a name="edit-a-segment"></a>Redigere et segment

1. Gå til **Data** > **Segmenter**.
1. Velg segmentet i listen for å åpne det. 
1. Endre eller legg til verdier etter behov.
1. Velg **Lagre** for å ta i bruk endringene.

## <a name="change-the-name-of-a-segment"></a>Endre navnet på et segment

1. Gå til **Data** > **Segmenter**.
1. Velg **Mer [...]** i segmentlisten. 
1. Velg **Rediger navn** i rullegardinlisten.
1. Skriv inn det nye navnet, og velg **Gi nytt navn**.

## <a name="delete-a-segment"></a>Slette et segment

1. Gå til **Data** > **Segmenter**.
1. Velg **Mer [...]** i segmentlisten. 
1. Velg **Slett** i rullegardinlisten.
1. Velg **Slett** for å bekrefte.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
