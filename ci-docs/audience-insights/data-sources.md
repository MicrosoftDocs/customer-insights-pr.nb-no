---
title: Bruke datakildene til å ta inn data
description: Lær hvordan du importerer data fra ulike kilder.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887906"
---
# <a name="data-sources-overview"></a><span data-ttu-id="3ca67-103">Oversikt over datakilder</span><span class="sxs-lookup"><span data-stu-id="3ca67-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3ca67-104">Funksjonen for målgruppeinnsikt i Dynamics 365 Customer Insights kobler til data fra et bredt sett med kilder.</span><span class="sxs-lookup"><span data-stu-id="3ca67-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="3ca67-105">Tilkobling til en datakilde kalles ofte *datainntak*.</span><span class="sxs-lookup"><span data-stu-id="3ca67-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="3ca67-106">Når du har integrert dataene, kan du [samle](data-unification.md) og utføre handlinger på dataene.</span><span class="sxs-lookup"><span data-stu-id="3ca67-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="3ca67-107">Legg til en datakilde</span><span class="sxs-lookup"><span data-stu-id="3ca67-107">Add a data source</span></span>

<span data-ttu-id="3ca67-108">Se i de detaljerte artiklene om hvordan du legger til en datakilde, avhengig av hvilket alternativ du velger.</span><span class="sxs-lookup"><span data-stu-id="3ca67-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="3ca67-109">Du kan legge til en datakilde på tre hovedmåter:</span><span class="sxs-lookup"><span data-stu-id="3ca67-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="3ca67-110">Gjennom dusinvis av Power Query-koblinger</span><span class="sxs-lookup"><span data-stu-id="3ca67-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="3ca67-111">Fra en mappe i Common Data Model</span><span class="sxs-lookup"><span data-stu-id="3ca67-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="3ca67-112">Fra din egen Common Data Service-datasjø</span><span class="sxs-lookup"><span data-stu-id="3ca67-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="3ca67-113">Legge til data fra lokale datakilder</span><span class="sxs-lookup"><span data-stu-id="3ca67-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="3ca67-114">Inntak av data fra lokale datakilder i Målgruppeinnsikt støttes basert på Power Platform-dataflyter.</span><span class="sxs-lookup"><span data-stu-id="3ca67-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="3ca67-115">Dataflyter kan aktiveres i Customer Insights ved å [angi Microsoft Dataverse-URL-adressen for miljøet](manage-environments.md#create-an-environment-in-an-existing-organization) under konfigurasjon av miljøet.</span><span class="sxs-lookup"><span data-stu-id="3ca67-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="3ca67-116">Datakilder som opprettes etter at et miljø er knyttet til et Dataverse-miljø med Customer Insights, bruker [Power Platform-dataflyter](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) som standard.</span><span class="sxs-lookup"><span data-stu-id="3ca67-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="3ca67-117">Dataflyter støtter tilkobling på stedet ved hjelp av datagatewayene.</span><span class="sxs-lookup"><span data-stu-id="3ca67-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="3ca67-118">Fjern og opprett på nytt datakilder som eksisterte før et Dataverse-miljø ble knyttet til, for å bruke lokale datagatewayer.</span><span class="sxs-lookup"><span data-stu-id="3ca67-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="3ca67-119">Datagatewayer fra et eksisterende Power BI- eller Power Apps-miljø vil være synlige og kan brukes på nytt i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3ca67-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="3ca67-120">Datakildesiden viser koblinger til å gå til Power Platform-miljøet der du kan vise og konfigurere lokale datagatewayer.</span><span class="sxs-lookup"><span data-stu-id="3ca67-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Skjermbilde av datakildesiden som viser koblinger som peker til Power Platform-miljøet.":::

## <a name="review-ingested-data"></a><span data-ttu-id="3ca67-122">Se gjennom integrerte data</span><span class="sxs-lookup"><span data-stu-id="3ca67-122">Review ingested data</span></span>

<span data-ttu-id="3ca67-123">Du ser navnet på hver integrerte datakilde, statusen og siste gang dataene ble oppdatert for kilden.</span><span class="sxs-lookup"><span data-stu-id="3ca67-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="3ca67-124">Du kan sortere listen over datakilder etter hver kolonne.</span><span class="sxs-lookup"><span data-stu-id="3ca67-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3ca67-125">![Tillagt datakilde](media/configure-data-datasource-added.png "Tillagt datakilde")</span><span class="sxs-lookup"><span data-stu-id="3ca67-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="3ca67-126">Status</span><span class="sxs-lookup"><span data-stu-id="3ca67-126">Status</span></span>  |<span data-ttu-id="3ca67-127">Beskrivelse</span><span class="sxs-lookup"><span data-stu-id="3ca67-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="3ca67-128">Vellykket</span><span class="sxs-lookup"><span data-stu-id="3ca67-128">Successful</span></span>   |<span data-ttu-id="3ca67-129">Datakilden ble tatt inn hvis et klokkeslett er nevnt i **Oppdatert**-kolonnen.</span><span class="sxs-lookup"><span data-stu-id="3ca67-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="3ca67-130">Ikke startet</span><span class="sxs-lookup"><span data-stu-id="3ca67-130">Not started</span></span>   |<span data-ttu-id="3ca67-131">Datakilden har ingen data som er tatt inn ennå, eller den er fremdeles i utkastmodus.</span><span class="sxs-lookup"><span data-stu-id="3ca67-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="3ca67-132">Oppdaterer</span><span class="sxs-lookup"><span data-stu-id="3ca67-132">Refreshing</span></span>    |<span data-ttu-id="3ca67-133">Datainntak pågår.</span><span class="sxs-lookup"><span data-stu-id="3ca67-133">Data ingestion is in progress.</span></span> <span data-ttu-id="3ca67-134">Du kan avbryte denne operasjonen ved å velge **Stopp oppdatering** i kolonnen **Handlinger**.</span><span class="sxs-lookup"><span data-stu-id="3ca67-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="3ca67-135">Hvis du stopper oppdateringen av en datakilde, blir den tilbakestilt til siste oppdateringstilstand.</span><span class="sxs-lookup"><span data-stu-id="3ca67-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="3ca67-136">Mislyktes</span><span class="sxs-lookup"><span data-stu-id="3ca67-136">Failed</span></span>     |<span data-ttu-id="3ca67-137">Det oppstod en feil i datainnhentingen.</span><span class="sxs-lookup"><span data-stu-id="3ca67-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="3ca67-138">Velg verdien i **Status**-kolonnen for en datakilde for å se gjennom flere detaljer.</span><span class="sxs-lookup"><span data-stu-id="3ca67-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="3ca67-139">Utvid **Datakilder** i ruten **Fremdriftsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="3ca67-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="3ca67-140">Velg **Se detaljer** for mer informasjon om oppdateringsstatusen, inkludert informasjon om feil og prosessoppdateringer nedstrøms.</span><span class="sxs-lookup"><span data-stu-id="3ca67-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="3ca67-141">Datainnlasting kan ta litt tid.</span><span class="sxs-lookup"><span data-stu-id="3ca67-141">Loading data can take some time.</span></span> <span data-ttu-id="3ca67-142">Etter en vellykket oppdatering kan de innhentede dataene gjennomgås fra siden **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="3ca67-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="3ca67-143">Hvis du vil ha mer informasjon, se [Enheter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="3ca67-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="3ca67-144">Oppdatere en datakilde</span><span class="sxs-lookup"><span data-stu-id="3ca67-144">Refresh a data source</span></span>

<span data-ttu-id="3ca67-145">Datakilder kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov.</span><span class="sxs-lookup"><span data-stu-id="3ca67-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="3ca67-146">Gå til **Administrasjon** > **System** > [**Plan**](system.md#schedule-tab) for å konfigurere planlagte oppdateringer av alle datakilder som er tatt inn.</span><span class="sxs-lookup"><span data-stu-id="3ca67-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="3ca67-147">Følg denne fremgangsmåten for å oppdatere en datakilde ved behov:</span><span class="sxs-lookup"><span data-stu-id="3ca67-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="3ca67-148">I Målgruppeinnsikt går du til **Data** > **Datakilder**</span><span class="sxs-lookup"><span data-stu-id="3ca67-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="3ca67-149">Velg den loddrette ellipsen ved siden av datakilden du vil oppdatere, og velg **Oppdater** fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="3ca67-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="3ca67-150">Datakilden utløses nå for manuell oppdatering.</span><span class="sxs-lookup"><span data-stu-id="3ca67-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="3ca67-151">Oppdatering av en datakilde vil oppdatere både enhetsskjemaet og dataene for alle enhetene som er angitt i datakilden.</span><span class="sxs-lookup"><span data-stu-id="3ca67-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="3ca67-152">Velg **Stopp oppdatering** hvis du vil avbryte en eksisterende oppdatering, og datakilden tilbakestilles til den siste oppdateringsstatusen.</span><span class="sxs-lookup"><span data-stu-id="3ca67-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="3ca67-153">Slette en datakilde</span><span class="sxs-lookup"><span data-stu-id="3ca67-153">Delete a data source</span></span>

1. <span data-ttu-id="3ca67-154">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="3ca67-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="3ca67-155">Merk den loddrette ellipsen ved siden av datakilden du vil fjerne, og velg **Slett** fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="3ca67-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="3ca67-156">Bekreft slettingen.</span><span class="sxs-lookup"><span data-stu-id="3ca67-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
