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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896017"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="5e08e-103">Supplement for kundeprofiler (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="5e08e-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="5e08e-104">Bruk data fra kilder som Microsoft og andre partnere for å berike kundedataene.</span><span class="sxs-lookup"><span data-stu-id="5e08e-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Side for suppleringshub":::

<span data-ttu-id="5e08e-106">I måltruppeinnsikt går du til **Data** > **Supplering** for å arbeide med suppleringsalternativer.</span><span class="sxs-lookup"><span data-stu-id="5e08e-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="5e08e-107">Du må ha tillatelse som bidragsyter eller administrator for å opprette eller redigere berikelser.</span><span class="sxs-lookup"><span data-stu-id="5e08e-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="5e08e-108">Du finner mer informasjon i [Tillatelser](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5e08e-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="5e08e-109">I kategorien **Oppdag** finner du følgende suppleringer:</span><span class="sxs-lookup"><span data-stu-id="5e08e-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="5e08e-110">[Merker](enrichment-microsoft.md) levert av Microsoft</span><span class="sxs-lookup"><span data-stu-id="5e08e-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="5e08e-111">[Interesser](enrichment-microsoft.md) levert av Microsoft</span><span class="sxs-lookup"><span data-stu-id="5e08e-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="5e08e-112">[Firmadata](enrichment-leadspace.md) levert av Leadspace</span><span class="sxs-lookup"><span data-stu-id="5e08e-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="5e08e-113">[Demografi](enrichment-experian.md) levert av Experian</span><span class="sxs-lookup"><span data-stu-id="5e08e-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="5e08e-114">[Stedsdata](enrichment-here.md) levert av HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="5e08e-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="5e08e-115">[Egendefinerte data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="5e08e-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="5e08e-116">I kategorien **Mine suppleringer** kan du se de suppleringene du har konfigurert, og redigere egenskapene deres.</span><span class="sxs-lookup"><span data-stu-id="5e08e-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="5e08e-117">Behandle eksisterende suppleringer</span><span class="sxs-lookup"><span data-stu-id="5e08e-117">Manage existing enrichments</span></span>

<span data-ttu-id="5e08e-118">Gå til **Mine suppleringer** for å se alle konfigurerte suppleringer.</span><span class="sxs-lookup"><span data-stu-id="5e08e-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="5e08e-119">Hvert supplering vises som en rad som inneholder tilleggsinformasjon om suppleringen.</span><span class="sxs-lookup"><span data-stu-id="5e08e-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="5e08e-120">Velg en supplering for å vise de tilgjengelige alternativene.</span><span class="sxs-lookup"><span data-stu-id="5e08e-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="5e08e-121">Du kan også velge ellipsen (...) i et listeelement for å vise alternativene.</span><span class="sxs-lookup"><span data-stu-id="5e08e-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Alternativer for å behandle suppleringer i listen over suppleringer":::

- <span data-ttu-id="5e08e-123">**Vis** suppleringsdetaljer med antall supplerte kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="5e08e-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="5e08e-124">**Rediger** suppleringskonfigurasjonen.</span><span class="sxs-lookup"><span data-stu-id="5e08e-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="5e08e-125">**Kjør** supplementet for å oppdatere kundeprofiler med de nyeste dataene.</span><span class="sxs-lookup"><span data-stu-id="5e08e-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="5e08e-126">**Deaktiver** en eksisterende supplering for å unngå at den oppdateres automatisk med hver planlagte oppdatering.</span><span class="sxs-lookup"><span data-stu-id="5e08e-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="5e08e-127">Data fra den siste vellykkede oppdateringen er fortsatt tilgjengelige.</span><span class="sxs-lookup"><span data-stu-id="5e08e-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="5e08e-128">**Aktiver** en inaktiv supplering for å starte automatisk oppdatering på nytt med hver planlagte oppdatering.</span><span class="sxs-lookup"><span data-stu-id="5e08e-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="5e08e-129">**Slett** en supplering.</span><span class="sxs-lookup"><span data-stu-id="5e08e-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="5e08e-130">Du kan kjøre eller deaktivere flere supplementer samtidig ved å velge dem i listen.</span><span class="sxs-lookup"><span data-stu-id="5e08e-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="5e08e-131">Alternativer for visning og redigering er ikke tilgjengelige som massehandling og fungerer bare for én supplering om gangen.</span><span class="sxs-lookup"><span data-stu-id="5e08e-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="5e08e-132">Suppleringer og tilkoblinger</span><span class="sxs-lookup"><span data-stu-id="5e08e-132">Enrichments and connections</span></span>

<span data-ttu-id="5e08e-133">Tredjeparts suppleringer konfigureres ved hjelp av [tilkoblinger](connections.md), som en administrator konfigurerer med legitimasjon og gir samtykketil dataoverføringer.</span><span class="sxs-lookup"><span data-stu-id="5e08e-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="5e08e-134">Tilkoblingen kan brukes av administratorer og bidragsytere til å konfigurere suppleringer.</span><span class="sxs-lookup"><span data-stu-id="5e08e-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="5e08e-135">Flere suppleringer av samme type</span><span class="sxs-lookup"><span data-stu-id="5e08e-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="5e08e-136">Enheten som skal suppleres, angis under suppleringskonfigurasjonen, noe som gjør at du bare kan supplere et delsett av profilene.</span><span class="sxs-lookup"><span data-stu-id="5e08e-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="5e08e-137">For eksempel supplerer du bare data for et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="5e08e-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="5e08e-138">Du kan konfigurere flere suppleringer av samme type og bruke samme tilkobling på nytt.</span><span class="sxs-lookup"><span data-stu-id="5e08e-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="5e08e-139">Noen suppleringer vil ha begrensninger på antall suppleringer av samme type som kan opprettes.</span><span class="sxs-lookup"><span data-stu-id="5e08e-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="5e08e-140">Du kan se grensene og gjeldende bruk på **Supplering**-siden.</span><span class="sxs-lookup"><span data-stu-id="5e08e-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
