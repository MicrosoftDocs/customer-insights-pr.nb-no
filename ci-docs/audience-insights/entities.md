---
title: Enheter og datasett
description: Vise data på Enheter-siden.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 1e1abdf49a3c1fe6f9fdd2cf5353a7723454f47b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355332"
---
# <a name="entities-in-audience-insights"></a>Enheter i målgruppeinnsikt

Når du har [konfigurert datakildene](data-sources.md), går du til siden **Enheter** for å vurdere kvaliteten på de innhentede dataene. Enheter anses som datasett. Flere funksjoner i Dynamics 365 Customer Insights er bygget rundt disse enhetene. Når du ser gjennom dem, kan det hjelpe deg med å validere utdataene fra disse funksjonene.

**Enheter**-siden viser enheter og inneholder disse kolonnene:

- **Navn**: Navnet på dataenheten. Hvis du ser et varselsymbol ved siden av et enhetsnavn, betyr det at dataene for enheten ikke ble lastet inn på riktig måte.
- **Kilde**: Typen datakilde som inkluderte enheten.
- **Oppdatert**: Klokkeslett for når enheten sist ble oppdatert.
- **Status**: Detaljer om den siste oppdateringen av enheten.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Utforsk dataene til en bestemt enhet

1. I Målgruppeinnsikt går du til **Data** > **Enheter**.
1. Velg en enhet for å åpne detaljsiden fra **Enheter**-siden.  
1. Utforsk de forskjellige feltene og oppføringene for enheten.

- Fanen **Attributter** velges som standard og viser en tabell for å se gjennom detaljer for den valgte enheten, for eksempel feltnavn, datatyper og typer. **Type**-kolonnen viser Common Data Model-tilknyttede typer, som enten er automatisk identifiserte av systemet eller [manuelt tilordnede](map-entities.md) av brukere. Disse typene er semantiske typer som kan være forskjellige fra datatypene for attributtene. Feltet *E-post* nedenfor har for eksempel datatypen *Tekst*, men typen Common Data Model (semantisk) kan være *E-post* eller *EmailAddress*.

> [!div class="mx-imgBorder"]
> ![Tabellen Felter.](media/data-manager-entities-fields.PNG "Tabellen Felt")

> [!NOTE]
> Denne siden viser bare et eksempel på enhetsdataene. Hvis du vil vise hele datasettet, går du til siden **Datakilder**, velger en enhet, velger **Rediger** og deretter viser enhetens data med Power Query-redigeringsprogrammet som forklart i [Datakilder](data-sources.md).

Hvis du vil lære mer om data som hentes inn i enheten, gir kolonnen **Sammendrag** deg noen viktige egenskaper for dataene, for eksempel nuller, manglende verdier, unike verdier, antall og fordelinger, i henhold til hva som gjelder for dataene dine. Velg diagramikonet for å vise sammendraget av dataene.

> [!div class="mx-imgBorder"]
> ![Sammendragssymbol.](media/data-manager-entities-summary.png "Tabell for datasammendrag")

- Fanen **Data** viser en tabell som viser detaljer om enkeltoppføringer for enheten. Hvilke detaljer som vises, avhenger av datatypen for enheten.

> [!div class="mx-imgBorder"]
> ![Velg en enhet.](media/data-manager-entities-data.png "Velg en enhet")

- I kategorien **Rapporter** (tilgjengelig for enkelte enheter) kan du visualisere dataene ved å opprette en rapport og inkluderer disse kolonnene:

  - **Rapportnavn**: Navnet på rapporten.
  - **Opprettet av**: Navnet på personen som opprettet enheten.
  - **Opprettet**: Dato og klokkeslett for enhetsopprettingen.
  - **Redigert av**: Navnet på personen som endret enheten.
  - **Redigert**: Dato og klokkeslett for enhetsendringen. 

## <a name="entity-specific-information"></a>Enhetsbestemt informasjon

Delen nedenfor inneholder informasjon om noen systemopprettede enheter.

### <a name="corrupted-data-sources"></a>Ødelagte datakilder

Felter fra en inntatt datakilde kan inneholde ødelagte data. Oppføringer med ødelagte felter vises i systemopprettede enheter. Hvis du vet om ødelagte oppføringer, blir det enklere å identifisere hvilke data du vil se gjennom og oppdatere i kildesystemet. Etter den neste oppdateringen av datakilden, blir de korrigerte oppføringene overført til Customer Insights og videre til nedstrømsprosesser. 

En fødselsdag-kolonne har for eksempel datatypen angitt som dato. En kundeoppføring har fødselsdag angitt som 01/01/19777. Denne oppføringen flagges som ødelagt. Noen kan nå endre fødselsdagen i kildesystemet til 1977. Etter en automatisk oppdatering av datakildene, har feltet nå et gyldig format, og oppføringen blir fjernet fra den ødelagte enheten. 

Gå til **Data** > **Enheter**, og se etter de ødelagte enhetene i **System**-delen. Navneskjema for ødelagte enheter: DataSourceName_EntityName_corrupt. Velg en skadet enhet for å identifisere alle de skadede feltene og årsaken til dette på enkeltoppføringsnivå.
> [!div class="mx-imgBorder"]
> ![Skadeårsak.](media/corruption-reason.png "Skadeårsak")

Customer Insights behandler fremdeles ødelagte oppføringer. Det kan imidlertid føre til problemer når du arbeider med de enhetlige dataene.

Følgende kontroller kjører på de innhentede dataene for å vise skadede oppføringer: 

- Verdien i et felt samsvarer ikke med datatypen for kolonnen.
- Felter inneholder tegn som fører til at kolonnene ikke samsvarer med det forventede skjemaet. Eksempel: feil formaterte anførselstegn, anførselstegn som ikke er reserver, eller tegn for ny linje.
- Hvis det finnes kolonner for datetime/date/datetimeoffset, må formatet angis i modellen hvis det ikke følger ISO-standardformatet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
