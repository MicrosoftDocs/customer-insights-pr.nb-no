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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085542"
---
# <a name="data-sources-overview"></a><span data-ttu-id="50781-103">Oversikt over datakilder</span><span class="sxs-lookup"><span data-stu-id="50781-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="50781-104">Funksjonen for målgruppeinnsikt i Dynamics 365 Customer Insights kobler til data fra et bredt sett med kilder.</span><span class="sxs-lookup"><span data-stu-id="50781-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="50781-105">Tilkobling til en datakilde kalles ofte *datainntak*.</span><span class="sxs-lookup"><span data-stu-id="50781-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="50781-106">Når du har integrert dataene, kan du [samle](data-unification.md) og utføre handlinger på dataene.</span><span class="sxs-lookup"><span data-stu-id="50781-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="50781-107">Legg til en datakilde</span><span class="sxs-lookup"><span data-stu-id="50781-107">Add a data source</span></span>

<span data-ttu-id="50781-108">Se i de detaljerte artiklene om hvordan du legger til en datakilde, avhengig av hvilket alternativ du velger.</span><span class="sxs-lookup"><span data-stu-id="50781-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="50781-109">Du kan legge til en datakilde på tre hovedmåter:</span><span class="sxs-lookup"><span data-stu-id="50781-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="50781-110">Gjennom dusinvis av Power Query-koblinger</span><span class="sxs-lookup"><span data-stu-id="50781-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="50781-111">Fra en mappe i Common Data Model</span><span class="sxs-lookup"><span data-stu-id="50781-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="50781-112">Fra din egen Common Data Service-datasjø</span><span class="sxs-lookup"><span data-stu-id="50781-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="50781-113">Legge til data fra lokale datakilder</span><span class="sxs-lookup"><span data-stu-id="50781-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="50781-114">Inntak av data fra lokale datakilder i Målgruppeinnsikt støttes basert på Power Platform-dataflyter.</span><span class="sxs-lookup"><span data-stu-id="50781-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="50781-115">Dataflyter kan aktiveres i Customer Insights ved å [angi Microsoft Dataverse-URL-adressen for miljøet](manage-environments.md#create-an-environment-in-an-existing-organization) under konfigurasjon av miljøet.</span><span class="sxs-lookup"><span data-stu-id="50781-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="50781-116">Datakilder som opprettes etter at et miljø er knyttet til et Dataverse-miljø med Customer Insights, bruker [Power Platform-dataflyter](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) som standard.</span><span class="sxs-lookup"><span data-stu-id="50781-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="50781-117">Dataflyter støtter tilkobling på stedet ved hjelp av datagatewayen.</span><span class="sxs-lookup"><span data-stu-id="50781-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="50781-118">Fjern og opprett på nytt datakilder som eksisterte før et Dataverse-miljø ble knyttet til, for å [bruke lokale datagatewayer](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="50781-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="50781-119">Datagatewayer fra et eksisterende Power BI- eller Power Apps-miljø vil være synlige og kan brukes på nytt i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="50781-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="50781-120">Datakildesiden viser koblinger til å gå til Power Platform-miljøet der du kan vise og konfigurere lokale datagatewayer.</span><span class="sxs-lookup"><span data-stu-id="50781-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="50781-121">Se gjennom integrerte data</span><span class="sxs-lookup"><span data-stu-id="50781-121">Review ingested data</span></span>

<span data-ttu-id="50781-122">Du ser navnet på hver integrerte datakilde, statusen og siste gang dataene ble oppdatert for kilden.</span><span class="sxs-lookup"><span data-stu-id="50781-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="50781-123">Du kan sortere listen over datakilder etter hver kolonne.</span><span class="sxs-lookup"><span data-stu-id="50781-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="50781-124">![Tillagt datakilde](media/configure-data-datasource-added.png "Tillagt datakilde")</span><span class="sxs-lookup"><span data-stu-id="50781-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="50781-125">Status</span><span class="sxs-lookup"><span data-stu-id="50781-125">Status</span></span>  |<span data-ttu-id="50781-126">Beskrivelse</span><span class="sxs-lookup"><span data-stu-id="50781-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="50781-127">Vellykket</span><span class="sxs-lookup"><span data-stu-id="50781-127">Successful</span></span>   |<span data-ttu-id="50781-128">Datakilden ble tatt inn hvis et klokkeslett er nevnt i **Oppdatert**-kolonnen.</span><span class="sxs-lookup"><span data-stu-id="50781-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="50781-129">Ikke startet</span><span class="sxs-lookup"><span data-stu-id="50781-129">Not started</span></span>   |<span data-ttu-id="50781-130">Datakilden har ingen data som er tatt inn ennå, eller den er fremdeles i utkastmodus.</span><span class="sxs-lookup"><span data-stu-id="50781-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="50781-131">Oppdaterer</span><span class="sxs-lookup"><span data-stu-id="50781-131">Refreshing</span></span>    |<span data-ttu-id="50781-132">Datainntak pågår.</span><span class="sxs-lookup"><span data-stu-id="50781-132">Data ingestion is in progress.</span></span> <span data-ttu-id="50781-133">Du kan avbryte denne operasjonen ved å velge **Stopp oppdatering** i kolonnen **Handlinger**.</span><span class="sxs-lookup"><span data-stu-id="50781-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="50781-134">Hvis du stopper oppdateringen av en datakilde, blir den tilbakestilt til siste oppdateringstilstand.</span><span class="sxs-lookup"><span data-stu-id="50781-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="50781-135">Mislyktes</span><span class="sxs-lookup"><span data-stu-id="50781-135">Failed</span></span>     |<span data-ttu-id="50781-136">Det oppstod en feil i datainnhentingen.</span><span class="sxs-lookup"><span data-stu-id="50781-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="50781-137">Velg verdien i **Status**-kolonnen for en datakilde for å se gjennom flere detaljer.</span><span class="sxs-lookup"><span data-stu-id="50781-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="50781-138">Utvid **Datakilder** i ruten **Fremdriftsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="50781-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="50781-139">Velg **Se detaljer** for mer informasjon om oppdateringsstatusen, inkludert informasjon om feil og prosessoppdateringer nedstrøms.</span><span class="sxs-lookup"><span data-stu-id="50781-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="50781-140">Datainnlasting kan ta litt tid.</span><span class="sxs-lookup"><span data-stu-id="50781-140">Loading data can take some time.</span></span> <span data-ttu-id="50781-141">Etter en vellykket oppdatering kan de innhentede dataene gjennomgås fra siden **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="50781-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="50781-142">Hvis du vil ha mer informasjon, se [Enheter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="50781-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="50781-143">Oppdatere en datakilde</span><span class="sxs-lookup"><span data-stu-id="50781-143">Refresh a data source</span></span>

<span data-ttu-id="50781-144">Datakilder kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov.</span><span class="sxs-lookup"><span data-stu-id="50781-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="50781-145">Gå til **Administrasjon** > **System** > [**Plan**](system.md#schedule-tab) for å konfigurere planlagte oppdateringer av alle datakilder som er tatt inn.</span><span class="sxs-lookup"><span data-stu-id="50781-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="50781-146">Følg denne fremgangsmåten for å oppdatere en datakilde ved behov:</span><span class="sxs-lookup"><span data-stu-id="50781-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="50781-147">I Målgruppeinnsikt går du til **Data** > **Datakilder**</span><span class="sxs-lookup"><span data-stu-id="50781-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="50781-148">Velg den loddrette ellipsen ved siden av datakilden du vil oppdatere, og velg **Oppdater** fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="50781-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="50781-149">Datakilden utløses nå for manuell oppdatering.</span><span class="sxs-lookup"><span data-stu-id="50781-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="50781-150">Oppdatering av en datakilde vil oppdatere både enhetsskjemaet og dataene for alle enhetene som er angitt i datakilden.</span><span class="sxs-lookup"><span data-stu-id="50781-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="50781-151">Velg **Stopp oppdatering** hvis du vil avbryte en eksisterende oppdatering, og datakilden tilbakestilles til den siste oppdateringsstatusen.</span><span class="sxs-lookup"><span data-stu-id="50781-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="50781-152">Slette en datakilde</span><span class="sxs-lookup"><span data-stu-id="50781-152">Delete a data source</span></span>

1. <span data-ttu-id="50781-153">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="50781-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="50781-154">Merk den loddrette ellipsen ved siden av datakilden du vil fjerne, og velg **Slett** fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="50781-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="50781-155">Bekreft slettingen.</span><span class="sxs-lookup"><span data-stu-id="50781-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
