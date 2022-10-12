---
title: Enheter i Customer Insights
description: Vise data på Enheter-siden.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610110"
---
# <a name="entities-in-customer-insights"></a>Enheter i Customer Insights

Når du har [konfigurert datakildene](data-sources.md), går du til siden **Enheter** for å vurdere kvaliteten på de innhentede dataene. Enheter anses som datasett. Flere funksjoner i Dynamics 365 Customer Insights er bygget rundt disse enhetene. Når du ser gjennom dem, kan det hjelpe deg med å validere utdataene fra disse funksjonene.

Når du arbeider i Customer Insights og supplerer dataene eller oppretter segmenter, mål og aktiviteter, vises enhetene som opprettes fra disse handlingene, på **Entiteter**-siden.

## <a name="view-a-list-of-entities"></a>Vis en liste over enheter

Gå til **Data** > **Enheter** for å vise en liste over enheter. Følgende informasjon vises for hver enhet.

- **Navn**: Navnet på dataenheten. Hvis du ser et varselsymbol ved siden av et enhetsnavn, betyr det at dataene for enheten ikke ble lastet inn på riktig måte.
- **Kilde**: Typen datakilde som inkluderte enheten.
- **Oppdatert**: Klokkeslett for når enheten sist ble oppdatert.
- **Status**: Detaljer om den siste oppdateringen av enheten.

## <a name="explore-a-specific-entitys-data"></a>Utforsk dataene til en bestemt enhet

1. Gå til **Data** > **Enheter**.
1. Velg en enhet for å åpne detaljsiden.  
1. Utforsk de forskjellige feltene og oppføringene for enheten.

- **Attributter**-fanen velges som standard og viser detaljer for den valgte enheten, for eksempel feltnavn, datatyper og typer. **Type**-kolonnen viser Common Data Model-tilknyttede typer, som enten er automatisk identifiserte av systemet eller [manuelt tilordnede](map-entities.md) av brukere. Disse typene er semantiske typer som kan være forskjellige fra datatypene for attributtene. Feltet *E-post* nedenfor har for eksempel datatypen *Streng*, men den (semantiske) typen Common Data Model kan være *E-post* eller *EmailAddress* eller *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabellen Felter.":::

   > [!NOTE]
   > Denne siden viser bare et eksempel på enhetsdataene. Hvis du vil vise hele datasettet, går du til siden **Datakilder**, velger en enhet, velger **Rediger** og deretter viser enhetens data med Power Query-redigeringsprogrammet som forklart i [Datakilder](data-sources.md).

   Hvis du vil vite mer om data som hentes inn i enheten, inneholder kolonnen **Sammendrag** noen viktige dataegenskaper, for eksempel nuller, manglende verdier, unike verdier, antall og distribusjoner, uansett hva som gjelder for dataene dine. Velg diagramikonet for å vise sammendraget av dataene.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tabell for datasammendrag.":::

- **Data**-fanen viser detaljer om enkeltoppføringer for enheten. Hvilke detaljer som vises, avhenger av datatypen for enheten.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Velg en enhet.":::

- I **Rapporter**-fanen (tilgjengelig for enkelte enheter) kan du visualisere dataene ved å opprette en rapport som inneholder disse kolonnene:

  - **Rapportnavn**: Navnet på rapporten.
  - **Opprettet av**: Navnet på personen som opprettet enheten.
  - **Opprettet**: Dato og klokkeslett for enhetsopprettingen.
  - **Redigert av**: Navnet på personen som endret enheten.
  - **Redigert**: Dato og klokkeslett for enhetsendringen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
