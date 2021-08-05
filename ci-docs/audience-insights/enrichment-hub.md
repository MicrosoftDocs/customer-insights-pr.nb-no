---
title: Supplere enhetlige kundeprofiler
description: Bruk funksjoner for å supplere kundedataene.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: d12c0a9dd65d31f9ae8a9cafeafab2767d57893e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555273"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Supplement for kundeprofiler (forhåndsversjon)

Bruk data fra kilder som Microsoft og andre partnere for å berike kundedataene.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Side for suppleringshub.":::

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

Velg suppleringen for å vise de tilgjengelige alternativene. Du kan også velge ellipsen (...) i et listeelement for å vise alternativene. Hvis du har konfigurert flere suppleringer, kan du bruke søkeboksen til å finne den raskt.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativer for å behandle suppleringer i listen over suppleringer.":::

- **Vis** suppleringsdetaljer med antall supplerte kundeprofiler.
- **Rediger** suppleringskonfigurasjonen.
- **Kjør** supplementet for å oppdatere kundeprofiler med de nyeste dataene.
- **Deaktiver** en eksisterende supplering for å unngå at den oppdateres automatisk med hver planlagte oppdatering. Data fra den siste vellykkede oppdateringen er fortsatt tilgjengelige. **Aktiver** en inaktiv supplering for å starte automatisk oppdatering på nytt med hver planlagte oppdatering.
- **Slett** suppleringen.

Kjør eller deaktiver flere suppleringer samtidig ved å merke dem i listen. Visnings- og redigeringsalternativer er ikke tilgjengelige som massehandling. De fungerer bare for én supplering om gangen.

## <a name="enrichments-and-connections"></a>Suppleringer og tilkoblinger

Tredjeparts suppleringer konfigureres ved hjelp av [tilkoblinger](connections.md), som en administrator konfigurerer med legitimasjon og gir samtykketil dataoverføringer. Tilkoblingen kan brukes av administratorer og bidragsytere til å konfigurere suppleringer.  

## <a name="multiple-enrichments-of-the-same-type"></a>Flere suppleringer av samme type

Enheten som skal suppleres, angis under suppleringskonfigurasjonen, noe som gjør at du bare kan supplere et delsett av profilene. Du kan for eksempel bare supplere data for et bestemt segment. Du kan konfigurere flere suppleringer av samme type og bruke samme tilkobling på nytt. Noen suppleringer vil ha begrensninger på antall suppleringer av samme type som kan opprettes. Du kan se grensene og gjeldende bruk på **Supplering**-siden.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
