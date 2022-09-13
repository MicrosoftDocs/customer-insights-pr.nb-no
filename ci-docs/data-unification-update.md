---
title: Oppdatere innstillinger for kunde-, forretningsforbindelses- eller kontaktsamling
description: Oppdater duplikatregler, samsvarsregler eller samlede felter i innstillingene for kunde- eller forretningsforbindelsessamling.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392483"
---
# <a name="update-unification-settings"></a>Oppdater samlingsinnstillinger

Hvis du vil se gjennom eller endre eventuelle enhetlige innstillinger når en enhetlig profil er opprettet, utfører du følgende trinn:

1. Gå til **Data** > **Samle**.

   For enkeltkunder (B2C) viser **Samle**-siden antall samlede kundeprofiler og -fliser for hvert av samlingstrinnene.

   :::image type="content" source="media/m3_unified.png" alt-text="Skjermbilde av siden for datasamling etter at dataene er enhetlig." lightbox="media/m3_unified.png":::

   For forretningsforbindelser (B2B) viser **Samle**-siden antall samlede forretningsforbindelsesprofiler og -fliser for hvert av samlingstrinnene for forretningsforbindelse. Hvis kontaktene er samlet, vises antall samlede kontaktprofiler og -fliser for hvert av samlingstrinnene for kontakt. Velg den riktige flisen under **Samle forretningsforbindelser** eller **Samle kontakter (forhåndsversjon)** avhengig av hva du vil oppdatere.

   :::image type="content" source="media/b2b_unified.png" alt-text="Skjermbilde av siden for datasamling etter at forretningsforbindelses- og kontaktdataene er samlet." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Flisen **Samsvarende betingelser** vises bare hvis flere enheter er valgt.

1. Velg hva du vil oppdatere:
   - [Kildefelter](#edit-source-fields) for å legge til attributter eller enheter eller endre attributtyper. Hvis du vil fjerne et attributt, kan du se [Fjerne et samlet felt](#remove-a-unified-field). Hvis du vil fjerne en enhet, kan du se [Fjerne en samlet enhet](#remove-a-unified-entity).
   - [Duplikatoppføringer](#manage-deduplication-rules) for å behandle dupliseringsregler eller fletteinnstillinger.
   - [Samsvarende betingelser](#manage-match-rules) for å oppdatere samsvarende regler på tvers av to eller flere enheter.
   - [Enhetlige kundefelter](#manage-unified-fields) som kan kombinere eller utelate felter. Du kan også gruppere relaterte profiler i klynger.
   - [Semantiske felter](#manage-semantic-fields-for-unified-contacts) for å behandle semantiske typer for samlede kontaktfelter.
   - [Relasjoner](#manage-contact-and-account-relationships) for å administrere relasjonen mellom kontakt og forretningsforbindelse.

1. Når du har gjort endringene, velger du det neste alternativet:

   - [Kjør samsvarende betingelser](#run-matching-conditions) for å evaluere kvaliteten på de samsvarende betingelsene (deduplisering og samsvarsregler) uten å oppdatere den enhetlige profilen. Alternativet **Kjør bare samsvarende betingelser** vises ikke for én enhet.
   - [Samle profiler](#run-updates-to-the-unified-profile) for å kjøre samsvarende betingelser og oppdatere enheten for samlet profil uten at det påvirker avhengigheter (for eksempel suppleringer, segmenter eller mål). Avhengige prosesser kjøres ikke, men oppdateres som [definert i oppdateringsplanen](schedule-refresh.md).
   - [Samle profiler og avhengigheter](#run-updates-to-the-unified-profile) for å kjøre samsvarende betingelser, oppdatere enheten for samlet profil og oppdatere alle avhengigheter (for eksempel suppleringer, segmenter eller mål). Alle prosesser kjører på nytt automatisk. I B2B kjøres samling på både forretningsforbindelses- og kontaktenhetene, slik at de samlede profilene oppdateres.

## <a name="edit-source-fields"></a>Rediger kildefelter

1. Velg **Rediger** på flisen **Kildefelter**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Skjermbilde av siden for kildefelter som viser antall primærnøkler, tildelte og ikke tildelte felter":::

   Antall tildelte og ikke tildelte felter vises.

1. Velg **Velg enheter og felter** for å legge til andre attributter eller enheter.

1. Du kan eventuelt endre primærnøkkelen for en enhet, attributtypene og aktivere eller deaktivere **Intelligent tildeling**. Hvis du vil ha mer informasjon, kan du se [Velg kildefelter](map-entities.md).

1. Velg **Neste** for å gjøre endringer i dedupliseringsregler, eller velg **Lagre og lukk** og gå tilbake til [Oppdater samlingsinnstillinger](#update-unification-settings).

### <a name="remove-a-unified-field"></a>Fjerne et samlet felt

Hvis du vil fjerne et felt som er samlet, må du fjerne det fra eventuelle avhengigheter, for eksempel segmenter, mål, suppleringer eller relasjoner.

1. Når alle avhengighetene for feltet er fjernet, går du til **Data** > **Samle**.

1. Velg **Rediger** på flisen **Enhetlige kundefelter**.

1. Velg alle forekomster av feltet, og velg deretter **Utelat**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Skjermbilde av siden for samlede felter med valgte felter og Utelat-knappen":::

1. Velg **Ferdig** for å bekrefte, og velg deretter **Lagre og lukk**.

   > [!TIP]
   > Hvis du får meldingen «Kan ikke lagre samlingen. Den angitte ressursen kan ikke endres eller slettes på grunn av nedstrømsavhengigheter», brukes feltet fortsatt i en nedstrømsavhengighet.

1. Hvis feltet brukes i en regel for dupliserte oppføringer eller samsvarende betingelser, gjør du følgende: Ellers går du til neste trinn.
   1. Velg **Rediger** på flisen **Duplikatoppføringer**.
   1. Fjern feltet fra eventuelle regler det brukes i, og velg deretter **Neste**.
   1. På siden **Samsvarende betingelser** fjerner du feltet fra eventuelle regler det brukes i, og deretter velger du **Lagre og lukk**.
   1. Velg **Samle** > **Samle kundeprofiler og avhengigheter**. Vent til samlingen er fullført før du går til neste trinn.

1. Velg **Rediger** på flisen **Kildefelter**.

1. Velg **Velg enheter og felter**, og fjern merket for hver forekomst av feltet.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Skjermbilde av dialogboksen Velg enheter og felter som viser tomme avmerkingsbokser":::

1. Velg **Bruk**.

1. Velg **Lagre og lukk**.

1. Velg **Samle** > **Samle kundeprofiler og avhengigheter** for å oppdatere den samlede profilen.

### <a name="remove-a-unified-entity"></a>Fjerne en samlet enhet

Hvis du vil en enhet som er samlet, må du fjerne den fra eventuelle avhengigheter, for eksempel segmenter, mål, suppleringer eller relasjoner.

1. Når alle avhengighetene for enheten er fjernet, går du til **Data** > **Samle**.

1. Velg **Rediger** på flisen **Enhetlige kundefelter**.

1. Velg alle feltene for enheten, og velg deretter **Utelat**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Skjermbilde av samlede felter med alle feltene valgt for en enhet og Utelat-knappen":::

1. Velg **Ferdig** for å bekrefte, og velg deretter **Lagre og lukk**.

   > [!TIP]
   > Hvis du får meldingen «Kan ikke lagre samlingen. Den angitte ressursen kan ikke endres eller slettes på grunn av nedstrømsavhengigheter», brukes enheten fortsatt i en nedstrømsavhengighet.

1. Velg **Rediger** på flisen **Duplikatoppføringer**.

1. Fjern eventuelle regler fra enheten, og velg deretter **Neste**.

1. Velg enheten på siden **Samsvarende betingelser**, og velg deretter **Slett**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Skjermbilde av Samsvarende betingelser med valgt enhet og Slett-knappen":::

1. Velg **Lagre og lukk**.

1. Velg **Rediger** på flisen **Kildefelter**.

1. Velg **Velg enheter og felter**, og fjern merket for enheten.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Skjermbilde av dialogboksen Velg enheter og felter med tom avmerkingsboks for enhet":::

1. Velg **Bruk**.

1. Velg **Lagre og lukk**.

1. Velg **Samle** > **Samle kundeprofiler og avhengigheter** for å oppdatere den samlede profilen.

## <a name="manage-deduplication-rules"></a>Administrer dedupliseringsregler

1. Velg **Rediger** på flisen **Duplikatoppføringer**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Skjermbilde av siden for duplikatoppføringer som viser antall dupliserte oppføringer" lightbox="media/m3_duplicates_edit.png":::

   Antall duplikatoppføringer som ble funnet, vises under **Duplikater**. Kolonnen **Oppføringer som er deduplisert**, viser hvilke enheter som hadde duplikatoppføringer og prosentandelen dupliserte oppføringer.

1. Hvis du bruker en supplert enhet, velger du **Bruk supplerte enheter**. Hvis du vil ha mer informasjon, kan du se [Supplering for datakilder](data-sources-enrichment.md).

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

   1. Velg **Ferdig**.

1. Velg **Neste** for å gjøre endringer i samsvarende betingelser, eller velg **Lagre og lukk** og gå tilbake til [Oppdater samlingsinnstillinger](#update-unification-settings).

## <a name="manage-match-rules"></a>Administrer samsvarsregler

Du kan omkonfigurere og finjustere de fleste av samsvarsparameterne. Du kan ikke legge til eller slette enheter. Samsvarsregler gjelder ikke én enkelt enhet.

1. Velg **Rediger** på flisen **Samsvarende betingelser**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Skjermbilde av siden for samsvarsregler og betingelser med statistikk." lightbox="media/m3_match_edit.png":::

   Siden viser samsvarsrekkefølgen og definerte regler og følgende statistikk:
   - **Unike kildeoppføringer** viser antall individuelle kildeoppføringer som ble behandlet i siste samsvarskjøring.
   - **Samsvarende og ikke-samsvarende oppføringer** uthever hvor mange unike oppføringer som gjenstår etter behandling av samsvarsreglene.
   - **Bare samsvarende oppføringer** viser antall treff på tvers av alle samsvarsparene.

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

1. Velg **Neste** for å gjøre endringer i samlede felter, eller velg **Lagre og lukk** og gå tilbake til [Oppdater samlingsinnstillinger](#update-unification-settings).

## <a name="manage-unified-fields"></a>Administrer enhetlige felter

1. Velg **Rediger** på flisen **Enhetlige kundefelter**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Skjermbilde av enhetlige kundefelter":::

1. Se gjennom de kombinerte og ekskluderte feltene, og gjør eventuelle endringer. Legg til eller rediger CustomerID-nøkkelen eller gruppeprofilene i klynger. Hvis du vil ha mer informasjon, kan du se [Samle kundefelter](merge-entities.md).

1. For kunder eller forretningsforbindelser velger du **Neste** for å se gjennom og [oppdatere den samlede profilen og avhengighetene](#run-updates-to-the-unified-profile). Eller velg **Lagre og lukk** og gå tilbake til [Oppdater samlingsinnstillinger](#update-unification-settings) for å gjøre flere endringer.

   For kontakter velger du **Neste** for å behandle semantiske felter. Eller velg **Lagre og lukk** og gå tilbake til [Oppdater samlingsinnstillinger](#update-unification-settings) for å gjøre flere endringer.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Administrer semantiske felter for samlede kontakter

1. Velg **Rediger** på flisen **Semantiske felter**.

1. Hvis du vil endre den semantiske typen for et samlet felt, velger du en ny type. Hvis du vil ha mer informasjon, kan du se [Definer semantiske felter for samlede kontakter](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Velg **Neste** for å administrere forretningsforbindelses- og kontaktrelasjonen, eller velg **Lagre og lukk** og gå tilbake til [Oppdater samlingsinnstillinger](#update-unification-settings) for å gjøre flere innstillinger.

## <a name="manage-contact-and-account-relationships"></a>Administrer relasjoner mellom kontakter og forretningsforbindelser

1. Velg **Rediger** på **Relasjoner**-flisen.

1. Hvis du vil endre relasjonen mellom kontakt og forretningsforbindelse, endrer du følgende informasjon:

   - **Sekundærnøkkel fra kontaktenhet**: Velg attributtet som kobler kontaktenheten til forretningsforbindelsen.
   - **Til forretningsforbindelsesenhet**: Velg forretningsforbindelsesenheten som er knyttet til kontakten.

1. Velg **Neste** for å se gjennom samlingsinnstillingene og [oppdatere den samlede profilen og avhengighetene](#run-updates-to-the-unified-profile), eller velg **Lagre og lukk** og gå tilbake til [Oppdater samlingsinnstillinger](#update-unification-settings) for å gjøre flere endringer.

## <a name="run-matching-conditions"></a>Kjør samsvarende betingelser

Kjør samsvarende betingelser kjører bare deduplisering og samsvarsregler, og oppdaterer enhetene *Deduplication_* og *ConflationMatchPair*.

1. Velg **Kjør bare samsvarende betingelser** på siden **Data** > **Samle**.

   Flisene **Duplikatoppføringer** og **Samsvarende betingelser** viser statusen **I kø** eller **Oppdaterer**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Når den samsvarende prosessen er fullført, velger du **Rediger** på flisen **Samsvarende betingelser**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Beskjært skjermbilde av nøkkelmåledataene på Samsvar-siden med tall og detaljer.":::

1. Hvis du vil gjøre endringer, kan du se [Administrer dedupliseringsregler](#manage-deduplication-rules) eller [Administrer samsvarsregler](#manage-match-rules).

1. Kjør samsvarsprosessen på nytt, eller [kjør oppdateringer for profilen](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Kjør oppdateringer for den samlede profilen

- For å kjøre samsvarende betingelser og oppdatere enheten for samlet profil *uten* at det påvirker avhengigheter (for eksempel kundekort, suppleringer, segmenter eller mål), velger du **Samle kundeprofiler**. For forretningsforbindelser velger du **Samle forretningsforbindelser** > **Samle profiler**. For kontakter velger du **Samle kontakter (forhåndsversjon)** > **Samle profiler**. Avhengige prosesser kjøres ikke, men oppdateres som [definert i oppdateringsplanen](schedule-refresh.md).
- For å kjøre samsvarende betingelser, oppdatere den samlede profilen og kjøre alle avhengigheter velger du **Samle kundeprofiler og avhengigheter**. Alle prosesser kjører på nytt automatisk. Når det gjelder forretningsforbindelser og kontakter, velger du **Samle forretningsforbindelser** > **Samle profiler og avhengigheter**. Samsvarende betingelser kjører for både forretningsforbindelser og kontakter, slik at både samlede profiler og alle andre avhengigheter kjøres.

Alle fliser unntatt **Kildefelter** viser **I kø** eller **Oppdaterer**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Resultatet av et vellykket kjøring vises på **Samle**-siden som viser antall samlede profiler.
