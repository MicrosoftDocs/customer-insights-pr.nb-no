---
title: Supplere enhetlige kundeprofiler
description: Bruk funksjoner for å supplere kundedataene.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269480"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="be834-103">Supplement for kundeprofiler (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="be834-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="be834-104">Bruk data fra kilder som Microsoft og andre partnere for å berike kundedataene.</span><span class="sxs-lookup"><span data-stu-id="be834-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Side for suppleringshub":::

<span data-ttu-id="be834-106">I måltruppeinnsikt går du til **Data** > **Supplering** for å arbeide med suppleringsalternativer.</span><span class="sxs-lookup"><span data-stu-id="be834-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="be834-107">Du må ha tillatelse som bidragsyter eller administrator for å opprette eller redigere berikelser.</span><span class="sxs-lookup"><span data-stu-id="be834-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="be834-108">Du finner mer informasjon i [Tillatelser](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="be834-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="be834-109">I kategorien **Oppdag** finner du følgende suppleringer:</span><span class="sxs-lookup"><span data-stu-id="be834-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="be834-110">[Merker](enrichment-microsoft-graph.md) formidlet av Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="be834-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="be834-111">[Interesser](enrichment-microsoft-graph.md) formidlet av Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="be834-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="be834-112">[Firmadata](enrichment-leadspace.md) levert av Leadspace</span><span class="sxs-lookup"><span data-stu-id="be834-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="be834-113">[Demografi](enrichment-experian.md) levert av Experian</span><span class="sxs-lookup"><span data-stu-id="be834-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="be834-114">[Stedsdata](enrichment-here.md) levert av HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="be834-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="be834-115">[Egendefinerte data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="be834-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="be834-116">I kategorien **Mine suppleringer** kan du se de suppleringene du har konfigurert, og redigere egenskapene deres.</span><span class="sxs-lookup"><span data-stu-id="be834-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="be834-117">Behandle eksisterende suppleringer</span><span class="sxs-lookup"><span data-stu-id="be834-117">Manage existing enrichments</span></span>

<span data-ttu-id="be834-118">Gå til **Mine suppleringer** for å se alle konfigurerte suppleringer.</span><span class="sxs-lookup"><span data-stu-id="be834-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="be834-119">Hvert supplering vises som en rad som inneholder tilleggsinformasjon om suppleringen.</span><span class="sxs-lookup"><span data-stu-id="be834-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="be834-120">Velg en supplering for å vise de tilgjengelige alternativene.</span><span class="sxs-lookup"><span data-stu-id="be834-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="be834-121">Du kan også velge en ellipse (...) for et listeelement for å vise alternativene.</span><span class="sxs-lookup"><span data-stu-id="be834-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativer for å behandle suppleringer i listen over suppleringer":::

- <span data-ttu-id="be834-123">**Vis** suppleringsdetaljer med antall supplerte kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="be834-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="be834-124">**Rediger** suppleringskonfigurasjonen.</span><span class="sxs-lookup"><span data-stu-id="be834-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="be834-125">**Kjør** supplementet for å oppdatere kundeprofiler med de nyeste dataene.</span><span class="sxs-lookup"><span data-stu-id="be834-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="be834-126">**Deaktiver** en eksisterende supplering for å unngå at den oppdateres automatisk med hver planlagte oppdatering.</span><span class="sxs-lookup"><span data-stu-id="be834-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="be834-127">Data fra den siste vellykkede oppdateringen er fortsatt tilgjengelige.</span><span class="sxs-lookup"><span data-stu-id="be834-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="be834-128">**Aktiver** en inaktiv supplering for å starte automatisk oppdatering på nytt med hver planlagte oppdatering.</span><span class="sxs-lookup"><span data-stu-id="be834-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="be834-129">**Slett** en supplering.</span><span class="sxs-lookup"><span data-stu-id="be834-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="be834-130">Du kan kjøre eller deaktivere flere supplementer samtidig ved å velge dem i listen.</span><span class="sxs-lookup"><span data-stu-id="be834-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="be834-131">Alternativer for visning og redigering er ikke tilgjengelige som massehandling og fungerer bare for én supplering om gangen.</span><span class="sxs-lookup"><span data-stu-id="be834-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]