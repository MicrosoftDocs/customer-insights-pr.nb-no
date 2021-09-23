---
title: Bruk demografiske dimensjoner for deling av virkemåtedata (kuraterte dimensjoner)
description: Bruk de kuraterte dimensjonene for enhetlig profil til å aktivere kundeprofilegenskapene for målgruppeinnsikt.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466360"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Bruk demografiske dimensjoner for deling av virkemåtedata

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ved å bruke demografiske dimensjoner for enhetlige profiler kan engasjementsinnsiktsbrukere få målgruppeinnsiktsprofilegenskaper. Du kan deretter bruke disse egenskapene i interaktive analyser av atferdsdata, inkludert data som er registrert av engasjementsinnsikt på nettstedet ditt eller i mobilappen din.

>[!NOTE]
> Engasjementsinnsikt omfatter bruksklare dimensjoner for hendelsesegenskaper. Mer informasjon: [Vis og opprett dimensjoner](dimensions.md)

## <a name="prerequisite"></a>Forutsetning

- Et engasjementsinnsiktmiljø der du har data om kundeprofiler koblet til målgruppeinnsiktsmiljøet der kundeprofilene er opprettet. Mer informasjon: [Opprett en kobling mellom målgruppeinnsikt og engasjementsinnsikt](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Når du har opprettet en kobling mellom målgruppeinnsikts- og engasjementsinnsiktsmiljøene, vil du kanskje bare ha data som er spesifikke for kundeprofilegenskaper, noe som kan være nyttig som dimensjoner i engasjementsinnsikt. Hvis du vil ha mer informasjon, kan du gå til [Aktiver attributter og segmenter for enhetlige profiler for målgruppeinnsikt](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Opprett en ny egendefinert rapport

1. Velg **Egendefinert** > **Ny rapport** i ruten til venstre, og velg deretter ønsket måledata. (I dette eksemplet valgte vi **Sidevisninger etter time**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Velg måledata.":::

2. Velg **Dimensjoner** i visualiseringsredigeringen, og velg deretter **Demografi** på rullegardinlisten **Dimensjonstype**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Velg demografiske data.":::

3. Velg et **Signal.Customer.*xxx***-dimensjon. (Dette eksemplet viser Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Velg en dimensjon.":::
  
## <a name="limitations"></a>Begrensninger

For øyeblikket kan du bare bruke demografiske dimensjoner for deling av virkemåtedata.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
