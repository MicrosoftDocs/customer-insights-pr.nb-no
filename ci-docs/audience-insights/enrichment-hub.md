---
title: Supplere enhetlige kundeprofiler
description: Bruk funksjoner for å supplere kundedataene.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305260"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Supplement for kundeprofiler (forhåndsversjon)

Bruk data fra kilder som Microsoft og andre partnere for å berike kundedataene.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Side for suppleringshub":::

I måltruppeinnsikt går du til **Data** > **Supplering** for å arbeide med suppleringsalternativer.  

Du må ha tillatelse som bidragsyter eller administrator for å opprette eller redigere berikelser. Du finner mer informasjon i [Tillatelser](permissions.md).

I kategorien **Oppdag** finner du følgende suppleringer:

- [Merker](enrichment-microsoft.md) levert av Microsoft
- [Interesser](enrichment-microsoft.md) levert av Microsoft
- [Forbedrede adresser](enrichment-enhanced-addresses.md) levert av Microsoft
- [Firmadata](enrichment-leadspace.md) levert av Leadspace
- [Demografi](enrichment-experian.md) levert av Experian
- [Stedsdata](enrichment-here.md) levert av HERE Technologies
- [Egendefinerte data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

I kategorien **Mine suppleringer** kan du se de suppleringene du har konfigurert, og redigere egenskapene deres.

## <a name="manage-existing-enrichments"></a>Behandle eksisterende suppleringer

Gå til fanen **Mine suppleringer** for å vise alle konfigurerte pårikninger. Hvert supplering vises som en rad som inneholder tilleggsinformasjon om suppleringen.

Velg en supplering for å vise de tilgjengelige alternativene. Du kan også velge ellipsen (...) i et listeelement for å vise alternativene.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativer for å behandle suppleringer i listen over suppleringer":::

- **Vis** suppleringsdetaljer med antall supplerte kundeprofiler.
- **Rediger** suppleringskonfigurasjonen.
- **Kjør** supplementet for å oppdatere kundeprofiler med de nyeste dataene.
- **Deaktiver** en eksisterende supplering for å unngå at den oppdateres automatisk med hver planlagte oppdatering. Data fra den siste vellykkede oppdateringen er fortsatt tilgjengelige. **Aktiver** en inaktiv supplering for å starte automatisk oppdatering på nytt med hver planlagte oppdatering.
- **Slett** en supplering.

Du kan kjøre eller deaktivere flere supplementer samtidig ved å velge dem i listen. Alternativer for visning og redigering er ikke tilgjengelige som massehandling og fungerer bare for én supplering om gangen.

## <a name="enrichments-and-connections"></a>Suppleringer og tilkoblinger

Tredjeparts suppleringer konfigureres ved hjelp av [tilkoblinger](connections.md), som en administrator konfigurerer med legitimasjon og gir samtykketil dataoverføringer. Tilkoblingen kan brukes av administratorer og bidragsytere til å konfigurere suppleringer.  

## <a name="multiple-enrichments-of-the-same-type"></a>Flere suppleringer av samme type

Enheten som skal suppleres, angis under suppleringskonfigurasjonen, noe som gjør at du bare kan supplere et delsett av profilene. Du kan for eksempel bare supplere data for et bestemt segment. Du kan konfigurere flere suppleringer av samme type og bruke samme tilkobling på nytt. Noen suppleringer vil ha begrensninger på antall suppleringer av samme type som kan opprettes. Du kan se grensene og gjeldende bruk på **Supplering**-siden.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
