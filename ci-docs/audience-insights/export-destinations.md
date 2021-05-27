---
title: Eksportere data fra Customer Insights
description: Administrer eksporter for å dele data.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016626"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="db26b-103">Oversikt over Eksporter (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="db26b-103">Exports (preview) overview</span></span>

<span data-ttu-id="db26b-104">**Eksporter**-siden viser alle konfigurerte eksporter.</span><span class="sxs-lookup"><span data-stu-id="db26b-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="db26b-105">Eksporter deler bestemte data med forskjellige programmer.</span><span class="sxs-lookup"><span data-stu-id="db26b-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="db26b-106">De kan omfatte kundeprofiler eller enheter, skjemaer og tilordningsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="db26b-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="db26b-107">Hver eksport krever en [tilkobling, konfigurert av en administrator, for å administrere godkjenning og tilgang](connections.md).</span><span class="sxs-lookup"><span data-stu-id="db26b-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="db26b-108">Gå til **Data** > **Eksporter** for å vise eksportsiden.</span><span class="sxs-lookup"><span data-stu-id="db26b-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="db26b-109">Alle brukerroller har tilgang til å vise konfigurerte eksporter.</span><span class="sxs-lookup"><span data-stu-id="db26b-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="db26b-110">Bruk av søkefeltet på kommandolinjen til å søke etter eksporter etter navn, tilkoblingsnavn eller tilkoblingstype.</span><span class="sxs-lookup"><span data-stu-id="db26b-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="db26b-111">Konfigurer en ny eksport</span><span class="sxs-lookup"><span data-stu-id="db26b-111">Set up a new export</span></span>

<span data-ttu-id="db26b-112">Hvis du vil konfigurere eller redigere en eksport, må du ha tilkoblinger tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="db26b-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="db26b-113">Tilkoblinger avhenger av [brukerrollen din](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="db26b-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="db26b-114">Administratorer har tilgang til alle tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="db26b-114">Administrators have access to all connections.</span></span> <span data-ttu-id="db26b-115">De kan også opprette nye tilkoblinger når de konfigurerer en eksport.</span><span class="sxs-lookup"><span data-stu-id="db26b-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="db26b-116">Bidragsytere kan ha tilgang til bestemte tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="db26b-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="db26b-117">De er avhengig av administratorer for å konfigurere og dele tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="db26b-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="db26b-118">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="db26b-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="db26b-119">Visningsprogrammer kan bare vise eksisterende eksporter, men ikke opprette dem.</span><span class="sxs-lookup"><span data-stu-id="db26b-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="db26b-120">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="db26b-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="db26b-121">Velg **Legg til eksport** for å opprette et nytt eksportmål.</span><span class="sxs-lookup"><span data-stu-id="db26b-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="db26b-122">Velg hvilken tilkobling som skal brukes, i ruten **Konfigurer eksport**.</span><span class="sxs-lookup"><span data-stu-id="db26b-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="db26b-123">[Tilkoblinger](connections.md) administreres av administratorer.</span><span class="sxs-lookup"><span data-stu-id="db26b-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="db26b-124">Oppgi de nødvendige detaljene, og velg **Lagre** for å opprette eksporten.</span><span class="sxs-lookup"><span data-stu-id="db26b-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="db26b-125">Rediger en eksport</span><span class="sxs-lookup"><span data-stu-id="db26b-125">Edit an export</span></span>

1. <span data-ttu-id="db26b-126">Velg den loddrette ellipsen for eksportmålet du vil redigere.</span><span class="sxs-lookup"><span data-stu-id="db26b-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="db26b-127">Velg **Rediger** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="db26b-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="db26b-128">Endre verdiene du vil oppdatere, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="db26b-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="db26b-129">Vise eksporter og eksportdetaljer</span><span class="sxs-lookup"><span data-stu-id="db26b-129">View Exports and export details</span></span>

<span data-ttu-id="db26b-130">Når du har opprettet eksportmål, vises de i **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="db26b-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="db26b-131">Alle brukere kan se hvilke data som deles, og den nyeste statusen.</span><span class="sxs-lookup"><span data-stu-id="db26b-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="db26b-132">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="db26b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="db26b-133">Brukere uten redigeringstillatelser velger **Vis** i stedet for **Rediger** for å se eksportdetaljene.</span><span class="sxs-lookup"><span data-stu-id="db26b-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="db26b-134">Denne sideruten viser oppsettet for denne eksporten.</span><span class="sxs-lookup"><span data-stu-id="db26b-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="db26b-135">Du kan ikke endre verdier uten redigeringstillatelser.</span><span class="sxs-lookup"><span data-stu-id="db26b-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="db26b-136">Velg **Lukk** for å gå tilbake til eksportsiden.</span><span class="sxs-lookup"><span data-stu-id="db26b-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="db26b-137">Kjør eksporter ved behov</span><span class="sxs-lookup"><span data-stu-id="db26b-137">Run exports on demand</span></span>

<span data-ttu-id="db26b-138">Når du har konfigurert en eksport, kjøres den med alle [planlagte oppdateringer](system.md#schedule-tab) så lenge den har en fungerende tilkobling.</span><span class="sxs-lookup"><span data-stu-id="db26b-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="db26b-139">Hvis du vil eksportere data uten å vente på en planlagt oppdatering, går du til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="db26b-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="db26b-140">Du har to alternativer:</span><span class="sxs-lookup"><span data-stu-id="db26b-140">You have two options:</span></span>

- <span data-ttu-id="db26b-141">Hvis du vil kjøre alle eksporter, velger du **Kjør alle** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="db26b-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="db26b-142">Hvis du vil kjøre én enkelt eksport, velger du ellipsen (...) på et listeelement, og deretter velger du **Kjør**.</span><span class="sxs-lookup"><span data-stu-id="db26b-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="db26b-143">Fjerne en eksport</span><span class="sxs-lookup"><span data-stu-id="db26b-143">Remove an Export</span></span>

1. <span data-ttu-id="db26b-144">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="db26b-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="db26b-145">Velg den loddrette ellipsen for eksporten du vil fjerne.</span><span class="sxs-lookup"><span data-stu-id="db26b-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="db26b-146">Velg **Fjern** fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="db26b-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="db26b-147">Bekreft fjerningen ved å velge **Fjern** i bekreftelsesdialogboksen.</span><span class="sxs-lookup"><span data-stu-id="db26b-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
