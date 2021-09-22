---
title: Vise og opprette segmenter
description: Hvordan du oppretter, redigerer og sletter segmenter, og hvor du bruker dem.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036160"
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

1. Velg attributtet du vil filtrere etter, i **Ressursbibliotek**. For øyeblikket kan du bare opprette segmenter basert på dimensjoner.

1. Velg en operator og en verdi for det valgte attributtet. Følgende operasjoner støttes ikke.
   - **er**: krever nøyaktig treff for å ta med verdier. Bruker **er lik** for én verdi eller **noen av** for å ta med flere verdier.
   - **er ikke**: krever nøyaktig treff for å utelate verdier. Bruker **er lik** for én verdi eller **noen av** for å ta med flere verdier.
   - **begynner med**: en streng som de samsvarende verdiene begynner med.
   - **slutter med**: en streng som de samsvarende verdiene slutter med.
   - **inneholder**: en streng i samsvarende verdier.

1. Hvis du vil legge til flere betingelser i en gruppe, kan du bruke to logiske operatorer. Beregnede attributter beregner ved bruk av angitte operatorer.
   - **AND**-operator: Begge betingelser må oppfylles som en del av segmentprosessen. Dette alternativet er svært nyttig når du definerer betingelser på tvers av forskjellige enheter.
   - **OR**-operator: En av betingelsene må oppfylles som en del av segmenteringsprosessen. Dette alternativet er svært nyttig når du definerer flere betingelser for samme enhet.

1. Velg **Lagre**, og gi segmentet et navn. 

Segmentet vises på Segmenter-siden, og du kan bruke det på alle rapporter og trakter i arbeidsområdet.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Bruke et segment på en rapport eller trakt

Du kan bruke segmenter på en rapport eller trakt for å filtrere dem basert på betingelsene i segmentet. Du kan imidlertid ikke bruke segmenter på bruksrapporter i sanntid.

:::image type="content" source="media/segment-reports-filter.png" alt-text="En sidevisningsrapport med en utvidet rullegardinliste for å velge hvilke segmenter som skal brukes.":::

Åpne rapporten eller trakten for å bruke et segment. Velg **Legg til betingelse**, og velg **Filtrer etter segment**. Velg segmentet du vil bruke, fra listen. Segmentet brukes på rapporten. Hvis et diagram ikke støtter segmentet, vises det en feil.
 
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
