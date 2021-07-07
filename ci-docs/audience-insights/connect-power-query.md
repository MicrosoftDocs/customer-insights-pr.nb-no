---
title: Ta inn data via en Power Query-kobling
description: Koblinger til datakilder basert på Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305903"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="4482c-103">Koble til et Power Query-datakilde</span><span class="sxs-lookup"><span data-stu-id="4482c-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="4482c-104">Power Query tilbyr et bredt sett med koblinger for å hente data.</span><span class="sxs-lookup"><span data-stu-id="4482c-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="4482c-105">De fleste av disse koblingene støttes av Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4482c-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="4482c-106">Når du legger til datakilder basert på Power Query-koblingene, følges generelt fremgangsmåtene som er beskrevet i neste del.</span><span class="sxs-lookup"><span data-stu-id="4482c-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="4482c-107">Avhengig av hvilken kontakt du bruker, er det imidlertid nødvendig med forskjellig informasjon.</span><span class="sxs-lookup"><span data-stu-id="4482c-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="4482c-108">Hvis du vil ha mer informasjon, kan du se dokumentasjonen for enkeltkoblinger i [Power Query-koblingsreferanse](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="4482c-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="4482c-109">Opprette en ny datakilde</span><span class="sxs-lookup"><span data-stu-id="4482c-109">Create a new data source</span></span>

1. <span data-ttu-id="4482c-110">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="4482c-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="4482c-111">Velg **Legg til datakilde**.</span><span class="sxs-lookup"><span data-stu-id="4482c-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="4482c-112">Velg **Importer data**-metoden, og velg deretter **Neste**.</span><span class="sxs-lookup"><span data-stu-id="4482c-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="4482c-113">Angi et **Navn** for datakilden, og velg deretter **Neste** for å opprette datakilden.</span><span class="sxs-lookup"><span data-stu-id="4482c-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="4482c-114">Navneretningslinjer:</span><span class="sxs-lookup"><span data-stu-id="4482c-114">Name guidelines:</span></span> 
   - <span data-ttu-id="4482c-115">Start med en bokstav.</span><span class="sxs-lookup"><span data-stu-id="4482c-115">Start with a letter.</span></span>
   - <span data-ttu-id="4482c-116">Bruk bare bokstaver og tall.</span><span class="sxs-lookup"><span data-stu-id="4482c-116">Use letters and numbers only.</span></span> <span data-ttu-id="4482c-117">Spesialtegn og mellomrom er ikke tillatt.</span><span class="sxs-lookup"><span data-stu-id="4482c-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="4482c-118">Bruk mellom 3 og 64 tegn.</span><span class="sxs-lookup"><span data-stu-id="4482c-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="4482c-119">Velg én av de [tilgjengelige koblingene](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="4482c-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="4482c-120">I dette eksemplet velger vi **Tekst/CSV**-koblingen.</span><span class="sxs-lookup"><span data-stu-id="4482c-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4482c-121">Angi de nødvendige detaljene i **Tilkoblingsinnstillinger** for den valgte koblingen, og velg **Neste** for å vise en forhåndsvisning av dataene.</span><span class="sxs-lookup"><span data-stu-id="4482c-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="4482c-122">Velg **Transformere data**.</span><span class="sxs-lookup"><span data-stu-id="4482c-122">Select **Transform data**.</span></span> <span data-ttu-id="4482c-123">I dette trinnet skal du legge til enheter i datakilden.</span><span class="sxs-lookup"><span data-stu-id="4482c-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="4482c-124">Enheter er datasett.</span><span class="sxs-lookup"><span data-stu-id="4482c-124">Entities are datasets.</span></span> <span data-ttu-id="4482c-125">Hvis du har en database som inneholder flere datasett, er hvert datasett sin egen enhet.</span><span class="sxs-lookup"><span data-stu-id="4482c-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="4482c-126">Dialogboksen **Power Query – Rediger spørringer** lar deg se gjennom og finjustere dataene.</span><span class="sxs-lookup"><span data-stu-id="4482c-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="4482c-127">Enhetene som systemene identifiserte i den valgte datakilden, vises i venstre rute.</span><span class="sxs-lookup"><span data-stu-id="4482c-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4482c-128">![Dialogboksen Rediger spørringer](media/data-manager-configure-edit-queries.png "Dialogboksen Rediger spørringer")</span><span class="sxs-lookup"><span data-stu-id="4482c-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="4482c-129">Du kan også endre dataene dine.</span><span class="sxs-lookup"><span data-stu-id="4482c-129">You can also transform your data.</span></span> <span data-ttu-id="4482c-130">Velg en enhet som skal redigeres eller transformeres.</span><span class="sxs-lookup"><span data-stu-id="4482c-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="4482c-131">Bruk alternativene i Power Query-vinduet til å bruke transformasjoner.</span><span class="sxs-lookup"><span data-stu-id="4482c-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="4482c-132">Hver transformasjon blir ført opp under **Brukte trinn**.</span><span class="sxs-lookup"><span data-stu-id="4482c-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="4482c-133">Power Query inneholder en rekke forhåndsbygde transformeringsalternativer.</span><span class="sxs-lookup"><span data-stu-id="4482c-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="4482c-134">For mer informasjon, kan du se [Power Query-transformeringer](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="4482c-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="4482c-135">Du kan legge til flere enheter i datakilden ved å velge **Hent data** i dialogboksen **Rediger spørringer**.</span><span class="sxs-lookup"><span data-stu-id="4482c-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="4482c-136">Disse transformasjonene anbefales på det sterkeste:</span><span class="sxs-lookup"><span data-stu-id="4482c-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="4482c-137">Hvis du heter data fra en CSV-fil, inneholder den første raden ofte overskrifter.</span><span class="sxs-lookup"><span data-stu-id="4482c-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="4482c-138">Gå til **Transformer tabell**, og velg **Bruk overskrifter som første rad**.</span><span class="sxs-lookup"><span data-stu-id="4482c-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="4482c-139">Kontroller at datatypen er angitt riktig.</span><span class="sxs-lookup"><span data-stu-id="4482c-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="4482c-140">Velg **Lagre** nederst i Power Query-vinduet for å lagre transformeringene.</span><span class="sxs-lookup"><span data-stu-id="4482c-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="4482c-141">Etter at du har lagret, finner du datakilden på **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="4482c-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="4482c-142">På **Data kilder**-siden vil du legge merke til at den nye datakilden har **Oppdatering**-status.</span><span class="sxs-lookup"><span data-stu-id="4482c-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="4482c-143">Tilgjengelige Power Query-datakilder</span><span class="sxs-lookup"><span data-stu-id="4482c-143">Available Power Query data sources</span></span>

<span data-ttu-id="4482c-144">Se [Power Query-referansekobling](/power-query/connectors/) for å få en oppdatert liste over koblinger som du kan velge for å importere data til Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4482c-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="4482c-145">Kontakter med en hake i kolonnen **Customer Insights (dataflyter)** er tilgjengelige for oppretting av nye datakilder basert på Power Query.</span><span class="sxs-lookup"><span data-stu-id="4482c-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="4482c-146">Se gjennom dokumentasjonen for en bestemt kobling for å finne ut mer om forhåndskravene, begrensningene og andre detaljer.</span><span class="sxs-lookup"><span data-stu-id="4482c-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="4482c-147">Redigere Power Query-datakilder</span><span class="sxs-lookup"><span data-stu-id="4482c-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="4482c-148">Det kan hende at det ikke er mulig å gjøre endringer i datakilder som for øyeblikket brukes i en av appenes prosesser (*segmentering*, *samsvar* eller *sammenslåing*, for eksempel).</span><span class="sxs-lookup"><span data-stu-id="4482c-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="4482c-149">Ved å bruke siden **Innstillinger** kan du spore fremdriften for hver av de aktive prosessene.</span><span class="sxs-lookup"><span data-stu-id="4482c-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="4482c-150">Når en prosess er fullført, kan du gå tilbake til siden **Datakilder** og utføre endringene.</span><span class="sxs-lookup"><span data-stu-id="4482c-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="4482c-151">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="4482c-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="4482c-152">Velg den loddrette ellipsen ved siden av datakildene du vil endre, og velg **Rediger** fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="4482c-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the dropdown menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4482c-153">![Rediger-alternativet](media/edit-option-data-sources.png "Rediger-alternativet")</span><span class="sxs-lookup"><span data-stu-id="4482c-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="4482c-154">Ta i bruk endringene og transformasjonene i dialogboksen **Power Query – Rediger spørringer** slik det er beskrevet i delen [Opprett en ny datakilde](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="4482c-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="4482c-155">Velg **Lagre** i Power Query når du har fullført endringene, for å lagre endringene.</span><span class="sxs-lookup"><span data-stu-id="4482c-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]