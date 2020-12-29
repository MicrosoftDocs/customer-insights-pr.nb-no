---
title: Supplere enhetlige kundeprofiler
description: Bruk funksjoner for å supplere kundedataene.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667106"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Supplement for kundeprofiler (forhåndsversjon)

Bruk data fra kilder som Microsoft og andre partnere for å berike kundedataene.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Side for suppleringshub":::

I måltruppeinnsikt går du til **Data** > **Supplering** for å arbeide med suppleringsalternativer.    
Du må ha tillatelse som bidragsyter eller administrator for å opprette eller redigere berikelser. Du finner mer informasjon i [Tillatelser](permissions.md).

I kategorien **Oppdag** finner du følgende suppleringer:

- [Merker](enrichment-microsoft-graph.md) formidlet av Microsoft Graph
- [Interesser](enrichment-microsoft-graph.md) formidlet av Microsoft Graph
- [Firmadata](enrichment-leadspace.md) levert av Leadspace
- [Demografi](enrichment-experian.md) levert av Experian
- [Stedsdata](enrichment-here.md) levert av HERE Technologies
- [Egendefinerte data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

I kategorien **Mine suppleringer** kan du se de suppleringene du har konfigurert, og redigere egenskapene deres.

## <a name="manage-existing-enrichments"></a>Behandle eksisterende suppleringer

Gå til **Mine suppleringer** for å se alle konfigurerte suppleringer. Hvert supplering vises som en rad som inneholder tilleggsinformasjon om suppleringen.

Velg en supplering for å vise de tilgjengelige alternativene. Du kan også velge en ellipse (...) for et listeelement for å vise alternativene.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativer for å behandle suppleringer i listen over suppleringer":::

- **Vis** suppleringsdetaljer med antall supplerte kundeprofiler.
- **Rediger** suppleringskonfigurasjonen.
- **Kjør** supplementet for å oppdatere kundeprofiler med de nyeste dataene.
- **Deaktiver** en eksisterende supplering for å unngå at den oppdateres automatisk med hver planlagte oppdatering. Data fra den siste vellykkede oppdateringen er fortsatt tilgjengelige. **Aktiver** en inaktiv supplering for å starte automatisk oppdatering på nytt med hver planlagte oppdatering.
- **Slett** en supplering.

Du kan kjøre eller deaktivere flere supplementer samtidig ved å velge dem i listen. Alternativer for visning og redigering er ikke tilgjengelige som massehandling og fungerer bare for én supplering om gangen.
