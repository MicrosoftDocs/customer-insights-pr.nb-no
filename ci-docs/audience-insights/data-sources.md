---
title: Bruke datakildene til å ta inn data
description: Lær hvordan du importerer data fra ulike kilder.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595959"
---
# <a name="data-sources-overview"></a><span data-ttu-id="b28bd-103">Oversikt over datakilder</span><span class="sxs-lookup"><span data-stu-id="b28bd-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b28bd-104">Funksjonen for målgruppeinnsikt i Dynamics 365 Customer Insights kobler til data fra et bredt sett med kilder.</span><span class="sxs-lookup"><span data-stu-id="b28bd-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="b28bd-105">Tilkobling til en datakilde kalles ofte *datainntak*.</span><span class="sxs-lookup"><span data-stu-id="b28bd-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="b28bd-106">Når du har integrert dataene, kan du [samle](data-unification.md) og utføre handlinger på dataene.</span><span class="sxs-lookup"><span data-stu-id="b28bd-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="b28bd-107">Legg til en datakilde</span><span class="sxs-lookup"><span data-stu-id="b28bd-107">Add a data source</span></span>

<span data-ttu-id="b28bd-108">Se i de detaljerte artiklene om hvordan du legger til en datakilde, avhengig av hvilket alternativ du velger.</span><span class="sxs-lookup"><span data-stu-id="b28bd-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="b28bd-109">Du kan legge til en datakilde på tre hovedmåter:</span><span class="sxs-lookup"><span data-stu-id="b28bd-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="b28bd-110">Gjennom dusinvis av Power Query-koblinger</span><span class="sxs-lookup"><span data-stu-id="b28bd-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="b28bd-111">Fra en mappe i Common Data Model</span><span class="sxs-lookup"><span data-stu-id="b28bd-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="b28bd-112">Fra din egen Common Data Service-datasjø</span><span class="sxs-lookup"><span data-stu-id="b28bd-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="b28bd-113">Du kan ikke legge til data fra lokale datakilder ennå.</span><span class="sxs-lookup"><span data-stu-id="b28bd-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="b28bd-114">Se gjennom integrerte data</span><span class="sxs-lookup"><span data-stu-id="b28bd-114">Review ingested data</span></span>

<span data-ttu-id="b28bd-115">Du ser navnet på hver integrerte datakilde, statusen og siste gang dataene ble oppdatert for kilden.</span><span class="sxs-lookup"><span data-stu-id="b28bd-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="b28bd-116">Du kan sortere listen over datakilder etter hver kolonne.</span><span class="sxs-lookup"><span data-stu-id="b28bd-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b28bd-117">![Tillagt datakilde](media/configure-data-datasource-added.png "Tillagt datakilde")</span><span class="sxs-lookup"><span data-stu-id="b28bd-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="b28bd-118">Status</span><span class="sxs-lookup"><span data-stu-id="b28bd-118">Status</span></span>  |<span data-ttu-id="b28bd-119">Beskrivelse</span><span class="sxs-lookup"><span data-stu-id="b28bd-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b28bd-120">Vellykket</span><span class="sxs-lookup"><span data-stu-id="b28bd-120">Successful</span></span>   |<span data-ttu-id="b28bd-121">Datakilden ble tatt inn hvis et klokkeslett er nevnt i **Oppdatert**-kolonnen.</span><span class="sxs-lookup"><span data-stu-id="b28bd-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="b28bd-122">Ikke startet</span><span class="sxs-lookup"><span data-stu-id="b28bd-122">Not started</span></span>   |<span data-ttu-id="b28bd-123">Datakilden har ingen data som er tatt inn ennå, eller den er fremdeles i utkastmodus.</span><span class="sxs-lookup"><span data-stu-id="b28bd-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="b28bd-124">Oppdaterer</span><span class="sxs-lookup"><span data-stu-id="b28bd-124">Refreshing</span></span>    |<span data-ttu-id="b28bd-125">Datainntak pågår.</span><span class="sxs-lookup"><span data-stu-id="b28bd-125">Data ingestion is in progress.</span></span> <span data-ttu-id="b28bd-126">Du kan avbryte denne operasjonen ved å velge **Stopp oppdatering** i kolonnen **Handlinger**.</span><span class="sxs-lookup"><span data-stu-id="b28bd-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="b28bd-127">Hvis du stopper oppdateringen av en datakilde, blir den tilbakestilt til siste oppdateringstilstand.</span><span class="sxs-lookup"><span data-stu-id="b28bd-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="b28bd-128">Mislyktes</span><span class="sxs-lookup"><span data-stu-id="b28bd-128">Failed</span></span>     |<span data-ttu-id="b28bd-129">Det oppstod en feil i datainnhentingen.</span><span class="sxs-lookup"><span data-stu-id="b28bd-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="b28bd-130">Velg verdien i **Status**-kolonnen for en datakilde for å se gjennom flere detaljer.</span><span class="sxs-lookup"><span data-stu-id="b28bd-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="b28bd-131">Utvid **Datakilder** i ruten **Fremdriftsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="b28bd-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="b28bd-132">Velg **Se detaljer** for mer informasjon om oppdateringsstatusen, inkludert informasjon om feil og prosessoppdateringer nedstrøms.</span><span class="sxs-lookup"><span data-stu-id="b28bd-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="b28bd-133">Datainnlasting kan ta litt tid.</span><span class="sxs-lookup"><span data-stu-id="b28bd-133">Loading data can take some time.</span></span> <span data-ttu-id="b28bd-134">Etter en vellykket oppdatering kan de innhentede dataene gjennomgås fra siden **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="b28bd-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="b28bd-135">Hvis du vil ha mer informasjon, se [Enheter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="b28bd-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="b28bd-136">Oppdatere en datakilde</span><span class="sxs-lookup"><span data-stu-id="b28bd-136">Refresh a data source</span></span>

<span data-ttu-id="b28bd-137">Datakilder kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov.</span><span class="sxs-lookup"><span data-stu-id="b28bd-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="b28bd-138">Gå til **Administrasjon** > **System** > [**Plan**](system.md#schedule-tab) for å konfigurere planlagte oppdateringer av alle datakilder som er tatt inn.</span><span class="sxs-lookup"><span data-stu-id="b28bd-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="b28bd-139">Følg denne fremgangsmåten for å oppdatere en datakilde ved behov:</span><span class="sxs-lookup"><span data-stu-id="b28bd-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="b28bd-140">I Målgruppeinnsikt går du til **Data** > **Datakilder**</span><span class="sxs-lookup"><span data-stu-id="b28bd-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="b28bd-141">Velg den loddrette ellipsen ved siden av datakilden du vil oppdatere, og velg **Oppdater** fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="b28bd-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="b28bd-142">Datakilden utløses nå for manuell oppdatering.</span><span class="sxs-lookup"><span data-stu-id="b28bd-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="b28bd-143">Når du oppdaterer en datakilde, oppdateres både enhetsskjemaet og dataene for alle enhetene som er angitt i datakilden.</span><span class="sxs-lookup"><span data-stu-id="b28bd-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="b28bd-144">Velg **Stopp oppdatering** hvis du vil avbryte en eksisterende oppdatering, og datakilden tilbakestilles til den siste oppdateringsstatusen.</span><span class="sxs-lookup"><span data-stu-id="b28bd-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="b28bd-145">Slette en datakilde</span><span class="sxs-lookup"><span data-stu-id="b28bd-145">Delete a data source</span></span>

1. <span data-ttu-id="b28bd-146">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="b28bd-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b28bd-147">Merk den loddrette ellipsen ved siden av datakilden du vil fjerne, og velg **Slett** fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="b28bd-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="b28bd-148">Bekreft slettingen.</span><span class="sxs-lookup"><span data-stu-id="b28bd-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]