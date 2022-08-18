---
title: Oppdater samlingsinnstillingene
description: Oppdater duplikatregler, samsvarsregler eller enhetlige felter i samlingsinnstillingene.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: a7cf06c07e4b95b848a55dfe5fe0b09397fe744e
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245606"
---
# <a name="update-the-unification-settings"></a>Oppdater samlingsinnstillingene

Hvis du vil se gjennom eller endre eventuelle enhetlige innstillinger når en enhetlig profil er opprettet, utfører du følgende trinn:

1. Gå til **Data** > **Samle**.

   :::image type="content" source="media/m3_unified.png" alt-text="Skjermbilde av siden for datasamling etter at dataene er enhetlig.":::

   > [!TIP]
   > Flisen **Samsvarende betingelser** vises bare hvis flere enheter er valgt.

1. Velg hva du vil oppdatere:
   - [Kildefelter](#edit-source-fields) for å legge til enheter eller attributter eller endre attributtyper.
   - [Duplikatoppføringer](#manage-deduplication-rules) for å behandle dupliseringsregler eller fletteinnstillinger.
   - [Samsvarende betingelser](#manage-match-rules) for å oppdatere samsvarende regler på tvers av to eller flere enheter.
   - [Enhetlige kundefelter](#manage-unified-fields) som kan kombinere eller utelate felter. Du kan også gruppere relaterte profiler i klynger.

1. Når du har gjort endringene, velger du det neste alternativet:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Skjermbilde av siden for datasamling med alternativene for samling uthevet.":::

   - [Kjør samsvarende betingelser](#run-matching-conditions) for å evaluere kvaliteten på de samsvarende betingelsene (deduplisering og samsvarsregler) uten å oppdatere den enhetlige profilen. Alternativet **Kjør bare samsvarende betingelser** vises ikke for én enhet.
   - [Samle kundeprofiler](#run-updates-to-the-unified-customer-profile) for å kjøre samsvarende betingelser og oppdatere enheten for Unified customer profile uten at det påvirker avhengigheter (for eksempel suppleringer, segmenter eller tiltak). Avhengige prosesser kjøres ikke, men oppdateres som [definert i oppdateringsplanen](schedule-refresh.md).
   - [Samle kundeprofiler og -avhengigheter](#run-updates-to-the-unified-customer-profile) for å kjøre samsvarende betingelser og oppdatere enheten for Unified customer profile og alle avhengigheter (for eksempel suppleringer, segmenter eller tiltak). Alle prosesser kjører på nytt automatisk.

## <a name="edit-source-fields"></a>Rediger kildefelter

Du kan ikke fjerne et attributt eller en enhet hvis de allerede er samlet.

1. Velg **Rediger** på flisen **Kildefelter**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Skjermbilde av siden for kildefelter som viser antall primærnøkler, tildelte og ikke tildelte felter":::

   Antall tildelte og ikke tildelte felter vises.

1. Velg **Velg enheter og felter** for å legge til andre attributter eller enheter. Bruk søket eller rull for å finne og velge ønskede attributter og enheter. Velg **Bruk**.

1. Du kan eventuelt endre primærnøkkelen for en enhet, attributtypene og aktivere eller deaktivere **Intelligent tildeling**. Hvis du vil ha mer informasjon, kan du se [Velg primærnøkkel og semantisk type for attributter](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Velg **Neste** for å gjøre endringer i dedupliseringsregler, eller velg **Lagre og lukk** og gå tilbake til [Oppdater samlingsinnstillingene](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Administrer dedupliseringsregler

1. Velg **Rediger** på flisen **Duplikatoppføringer**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Skjermbilde av siden for duplikatoppføringer som viser antall dupliserte oppføringer" lightbox="media/m3_duplicates_edit.png":::

   Antall duplikatoppføringer som ble funnet, vises under **Duplikater**. Kolonnen **Oppføringer som er deduplisert**, viser hvilke enheter som hadde duplikatoppføringer og prosentandelen dupliserte oppføringer.

1. Hvis du har lagt til en supplert enhet, velger du **Bruk supplerte enheter**. Hvis du vil ha mer informasjon, kan du se [Supplering for datakilder](data-sources-enrichment.md).

1. Velg et av følgende alternativer for å behandle dedupliseringsregler:
   - **Opprett en ny regel**: Velg **Legg til regel** under den riktige enheten. Hvis du vil ha mer informasjon, kan du se [Definer dedupliseringsregler](remove-duplicates.md#define-deduplication-rules).
   - **Endre regelbetingelser**: Velg regelen og deretter **Rediger**. Endre felter, legg til eller fjern betingelser, eller legg til eller fjern unntak.
   - **Forhåndsvisning**: Velg regelen og deretter **Forhåndsvis** for å vise resultatene for siste kjøring for denne regelen.
   - **Deaktiver en regel**: Velg regelen og deretter **Deaktiver** for å beholde en dedupliseringsregel når den utelates fra den samsvarende prosessen.
   - **Dupliser en regel**: Velg regelen og deretter **Dupliser** for å opprette en lignende regel med endringer.
   - **Slett en regel**: Velg regelen og deretter **Slett**.

1. Hvis du vil endre fletteinnstillinger, velger du enheten. Du kan bare endre innstillingene hvis en regel er opprettet.
   1. Velg **Rediger fletteinnstillinger** og endre alternativet **Oppføring som skal beholdes**.
   1. Hvis du vil endre fletteinnstillinger for enkeltattributter for en enhet, velger du **Avansert** og gjør de nødvendige endringene.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Skjermbilde av avanserte fletteinnstillinger som viser den nyeste e-posten og den mest fullstendige adressen":::

   1. Velg **Ferdig**.

1. Velg **Neste** for å gjøre endringer i samsvarende betingelser, eller velg **Lagre og lukk** og gå tilbake til [Oppdater samlingsinnstillingene](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Administrer samsvarsregler

Du kan omkonfigurere og finjustere de fleste av samsvarsparameterne. Du kan ikke legge til eller slette enheter. Samsvarsregler gjelder ikke én enkelt enhet.

1. Velg **Rediger** på flisen **Samsvarende betingelser**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Skjermbilde av siden for samsvarsregler og betingelser med statistikk." lightbox="media/m3_match_edit.png":::

   Siden viser samsvarsrekkefølgen og definerte regler og følgende statistikk:
   - **Unike kildeoppføringer** viser antall individuelle kildeoppføringer som ble behandlet i siste samsvarskjøring.
   - **Samsvarende og ikke-samsvarende oppføringer** uthever hvor mange unike oppføringer som gjenstår etter behandling av samsvarsreglene.
   - **Bare samsvarende oppføringer** viser bare antall treff på tvers av alle samsvarsparene.

1. Velg **Vis sist kjørt** for å vise resultatene for alle reglene og resultatene for dem. Resultatene vises, inkludert de alternative kontakt-ID-ene. Du kan laste ned resultatene.

1. Hvis du vil vise resultatene og resultatene for en bestemt regel, velger du regelen og deretter **Forhåndsvis**. Resultatene vises. Du kan laste ned resultatene.

1. Hvis du vil vise resultatene for en bestemt betingelse på en regel, velger du regelen og deretter **Rediger**. Velg **Forhåndsvis** under betingelsen i Rediger-ruten. Du kan laste ned resultatene.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafisk representasjon av oppføringer som ikke samsvarer, inkludert en liste over dataene.":::

1. Hvis du har lagt til en supplert enhet, velger du **Bruk supplerte enheter**. Hvis du vil ha mer informasjon, kan du se [Supplering for datakilder](data-sources-enrichment.md).

1. Velg et av følgende alternativer for å behandle regler:
   - **Opprett en ny regel**: Velg **Legg til regel** under den riktige enheten. Hvis du vil ha mer informasjon, kan du se [Definer regler for samsvarspar](match-entities.md#define-rules-for-match-pairs).
   - **Endre rekkefølgen på reglene** hvis du definerte flere regler: Flytt og slipp reglene i den rekkefølgen du ønsker. Hvis du vil ha mer informasjon, kan du se [Angi samsvarsrekkefølgen](match-entities.md#specify-the-match-order).
   - **Endre regelbetingelser**: Velg regelen og deretter **Rediger**. Endre felter, legg til eller fjern betingelser, eller legg til eller fjern unntak.
   - **Deaktiver en regel**: Velg regelen og deretter **Deaktiver** for å beholde en samsvarsregel når den utelates fra den samsvarende prosessen.
   - **Dupliser en regel**: Velg regelen og deretter **Dupliser** for å opprette en lignende regel med endringer.
   - **Slett en regel**: Velg regelen og deretter **Slett**.

1. Velg **Neste** for å gjøre endringer i enhetlige felter, eller velg **Lagre og lukk** og gå tilbake til [Oppdater samlingsinnstillingene](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Administrer enhetlige felter

1. Velg **Rediger** på flisen **Enhetlige kundefelter**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Skjermbilde av enhetlige kundefelter":::

1. Se gjennom de kombinerte og ekskluderte feltene, og gjør eventuelle endringer. Legg til eller rediger CustomerID-nøkkelen eller gruppeprofilene i klynger. Hvis du vil ha mer informasjon, kan du se [Samle kundefelter](merge-entities.md).

1. Velg **Neste** for å se gjennom samlingsinnstillingene og [oppdatere den enhetlige profilen og avhengighetene](#run-updates-to-the-unified-customer-profile), eller velg **Lagre og lukk** og gå tilbake til [Oppdater samlingsinnstillingene](#update-the-unification-settings) for å gjøre flere endringer.

## <a name="run-matching-conditions"></a>Kjør samsvarende betingelser

Kjør samsvarende betingelser kjører bare deduplisering og samsvarsregler, og oppdaterer enhetene *Deduplication_* og *ConflationMatchPair*.

1. Velg **Kjør bare samsvarende betingelser** på siden **Data** > **Samle**.

   Flisene **Duplikatoppføringer** og **Samsvarende betingelser** viser statusen **I kø** eller **Oppdaterer**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Når den samsvarende prosessen er fullført, velger du **Rediger** på flisen **Samsvarende betingelser**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Beskjært skjermbilde av nøkkelmåledataene på Samsvar-siden med tall og detaljer.":::

1. Hvis du vil gjøre endringer, kan du se [Administrer dedupliseringsregler](#manage-deduplication-rules) eller [Administrer samsvarsregler](#manage-match-rules).

1. Kjør samsvarsprosessen på nytt, eller [kjør oppdateringer til kundeprofilen](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Kjør oppdateringer til den enhetlige kundeprofilen

1. Velg følgende på siden **Data** > **Samle**:

   - **Samle kundeprofiler**: Kjører samsvarende betingelser og oppdaterer enheten for Unified customer profile uten at det påvirker avhengigheter (for eksempel suppleringer, segmenter eller tiltak). Avhengige prosesser kjøres ikke, men oppdateres som [definert i oppdateringsplanen](schedule-refresh.md).

   - **Samle kundeprofiler og avhengigheter**: Kjører samsvarende betingelser og oppdaterer den enhetlige profilen og alle avhengigheter. Alle prosesser kjører på nytt automatisk. Når alle nedstrømsprosesser er fullført, gjenspeiler kundeprofilen de oppdaterte dataene.

   Flisene **Duplikatoppføringer**, **Samsvarende betingelser** og **Enhetlige kundefelter** viser statusen **I kø** eller **Oppdaterer**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Resultatet av et vellykket kjøring vises på **Samle**-siden som viser antall enhetlige kundeprofiler.
