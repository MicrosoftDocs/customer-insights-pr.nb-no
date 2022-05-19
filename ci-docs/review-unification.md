---
title: Se gjennom datasamling
description: Gå gjennom trinnene for datasamling, opprett enhetlige kundeprofiler og se gjennom resultatene
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741719"
---
# <a name="review-data-unification"></a>Se gjennom datasamling

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Dette siste trinnet i samlingsprosessen viser et sammendrag av trinnene i prosessen og gir mulighet til å gjøre endringer før du oppretter den enhetlige profilen.

:::image type="content" source="media/m3_review.png" alt-text="Skjermbilde av Se gjennom og Opprett kundeprofiler.":::

## <a name="review-the-data-unification-steps"></a>Gå gjennom trinnene for datasamling

1. Velg **Rediger** i en av datasamlingstrinnene for å se gjennom og gjøre endringer.

1. Hvis du er fornøyd med valgene dine, velger du **Opprett kundeprofiler**. **Samle**-siden vises mens den enhetlige kundeprofilen opprettes. Det tar litt tid å fullføre samlingsalgoritmen, og du kan ikke endre konfigurasjonen før den er fullført.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Når samlingsprosessen er fullført, vises enheten for den enhetlige kundeprofilen, kalt *Kunde*, på **Enheter**-siden i **Profiler**-delen. Første vellykkede samlingskjøring oppretter den enhetlige *Kunde*-enheten. Alle påfølgende kjøringer utvider enheten.

## <a name="review-the-results-of-data-unification"></a>Gå gjennom resultatene for datasamling

Etter samling viser siden **Data** > **Samle** antall enhetlige kundeprofiler. Resultatene av hvert trinn i samlingsprosessen vises på hver flis. **Kildefelter** viser for eksempel antall tildelte attributter (felter) og **Duplikatoppføringer** viser antall duplikatoppføringer som ble funnet.

:::image type="content" source="media/m3_unified.png" alt-text="Skjermbilde av siden for datasamling etter at dataene er enhetlig.":::

> [!TIP]
> Flisen **Samsvarende betingelser** vises bare hvis flere enheter er valgt.

Vi anbefaler at du ser gjennom resultatene, spesielt kvaliteten på [samsvarsreglene](data-unification-update.md#manage-match-rules) dine og finjusterer dem om nødvendig.

Når det er nødvendig, [kan du gjøre endringer i samlingsinnstillingene](data-unification-update.md) og kjøre den enhetlige profilen på nytt.

## <a name="next-step"></a>Neste trinn

Konfigurer [aktiviteter](activities.md), [supplering](enrichment-hub.md), [relasjoner](relationships.md) eller [tiltak](measures.md) for å få mer innsikt om kundene.

[!INCLUDE[footer-include](includes/footer-banner.md)]
