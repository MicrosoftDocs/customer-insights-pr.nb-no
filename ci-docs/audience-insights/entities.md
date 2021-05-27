---
title: Enheter og datasett
description: Vise data på Enheter-siden.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049406"
---
# <a name="entities-in-audience-insights"></a>Enheter i målgruppeinnsikt

Når du har [konfigurert datakildene](data-sources.md), går du til siden **Enheter** for å vurdere kvaliteten på de innhentede dataene. Enheter anses som datasett. Flere funksjoner i Dynamics 365 Customer Insights er bygget rundt disse enhetene. Når du ser gjennom dem, kan det hjelpe deg med å validere utdataene fra disse funksjonene.

Siden **Enheter** viser enheter og inneholder flere kolonner:

- **Navn**: Navnet på dataenheten. Hvis du ser et varselsymbol ved siden av et enhetsnavn, betyr det at dataene for enheten ikke ble lastet inn på riktig måte.
- **Kilde**: Typen datakilde som hentet inn enheten
- **Opprettet av**: Navnet på personen som opprettet enheten
- **Opprettet**: Dato og klokkeslett for enhetsopprettingen
- **Opprettet av**: Navnet på personen som oppdaterte enheten
- **Sist oppdatert**: Dato og klokkeslett for den siste oppdateringen av enheten
- **Siste oppdatering**: Dato og klokkeslett for den siste dataoppdateringen

## <a name="exploring-a-specific-entitys-data"></a>Utforske dataene til en bestemt enhet

Velg en enhet for å utforske de forskjellige feltene og oppføringene som er inkludert i enheten.

> [!div class="mx-imgBorder"]
> ![Velg en enhet](media/data-manager-entities-data.png "Velg en enhet")

- Fanen **Data** viser en tabell som viser detaljer om enkeltoppføringer for enheten.

> [!div class="mx-imgBorder"]
> ![Tabellen Felt](media/data-manager-entities-fields.PNG "Tabellen Felt")

- Fanen **Attributter** velges som standard og viser en tabell for å se gjennom detaljer for den valgte enheten, for eksempel feltnavn, datatyper og typer. **Type**-kolonnen viser Common Data Model-tilknyttede typer, som enten er automatisk identifiserte av systemet eller [manuelt tilordnede](map-entities.md) av brukere. Dette er semantiske typer som kan være forskjellige fra attributtenes datatyper – for eksempel har feltet *E-post* nedenfor datatypen *Tekst*, men (semantisk) Common Data Model-type kan være *E-post* eller *EmailAddress*.

> [!NOTE]
> Begge tabellene viser bare et eksempel på enhetens data. Hvis du vil vise hele datasettet, går du til siden **Datakilder**, velger en enhet, velger **Rediger** og deretter viser enhetens data med Power Query-redigeringsprogrammet som forklart i [Datakilder](data-sources.md).

Hvis du vil lære mer om data som hentes inn i enheten, gir kolonnen **Sammendrag** deg noen viktige egenskaper for dataene, for eksempel nuller, manglende verdier, unike verdier, antall og fordelinger, i henhold til hva som gjelder for dataene dine.

Velg diagramikonet for å vise sammendraget av dataene.

> [!div class="mx-imgBorder"]
> ![Sammendragssymbol](media/data-manager-entities-summary.png "Tabell for datasammendrag")

### <a name="next-step"></a>Neste trinn

Se emnet [Samle](data-unification.md) for å lære hvordan du *tilordner*, *samsvarer* og *slår sammen* de innhentede dataene.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
