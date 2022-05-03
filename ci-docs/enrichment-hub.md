---
title: Supplere enhetlige kundeprofiler
description: Bruk funksjoner for å supplere kundedataene.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 5c14e6c96d2f907ba161331b6f92277191cbdbef
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653535"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Supplement for kundeprofiler (forhåndsversjon)

Bruk data fra kilder som Microsoft og andre partnere for å berike kundedataene.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Side for suppleringshub.":::

Gå til **Data** > **Supplering** for å arbeide med suppleringsalternativer.  

Du må ha tillatelse som bidragsyter eller administrator for å opprette eller redigere berikelser. Du finner mer informasjon i [Tillatelser](permissions.md).

I kategorien **Oppdag** finner du alle støttede suppleringsalternativer.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

- [Merker](enrichment-microsoft.md) levert av Microsoft
- [Interesser](enrichment-microsoft.md) levert av Microsoft
- [Forbedrede adresser](enrichment-enhanced-addresses.md) levert av Microsoft 
- [Demografi](enrichment-experian.md) levert av Experian
- [Egendefinerte data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) levert av Microsoft
- [Stedsdata](enrichment-here.md) levert av HERE Technologies 
- [Identitet](enrichment-liveramp.md) angitt av LiveRamp AbiliTec

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

- [Firmadata](enrichment-leadspace.md) levert av Leadspace
- [Forbedrede adresser](enrichment-enhanced-addresses.md) levert av Microsoft 
- [Forbedrede firmadata](enrichment-enhanced-company-data.md) fra Microsoft
- [Stedsdata](enrichment-here.md) levert av HERE Technologies 
- [Egendefinerte data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) levert av Microsoft
- [Firmadata](enrichment-dnb.md) levert av Dun & Bradstreet
- [Kontoengasjementsdata](enrichment-office.md) fra Microsoft

---

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

Tredjeparts suppleringer konfigureres ved hjelp av [tilkoblinger](connections.md), som en administrator konfigurerer med legitimasjon og gir samtykketil dataoverføringer. Tilkoblingene kan brukes av administratorer og bidragsytere til å konfigurere suppleringer.  

## <a name="multiple-enrichments-of-the-same-type"></a>Flere suppleringer av samme type

Enheten som skal suppleres, angis under suppleringskonfigurasjonen, noe som gjør at du bare kan supplere et delsett av profilene. Du kan for eksempel bare supplere data for et bestemt segment. Du kan konfigurere flere suppleringer av samme type og bruke samme tilkobling på nytt. Noen suppleringer vil ha begrensninger på antall suppleringer av samme type som kan opprettes. Du kan se grensene og gjeldende bruk på **Supplering**-siden.

## <a name="enrich-data-sources-before-unification"></a>Supplere datakilder før foreningen

Du kan supplere kundedataene før dataforeningen, slik at kvaliteten på et datassamsvar økes. Hvis du vil ha mer informasjon, kan du se [datakildesupplering](data-sources-enrichment.md).

## <a name="see-the-progress-of-the-enrichment-process"></a>Se fremdriften for suppleringsprosessen

Du kan finne detaljer om behandlingen av en supplering, blant annet status og potensielle problemer når den oppdateres eller etter at en oppdatering er fullført. Forstå hvilke prosesser som er involvert i oppdatering av en supplering, og hvor lang tid det tok å kjøre prosessene. Suppleringsstatusen støttes for Experian, Leadspace, HERE Technologies, SFTP-import og Azure Maps.

Slik viser du statusen for en supplering

1. Gå til **Data** > **Supplering**. 
1. I fanen **Mine supplering** velger du statusen for en supplering for å åpne en siderute. 
1. Utvid **Suppleringer**-delen i **Fremdrift**-detaljruten. 
1. Velg **Se detaljer** under suppleringen du vil vise fremdriften for. 
1. Velg **Vis detaljer** i **Oppgavedetaljer**-ruten for å vise prosessene som er involvert i oppdatering av suppleringen og statusen deres. 

## <a name="enrichment-results"></a>Resultater av supplering

Etter en fullført suppleringskjøring, kan du se gjennom suppleringsresultatene.

1. Gå til **Data** > **Supplering**. 
1. Velg suppleringen du vil ha informasjon om.

Alle suppleringer viser grunnleggende informasjon, for eksempel antall supplerte profiler, en forhåndsvisning av den genererte suppleringsenheten og antall supplerte profiler over tid. Hvis tilgjengelig gir **Antall kunder supplert av feltet** en neddrilling i dekningen av hvert supplerte felt.

:::image type="content" source="media/enrichments-results.png" alt-text="Suppleringsresultater-siden.":::

Noen suppleringer viser også informasjon som er spesifikk for suppleringstypen. Se dokumentasjonen for den relevante suppleringen hvis du vil ha mer informasjon.


[!INCLUDE [footer-include](includes/footer-banner.md)]
