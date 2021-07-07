---
title: Segmenter i målgruppeinnsikt
description: Oversikt over segmenter og hvordan du oppretter og administrerer dem.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306269"
---
# <a name="segments-overview"></a><span data-ttu-id="a09b7-103">Oversikt over segmenter</span><span class="sxs-lookup"><span data-stu-id="a09b7-103">Segments overview</span></span>

<span data-ttu-id="a09b7-104">Med segmenter kan du gruppere kunder basert på demografiske, transaksjonelle eller atferdsmessige attributter.</span><span class="sxs-lookup"><span data-stu-id="a09b7-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="a09b7-105">Du kan bruke segmenter til å målrette kampanjer, salgsaktiviteter og kundestøttehandlinger slik at du oppnår forretningsmålene dine.</span><span class="sxs-lookup"><span data-stu-id="a09b7-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="a09b7-106">Kundeprofiler som samsvarer med filtrene i en segmentdefinisjon, kalles *medlemmer* av et segment.</span><span class="sxs-lookup"><span data-stu-id="a09b7-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="a09b7-107">Enkelte [tjenestebegrensninger](service-limits.md) gjelder.</span><span class="sxs-lookup"><span data-stu-id="a09b7-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="a09b7-108">Opprett et nytt segment</span><span class="sxs-lookup"><span data-stu-id="a09b7-108">Create a new segment</span></span>

<span data-ttu-id="a09b7-109">Du kan opprette et nytt segment på flere måter:</span><span class="sxs-lookup"><span data-stu-id="a09b7-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="a09b7-110">Komplekst segment med segmentverktøyet: [Tomt segment](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="a09b7-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="a09b7-111">Enkle segmenter med én operator: [Hurtigsegment](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="a09b7-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="a09b7-112">AI-drevne måter å finne lignende kunder på: [Lignende kunder](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="a09b7-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="a09b7-113">AI-drevne forslag basert på mål eller attributter: [Foreslåtte segmenter for å forbedre tiltak](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="a09b7-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="a09b7-114">Forslag basert på aktiviteter: [Foreslåtte segmenter basert på kundeaktivitet](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="a09b7-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="a09b7-115">Behandle eksisterende segmenter</span><span class="sxs-lookup"><span data-stu-id="a09b7-115">Manage existing segments</span></span>

<span data-ttu-id="a09b7-116">Gå til **Segmenter**-siden for å vise alle lagrede segmenter og behandle dem.</span><span class="sxs-lookup"><span data-stu-id="a09b7-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="a09b7-117">Hvert segment representeres av en rad som inneholder tilleggsinformasjon om segmentet.</span><span class="sxs-lookup"><span data-stu-id="a09b7-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valgt segment med rullegardinliste med alternativer og tilgjengelige alternativer.":::

<span data-ttu-id="a09b7-119">Følgende handling er tilgjengelig når du velger et segment:</span><span class="sxs-lookup"><span data-stu-id="a09b7-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="a09b7-120">**Vis** segmentdetaljene, inkludert medlemsantall, som viser en forhåndsvisning av segmentmedlemmer.</span><span class="sxs-lookup"><span data-stu-id="a09b7-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="a09b7-121">**Rediger** segmentet for å endre egenskapene.</span><span class="sxs-lookup"><span data-stu-id="a09b7-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="a09b7-122">**Opprett duplikat** av et segment.</span><span class="sxs-lookup"><span data-stu-id="a09b7-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="a09b7-123">Du kan velge å redigere egenskapene med en gang, eller ganske enkelt lagre duplikatet.</span><span class="sxs-lookup"><span data-stu-id="a09b7-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="a09b7-124">**Oppdater** segmentet slik at det inneholder de nyeste dataene.</span><span class="sxs-lookup"><span data-stu-id="a09b7-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="a09b7-125">**Aktiver** eller **Deaktiver** segmentet.</span><span class="sxs-lookup"><span data-stu-id="a09b7-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="a09b7-126">Segmenter har to mulige tilstander – aktive eller inaktive.</span><span class="sxs-lookup"><span data-stu-id="a09b7-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="a09b7-127">Disse tilstandene er nyttige når du redigerer et segment.</span><span class="sxs-lookup"><span data-stu-id="a09b7-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="a09b7-128">For inaktive segmenter finnes segmentdefinisjonen, men den inneholder ingen kunder ennå.</span><span class="sxs-lookup"><span data-stu-id="a09b7-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="a09b7-129">Når du aktiverer et segment, endres statusen fra inaktiv til aktiv, og den begynner å se etter kunder som samsvarer med segmentdefinisjonen.</span><span class="sxs-lookup"><span data-stu-id="a09b7-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="a09b7-130">Hvis en [planlagt oppdatering](system.md#schedule-tab) er konfigurert, har inaktive segmenter **Status** oppført som **Hoppet over**, og dette tyder på at en oppdatering ikke ble forsøkt.</span><span class="sxs-lookup"><span data-stu-id="a09b7-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="a09b7-131">Når et inaktivt segment blir aktivert, oppdateres det og tas med i planlagte oppdateringer.</span><span class="sxs-lookup"><span data-stu-id="a09b7-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="a09b7-132">Du kan også bruke funksjonen **Planlegg senere** i rullegardinlisten **Aktiver/Deaktiver** for å angi en fremtidig dato og klokkeslett for acktivering og deaktivering av et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="a09b7-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="a09b7-133">**Gi nytt navn** til segmentet.</span><span class="sxs-lookup"><span data-stu-id="a09b7-133">**Rename** the segment.</span></span>
- <span data-ttu-id="a09b7-134">**Last ned** listen over medlemmer som en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="a09b7-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="a09b7-135">**Behandle eksporter** for å se eksporter som er knyttet til segment, og administrere dem.</span><span class="sxs-lookup"><span data-stu-id="a09b7-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="a09b7-136">Finn ut mer om eksporter.</span><span class="sxs-lookup"><span data-stu-id="a09b7-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="a09b7-137">**Slett** segmentet.</span><span class="sxs-lookup"><span data-stu-id="a09b7-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="a09b7-138">Oppdatere segmenter</span><span class="sxs-lookup"><span data-stu-id="a09b7-138">Refresh segments</span></span>

<span data-ttu-id="a09b7-139">Du kan oppdatere alle segmenter samtidig ved å velge **Oppdater alle** på **Segmenter**-siden, eller du kan oppdatere ett eller flere segmenter når du velger dem, og deretter velge **Oppdater** fra alternativene.</span><span class="sxs-lookup"><span data-stu-id="a09b7-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="a09b7-140">Du kan også konfigurere en regelmessig oppdatering under **Admin** > **System** > **Tidsplan**.</span><span class="sxs-lookup"><span data-stu-id="a09b7-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="a09b7-141">Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser.</span><span class="sxs-lookup"><span data-stu-id="a09b7-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a09b7-142">De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a09b7-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a09b7-143">Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben.</span><span class="sxs-lookup"><span data-stu-id="a09b7-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a09b7-144">Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.</span><span class="sxs-lookup"><span data-stu-id="a09b7-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="a09b7-145">Eksportere segmenter</span><span class="sxs-lookup"><span data-stu-id="a09b7-145">Export segments</span></span>

<span data-ttu-id="a09b7-146">Du kan eksportere et segment fra segmentsiden eller [eksportsiden](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a09b7-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="a09b7-147">Gå til siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="a09b7-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="a09b7-148">Velg **Vis mer [...]** for segmentet du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="a09b7-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="a09b7-149">Velg **Behandle eksporter** fra rullegardinlisten over handlinger.</span><span class="sxs-lookup"><span data-stu-id="a09b7-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="a09b7-150">Siden **Eksporter (forhåndsversjon) for segmentet** åpnes.</span><span class="sxs-lookup"><span data-stu-id="a09b7-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="a09b7-151">Du kan se alle konfigurerte eksporter gruppert etter eksporter som inneholder gjeldende segment eller ikke inneholder det.</span><span class="sxs-lookup"><span data-stu-id="a09b7-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="a09b7-152">Hvis du vil legge til det valgte segmentet i en eksport, velger du eksporten fra listen og velger **Legg til segment**.</span><span class="sxs-lookup"><span data-stu-id="a09b7-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="a09b7-153">Hvis du vil opprette en ny eksport med det valgte segmentet, velger du **Legg til eksport**.</span><span class="sxs-lookup"><span data-stu-id="a09b7-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="a09b7-154">Hvis du vil ha mer informasjon om hvordan du oppretter eksporter, kan du se [Konfigurere en ny eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a09b7-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a09b7-155">Velg **Tilbake** for å gå tilbake til hovedsiden for segmenter.</span><span class="sxs-lookup"><span data-stu-id="a09b7-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="a09b7-156">Vis behandlingslogg og segmentmedlemmer</span><span class="sxs-lookup"><span data-stu-id="a09b7-156">View processing history and segment members</span></span>

<span data-ttu-id="a09b7-157">Du kan vise konsoliderte data om et segment ved å se gjennom detaljene.</span><span class="sxs-lookup"><span data-stu-id="a09b7-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="a09b7-158">På siden **Segmenter** velger du segmentet du vil se gjennom.</span><span class="sxs-lookup"><span data-stu-id="a09b7-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="a09b7-159">Den øvre delen av siden inneholder et trendgraf som visualiserer endringer i medlemsantall.</span><span class="sxs-lookup"><span data-stu-id="a09b7-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="a09b7-160">Beveg pekeren over datapunkter for å se medlemsantallet på en bestemt dato.</span><span class="sxs-lookup"><span data-stu-id="a09b7-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="a09b7-161">Du kan oppdatere tidsrammen for visualiseringen.</span><span class="sxs-lookup"><span data-stu-id="a09b7-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a09b7-162">![Tidsintervall for segment](media/segment-time-range.png "Tidsintervall for segment")</span><span class="sxs-lookup"><span data-stu-id="a09b7-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="a09b7-163">Den nedre delen inneholder en liste over medlemmene i segmentet.</span><span class="sxs-lookup"><span data-stu-id="a09b7-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="a09b7-164">Felt som vises i listen, er basert på attributtene til enhetene i segmentet.</span><span class="sxs-lookup"><span data-stu-id="a09b7-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="a09b7-165">Listen er en forhåndsvisning av de samsvarende segmentmedlemmene og viser de første 100 oppføringene av segmentet, slik at du raskt kan evaluere det og se gjennom definisjonene hvis det er nødvendig.</span><span class="sxs-lookup"><span data-stu-id="a09b7-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="a09b7-166">Hvis du vil vise alle samsvarende oppføringer, må du [eksportere segmentet](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a09b7-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
