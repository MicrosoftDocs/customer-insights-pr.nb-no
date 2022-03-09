---
title: Behandle standard samtykkeregler for segmenter
description: Med funksjonen for samtykkebehandling kan du deaktivere eller endre standard regler for samtykke hvis overstyringer er aktivert.
ms.date: 12/01/2021
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4eae4da67fd4c6e70800f495ba30366d4fc9a0dd
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228951"
---
# <a name="disable-or-change-default-consent-rules"></a>Deaktivere eller endre standard samtykkeregler

Hvis organisasjonene dine [samtykkebehandlingsmulighetene](../consent-management/overview.md) kombinert med målgruppeinnsikt, [kan administratorer håndheve samtykkeregler](activate-consent.md) for segmenter. 

Ved hjelp av håndhevede samtykkeregler i segmentområdet informerer hvert segment om tilstanden til samtykkekontrollen og -reglene. Hvis overstyringer er tillatt, deaktiveres standardregler for samtykke for bestemte segmenter. Hver oppretter av et segment kan legge til flere samtykkeregler på toppen av standardreglene for et segment. 

## <a name="for-administrators"></a>For systemansvarlige

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Segmentbygger med alternativer for samtykkeregel.":::

**Slik deaktiverer du standard samtykkeregler:**

1. Velg **Se detaljer** i varselet om **Samtykkeregler**. 

1. Sett veksleknappen til **Av** for **Standard samtykkeregler**.

**Slik legger du til flere samtykkeregler:**

1. Velg **Se detaljer** i varselet om **Samtykkeregler**. 

1. Velg **Legg til samtykkeregler**, og velg en samtykkeregel fra rullegardinlisten **Velg samtykkedatatype**.

1. Velg **Lagre** for å bruke den nye regelen på segmentet.

## <a name="for-contributors"></a>For bidragsytere

Hvis du vil opprette et segment uten håndhevede samtykkeregler, må du arbeide med administratoren for å deaktivere dem på segmentet. Du kan imidlertid legge til dine egne samtykkeregler i segmenter du eier og administrerer.

Det er en tretrinnsprosess: 
1. [Opprett segmentet](segments.md) i målgruppeinnsikt, og lagre det. 

1. Del segmentnavnet med administratoren din, og be vedkommende om å [aktivere overstyringer for segmentet](activate-consent.md). 

1. Åpne segmentene på nytt. I **Samtykkeregler**-varslingen velger du **Se detaljer** og legger til samtykkereglene du vil bruke. **Lagre** og **Kjør** deretter segmentet.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
