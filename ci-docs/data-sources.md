---
title: Oversikt over datakilder
description: Lær hvordan du importerer eller innhenter data fra ulike kilder.
ms.date: 09/29/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610064"
---
# <a name="data-sources-overview"></a>Oversikt over datakilder

Dynamics 365 Customer Insights gir tilkoblinger for å hente data fra en rekke kilder. Tilkobling til en datakilde kalles ofte *datainntak*. Når dataene er inntatt, kan du [samle](data-unification.md), generere innsikt og aktivere dataene for å bygge tilpassede opplevelser.

## <a name="add-or-edit-data-sources"></a>Legg til eller rediger datakilder

Du kan legge ved eller importere datakilder til Customer Insights. Koblingene nedenfor inneholder instruksjoner om hvordan du legger til og redigerer datakilder.

**Legg ved en datakilde**

Hvis du har data klargjort i en av Microsofts Azure-datatjenester, kan Customer Insights enkelt koble til datakilde uten å måtte legge inn dataene på nytt. Velg ett av følgende alternativer:
- [Azure Data Lake Storage (csv- eller parquet-filer i en Common Data Model-mappe)](connect-common-data-model.md)
- [Azure Synapse Analytics (sjødatabaser)](connect-synapse.md)
- [Microsoft Dataverse-datasjø](connect-dataverse-managed-lake.md)

**Importer og transformer**

Hvis du bruker lokale datakilder, Microsoft- eller tredjepartsdata, importerer og transformerer du dataene ved hjelp av Power Query-koblinger.
- [Power Query-koblinger](connect-power-query.md)

## <a name="review-data-sources"></a>Gå gjennom datakilder

Hvis miljøet er konfigurert til å bruke Customer Insights-lagring og du bruker lokale datakilder, bruker du Power Platform-dataflyter. Med Power Platform-dataflyter kan du vise delte datakilder og datakilder som andre administrerer. Siden **Datakilder** viser datakildene i tre deler:
- **Delt**: Datakilder som kan administreres av alle Customer Insights-administratorer. Power Platform-dataflyter, din egen lagringskonto og tilknytning til en Dataverse-administrert data lake er eksempler på delte datakilder.
- **Administrert av meg**: Power Platform-dataflyter opprettet og administrert bare av deg. Andre Customer Insights-administratorer kan bare vise disse dataflytene, men ikke redigere, oppdatere eller slette dem.
- **Administrert av andre**: Power Platform-dataflyter som er opprettet av andre administratorer. Du kan bare vise dem. Den viser eieren av dataflyten for å få hjelp.
> [!NOTE]
> Alle enheter kan vises og brukes av andre brukere. Datakilder eies av brukeren som opprettet dem, men de resulterende enhetene fra datainntaket kan brukes av hver bruker av Customer Insights.

Hvis miljøet ikke bruker Power Platform-dataflyter, inneholder siden **Datakilder** bare en liste over alle datakildene. Ingen inndelinger vises.

## <a name="manage-existing-data-sources"></a>Administrer eksisterende datakilder

Gå til **Data** > **Datakilder** for å vise navnet på hver innlagte datakilde, dens status og sist gang dataene ble oppdatert for den kilden. Du kan sortere listen over datakilder etter en hvilken som helst kolonne, eller du kan bruke søkefeltet til å finne datakilden du vil administrere.

Velg en datakilde for å vise tilgjengelige handlinger.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Tillagt datakilde.":::

- [**Rediger**](#add-or-edit-data-sources) datakilden for å endre egenskapene.
- [**Oppdater**](#refresh-data-sources) datakilden slik at det inneholder de nyeste dataene.
- [**Suppler**](data-sources-enrichment.md) datakilden før samlingen.
- **Slett** datakilden. En datakilde kan bare slettes hvis dataene ikke brukes i behandlinger, for eksempel for samling, innsikt, aktiveringer eller eksporter.

## <a name="refresh-data-sources"></a>Oppdater datakilder

Datakilder kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov. [Lokale datakilder](connect-power-query.md#add-data-from-on-premises-data-sources) oppdateres på egne tidsplaner, som konfigureres under datainntak. Hvis du vil ha feilsøkingstips, kan du se [Feilsøke problemer med PPDF Power Query-basert datakildeoppdatering](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

For tilknyttede datakilder bruker datainntak de nyeste dataene som er tilgjengelige fra den datakilde.

Gå til **Administrator** > **System** > [**Planlegg**](schedule-refresh.md) for å konfigurere systemplanlagte oppdateringer av de inntatte datakildene.

Slik oppdaterer du en datakilde ved behov:

1. Gå til **Data** > **Datakilder**.

1. Velg datakilden du vil oppdatere, og velg **Oppdater**. Datakilden utløses nå for manuell oppdatering. Oppdatering av en datakilde vil oppdatere både enhetsskjemaet og dataene for alle enhetene som er angitt i datakilden.

1. Velg statusen for å åpne **Fremdriftsdetaljer**-ruten og vise fremdriften. Hvis du vil avbryte jobben, velger du **Avbryt jobb** nederst i ruten.

## <a name="corrupt-data-sources"></a>Skadede datakilder

Data som tas inn, kan ha skadede oppføringer som kan gjøre at datainntaket fullføres med feil eller advarsler.

> [!NOTE]
> Hvis datainntak fullføres med feil, blir påfølgende behandling (for eksempel samling eller aktivitetsopprettelse) som bruker denne datakilden, hoppet over. Hvis inntak fullføres med advarsler, fortsetter påfølgende behandling, men noen av oppføringene blir kanskje ikke tatt med.

Du kan se disse feilene i oppgavedetaljene.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Oppgavedetalj som viser feil som skyldes skadede data.":::

Skadede oppføringer vises i systemopprettede enheter.

### <a name="fix-corrupt-data"></a>Reparer skadede data

1. Du kan vise de skadede dataene, ved å gå til **Data** > **Enheter** og se etter de skadede enhetene i **System**-delen. Navneskjemaet for skadede enheter: DataSourceName_EntityName_corrupt.

1. Velg en skadet enhet og deretter **Data**-fanen.

1. Identifiser de skadede feltene i en oppføring og årsaken.

   :::image type="content" source="media/corruption-reason.png" alt-text="Skadeårsak." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Data** > **Enheter** viser bare en del av de skadede oppføringene. Hvis du vil vise alle skadede oppføringer, eksporterer du filene til en beholder i lagringskontoen ved hjelp av [Customer Insights-eksportprosessen](export-destinations.md). Hvis du brukte din egen lagringskonto, kan du også se i Customer Insights-mappen i lagringskontoen.

1. Reparer de skadede dataene. Når det for eksempel gjelder Azure Data Lake-datakilder, [reparerer du dataene i Data Lake Storage eller oppdaterer datatypene i filen manifest/model.json](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Når det gjelder Power Query-datakilder, reparerer du dataene i kildefilen og [korrigerer datatypen i transformasjonstrinnet](connect-power-query.md#data-type-does-not-match-data) på siden **Power Query – Rediger spørringer**.

Etter den neste oppdateringen av datakilden, blir de korrigerte oppføringene overført til Customer Insights og videre til nedstrømsprosesser.

En fødselsdag-kolonne har for eksempel datatypen angitt som dato. En kundeoppføring har fødselsdag angitt som 01/01/19777. Systemet flagger denne oppføringen som skadet. Endre fødselsdagen i kildesystemet til 1977. Etter en automatisk oppdatering av datakildene, har feltet nå et gyldig format, og oppføringen fjernes fra den skadede enheten.

[!INCLUDE [footer-include](includes/footer-banner.md)]
