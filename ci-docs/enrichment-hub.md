---
title: Oversikt over datasupplering (forhåndsversjon)
description: Bruk funksjoner fra Microsoft og andre tredjepartstjenester til å supplere kundedataene.
ms.date: 06/10/2022
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
ms.openlocfilehash: fb747f7adc7d87f30f66c5d0ed20bbe238558fde
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304531"
---
# <a name="data-enrichment-preview-overview"></a>Oversikt over datasupplering (forhåndsversjon)

Bruk data fra kilder som Microsoft og andre partnere for å berike kundedataene. Tredjeparts suppleringer konfigureres ved hjelp av [tilkoblinger](connections.md), som en administrator konfigurerer med legitimasjon og gir samtykketil dataoverføringer. Tilkoblingene kan brukes av administratorer og bidragsytere til å konfigurere suppleringer.  

## <a name="multiple-enrichments-of-the-same-type"></a>Flere suppleringer av samme type

Enheten som skal suppleres, angis under suppleringskonfigurasjonen, noe som gjør at du bare kan supplere et delsett av profilene. Du kan for eksempel bare supplere data for et bestemt segment. Du kan konfigurere flere suppleringer av samme type og bruke samme tilkobling på nytt. Noen suppleringer vil ha begrensninger på antall suppleringer av samme type som kan opprettes. Du kan se grensene og nåværende bruk for hver flis på fanen **Oppdag** på siden **Supplering**.

## <a name="enrich-data-sources-before-unification"></a>Supplere datakilder før foreningen

Du kan supplere kundedataene før dataforeningen, slik at kvaliteten på et datassamsvar økes. Hvis du vil ha mer informasjon, kan du se [datakildesupplering](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Opprett en supplering

Du må ha [tillatelse](permissions.md) som bidragsyter eller administrator for å opprette eller redigere suppleringer.

Gå til **Data** > **Supplering**. Fanen **Oppdag** viser alle støttede suppleringsalternativer.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Side for suppleringshub.":::

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

- [AbiliTec-identitet](enrichment-liveramp.md) levert av LiveRamp AbiliTec
- [Merker](enrichment-microsoft.md) levert av Microsoft
- [Demografi](enrichment-experian.md) levert av Experian
- [Forbedrede adresser](enrichment-enhanced-addresses.md) levert av Microsoft
- [Interesser](enrichment-microsoft.md) levert av Microsoft
- [Stedsdata](enrichment-azure-maps.md) levert av Microsoft Azure Maps
- [Stedsdata](enrichment-here.md) levert av HERE Technologies
- [SFTP-egendefinerte data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

- [Kontoengasjementsdata](enrichment-office.md) fra Microsoft
- [Firmadata](enrichment-dnb.md) levert av Dun & Bradstreet
- [Firmadata](enrichment-leadspace.md) levert av Leadspace
- [Forbedrede adresser](enrichment-enhanced-addresses.md) levert av Microsoft
- [Forbedrede firmadata](enrichment-enhanced-company-data.md) fra Microsoft
- [Stedsdata](enrichment-azure-maps.md) levert av Microsoft Azure Maps
- [Stedsdata](enrichment-here.md) levert av HERE Technologies
- [SFTP-egendefinerte data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

---

## <a name="manage-existing-enrichments"></a>Behandle eksisterende suppleringer

Gå til **Data** > **Supplering**. Fanen **Mine suppleringer** viser konfigurerte suppleringer, statusen, antall supplerte kunder og sist gang dataene ble oppdatert. Du kan sortere listen over suppleringer etter en hvilken som helst kolonne, eller du kan bruke søkefeltet til å finne suppleringen du vil administrere.

Velg suppleringen for å vise tilgjengelige handlinger.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativer for å behandle suppleringer i listen over suppleringer.":::

- **Vis** suppleringsdetaljer med antall supplerte kundeprofiler.
- **Rediger** suppleringskonfigurasjonen.
- [**Kjør**](#run-or-refresh-enrichments) suppleringen for å oppdatere kundeprofiler med de nyeste dataene. Kjør flere suppleringer samtidig ved å velge dem i listen.
- **Aktiver** eller **deaktiver** en supplering. Inaktive suppleringer oppdateres ikke under en [planlagt oppdatering](schedule-refresh.md).
- **Slett** suppleringen.

Du kan også opprette [segmenter](segments.md) eller [mål](measures.md) fra suppleringer.

## <a name="run-or-refresh-enrichments"></a>Kjør eller oppdater suppleringer

Når den er kjørt, kan suppleringer oppdateres automatisk eller oppdateres manuelt ved behov.

1. Hvis du vil oppdatere en eller flere suppleringer manuelt, velger du dem og velger **Kjør**. Hvis du vil [planlegge en automatisk oppdatering](schedule-refresh.md), går du til **Administrator** > **System** > **Plan**. Behandlingstiden avhenger av størrelsen på kundedataene.

1. Se eventuelt [fremdriften for suppleringsprosessen](#see-the-progress-of-the-enrichment-process).

1. Når suppleringsprosessen er fullført, går du til **Mine suppleringer** for å se gjennom de nylig supplerte kundeprofildataene, tidspunktet for den siste oppdateringen og antall supplerte profiler.

1. Velg suppleringen for å se [suppleringsresultatene](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Se fremdriften for suppleringsprosessen

Du kan finne detaljer om behandlingen av en supplering, blant annet status og potensielle problemer når den oppdateres eller etter at en oppdatering er fullført. Forstå hvilke prosesser som er involvert i oppdatering av en supplering, og hvor lang tid det tok å kjøre prosessene. Suppleringsstatusen støttes for Experian, Leadspace, HERE Technologies, SFTP-import og Azure Maps.

1. Gå til **Data** > **Supplering**.
1. I fanen **Mine suppleringer** velger du statusen for suppleringen for å åpne en siderute.
1. Utvid **Suppleringer**-delen i **Fremdrift**-detaljruten.
1. Velg **Se detaljer** under suppleringen du vil vise fremdriften for.
1. Velg **Vis detaljer** i **Oppgavedetaljer**-ruten for å vise prosessene som er involvert i oppdatering av suppleringen og statusen deres.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Vis suppleringsresultater

Etter en fullført suppleringskjøring, kan du se gjennom suppleringsresultatene.

1. Gå til **Data** > **Supplering**.
1. I fanen **Mine suppleringer** velger du suppleringen du vil vise.

Alle suppleringer viser grunnleggende informasjon, for eksempel antall supplerte profiler og antall supplerte profiler over tid. Flisen **Forhåndsvisning av supplerte kunder** viser et eksempel på den genererte suppleringsenheten. Velg **Vis mer**, og velg fanen **Data** for å se en detaljert visning.

:::image type="content" source="media/enrichments-results.png" alt-text="Suppleringsresultater-siden.":::

Hvis tilgjengelig gir **Antall kunder supplert av feltet** en neddrilling i dekningen av hvert supplerte felt.

Noen suppleringer viser også informasjon som er spesifikk for suppleringstypen. Hvis du vil ha mer informasjon, kan du se relatert dokumentasjon.

[!INCLUDE [footer-include](includes/footer-banner.md)]
