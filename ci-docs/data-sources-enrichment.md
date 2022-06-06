---
title: Datakildesupplering
description: Supplere datakilder før du går gjennom datasamlingsprosessen.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 1225482c4bf432ed747537b2c9bec9ab0e692a51
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800293"
---
# <a name="enrichment-for-data-sources-preview"></a>Supplering for datakilder (forhåndsversjon)

Bruk data fra kilder som Microsoft og andre partnere til å forbedre kundedataene før dataforeningen. Datakildesupplering bidrar til å gi høyere datafullstendighet og -kvalitet som kan bidra til å oppnå bedre resultater når dataene samles. Hvis du for eksempel bruker et normalisert og standardisert format for adresser, økes kvaliteten på samsvarsresultatene. Hvis du vil ha en liste over støttede suppleringer, kan du se [alternativer alternativer for datakildesupplering](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Supplere en datakilde

Du må ha bidragsyter- eller administratortillatelser til å opprette eller redigere suppleringer. Du finner mer informasjon i [Tillatelser](permissions.md).  

1. Gå til **Data** > **Samle**. Velg enheten du vil supplere, og velg ett attributt som hovednøkkel for enheten. Hvis du vil ha mer informasjon, kan du se [Velg primærnøkkel](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Gå til **Data** > **Datakilder**.

1. Velg den loddrette ellipsen (&vellip;) ved siden av datakilden du vil berike, og velg **Suppler**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Side for datakildesupplering.":::

   Kategorien **Oppdag** viser [alternativene for støttede datakildesuppleringer](#supported-data-source-enrichments).

1. Velg **Suppler dataene** for å konfigurere en datakildesupplering. Navnet på utdataenhet fylles ut automatisk.

## <a name="supported-data-source-enrichments"></a>Støttede datakildesuppleringer

Følgende suppleringer er for øyeblikket tilgjengelige for datakilder. Se gjennom de detaljerte trinnene for supplering for å lære hvordan du konfigurerer den.

- [Forbedrede adresser](enrichment-enhanced-addresses.md)
- [Forbedrede firmadata](enrichment-enhanced-company-data.md)
- [Identitetsdata fra LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Administrere eksisterende datakildesuppleringer

Gå til fanen **Mine suppleringer** for å vise alle konfigurerte pårikninger.

Velg suppleringen for å vise de tilgjengelige alternativene. Du kan også velge den loddrette ellipsen (&vellip;) i et listeelement for å vise alternativene. Hvis du har konfigurert flere suppleringer, kan du bruke søkeboksen til å finne den raskt.

Du kan vise, redigere, kjøre eller slette datakildesupplering. Hvis du vil ha mer informasjon, kan du se [Behandle eksisterende suppleringer](enrichment-hub.md).
