---
title: Bruke datakildene til å ta inn data
description: Lær hvordan du importerer data fra ulike kilder.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 355d52eabde90e0764817cf479821264ebb2e5eb
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800478"
---
# <a name="data-sources-overview"></a>Oversikt over datakilder



Dynamics 365 Customer Insights kobler til data fra en rekke kilder. Tilkobling til en datakilde kalles ofte *datainntak*. Når du har integrert dataene, kan du [samle](data-unification.md) og utføre handlinger på dataene.

## <a name="add-a-data-source"></a>Legg til en datakilde

Se de detaljerte artiklene om hvordan du legger til datakilde, avhengig av alternativet du velger.

Du kan legge til følgende datakilder:

- [Gjennom en rekke Power Query-kontakter](connect-power-query.md)
- [Fra en mappe i Common Data Model](connect-common-data-model.md)
- [Fra din egen Microsoft Dataverse-datasjø](connect-dataverse-managed-lake.md)
- [Fra en Azure Synapse Analytics-database](connect-synapse.md)

## <a name="add-data-from-on-premises-data-sources"></a>Legge til data fra lokale datakilder

Inntak av data fra lokale datakilder støttes basert på Microsoft Power Platform-dataflyter. Du kan aktivere dataflyter i Customer Insights ved [å angi Microsoft Dataverse URL-adressen for miljøet](create-environment.md) når du konfigurerer miljøet.

Datakilder som opprettes etter at et miljø er knyttet til et Dataverse-miljø med Customer Insights, bruker [Power Platform dataflyter](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) som standard. Dataflyter støtter tilkobling på stedet ved hjelp av datagatewayen. Du kan fjerne og opprette datakilder som eksisterte før et Dataverse miljø ble knyttet til, [ved å bruke lokale datagatewayer](/data-integration/gateway/service-gateway-app).

Datagatewayer fra et eksisterende Power BI- eller Power Apps-miljø vil være synlige og kan brukes på nytt i Customer Insights. Datakildesiden viser koblinger for å gå til Microsoft Power Platform-miljøet der du kan vise og konfigurere lokale datagatewayer.

> [!IMPORTANT]
> Kontroller at gatewayene er oppdatert til nyeste versjon. Du kan installere en oppdatering og konfigurere en gateway på nytt fra en ledetekst som vises på gateway-skjermen direkte, eller [laste ned den nyeste versjonen](https://powerapps.microsoft.com/downloads/). Hvis du ikke bruker den nyeste gateway-versjonen, mislykkes dataflytoppdateringen med feilmeldinger som **Nøkkelordet støttes ikke: konfigurasjonsegenskaper. Parameternavn: nøkkelord**.

## <a name="review-ingested-data"></a>Se gjennom integrerte data
Hvis miljøet inneholder Power Platform-dataflyter, viser **Datakilder**-siden tre deler: 
- **Delt**: Datakilder som kan administreres av alle Customer Insights-administratorer. Power BI-dataflyter, din egen lagringskonto og tilknytning til en Dataverse-administrert data lake er eksempler på delte datakilder.
- **Administrert av meg**: Power Platform-dataflyter opprettet og kan bare administreres av deg. Andre Customer Insights-administratorer kan bare vise disse dataflytene, men ikke redigere, oppdatere eller slette dem.
- **Administrert av andre**: Power Platform-dataflyter som er opprettet av andre administratorer. Du kan bare vise dem. Den viser eieren av dataflyten for å få hjelp.
> [!NOTE]
> Alle enheter kan vises og brukes av andre brukere. Brukerkontekstalitet gjelder bare for datakildene og ikke for enhetene som er resultat av disse dataflytene.

Hvis ingen Power Platform-dataflyter brukes, vises ingen grupper eller deler. **Datakilder**-siden inneholder bare en liste over alle datakilder.

Du ser navnet på hver integrerte datakilde, statusen og siste gang dataene ble oppdatert for kilden. Du kan sortere listen over datakilder etter hver kolonne.

> [!div class="mx-imgBorder"]
> ![Tillagt datakilde.](media/configure-data-datasource-added.png "Tillagt datakilde")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan ta tid å laste inn data. Etter en vellykket oppdatering kan de innhentede dataene gjennomgås fra siden **Enheter**. Hvis du vil ha mer informasjon, se [Enheter](entities.md).

## <a name="refresh-a-data-source"></a>Oppdatere en datakilde

Datakilder kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov. 

Gå til **Administrasjon** > **System** > [**Plan**](system.md#schedule-tab) for å konfigurere planlagte oppdateringer av alle datakilder som er tatt inn.

Følg denne fremgangsmåten for å oppdatere en datakilde ved behov:

1. Gå til **Data** > **Datakilder**.

2. Velg den loddrette ellipsen (&vellip;) ved siden av datakildene du vil oppdatere, og velg **Oppdater** fra rullegardinlisten.

3. Datakilden utløses nå for manuell oppdatering. Oppdatering av en datakilde vil oppdatere både enhetsskjemaet og dataene for alle enhetene som er angitt i datakilden.

4. Velg **Stopp oppdatering** hvis du vil avbryte en eksisterende oppdatering, og datakilden tilbakestilles til den siste oppdateringsstatusen.

## <a name="delete-a-data-source"></a>Slette en datakilde

1. Gå til **Data** > **Datakilder**.

2. Velg den loddrette ellipsen (&vellip;) ved siden av datakildene du vil fjerne, og velg **Slett** fra rullegardinmenyen.

3. Bekreft slettingen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
