---
title: Eksportmål
description: Eksporter data og administrer eksportmål.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643875"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="b295b-103">Eksportmål (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="b295b-103">Export destinations (preview)</span></span>

<span data-ttu-id="b295b-104">Siden **Eksportmål** viser alle stedene du har konfigurert til å eksportere data til.</span><span class="sxs-lookup"><span data-stu-id="b295b-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="b295b-105">Du kan også legge til nye mål for eksport.</span><span class="sxs-lookup"><span data-stu-id="b295b-105">You can also add new destinations for export.</span></span> <span data-ttu-id="b295b-106">I tillegg vises det tilgjengelige alternativer for eksport.</span><span class="sxs-lookup"><span data-stu-id="b295b-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="b295b-107">Få en rask oversikt og en beskrivelse, og finn ut hva du kan gjøre med hvert utvidelsesalternativ.</span><span class="sxs-lookup"><span data-stu-id="b295b-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="b295b-108">Eksporter samlede profiler, mål og segmenter til apper som støttes for virksomheten din.</span><span class="sxs-lookup"><span data-stu-id="b295b-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="b295b-109">Gå til **Admin** > **Eksportmål** for å finne følgende utvidelsesalternativer:</span><span class="sxs-lookup"><span data-stu-id="b295b-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="b295b-110">Dynamics 365-kundekorttillegg</span><span class="sxs-lookup"><span data-stu-id="b295b-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="b295b-111">Kobling for Facebook Annonseadministrasjon</span><span class="sxs-lookup"><span data-stu-id="b295b-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="b295b-112">Power Automate-kobling</span><span class="sxs-lookup"><span data-stu-id="b295b-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="b295b-113">Power Apps-kobling</span><span class="sxs-lookup"><span data-stu-id="b295b-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="b295b-114">Power BI-kobling</span><span class="sxs-lookup"><span data-stu-id="b295b-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="b295b-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="b295b-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="b295b-116">Dynamics 365 for salg</span><span class="sxs-lookup"><span data-stu-id="b295b-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="b295b-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="b295b-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="b295b-118">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="b295b-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="b295b-119">LiveRamp&reg;-kobling</span><span class="sxs-lookup"><span data-stu-id="b295b-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="b295b-120">Robot for Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b295b-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="b295b-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="b295b-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="b295b-122">Customer Insights-API</span><span class="sxs-lookup"><span data-stu-id="b295b-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="b295b-123">Legge til et nytt eksportmål</span><span class="sxs-lookup"><span data-stu-id="b295b-123">Add a new export destination</span></span>

<span data-ttu-id="b295b-124">Hvis du vil legge til eksportmål, må du ha [administratortillatelser](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b295b-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="b295b-125">Hvis du eksporterer til Microsoft-tjenester, antas det at begge tjenestene er i samme organisasjon.</span><span class="sxs-lookup"><span data-stu-id="b295b-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="b295b-126">Gå til **Admin** > **Eksporter mål**.</span><span class="sxs-lookup"><span data-stu-id="b295b-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b295b-127">Bytt til kategorien **Mine eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="b295b-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="b295b-128">Velg **Legg til mål** for å opprette et nytt eksportmål.</span><span class="sxs-lookup"><span data-stu-id="b295b-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="b295b-129">I ruten **Legg til mål** velger du **Type** eksportmål i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="b295b-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="b295b-130">Angi de nødvendige detaljene, og velg deretter **Neste** for å opprette eksportmålet.</span><span class="sxs-lookup"><span data-stu-id="b295b-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="b295b-131">Du kan også velge **Konfigurer** på en flis i kategorien **Oppdag**.</span><span class="sxs-lookup"><span data-stu-id="b295b-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="b295b-132">Vise eksportmål</span><span class="sxs-lookup"><span data-stu-id="b295b-132">View Export destinations</span></span>

<span data-ttu-id="b295b-133">Når du har opprettet eksportmålene, finner du dem i en tabell i kategorien **Mine eksportmål**. Denne tabellen har tre kolonner:</span><span class="sxs-lookup"><span data-stu-id="b295b-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="b295b-134">**Visningsnavn**: Navnet du angav da du opprettet målet.</span><span class="sxs-lookup"><span data-stu-id="b295b-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="b295b-135">**Type**: Typen eksportmål du angir når du oppretter målet.</span><span class="sxs-lookup"><span data-stu-id="b295b-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="b295b-136">**Opprettet**: Datoen du opprettet målet.</span><span class="sxs-lookup"><span data-stu-id="b295b-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="b295b-137">Redigere et eksportmål</span><span class="sxs-lookup"><span data-stu-id="b295b-137">Edit an export destination</span></span>

1. <span data-ttu-id="b295b-138">Velg den loddrette ellipsen for eksportmålet du vil redigere.</span><span class="sxs-lookup"><span data-stu-id="b295b-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b295b-139">![Loddrett ellipse](media/export-destinations-page-ellipsis.png "Loddrett ellipse")</span><span class="sxs-lookup"><span data-stu-id="b295b-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="b295b-140">Velg **Rediger** på rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="b295b-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="b295b-141">Endre verdiene som krever oppdatering, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="b295b-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="b295b-142">Eksportere data etter behov</span><span class="sxs-lookup"><span data-stu-id="b295b-142">Export data on demand</span></span>

<span data-ttu-id="b295b-143">Når du har konfigurert en kobling for et eksportmål, kjøres eksporter med alle [planlagte oppdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b295b-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="b295b-144">Hvis du vil eksportere data uten å vente på en planlagt oppdatering, kan du gå til kategorien **Mine eksportmål** på **Administrator** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="b295b-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b295b-145">![Loddrett ellipse](media/export-destinations-page-ellipsis.png "Loddrett ellipse")</span><span class="sxs-lookup"><span data-stu-id="b295b-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="b295b-146">Velg **Eksporter** over listen for å kjøre eksporten til alle eksportmålene samtidig.</span><span class="sxs-lookup"><span data-stu-id="b295b-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="b295b-147">Velg ellipsen (...) etter et listeelement, og velg deretter **Eksporter**-alternativet for å kjøre eksporten for et enkelt eksportmål.</span><span class="sxs-lookup"><span data-stu-id="b295b-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="b295b-148">Fjerne et eksportmål</span><span class="sxs-lookup"><span data-stu-id="b295b-148">Remove an Export destination</span></span>

<span data-ttu-id="b295b-149">Hvis du vil fjerne et eksportmål, starter du fra hovedsiden for **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="b295b-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="b295b-150">Velg den loddrette ellipsen for eksportmålet du vil fjerne.</span><span class="sxs-lookup"><span data-stu-id="b295b-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b295b-151">![Loddrett ellipse](media/export-destinations-page-ellipsis.png "Loddrett ellipse")</span><span class="sxs-lookup"><span data-stu-id="b295b-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="b295b-152">Velg **Fjern** fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="b295b-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="b295b-153">Bekreft fjerningen ved å velge **Fjern** i bekreftelsesdialogboksen.</span><span class="sxs-lookup"><span data-stu-id="b295b-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
