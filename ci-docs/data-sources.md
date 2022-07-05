---
title: Oversikt over datakilder
description: Lær hvordan du importerer eller innhenter data fra ulike kilder.
ms.date: 05/18/2022
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
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051465"
---
# <a name="data-sources-overview"></a>Oversikt over datakilder

Dynamics 365 Customer Insights gir tilkoblinger for å hente data fra en rekke kilder. Tilkobling til en datakilde kalles ofte *datainntak*. Når dataene er inntatt, kan du [samle](data-unification.md), generere innsikt og aktivere dataene for å bygge tilpassede opplevelser.

## <a name="add-data-sources"></a>Legg til datakilder

Du kan legge ved eller importere datakilder til Customer Insights. Koblingene nedenfor inneholder instruksjoner om hvordan du legger til datakilder.

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

Gå til **Data** > **Datakilder** for å vise navnet på hver innlagte datakilde, dens status og sist gang dataene ble oppdatert for den kilden. Du kan sortere listen over datakilder etter hver kolonne.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Tillagt datakilde.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan ta tid å laste inn data. Etter en vellykket oppdatering kan de innhentede dataene gjennomgås fra siden **Enheter**. Hvis du vil ha mer informasjon, se [Enheter](entities.md).

## <a name="refresh-data-sources"></a>Oppdater datakilder

Datakilder kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov. [Lokale datakilder](connect-power-query.md#add-data-from-on-premises-data-sources) oppdateres på egne tidsplaner, som konfigureres under datainntak. For tilknyttede datakilder bruker datainntak de nyeste dataene som er tilgjengelige fra den datakilde.

Gå til **Administrator** > **System** > [**Planlegg**](system.md#schedule-tab) for å konfigurere systemplanlagte oppdateringer av de inntatte datakildene.

Følg denne fremgangsmåten for å oppdatere en datakilde ved behov:

1. Gå til **Data** > **Datakilder**.

1. Velg den loddrette ellipsen (&vellip;) ved siden av datakildene du vil oppdatere, og velg **Oppdater** fra rullegardinlisten. Datakilden utløses nå for manuell oppdatering. Oppdatering av en datakilde vil oppdatere både enhetsskjemaet og dataene for alle enhetene som er angitt i datakilden.

1. Velg **Stopp oppdatering** hvis du vil avbryte en eksisterende oppdatering, og datakilden tilbakestilles til den siste oppdateringsstatusen.

## <a name="delete-a-data-source"></a>Slette en datakilde

En datakilde kan bare slettes hvis dataene ikke brukes i behandlinger, for eksempel for samling, innsikt, aktiveringer eller eksporter.

1. Gå til **Data** > **Datakilder**.

2. Velg den loddrette ellipsen (&vellip;) ved siden av datakildene du vil fjerne, og velg **Slett** fra rullegardinmenyen.

3. Bekreft slettingen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
