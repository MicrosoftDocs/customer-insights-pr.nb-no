---
title: Supplere enhetlige kundeprofiler
description: Bruk funksjoner for å supplere kundedataene.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954499"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="567a3-103">Supplement for kundeprofiler (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="567a3-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="567a3-104">Bruk data fra kilder som Microsoft og andre partnere for å berike kundedataene.</span><span class="sxs-lookup"><span data-stu-id="567a3-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Side for suppleringshub":::

<span data-ttu-id="567a3-106">I måltruppeinnsikt går du til **Data** > **Supplering** for å arbeide med suppleringsalternativer.</span><span class="sxs-lookup"><span data-stu-id="567a3-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="567a3-107">Du må ha tillatelse som bidragsyter eller administrator for å opprette eller redigere berikelser.</span><span class="sxs-lookup"><span data-stu-id="567a3-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="567a3-108">Du finner mer informasjon i [Tillatelser](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="567a3-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="567a3-109">I kategorien **Oppdag** finner du følgende suppleringer:</span><span class="sxs-lookup"><span data-stu-id="567a3-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="567a3-110">[Merker](enrichment-microsoft.md) levert av Microsoft</span><span class="sxs-lookup"><span data-stu-id="567a3-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="567a3-111">[Interesser](enrichment-microsoft.md) levert av Microsoft</span><span class="sxs-lookup"><span data-stu-id="567a3-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="567a3-112">[Forbedrede adresser](enrichment-enhanced-addresses.md) levert av Microsoft</span><span class="sxs-lookup"><span data-stu-id="567a3-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="567a3-113">[Firmadata](enrichment-leadspace.md) levert av Leadspace</span><span class="sxs-lookup"><span data-stu-id="567a3-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="567a3-114">[Demografi](enrichment-experian.md) levert av Experian</span><span class="sxs-lookup"><span data-stu-id="567a3-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="567a3-115">[Stedsdata](enrichment-here.md) levert av HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="567a3-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="567a3-116">[Egendefinerte data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="567a3-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="567a3-117">I kategorien **Mine suppleringer** kan du se de suppleringene du har konfigurert, og redigere egenskapene deres.</span><span class="sxs-lookup"><span data-stu-id="567a3-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="567a3-118">Behandle eksisterende suppleringer</span><span class="sxs-lookup"><span data-stu-id="567a3-118">Manage existing enrichments</span></span>

<span data-ttu-id="567a3-119">Gå til **Mine suppleringer** for å se alle konfigurerte suppleringer.</span><span class="sxs-lookup"><span data-stu-id="567a3-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="567a3-120">Hvert supplering vises som en rad som inneholder tilleggsinformasjon om suppleringen.</span><span class="sxs-lookup"><span data-stu-id="567a3-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="567a3-121">Velg en supplering for å vise de tilgjengelige alternativene.</span><span class="sxs-lookup"><span data-stu-id="567a3-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="567a3-122">Du kan også velge ellipsen (...) i et listeelement for å vise alternativene.</span><span class="sxs-lookup"><span data-stu-id="567a3-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativer for å behandle suppleringer i listen over suppleringer":::

- <span data-ttu-id="567a3-124">**Vis** suppleringsdetaljer med antall supplerte kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="567a3-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="567a3-125">**Rediger** suppleringskonfigurasjonen.</span><span class="sxs-lookup"><span data-stu-id="567a3-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="567a3-126">**Kjør** supplementet for å oppdatere kundeprofiler med de nyeste dataene.</span><span class="sxs-lookup"><span data-stu-id="567a3-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="567a3-127">**Deaktiver** en eksisterende supplering for å unngå at den oppdateres automatisk med hver planlagte oppdatering.</span><span class="sxs-lookup"><span data-stu-id="567a3-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="567a3-128">Data fra den siste vellykkede oppdateringen er fortsatt tilgjengelige.</span><span class="sxs-lookup"><span data-stu-id="567a3-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="567a3-129">**Aktiver** en inaktiv supplering for å starte automatisk oppdatering på nytt med hver planlagte oppdatering.</span><span class="sxs-lookup"><span data-stu-id="567a3-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="567a3-130">**Slett** en supplering.</span><span class="sxs-lookup"><span data-stu-id="567a3-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="567a3-131">Du kan kjøre eller deaktivere flere supplementer samtidig ved å velge dem i listen.</span><span class="sxs-lookup"><span data-stu-id="567a3-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="567a3-132">Alternativer for visning og redigering er ikke tilgjengelige som massehandling og fungerer bare for én supplering om gangen.</span><span class="sxs-lookup"><span data-stu-id="567a3-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="567a3-133">Suppleringer og tilkoblinger</span><span class="sxs-lookup"><span data-stu-id="567a3-133">Enrichments and connections</span></span>

<span data-ttu-id="567a3-134">Tredjeparts suppleringer konfigureres ved hjelp av [tilkoblinger](connections.md), som en administrator konfigurerer med legitimasjon og gir samtykketil dataoverføringer.</span><span class="sxs-lookup"><span data-stu-id="567a3-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="567a3-135">Tilkoblingen kan brukes av administratorer og bidragsytere til å konfigurere suppleringer.</span><span class="sxs-lookup"><span data-stu-id="567a3-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="567a3-136">Flere suppleringer av samme type</span><span class="sxs-lookup"><span data-stu-id="567a3-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="567a3-137">Enheten som skal suppleres, angis under suppleringskonfigurasjonen, noe som gjør at du bare kan supplere et delsett av profilene.</span><span class="sxs-lookup"><span data-stu-id="567a3-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="567a3-138">For eksempel supplerer du bare data for et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="567a3-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="567a3-139">Du kan konfigurere flere suppleringer av samme type og bruke samme tilkobling på nytt.</span><span class="sxs-lookup"><span data-stu-id="567a3-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="567a3-140">Noen suppleringer vil ha begrensninger på antall suppleringer av samme type som kan opprettes.</span><span class="sxs-lookup"><span data-stu-id="567a3-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="567a3-141">Du kan se grensene og gjeldende bruk på **Supplering**-siden.</span><span class="sxs-lookup"><span data-stu-id="567a3-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
