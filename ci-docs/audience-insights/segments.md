---
title: Opprette og behandle segmenter
description: Opprett segmenter av kunder for å gruppere dem basert på forskjellige attributter.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270368"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="9304c-103">Opprette og behandle segmenter</span><span class="sxs-lookup"><span data-stu-id="9304c-103">Create and manage segments</span></span>

<span data-ttu-id="9304c-104">Med segmenter kan du gruppere kunder basert på demografiske, transaksjonelle eller atferdsmessige attributter.</span><span class="sxs-lookup"><span data-stu-id="9304c-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="9304c-105">Du kan bruke segmenter til å målrette kampanjer, salgsaktiviteter og kundestøttehandlinger slik at du oppnår forretningsmålene dine.</span><span class="sxs-lookup"><span data-stu-id="9304c-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="9304c-106">Du kan definere komplekse filtre rundt kundeprofilenheten og de relaterte enhetene.</span><span class="sxs-lookup"><span data-stu-id="9304c-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="9304c-107">Hvert segment, etter behandlingen, oppretter et sett med kundeoppføringer som du kan eksportere og utføre handlinger på.</span><span class="sxs-lookup"><span data-stu-id="9304c-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="9304c-108">Enkelte [tjenestebegrensninger](service-limits.md) gjelder.</span><span class="sxs-lookup"><span data-stu-id="9304c-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="9304c-109">Med mindre noe annet er angitt, er alle segmenter **dynamiske segmenter**, som oppdateres etter en regelmessig tidsplan.</span><span class="sxs-lookup"><span data-stu-id="9304c-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="9304c-110">Eksemplet nedenfor viser bruken av segmenteringsfunksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="9304c-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="9304c-111">Vi har definert et segment for kunder som har bestilt varer for minst USD 500 i løpet av de siste 90 dagene *og* som var involvert i en kundeservicesamtale som ble videresendt.</span><span class="sxs-lookup"><span data-stu-id="9304c-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9304c-112">![Flere grupper](media/segmentation-group1-2.png "Flere grupper")</span><span class="sxs-lookup"><span data-stu-id="9304c-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="9304c-113">Opprett et nytt segment</span><span class="sxs-lookup"><span data-stu-id="9304c-113">Create a new segment</span></span>

<span data-ttu-id="9304c-114">Segmenter administreres på **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="9304c-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="9304c-115">I Målgruppeinnsikt går du til **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="9304c-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="9304c-116">Velg **Ny** > **Tomt segment**.</span><span class="sxs-lookup"><span data-stu-id="9304c-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="9304c-117">Velg ruten **Nytt segment**, gå til en segmenttype og angi et **Navn**.</span><span class="sxs-lookup"><span data-stu-id="9304c-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="9304c-118">Du kan eventuelt angi et visningsnavn og en beskrivelse som hjelper deg med å identifisere segmentet.</span><span class="sxs-lookup"><span data-stu-id="9304c-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="9304c-119">Velg **Neste** for å gå til siden for **Segmentverktøy**, der du definerer en gruppe.</span><span class="sxs-lookup"><span data-stu-id="9304c-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="9304c-120">En gruppe er et sett med kunder.</span><span class="sxs-lookup"><span data-stu-id="9304c-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="9304c-121">Velg enheten som inkluderer attributtet du vil segmentere etter.</span><span class="sxs-lookup"><span data-stu-id="9304c-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="9304c-122">Velg attributtet du vil segmentere etter.</span><span class="sxs-lookup"><span data-stu-id="9304c-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="9304c-123">Dette attributtet kan ha en av fire verdityper: numerisk, streng, dato eller boolsk.</span><span class="sxs-lookup"><span data-stu-id="9304c-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="9304c-124">Velg en operator og en verdi for det valgte attributtet.</span><span class="sxs-lookup"><span data-stu-id="9304c-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9304c-125">![Egendefinert gruppefilter](media/customer-group-numbers.png "Gruppefilter for kunde")</span><span class="sxs-lookup"><span data-stu-id="9304c-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="9304c-126">Antall</span><span class="sxs-lookup"><span data-stu-id="9304c-126">Number</span></span> |<span data-ttu-id="9304c-127">Definisjon</span><span class="sxs-lookup"><span data-stu-id="9304c-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="9304c-128">1</span><span class="sxs-lookup"><span data-stu-id="9304c-128">1</span></span>     |<span data-ttu-id="9304c-129">Entity</span><span class="sxs-lookup"><span data-stu-id="9304c-129">Entity</span></span>          |
   |<span data-ttu-id="9304c-130">2</span><span class="sxs-lookup"><span data-stu-id="9304c-130">2</span></span>     |<span data-ttu-id="9304c-131">Attributt</span><span class="sxs-lookup"><span data-stu-id="9304c-131">Attribute</span></span>          |
   |<span data-ttu-id="9304c-132">3</span><span class="sxs-lookup"><span data-stu-id="9304c-132">3</span></span>    |<span data-ttu-id="9304c-133">Operator</span><span class="sxs-lookup"><span data-stu-id="9304c-133">Operator</span></span>         |
   |<span data-ttu-id="9304c-134">4</span><span class="sxs-lookup"><span data-stu-id="9304c-134">4</span></span>    |<span data-ttu-id="9304c-135">Verdi</span><span class="sxs-lookup"><span data-stu-id="9304c-135">Value</span></span>         |

8. <span data-ttu-id="9304c-136">Hvis enheten er koblet til den enhetlige kundeenheten via [relasjoner](relationships.md), må du definere relasjonsbanen for å opprette et gyldig segment.</span><span class="sxs-lookup"><span data-stu-id="9304c-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="9304c-137">Legg til enhetene fra relasjonsbanen til du kan velge **Kunde: CustomerInsights**-enheten fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="9304c-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="9304c-138">Velg deretter **Alle oppføringer** for hver betingelse.</span><span class="sxs-lookup"><span data-stu-id="9304c-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9304c-139">![Relasjonsbane under opprettelse av segment](media/segments-multiple-relationships.png "Relasjonsbane under opprettelse av segment")</span><span class="sxs-lookup"><span data-stu-id="9304c-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="9304c-140">Velg **Lagre** for å lagre segmentet.</span><span class="sxs-lookup"><span data-stu-id="9304c-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="9304c-141">Segmentet blir lagret og behandlet hvis alle kravene valideres.</span><span class="sxs-lookup"><span data-stu-id="9304c-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="9304c-142">Hvis ikke blir det lagret som et utkast.</span><span class="sxs-lookup"><span data-stu-id="9304c-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="9304c-143">Velg **Tilbake til Segmenter** for å gå tilbake til **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="9304c-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="9304c-144">Behandle eksisterende segmenter</span><span class="sxs-lookup"><span data-stu-id="9304c-144">Manage existing segments</span></span>

<span data-ttu-id="9304c-145">På siden **Segmenter** kan du vise alle lagrede segmenter og administrere dem.</span><span class="sxs-lookup"><span data-stu-id="9304c-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="9304c-146">Hvert segment representeres av en rad som inneholder tilleggsinformasjon om segmentet.</span><span class="sxs-lookup"><span data-stu-id="9304c-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="9304c-147">Du kan sortere segmentene i en kolonne ved å velge kolonneoverskriften.</span><span class="sxs-lookup"><span data-stu-id="9304c-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="9304c-148">Bruk **Søk**-boksen øverst i høyre hjørne til å filtrere segmentene.</span><span class="sxs-lookup"><span data-stu-id="9304c-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9304c-149">![Alternativer for å behandle et eksisterende segment](media/segments-selected-segment.png "Alternativer for å behandle et eksisterende segment")</span><span class="sxs-lookup"><span data-stu-id="9304c-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="9304c-150">Følgende handling er tilgjengelig når du velger et segment:</span><span class="sxs-lookup"><span data-stu-id="9304c-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="9304c-151">**Vis** segmentdetaljene, inkludert medlemsantall, som viser en forhåndsvisning av segmentmedlemmer.</span><span class="sxs-lookup"><span data-stu-id="9304c-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="9304c-152">**Rediger** segmentet for å endre egenskapene.</span><span class="sxs-lookup"><span data-stu-id="9304c-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="9304c-153">**Oppdater** segmentet slik at det inneholder de nyeste dataene.</span><span class="sxs-lookup"><span data-stu-id="9304c-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="9304c-154">**Aktiver** eller **Deaktiver** segmentet.</span><span class="sxs-lookup"><span data-stu-id="9304c-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="9304c-155">Segmenter har to mulige tilstander – aktive eller inaktive.</span><span class="sxs-lookup"><span data-stu-id="9304c-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="9304c-156">Disse tilstandene er nyttige når du redigerer et segment.</span><span class="sxs-lookup"><span data-stu-id="9304c-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="9304c-157">For inaktive segmenter finnes segmentdefinisjonen, men den inneholder ingen kunder ennå.</span><span class="sxs-lookup"><span data-stu-id="9304c-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="9304c-158">Når du aktiverer et segment, endres statusen fra inaktiv til aktiv, og den begynner å se etter kunder som samsvarer med segmentdefinisjonen.</span><span class="sxs-lookup"><span data-stu-id="9304c-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="9304c-159">Hvis en [planlagt oppdatering](system.md#schedule-tab) er konfigurert, har inaktive segmenter **Status** oppført som **Hoppet over**, og dette tyder på at en oppdatering ikke ble forsøkt.</span><span class="sxs-lookup"><span data-stu-id="9304c-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="9304c-160">Når et inaktivt segment blir aktivert, oppdateres det og tas med i planlagte oppdateringer.</span><span class="sxs-lookup"><span data-stu-id="9304c-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="9304c-161">Du kan også bruke funksjonen **Planlegg senere** i rullegardinlisten **Aktiver/Deaktiver** for å angi en fremtidig dato og klokkeslett for acktivering og deaktivering av et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="9304c-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="9304c-162">**Gi nytt navn** til segmentet.</span><span class="sxs-lookup"><span data-stu-id="9304c-162">**Rename** the segment.</span></span>
- <span data-ttu-id="9304c-163">**Last ned** listen over medlemmer som en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="9304c-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="9304c-164">**Legg til**-alternativet sender listen over kunde-ID-er i segmentet til behandling i et annet program.</span><span class="sxs-lookup"><span data-stu-id="9304c-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="9304c-165">**Slett** segmentet.</span><span class="sxs-lookup"><span data-stu-id="9304c-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="9304c-166">Oppdatere segmenter</span><span class="sxs-lookup"><span data-stu-id="9304c-166">Refresh segments</span></span>

<span data-ttu-id="9304c-167">Du kan oppdatere alle segmenter samtidig ved å velge **Oppdater alle** på **Segmenter**-siden, eller du kan oppdatere ett eller flere segmenter når du velger dem, og deretter velge **Oppdater** fra alternativene.</span><span class="sxs-lookup"><span data-stu-id="9304c-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="9304c-168">Du kan også konfigurere en regelmessig oppdatering under **Admin** > **System** > **Tidsplan**.</span><span class="sxs-lookup"><span data-stu-id="9304c-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="9304c-169">Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser.</span><span class="sxs-lookup"><span data-stu-id="9304c-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="9304c-170">De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="9304c-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="9304c-171">Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben.</span><span class="sxs-lookup"><span data-stu-id="9304c-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="9304c-172">Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.</span><span class="sxs-lookup"><span data-stu-id="9304c-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="9304c-173">Laste ned og eksportere segmenter</span><span class="sxs-lookup"><span data-stu-id="9304c-173">Download and export segments</span></span>

<span data-ttu-id="9304c-174">Du kan laste ned segmentene til en CSV-fil eller eksportere dem til Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9304c-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="9304c-175">Laste ned segmenter til en CSV-fil</span><span class="sxs-lookup"><span data-stu-id="9304c-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="9304c-176">I Målgruppeinnsikt går du til **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="9304c-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="9304c-177">Velg en ellipse i flisen i et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="9304c-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="9304c-178">Velg **Last ned som CSV** fra rullegardinlisten for handlinger.</span><span class="sxs-lookup"><span data-stu-id="9304c-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="9304c-179">Eksporter segmenter til Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="9304c-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="9304c-180">Før du eksporterer segmenter til Dynamics 365 Sales, må en administrator [opprette eksportmålet](export-destinations.md) for Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9304c-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="9304c-181">I Målgruppeinnsikt går du til **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="9304c-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="9304c-182">Velg en ellipse i flisen i et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="9304c-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="9304c-183">Velg **Legg til i** fra rullegardinlisten for handlinger, og velg eksportmålet du vil sende dataene til.</span><span class="sxs-lookup"><span data-stu-id="9304c-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="9304c-184">Kladdemodus for segmenter</span><span class="sxs-lookup"><span data-stu-id="9304c-184">Draft mode for segments</span></span>

<span data-ttu-id="9304c-185">Hvis ikke alle krav til å behandle et segment er oppfylt, kan du lagre segmentet som et utkast og få tilgang til det fra siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="9304c-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="9304c-186">Det blir lagret som et inaktivt segment, og kan ikke aktiveres det før det er gyldig.</span><span class="sxs-lookup"><span data-stu-id="9304c-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="9304c-187">Legge til flere betingelser i en gruppe</span><span class="sxs-lookup"><span data-stu-id="9304c-187">Add more conditions to a group</span></span>

<span data-ttu-id="9304c-188">Hvis du vil legge til flere betingelser i en gruppe, kan du bruke to logiske operatorer:</span><span class="sxs-lookup"><span data-stu-id="9304c-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="9304c-189">**AND**-operator: Begge betingelser må oppfylles som en del av segmentprosessen.</span><span class="sxs-lookup"><span data-stu-id="9304c-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="9304c-190">Dette alternativet er svært nyttig når du definerer betingelser på tvers av forskjellige enheter.</span><span class="sxs-lookup"><span data-stu-id="9304c-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="9304c-191">**OR**-operator: En av betingelsene må oppfylles som en del av segmenteringsprosessen.</span><span class="sxs-lookup"><span data-stu-id="9304c-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="9304c-192">Dette alternativet er svært nyttig når du definerer flere betingelser for samme enhet.</span><span class="sxs-lookup"><span data-stu-id="9304c-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9304c-193">![OR-operator der begge betingelser må oppfylles](media/segmentation-either-condition.png "OR-operator der begge betingelser må oppfylles")</span><span class="sxs-lookup"><span data-stu-id="9304c-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="9304c-194">Det er for øyeblikket mulig å neste en **OR**-operator under en **AND**-operator, men ikke motsatt.</span><span class="sxs-lookup"><span data-stu-id="9304c-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="9304c-195">Kombinere flere grupper</span><span class="sxs-lookup"><span data-stu-id="9304c-195">Combine multiple groups</span></span>

<span data-ttu-id="9304c-196">Hver gruppe produserer et bestemt sett med kunder.</span><span class="sxs-lookup"><span data-stu-id="9304c-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="9304c-197">Du kan kombinere disse gruppene slik at de inneholder kundene som kreves for forretningssaken.</span><span class="sxs-lookup"><span data-stu-id="9304c-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="9304c-198">I Målgruppeinnsikt går du til **Segmenter**-siden og velger et segemtn.</span><span class="sxs-lookup"><span data-stu-id="9304c-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="9304c-199">Velg **Legg til gruppe**.</span><span class="sxs-lookup"><span data-stu-id="9304c-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9304c-200">![Legg til gruppe i kundegruppe](media/customer-group-add-group.png "Legg til gruppe i kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="9304c-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="9304c-201">Velg én av følgende sett operatorer: **Union**, **Skjæringspunkt** eller **Unntatt**.</span><span class="sxs-lookup"><span data-stu-id="9304c-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9304c-202">![Legg til union i kundegruppe](media/customer-group-union.png "Legg til union i kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="9304c-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="9304c-203">Velg en angitt operator for å definere en ny gruppe.</span><span class="sxs-lookup"><span data-stu-id="9304c-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="9304c-204">Lagre forskjellige grupper for å avgjøre hvilke data som beholdes:</span><span class="sxs-lookup"><span data-stu-id="9304c-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="9304c-205">**Union** forener de to gruppene.</span><span class="sxs-lookup"><span data-stu-id="9304c-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="9304c-206">**Intersect** overlapper de to gruppene.</span><span class="sxs-lookup"><span data-stu-id="9304c-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="9304c-207">Bare data som *er felles* for begge gruppene, beholdes i den enhetlige gruppen.</span><span class="sxs-lookup"><span data-stu-id="9304c-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="9304c-208">**Bortsett fra** kombinerer de to gruppene.</span><span class="sxs-lookup"><span data-stu-id="9304c-208">**Except** combines the two groups.</span></span> <span data-ttu-id="9304c-209">Bare data i gruppe A som *ikke er felles* med data i gruppe B, beholdes.</span><span class="sxs-lookup"><span data-stu-id="9304c-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="9304c-210">Vis behandlingslogg og segmentmedlemmer</span><span class="sxs-lookup"><span data-stu-id="9304c-210">View processing history and segment members</span></span>

<span data-ttu-id="9304c-211">Du kan vise konsoliderte data om et segment ved å se gjennom detaljene.</span><span class="sxs-lookup"><span data-stu-id="9304c-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="9304c-212">På siden **Segmenter** velger du segmentet du vil se gjennom.</span><span class="sxs-lookup"><span data-stu-id="9304c-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="9304c-213">Den øvre delen av siden inneholder et trendgraf som visualiserer endringer i medlemsantall.</span><span class="sxs-lookup"><span data-stu-id="9304c-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="9304c-214">Beveg pekeren over datapunkter for å se medlemsantallet på en bestemt dato.</span><span class="sxs-lookup"><span data-stu-id="9304c-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="9304c-215">Du kan oppdatere tidsrammen for visualiseringen.</span><span class="sxs-lookup"><span data-stu-id="9304c-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9304c-216">![Tidsintervall for segment](media/segment-time-range.png "Tidsintervall for segment")</span><span class="sxs-lookup"><span data-stu-id="9304c-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="9304c-217">Den nedre delen inneholder en liste over medlemmene i segmentet.</span><span class="sxs-lookup"><span data-stu-id="9304c-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="9304c-218">Felt som vises i listen, er basert på attributtene til enhetene i segmentet.</span><span class="sxs-lookup"><span data-stu-id="9304c-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="9304c-219">Listen er en forhåndsvisning av de samsvarende segmentmedlemmene og viser de første 100 oppføringene av segmentet, slik at du raskt kan evaluere det og se gjennom definisjonene hvis det er nødvendig.</span><span class="sxs-lookup"><span data-stu-id="9304c-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="9304c-220">Hvis du vil vise alle samsvarende oppføringer, må du [eksportere segmentet](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9304c-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="9304c-221">Hurtigsegmenter</span><span class="sxs-lookup"><span data-stu-id="9304c-221">Quick segments</span></span>

<span data-ttu-id="9304c-222">I tillegg til segmentverktøyet finnes det en annen bane for oppretting av segmenter.</span><span class="sxs-lookup"><span data-stu-id="9304c-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="9304c-223">Med hurtigsegmenter kan du bygge enkle segmenter (med én enkelt operator) raskt og med direkte innsikt.</span><span class="sxs-lookup"><span data-stu-id="9304c-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="9304c-224">På **Segmenter**-siden velger du **Ny** > **Hurtigopprett fra**.</span><span class="sxs-lookup"><span data-stu-id="9304c-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="9304c-225">Velg alternativet **Profiler** for å bygge et segment som er basert på den enhetlige kundeenheten.</span><span class="sxs-lookup"><span data-stu-id="9304c-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="9304c-226">Velg alternativet **Mål** for å bygge et segment rundt hver av Kundeattributt-måltypene du tidligere har opprettet på **Mål**-siden.</span><span class="sxs-lookup"><span data-stu-id="9304c-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="9304c-227">Velg alternativet **Intelligens** for å bygge et segment rundt én av de utgående enhetene du genererte ved hjelp av funksjonene **Prediksjoner** eller **Egendefinerte modeller**.</span><span class="sxs-lookup"><span data-stu-id="9304c-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="9304c-228">I dialogboksen **Nytt hurtigsegment** velger du et attributt fra **Felt**-rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="9304c-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="9304c-229">Systemet gir noe ekstra innsikt som hjelper deg med å lage bedre segmenter av kundene.</span><span class="sxs-lookup"><span data-stu-id="9304c-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="9304c-230">Vi viser de 10 største kundeantallene for kategoriske felt.</span><span class="sxs-lookup"><span data-stu-id="9304c-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="9304c-231">Velg en **Verdi** og deretter **Gå gjennom**.</span><span class="sxs-lookup"><span data-stu-id="9304c-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="9304c-232">For et numerisk attributt vil systemet vise hvilken attributtverdi som faller under hver kundepersentil.</span><span class="sxs-lookup"><span data-stu-id="9304c-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="9304c-233">Velg en **Operator** og en **Verdi**, og velg deretter **Gå gjennom**.</span><span class="sxs-lookup"><span data-stu-id="9304c-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="9304c-234">Systemet gir deg en **Beregnet segmentstørrelse**.</span><span class="sxs-lookup"><span data-stu-id="9304c-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="9304c-235">Du kan velge om du vil generere segmentet du har definert, eller først gå til det igjen for å få en annen segmentstørrelse.</span><span class="sxs-lookup"><span data-stu-id="9304c-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9304c-236">![Navn og beregning for et hurtigsegment](media/quick-segment-name.png "Navn og beregning for et hurtigsegment")</span><span class="sxs-lookup"><span data-stu-id="9304c-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="9304c-237">Angi et **Navn** for segmentet.</span><span class="sxs-lookup"><span data-stu-id="9304c-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="9304c-238">Alternativt kan du angi et **Visningsnavn**.</span><span class="sxs-lookup"><span data-stu-id="9304c-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="9304c-239">Velg **Lagre** for å opprette segmentet.</span><span class="sxs-lookup"><span data-stu-id="9304c-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="9304c-240">Når segmentet er ferdig behandlet, kan du vise det på samme måte som et hvilket som helst segment du har opprettet.</span><span class="sxs-lookup"><span data-stu-id="9304c-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="9304c-241">I følgende scenarioer anbefaler vi å bruke segmentverktøyet i stedet for den anbefalte segmentfunksjonen:</span><span class="sxs-lookup"><span data-stu-id="9304c-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="9304c-242">Opprette segmenter med filtre i kategorifelt der operatoren er forskjellig fra **Is**-operatoren</span><span class="sxs-lookup"><span data-stu-id="9304c-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="9304c-243">Opprette segmenter med filtre på numeriske felt der operatoren er forskjellig fra operatorene **Mellom**, **Større enn** og **Mindre enn**</span><span class="sxs-lookup"><span data-stu-id="9304c-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="9304c-244">Opprette segmenter med filtre på datotype-felt</span><span class="sxs-lookup"><span data-stu-id="9304c-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="9304c-245">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="9304c-245">Next steps</span></span>

<span data-ttu-id="9304c-246">[Eksporter et segment](export-destinations.md) og utforsk [Kundekort](customer-card-add-in.md) og [Koblinger](export-power-bi.md) for å få innsikt på kundenivået.</span><span class="sxs-lookup"><span data-stu-id="9304c-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]