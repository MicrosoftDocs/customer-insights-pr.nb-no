---
title: Bruke datakildene til å ta inn data
description: Lær hvordan du importerer data fra ulike kilder.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643965"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="ba51e-103">Oversikt over datakilder</span><span class="sxs-lookup"><span data-stu-id="ba51e-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ba51e-104">Funksjonen for målgruppeinnsikt i Dynamics 365 Customer Insights kobler til data fra et bredt sett med kilder.</span><span class="sxs-lookup"><span data-stu-id="ba51e-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="ba51e-105">Tilkobling til en datakilde kalles ofte *datainntak*.</span><span class="sxs-lookup"><span data-stu-id="ba51e-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="ba51e-106">Når du har integrert dataene, kan du [samle](data-unification.md) og utføre handlinger på dataene.</span><span class="sxs-lookup"><span data-stu-id="ba51e-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="ba51e-107">Legg til en datakilde</span><span class="sxs-lookup"><span data-stu-id="ba51e-107">Add a data source</span></span>

<span data-ttu-id="ba51e-108">Se i de detaljerte artiklene om hvordan du legger til en datakilde, avhengig av hvilket alternativ du velger.</span><span class="sxs-lookup"><span data-stu-id="ba51e-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="ba51e-109">Du kan legge til en datakilde på tre hovedmåter:</span><span class="sxs-lookup"><span data-stu-id="ba51e-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="ba51e-110">Gjennom dusinvis av Power Query-koblinger</span><span class="sxs-lookup"><span data-stu-id="ba51e-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="ba51e-111">Fra en mappe i Common Data Model</span><span class="sxs-lookup"><span data-stu-id="ba51e-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="ba51e-112">Fra din egen Common Data Service-datasjø</span><span class="sxs-lookup"><span data-stu-id="ba51e-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="ba51e-113">Du kan ikke legge til data fra lokale datakilder ennå.</span><span class="sxs-lookup"><span data-stu-id="ba51e-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="ba51e-114">Se gjennom integrerte data</span><span class="sxs-lookup"><span data-stu-id="ba51e-114">Review ingested data</span></span>

<span data-ttu-id="ba51e-115">Du ser navnet på hver integrerte datakilde, statusen og siste gang dataene ble oppdatert for kilden.</span><span class="sxs-lookup"><span data-stu-id="ba51e-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="ba51e-116">Du kan sortere listen over datakilder etter hver kolonne.</span><span class="sxs-lookup"><span data-stu-id="ba51e-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba51e-117">![Tillagt datakilde](media/configure-data-datasource-added.png "Tillagt datakilde")</span><span class="sxs-lookup"><span data-stu-id="ba51e-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="ba51e-118">Status</span><span class="sxs-lookup"><span data-stu-id="ba51e-118">Status</span></span>  |<span data-ttu-id="ba51e-119">Beskrivelse</span><span class="sxs-lookup"><span data-stu-id="ba51e-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="ba51e-120">Vellykket</span><span class="sxs-lookup"><span data-stu-id="ba51e-120">Successful</span></span>   |<span data-ttu-id="ba51e-121">Datakilden ble tatt inn hvis et klokkeslett er nevnt i **Oppdatert**-kolonnen.</span><span class="sxs-lookup"><span data-stu-id="ba51e-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="ba51e-122">Ikke startet</span><span class="sxs-lookup"><span data-stu-id="ba51e-122">Not started</span></span>   |<span data-ttu-id="ba51e-123">Datakilden har ingen data som er tatt inn ennå, eller den er fremdeles i utkastmodus.</span><span class="sxs-lookup"><span data-stu-id="ba51e-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="ba51e-124">Oppdaterer</span><span class="sxs-lookup"><span data-stu-id="ba51e-124">Refreshing</span></span>    |<span data-ttu-id="ba51e-125">Datainntak pågår.</span><span class="sxs-lookup"><span data-stu-id="ba51e-125">Data ingestion is in progress.</span></span> <span data-ttu-id="ba51e-126">Du kan avbryte denne operasjonen ved å velge **Stopp oppdatering** i kolonnen **Handlinger**.</span><span class="sxs-lookup"><span data-stu-id="ba51e-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="ba51e-127">Hvis du stopper oppdateringen av en datakilde, blir den tilbakestilt til siste oppdateringstilstand.</span><span class="sxs-lookup"><span data-stu-id="ba51e-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="ba51e-128">Mislyktes</span><span class="sxs-lookup"><span data-stu-id="ba51e-128">Failed</span></span>     |<span data-ttu-id="ba51e-129">Det oppstod en feil i datainnhentingen.</span><span class="sxs-lookup"><span data-stu-id="ba51e-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="ba51e-130">Velg **Oppdater status** for å vise flere detaljer om oppdateringsstatusen, inkludert informasjon om feil og prosessoppdateringer nedstrøms.</span><span class="sxs-lookup"><span data-stu-id="ba51e-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="ba51e-131">Datainnlasting kan ta litt tid.</span><span class="sxs-lookup"><span data-stu-id="ba51e-131">Loading data can take some time.</span></span> <span data-ttu-id="ba51e-132">Etter en vellykket oppdatering kan de innhentede dataene gjennomgås fra siden **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="ba51e-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="ba51e-133">Hvis du vil ha mer informasjon, se [Enheter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="ba51e-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="ba51e-134">Oppdatere en datakilde</span><span class="sxs-lookup"><span data-stu-id="ba51e-134">Refresh a data source</span></span>

<span data-ttu-id="ba51e-135">Datakilder kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov.</span><span class="sxs-lookup"><span data-stu-id="ba51e-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="ba51e-136">Gå til **Administrasjon** > **System** > [**Plan**](system.md#schedule-tab) for å konfigurere planlagte oppdateringer av alle datakilder som er tatt inn.</span><span class="sxs-lookup"><span data-stu-id="ba51e-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="ba51e-137">Følg denne fremgangsmåten for å oppdatere en datakilde ved behov:</span><span class="sxs-lookup"><span data-stu-id="ba51e-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="ba51e-138">I Målgruppeinnsikt går du til **Data** > **Datakilder**</span><span class="sxs-lookup"><span data-stu-id="ba51e-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="ba51e-139">Velg den loddrette ellipsen ved siden av datakilden du vil oppdatere, og velg **Oppdater** fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="ba51e-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="ba51e-140">Datakilden utløses nå for manuell oppdatering.</span><span class="sxs-lookup"><span data-stu-id="ba51e-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="ba51e-141">Når du oppdaterer en datakilde, oppdateres både enhetsskjemaet og dataene for alle enhetene som er angitt i datakilden.</span><span class="sxs-lookup"><span data-stu-id="ba51e-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="ba51e-142">Velg **Stopp oppdatering** hvis du vil avbryte en eksisterende oppdatering, og datakilden tilbakestilles til den siste oppdateringsstatusen.</span><span class="sxs-lookup"><span data-stu-id="ba51e-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="ba51e-143">Slette en datakilde</span><span class="sxs-lookup"><span data-stu-id="ba51e-143">Delete a data source</span></span>

1. <span data-ttu-id="ba51e-144">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="ba51e-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ba51e-145">Merk den loddrette ellipsen ved siden av datakilden du vil fjerne, og velg **Slett** fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="ba51e-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="ba51e-146">Bekreft slettingen.</span><span class="sxs-lookup"><span data-stu-id="ba51e-146">Confirm your deletion.</span></span>
