---
title: Opprette og behandle segmenter
description: Opprett segmenter av kunder for å gruppere dem basert på forskjellige attributter.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597066"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="1f6a6-103">Opprette og behandle segmenter</span><span class="sxs-lookup"><span data-stu-id="1f6a6-103">Create and manage segments</span></span>

<span data-ttu-id="1f6a6-104">Med segmenter kan du gruppere kunder basert på demografiske, transaksjonelle eller atferdsmessige attributter.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="1f6a6-105">Du kan bruke segmenter til å målrette kampanjer, salgsaktiviteter og kundestøttehandlinger slik at du oppnår forretningsmålene dine.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="1f6a6-106">Du kan definere komplekse filtre rundt kundeprofilenheten og de relaterte enhetene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="1f6a6-107">Hvert segment, etter behandlingen, oppretter et sett med kundeoppføringer som du kan eksportere og utføre handlinger på.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="1f6a6-108">Enkelte [tjenestebegrensninger](service-limits.md) gjelder.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="1f6a6-109">Med mindre noe annet er angitt, er alle segmenter **dynamiske segmenter**, som oppdateres etter en regelmessig tidsplan.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="1f6a6-110">Eksemplet nedenfor viser bruken av segmenteringsfunksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="1f6a6-111">Vi har definert et segment for kunder som har bestilt varer for minst USD 500 i løpet av de siste 90 dagene *og* som var involvert i en kundeservicesamtale som ble videresendt.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1f6a6-112">![Flere grupper](media/segmentation-group1-2.png "Flere grupper")</span><span class="sxs-lookup"><span data-stu-id="1f6a6-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="1f6a6-113">Opprett et nytt segment</span><span class="sxs-lookup"><span data-stu-id="1f6a6-113">Create a new segment</span></span>

<span data-ttu-id="1f6a6-114">Segmenter administreres på **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="1f6a6-115">I Målgruppeinnsikt går du til **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="1f6a6-116">Velg **Ny** > **Tomt segment**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="1f6a6-117">Velg ruten **Nytt segment**, gå til en segmenttype og angi et **Navn**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="1f6a6-118">Du kan eventuelt angi et visningsnavn og en beskrivelse som hjelper deg med å identifisere segmentet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="1f6a6-119">Velg **Neste** for å gå til siden for **Segmentverktøy**, der du definerer en gruppe.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="1f6a6-120">En gruppe er et sett med kunder.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="1f6a6-121">Velg enheten som inkluderer attributtet du vil segmentere etter.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="1f6a6-122">Velg attributtet du vil segmentere etter.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="1f6a6-123">Dette attributtet kan ha en av fire verdityper: numerisk, streng, dato eller boolsk.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="1f6a6-124">Velg en operator og en verdi for det valgte attributtet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1f6a6-125">![Egendefinert gruppefilter](media/customer-group-numbers.png "Gruppefilter for kunde")</span><span class="sxs-lookup"><span data-stu-id="1f6a6-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="1f6a6-126">Antall</span><span class="sxs-lookup"><span data-stu-id="1f6a6-126">Number</span></span> |<span data-ttu-id="1f6a6-127">Definisjon</span><span class="sxs-lookup"><span data-stu-id="1f6a6-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="1f6a6-128">1</span><span class="sxs-lookup"><span data-stu-id="1f6a6-128">1</span></span>     |<span data-ttu-id="1f6a6-129">Entity</span><span class="sxs-lookup"><span data-stu-id="1f6a6-129">Entity</span></span>          |
   |<span data-ttu-id="1f6a6-130">2</span><span class="sxs-lookup"><span data-stu-id="1f6a6-130">2</span></span>     |<span data-ttu-id="1f6a6-131">Attributt</span><span class="sxs-lookup"><span data-stu-id="1f6a6-131">Attribute</span></span>          |
   |<span data-ttu-id="1f6a6-132">3</span><span class="sxs-lookup"><span data-stu-id="1f6a6-132">3</span></span>    |<span data-ttu-id="1f6a6-133">Operator</span><span class="sxs-lookup"><span data-stu-id="1f6a6-133">Operator</span></span>         |
   |<span data-ttu-id="1f6a6-134">4</span><span class="sxs-lookup"><span data-stu-id="1f6a6-134">4</span></span>    |<span data-ttu-id="1f6a6-135">Verdi</span><span class="sxs-lookup"><span data-stu-id="1f6a6-135">Value</span></span>         |

8. <span data-ttu-id="1f6a6-136">Hvis enheten er koblet til den enhetlige kundeenheten via [relasjoner](relationships.md), må du definere relasjonsbanen for å opprette et gyldig segment.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="1f6a6-137">Legg til enhetene fra relasjonsbanen til du kan velge **Kunde: CustomerInsights**-enheten fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="1f6a6-138">Velg deretter **Alle oppføringer** for hver betingelse.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1f6a6-139">![Relasjonsbane under opprettelse av segment](media/segments-multiple-relationships.png "Relasjonsbane under opprettelse av segment")</span><span class="sxs-lookup"><span data-stu-id="1f6a6-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="1f6a6-140">Som standard genererer segmenter en utdataenhet som inneholder alle attributter for kundeprofiler som samsvarer med de definerte filtrene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="1f6a6-141">Hvis et segment er basert på andre enheter enn *Kunde*-enheten, kan du legge til flere attributter fra disse enhetene i utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="1f6a6-142">Velg **Prosjektattributter** for å velge attributtene som skal legges til i utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="1f6a6-143">Eksempel: Et segment er basert på en enhet som inneholder kundeaktivitetsdata som er relatert til *Kunde*-enheten.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="1f6a6-144">Segmentet ser etter alle kunder som har ringt til brukerstøtteavdelingen i løpet av de siste 60 dagene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="1f6a6-145">Du kan velge å tilføye samtalevarighet og antall samtaler til alle samsvarende kundeoppføringer i utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="1f6a6-146">Denne informasjonen kan være nyttig for å sende en e-post med nyttige koblinger til artikler i elektronisk hjelp og vanlige spørsmål til kunder som ofte har ringt.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="1f6a6-147">Velg **Lagre** for å lagre segmentet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="1f6a6-148">Segmentet blir lagret og behandlet hvis alle kravene valideres.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="1f6a6-149">Hvis ikke blir det lagret som et utkast.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="1f6a6-150">Velg **Tilbake til Segmenter** for å gå tilbake til **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="1f6a6-151">Behandle eksisterende segmenter</span><span class="sxs-lookup"><span data-stu-id="1f6a6-151">Manage existing segments</span></span>

<span data-ttu-id="1f6a6-152">På siden **Segmenter** kan du vise alle lagrede segmenter og administrere dem.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="1f6a6-153">Hvert segment representeres av en rad som inneholder tilleggsinformasjon om segmentet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="1f6a6-154">Du kan sortere segmentene i en kolonne ved å velge kolonneoverskriften.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="1f6a6-155">Bruk **Søk**-boksen øverst i høyre hjørne til å filtrere segmentene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1f6a6-156">![Alternativer for å behandle et eksisterende segment](media/segments-selected-segment.png "Alternativer for å behandle et eksisterende segment")</span><span class="sxs-lookup"><span data-stu-id="1f6a6-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="1f6a6-157">Følgende handling er tilgjengelig når du velger et segment:</span><span class="sxs-lookup"><span data-stu-id="1f6a6-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="1f6a6-158">**Vis** segmentdetaljene, inkludert medlemsantall, som viser en forhåndsvisning av segmentmedlemmer.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="1f6a6-159">**Rediger** segmentet for å endre egenskapene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="1f6a6-160">**Opprett duplikat** av et segment.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="1f6a6-161">Du kan velge å redigere egenskapene med en gang, eller ganske enkelt lagre duplikatet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="1f6a6-162">**Oppdater** segmentet slik at det inneholder de nyeste dataene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="1f6a6-163">**Aktiver** eller **Deaktiver** segmentet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="1f6a6-164">Segmenter har to mulige tilstander – aktive eller inaktive.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="1f6a6-165">Disse tilstandene er nyttige når du redigerer et segment.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="1f6a6-166">For inaktive segmenter finnes segmentdefinisjonen, men den inneholder ingen kunder ennå.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="1f6a6-167">Når du aktiverer et segment, endres statusen fra inaktiv til aktiv, og den begynner å se etter kunder som samsvarer med segmentdefinisjonen.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="1f6a6-168">Hvis en [planlagt oppdatering](system.md#schedule-tab) er konfigurert, har inaktive segmenter **Status** oppført som **Hoppet over**, og dette tyder på at en oppdatering ikke ble forsøkt.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="1f6a6-169">Når et inaktivt segment blir aktivert, oppdateres det og tas med i planlagte oppdateringer.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="1f6a6-170">Du kan også bruke funksjonen **Planlegg senere** i rullegardinlisten **Aktiver/Deaktiver** for å angi en fremtidig dato og klokkeslett for acktivering og deaktivering av et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="1f6a6-171">**Gi nytt navn** til segmentet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-171">**Rename** the segment.</span></span>
- <span data-ttu-id="1f6a6-172">**Last ned** listen over medlemmer som en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="1f6a6-173">**Legg til**-alternativet sender listen over kunde-ID-er i segmentet til behandling i et annet program.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="1f6a6-174">**Slett** segmentet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="1f6a6-175">Oppdatere segmenter</span><span class="sxs-lookup"><span data-stu-id="1f6a6-175">Refresh segments</span></span>

<span data-ttu-id="1f6a6-176">Du kan oppdatere alle segmenter samtidig ved å velge **Oppdater alle** på **Segmenter**-siden, eller du kan oppdatere ett eller flere segmenter når du velger dem, og deretter velge **Oppdater** fra alternativene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="1f6a6-177">Du kan også konfigurere en regelmessig oppdatering under **Admin** > **System** > **Tidsplan**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="1f6a6-178">Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="1f6a6-179">De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="1f6a6-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="1f6a6-180">Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="1f6a6-181">Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="1f6a6-182">Laste ned og eksportere segmenter</span><span class="sxs-lookup"><span data-stu-id="1f6a6-182">Download and export segments</span></span>

<span data-ttu-id="1f6a6-183">Du kan laste ned segmentene til en CSV-fil eller eksportere dem til Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="1f6a6-184">Laste ned segmenter til en CSV-fil</span><span class="sxs-lookup"><span data-stu-id="1f6a6-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="1f6a6-185">I Målgruppeinnsikt går du til **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="1f6a6-186">Velg en ellipse i flisen i et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="1f6a6-187">Velg **Last ned som CSV** fra rullegardinlisten for handlinger.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="1f6a6-188">Eksporter segmenter til Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="1f6a6-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="1f6a6-189">Før du eksporterer segmenter til Dynamics 365 Sales, må en administrator [opprette eksportmålet](export-destinations.md) for Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="1f6a6-190">I Målgruppeinnsikt går du til **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="1f6a6-191">Velg en ellipse i flisen i et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="1f6a6-192">Velg **Legg til i** fra rullegardinlisten for handlinger, og velg eksportmålet du vil sende dataene til.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="1f6a6-193">Kladdemodus for segmenter</span><span class="sxs-lookup"><span data-stu-id="1f6a6-193">Draft mode for segments</span></span>

<span data-ttu-id="1f6a6-194">Hvis ikke alle krav til å behandle et segment er oppfylt, kan du lagre segmentet som et utkast og få tilgang til det fra siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="1f6a6-195">Det blir lagret som et inaktivt segment, og kan ikke aktiveres det før det er gyldig.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="1f6a6-196">Legge til flere betingelser i en gruppe</span><span class="sxs-lookup"><span data-stu-id="1f6a6-196">Add more conditions to a group</span></span>

<span data-ttu-id="1f6a6-197">Hvis du vil legge til flere betingelser i en gruppe, kan du bruke to logiske operatorer:</span><span class="sxs-lookup"><span data-stu-id="1f6a6-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="1f6a6-198">**AND**-operator: Begge betingelser må oppfylles som en del av segmentprosessen.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="1f6a6-199">Dette alternativet er svært nyttig når du definerer betingelser på tvers av forskjellige enheter.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="1f6a6-200">**OR**-operator: En av betingelsene må oppfylles som en del av segmenteringsprosessen.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="1f6a6-201">Dette alternativet er svært nyttig når du definerer flere betingelser for samme enhet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1f6a6-202">![OR-operator der begge betingelser må oppfylles](media/segmentation-either-condition.png "OR-operator der begge betingelser må oppfylles")</span><span class="sxs-lookup"><span data-stu-id="1f6a6-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="1f6a6-203">Det er for øyeblikket mulig å neste en **OR**-operator under en **AND**-operator, men ikke motsatt.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="1f6a6-204">Kombinere flere grupper</span><span class="sxs-lookup"><span data-stu-id="1f6a6-204">Combine multiple groups</span></span>

<span data-ttu-id="1f6a6-205">Hver gruppe produserer et bestemt sett med kunder.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="1f6a6-206">Du kan kombinere disse gruppene slik at de inneholder kundene som kreves for forretningssaken.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="1f6a6-207">I Målgruppeinnsikt går du til **Segmenter**-siden og velger et segemtn.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="1f6a6-208">Velg **Legg til gruppe**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1f6a6-209">![Legg til gruppe i kundegruppe](media/customer-group-add-group.png "Legg til gruppe i kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="1f6a6-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="1f6a6-210">Velg én av følgende sett operatorer: **Union**, **Skjæringspunkt** eller **Unntatt**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1f6a6-211">![Legg til union i kundegruppe](media/customer-group-union.png "Legg til union i kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="1f6a6-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="1f6a6-212">Velg en angitt operator for å definere en ny gruppe.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="1f6a6-213">Lagre forskjellige grupper for å avgjøre hvilke data som beholdes:</span><span class="sxs-lookup"><span data-stu-id="1f6a6-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="1f6a6-214">**Union** forener de to gruppene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="1f6a6-215">**Intersect** overlapper de to gruppene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="1f6a6-216">Bare data som *er felles* for begge gruppene, beholdes i den enhetlige gruppen.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="1f6a6-217">**Bortsett fra** kombinerer de to gruppene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-217">**Except** combines the two groups.</span></span> <span data-ttu-id="1f6a6-218">Bare data i gruppe A som *ikke er felles* med data i gruppe B, beholdes.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="1f6a6-219">Vis behandlingslogg og segmentmedlemmer</span><span class="sxs-lookup"><span data-stu-id="1f6a6-219">View processing history and segment members</span></span>

<span data-ttu-id="1f6a6-220">Du kan vise konsoliderte data om et segment ved å se gjennom detaljene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="1f6a6-221">På siden **Segmenter** velger du segmentet du vil se gjennom.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="1f6a6-222">Den øvre delen av siden inneholder et trendgraf som visualiserer endringer i medlemsantall.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="1f6a6-223">Beveg pekeren over datapunkter for å se medlemsantallet på en bestemt dato.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="1f6a6-224">Du kan oppdatere tidsrammen for visualiseringen.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1f6a6-225">![Tidsintervall for segment](media/segment-time-range.png "Tidsintervall for segment")</span><span class="sxs-lookup"><span data-stu-id="1f6a6-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="1f6a6-226">Den nedre delen inneholder en liste over medlemmene i segmentet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="1f6a6-227">Felt som vises i listen, er basert på attributtene til enhetene i segmentet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="1f6a6-228">Listen er en forhåndsvisning av de samsvarende segmentmedlemmene og viser de første 100 oppføringene av segmentet, slik at du raskt kan evaluere det og se gjennom definisjonene hvis det er nødvendig.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="1f6a6-229">Hvis du vil vise alle samsvarende oppføringer, må du [eksportere segmentet](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1f6a6-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="1f6a6-230">Hurtigsegmenter</span><span class="sxs-lookup"><span data-stu-id="1f6a6-230">Quick segments</span></span>

<span data-ttu-id="1f6a6-231">I tillegg til segmentverktøyet finnes det en annen bane for oppretting av segmenter.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="1f6a6-232">Med hurtigsegmenter kan du bygge enkle segmenter (med én enkelt operator) raskt og med direkte innsikt.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="1f6a6-233">På **Segmenter**-siden velger du **Ny** > **Hurtigopprett fra**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="1f6a6-234">Velg alternativet **Profiler** for å bygge et segment som er basert på den enhetlige kundeenheten.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="1f6a6-235">Velg alternativet **Mål** for å bygge et segment rundt hver av Kundeattributt-måltypene du tidligere har opprettet på **Mål**-siden.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="1f6a6-236">Velg alternativet **Intelligens** for å bygge et segment rundt én av de utgående enhetene du genererte ved hjelp av funksjonene **Prediksjoner** eller **Egendefinerte modeller**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="1f6a6-237">I dialogboksen **Nytt hurtigsegment** velger du et attributt fra **Felt**-rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="1f6a6-238">Systemet gir noe ekstra innsikt som hjelper deg med å lage bedre segmenter av kundene.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="1f6a6-239">Vi viser de 10 største kundeantallene for kategoriske felt.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="1f6a6-240">Velg en **Verdi** og deretter **Gå gjennom**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="1f6a6-241">For et numerisk attributt vil systemet vise hvilken attributtverdi som faller under hver kundepersentil.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="1f6a6-242">Velg en **Operator** og en **Verdi**, og velg deretter **Gå gjennom**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="1f6a6-243">Systemet gir deg en **Beregnet segmentstørrelse**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="1f6a6-244">Du kan velge om du vil generere segmentet du har definert, eller først gå til det igjen for å få en annen segmentstørrelse.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1f6a6-245">![Navn og beregning for et hurtigsegment](media/quick-segment-name.png "Navn og beregning for et hurtigsegment")</span><span class="sxs-lookup"><span data-stu-id="1f6a6-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="1f6a6-246">Angi et **Navn** for segmentet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="1f6a6-247">Alternativt kan du angi et **Visningsnavn**.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="1f6a6-248">Velg **Lagre** for å opprette segmentet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="1f6a6-249">Når segmentet er ferdig behandlet, kan du vise det på samme måte som et hvilket som helst segment du har opprettet.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="1f6a6-250">I følgende scenarioer anbefaler vi å bruke segmentverktøyet i stedet for den anbefalte segmentfunksjonen:</span><span class="sxs-lookup"><span data-stu-id="1f6a6-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="1f6a6-251">Opprette segmenter med filtre i kategorifelt der operatoren er forskjellig fra **Is**-operatoren</span><span class="sxs-lookup"><span data-stu-id="1f6a6-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="1f6a6-252">Opprette segmenter med filtre på numeriske felt der operatoren er forskjellig fra operatorene **Mellom**, **Større enn** og **Mindre enn**</span><span class="sxs-lookup"><span data-stu-id="1f6a6-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="1f6a6-253">Opprette segmenter med filtre på datotype-felt</span><span class="sxs-lookup"><span data-stu-id="1f6a6-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="1f6a6-254">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="1f6a6-254">Next steps</span></span>

<span data-ttu-id="1f6a6-255">[Eksporter et segment](export-destinations.md) og utforsk [Kundekort](customer-card-add-in.md) og [Koblinger](export-power-bi.md) for å få innsikt på kundenivået.</span><span class="sxs-lookup"><span data-stu-id="1f6a6-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]