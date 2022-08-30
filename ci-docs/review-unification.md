---
title: Se gjennom datasamling
description: Gå gjennom trinnene for datasamling, opprett enhetlige kundeprofiler og se gjennom resultatene
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303979"
---
# <a name="review-data-unification"></a>Se gjennom datasamling

Se gjennom oversikten over endringene, opprett den samlede profilen, og se gjennom resultatene.

## <a name="review-and-create-customer-profiles"></a>Se gjennom og opprett kundeprofiler

Dette siste trinnet i samlingsprosessen viser et sammendrag av trinnene i prosessen og gir mulighet til å gjøre endringer før du oppretter den enhetlige profilen.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Skjermbilde av Se gjennom og opprett kundeprofiler.":::

1. Velg **Rediger** i en av datasamlingstrinnene for å se gjennom og gjøre endringer.

1. Hvis du er fornøyd med valgene dine, velger du **Opprett kundeprofiler** (eller **Opprett forretningsforbindelsesprofiler** for B2B). **Samle**-siden vises mens den enhetlige kundeprofilen opprettes.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Skjermbilde av Samle-siden med fliser som viser I kø eller Oppdaterer.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Det tar litt tid å fullføre samlingsalgoritmen, og du kan ikke endre konfigurasjonen før den er fullført.

## <a name="view-the-results-of-data-unification"></a>Vis resultatene for datasamling

Etter samling viser siden **Data** > **Samle** antall enhetlige kundeprofiler (eller forretningsforbindelsesprofiler for B2B). Resultatene av hvert trinn i samlingsprosessen vises på hver flis. **Kildefelter** viser for eksempel antall tildelte attributter (felter) og **Duplikatoppføringer** viser antall duplikatoppføringer som ble funnet.

:::image type="content" source="media/m3_unified.png" alt-text="Skjermbilde av siden for datasamling etter at dataene er enhetlig.":::

> [!TIP]
> Flisen **Samsvarende betingelser** vises bare hvis flere enheter er valgt.

Vi anbefaler at du ser gjennom resultatene, spesielt kvaliteten på [samsvarsreglene](data-unification-update.md#manage-match-rules) dine og finjusterer dem om nødvendig.

Når det er nødvendig, [kan du gjøre endringer i samlingsinnstillingene](data-unification-update.md) og kjøre den enhetlige profilen på nytt.

### <a name="verify-output-entities-from-data-unification"></a>Kontroller utdataenheter fra datasamling

Gå til **Data** > **Enheter** for å kontrollere utdataenhetene.

Enheten for enhetlig kundeprofil, som kalles *Kunde*, vises i **Profiler**-delen. Første vellykkede samlingskjøring oppretter den enhetlige *Kunde*-enheten. Alle påfølgende kjøringer utvider enheten.

Dedupliserings- og sammenslåingsenheter opprettes og vises i **System**-delen. En deduplisert enhet kalt **Deduplication_DataSource_Entity** opprettes for hver av kildeenhetene. Enheten **ConflationMatchPairs** inneholder informasjon om samsvar på tvers av enheter.

En utdataenhet for deduplisering inneholder følgende informasjon:
- ID-er/nøkler
  - Primærnøkkel- og Alternativ ID-felter. Alternativ ID-felt består av alle de alternative ID-ene som er identifisert for en oppføring.
  - Feltet Deduplication_GroupId viser gruppen eller klyngen som identifiseres i en enhet, som grupperer alle lignende oppføringer basert på de angitte dedupliseringsfeltene. Det brukes til systembehandlingsformål. Hvis det ikke er angitt noen regler for manuell deduplisering og systemdefinerte dedupliseringsregler gjelder, kan det hende du ikke finner dette feltet i utdataenheten for deduplisering.
  - Deduplication_WinnerId: Dette feltet inneholder vinner-ID-en fra de identifiserte gruppene eller klyngene. Hvis Deduplication_WinnerId er den samme som primærnøkkelverdien for en oppføring, betyr det at oppføringen er vinneroppføringen.
- Felter brukes til å definere dedupliseringsreglene.
- Feltene Regel og Poengsum for å angi hvilke av dedupliseringsreglene som ble brukt, og poengsummen som ble returnert av den samsvarende algoritmen.

## <a name="next-step"></a>Neste trinn

- For B2B kan du eventuelt utføre [kontaktsamling](data-unification-contacts.md).

- For B2B konfigurerer du [aktiviteter](activities.md), [suppleringer](enrichment-hub.md), [relasjoner](relationships.md) eller [mål](measures.md) for å få mer innsikt om kundene.

[!INCLUDE[footer-include](includes/footer-banner.md)]
