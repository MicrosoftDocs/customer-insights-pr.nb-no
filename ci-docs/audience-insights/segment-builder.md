---
title: Opprette og behandle segmenter
description: Opprett segmenter av kunder for å gruppere dem basert på forskjellige attributter.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064949"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="03ddb-103">Opprette og behandle segmenter</span><span class="sxs-lookup"><span data-stu-id="03ddb-103">Create and manage segments</span></span>

<span data-ttu-id="03ddb-104">Definer komplekse filtre rundt enheten for enhetlig kunde og de relaterte enhetene.</span><span class="sxs-lookup"><span data-stu-id="03ddb-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="03ddb-105">Hvert segment, etter behandlingen, oppretter et sett med kundeoppføringer som du kan eksportere og utføre handlinger på.</span><span class="sxs-lookup"><span data-stu-id="03ddb-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="03ddb-106">Segmenter administreres på **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="03ddb-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="03ddb-107">Eksemplet nedenfor viser bruken av segmenteringsfunksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="03ddb-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="03ddb-108">Vi har definert et segment for kunder som har bestilt varer for minst USD 500 i løpet av de siste 90 dagene *og* som var involvert i en kundeservicesamtale som ble videresendt.</span><span class="sxs-lookup"><span data-stu-id="03ddb-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Skjermbilde av grensesnittet for segmentverktøyet med to grupper som angir et kundesegment.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="03ddb-110">Opprett et nytt segment</span><span class="sxs-lookup"><span data-stu-id="03ddb-110">Create a new segment</span></span>

<span data-ttu-id="03ddb-111">Du kan opprette et nytt segment på flere måter.</span><span class="sxs-lookup"><span data-stu-id="03ddb-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="03ddb-112">Denne delen beskriver hvordan du oppretter et *tomt segment* fra bunnen av.</span><span class="sxs-lookup"><span data-stu-id="03ddb-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="03ddb-113">Du kan også opprette et *hurtigsegment* basert på eksisterende enheter eller bruke maskinlæringsmodeller til å få *foreslåtte segmenter*.</span><span class="sxs-lookup"><span data-stu-id="03ddb-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="03ddb-114">Mer informasjon: [Oversikt over segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="03ddb-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="03ddb-115">Når du oppretter et segment, kan du lagre et utkast.</span><span class="sxs-lookup"><span data-stu-id="03ddb-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="03ddb-116">Det blir lagret som et inaktivt segment og kan ikke aktiveres slik at det blir fullført med en gyldig konfigurasjon.</span><span class="sxs-lookup"><span data-stu-id="03ddb-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="03ddb-117">Gå til siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="03ddb-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="03ddb-118">Velg **Ny** > **Tomt segment**.</span><span class="sxs-lookup"><span data-stu-id="03ddb-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="03ddb-119">Velg en segmenttype i ruten **Ny segment**:</span><span class="sxs-lookup"><span data-stu-id="03ddb-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="03ddb-120">**Dynamiske segmenter** [oppdateres](segments.md#refresh-segments) i en regelmessig tidsplan.</span><span class="sxs-lookup"><span data-stu-id="03ddb-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="03ddb-121">**Statiske segmenter** kjører én gang når du oppretter den.</span><span class="sxs-lookup"><span data-stu-id="03ddb-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="03ddb-122">Angi et **navn på utdataenheten** for segmentet.</span><span class="sxs-lookup"><span data-stu-id="03ddb-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="03ddb-123">Du kan eventuelt angi et visningsnavn og en beskrivelse som hjelper deg med å identifisere segmentet.</span><span class="sxs-lookup"><span data-stu-id="03ddb-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="03ddb-124">Velg **Neste** for å gå til siden for **Segmentverktøy**, der du definerer en gruppe.</span><span class="sxs-lookup"><span data-stu-id="03ddb-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="03ddb-125">En gruppe er et sett med kunder.</span><span class="sxs-lookup"><span data-stu-id="03ddb-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="03ddb-126">Velg enheten som inkluderer attributtet du vil segmentere etter.</span><span class="sxs-lookup"><span data-stu-id="03ddb-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="03ddb-127">Velg attributtet du vil segmentere etter.</span><span class="sxs-lookup"><span data-stu-id="03ddb-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="03ddb-128">Dette attributtet kan ha en av fire verdityper: numerisk, streng, dato eller boolsk.</span><span class="sxs-lookup"><span data-stu-id="03ddb-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="03ddb-129">Velg en operator og en verdi for det valgte attributtet.</span><span class="sxs-lookup"><span data-stu-id="03ddb-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03ddb-130">![Egendefinert gruppefilter](media/customer-group-numbers.png "Gruppefilter for kunde")</span><span class="sxs-lookup"><span data-stu-id="03ddb-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="03ddb-131">Antall</span><span class="sxs-lookup"><span data-stu-id="03ddb-131">Number</span></span> |<span data-ttu-id="03ddb-132">Definisjon</span><span class="sxs-lookup"><span data-stu-id="03ddb-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="03ddb-133">1</span><span class="sxs-lookup"><span data-stu-id="03ddb-133">1</span></span>     |<span data-ttu-id="03ddb-134">Entity</span><span class="sxs-lookup"><span data-stu-id="03ddb-134">Entity</span></span>          |
   |<span data-ttu-id="03ddb-135">2</span><span class="sxs-lookup"><span data-stu-id="03ddb-135">2</span></span>     |<span data-ttu-id="03ddb-136">Attributt</span><span class="sxs-lookup"><span data-stu-id="03ddb-136">Attribute</span></span>          |
   |<span data-ttu-id="03ddb-137">3</span><span class="sxs-lookup"><span data-stu-id="03ddb-137">3</span></span>    |<span data-ttu-id="03ddb-138">Operatør</span><span class="sxs-lookup"><span data-stu-id="03ddb-138">Operator</span></span>         |
   |<span data-ttu-id="03ddb-139">4</span><span class="sxs-lookup"><span data-stu-id="03ddb-139">4</span></span>    |<span data-ttu-id="03ddb-140">Verdi</span><span class="sxs-lookup"><span data-stu-id="03ddb-140">Value</span></span>         |

   1. <span data-ttu-id="03ddb-141">Hvis du vil legge til flere betingelser i en gruppe, kan du bruke to logiske operatorer:</span><span class="sxs-lookup"><span data-stu-id="03ddb-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="03ddb-142">**AND**-operator: Begge betingelser må oppfylles som en del av segmentprosessen.</span><span class="sxs-lookup"><span data-stu-id="03ddb-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="03ddb-143">Dette alternativet er svært nyttig når du definerer betingelser på tvers av forskjellige enheter.</span><span class="sxs-lookup"><span data-stu-id="03ddb-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="03ddb-144">**OR**-operator: En av betingelsene må oppfylles som en del av segmenteringsprosessen.</span><span class="sxs-lookup"><span data-stu-id="03ddb-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="03ddb-145">Dette alternativet er svært nyttig når du definerer flere betingelser for samme enhet.</span><span class="sxs-lookup"><span data-stu-id="03ddb-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="03ddb-146">![OR-operator der begge betingelser må oppfylles](media/segmentation-either-condition.png "OR-operator der begge betingelser må oppfylles")</span><span class="sxs-lookup"><span data-stu-id="03ddb-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="03ddb-147">Det er for øyeblikket mulig å neste en **OR**-operator under en **AND**-operator, men ikke motsatt.</span><span class="sxs-lookup"><span data-stu-id="03ddb-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="03ddb-148">Hver gruppe samsvarer til et sett med kunder.</span><span class="sxs-lookup"><span data-stu-id="03ddb-148">Each group matches set of customers.</span></span> <span data-ttu-id="03ddb-149">Du kan kombinere grupper for å inkludere kundene som kreves for forretningssaken.</span><span class="sxs-lookup"><span data-stu-id="03ddb-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="03ddb-150">Velg **Legg til gruppe**.</span><span class="sxs-lookup"><span data-stu-id="03ddb-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="03ddb-151">![Legg til gruppe i kundegruppe](media/customer-group-add-group.png "Legg til gruppe i kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="03ddb-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="03ddb-152">Velg en av de angitte operatorer: **Union**, **Skjæringspunkt** eller **Unntatt**.</span><span class="sxs-lookup"><span data-stu-id="03ddb-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03ddb-153">![Legg til union i kundegruppe](media/customer-group-union.png "Legg til union i kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="03ddb-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="03ddb-154">**Union** forener de to gruppene.</span><span class="sxs-lookup"><span data-stu-id="03ddb-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="03ddb-155">**Intersect** overlapper de to gruppene.</span><span class="sxs-lookup"><span data-stu-id="03ddb-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="03ddb-156">Bare data som *er felles* for begge gruppene, beholdes i den enhetlige gruppen.</span><span class="sxs-lookup"><span data-stu-id="03ddb-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="03ddb-157">**Bortsett fra** kombinerer de to gruppene.</span><span class="sxs-lookup"><span data-stu-id="03ddb-157">**Except** combines the two groups.</span></span> <span data-ttu-id="03ddb-158">Bare data i gruppe A som *ikke er felles* med data i gruppe B, beholdes.</span><span class="sxs-lookup"><span data-stu-id="03ddb-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="03ddb-159">Hvis enheten er koblet til den enhetlige kundeenheten via [relasjoner](relationships.md), må du definere relasjonsbanen for å opprette et gyldig segment.</span><span class="sxs-lookup"><span data-stu-id="03ddb-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="03ddb-160">Legg til enhetene fra relasjonsbanen til du kan velge **Kunde: CustomerInsights**-enheten fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="03ddb-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="03ddb-161">Deretter velger du **Alle oppføringer** for hvert trinn.</span><span class="sxs-lookup"><span data-stu-id="03ddb-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03ddb-162">![Relasjonsbane under opprettelse av segment](media/segments-multiple-relationships.png "Relasjonsbane under opprettelse av segment")</span><span class="sxs-lookup"><span data-stu-id="03ddb-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="03ddb-163">Som standard genererer segmenter en utdataenhet som inneholder alle attributter for kundeprofiler som samsvarer med de definerte filtrene.</span><span class="sxs-lookup"><span data-stu-id="03ddb-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="03ddb-164">Hvis et segment er basert på andre enheter enn *Kunde*-enheten, kan du legge til flere attributter fra disse enhetene i utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="03ddb-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="03ddb-165">Velg **Prosjektattributter** for å velge attributtene som skal legges til i utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="03ddb-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="03ddb-166">Eksempel: Et segment er basert på en enhet som inneholder kundeaktivitetsdata som er relatert til *Kunde*-enheten.</span><span class="sxs-lookup"><span data-stu-id="03ddb-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="03ddb-167">Segmentet ser etter alle kunder som har ringt til brukerstøtteavdelingen i løpet av de siste 60 dagene.</span><span class="sxs-lookup"><span data-stu-id="03ddb-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="03ddb-168">Du kan velge å tilføye samtalevarighet og antall samtaler til alle samsvarende kundeoppføringer i utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="03ddb-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="03ddb-169">Denne informasjonen kan være nyttig for å sende en e-post med nyttige koblinger til artikler i elektronisk hjelp og vanlige spørsmål til kunder som ofte har ringt.</span><span class="sxs-lookup"><span data-stu-id="03ddb-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="03ddb-170">Beregnede attributter fungerer bare for enheter som har en én-til-mange-relasjon med kundeenheten.</span><span class="sxs-lookup"><span data-stu-id="03ddb-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="03ddb-171">Én kunde kan for eksempel ha flere abonnementer.</span><span class="sxs-lookup"><span data-stu-id="03ddb-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="03ddb-172">Du kan bare prosjektere attributter fra en enhet som brukes i hver gruppe med segmentspørringer du bygger.</span><span class="sxs-lookup"><span data-stu-id="03ddb-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="03ddb-173">Beregnede attributter beregner ved bruk av angitte operatorer.</span><span class="sxs-lookup"><span data-stu-id="03ddb-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="03ddb-174">Velg **Lagre** for å lagre segmentet.</span><span class="sxs-lookup"><span data-stu-id="03ddb-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="03ddb-175">Segmentet blir lagret og behandlet hvis alle kravene valideres.</span><span class="sxs-lookup"><span data-stu-id="03ddb-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="03ddb-176">Hvis ikke blir det lagret som et utkast.</span><span class="sxs-lookup"><span data-stu-id="03ddb-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="03ddb-177">Velg **Tilbake til Segmenter** for å gå tilbake til **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="03ddb-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="03ddb-178">Hurtigsegmenter</span><span class="sxs-lookup"><span data-stu-id="03ddb-178">Quick segments</span></span>

<span data-ttu-id="03ddb-179">Med hurtigsegmenter kan du bygge enkle segmenter med én operator raskt for raskere innsikt.</span><span class="sxs-lookup"><span data-stu-id="03ddb-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="03ddb-180">Velg **Ny** > **Opprett fra** på siden **Segment**.</span><span class="sxs-lookup"><span data-stu-id="03ddb-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="03ddb-181">Velg alternativet **Profiler** for å bygge et segment som er basert på den *enhetlige kundeenheten*.</span><span class="sxs-lookup"><span data-stu-id="03ddb-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="03ddb-182">Velg **Mål**-alternativet for å bygge et segment rundt mål du tidligere har opprettet.</span><span class="sxs-lookup"><span data-stu-id="03ddb-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="03ddb-183">Velg alternativet **Intelligens** for å bygge et segment rundt én av de utgående enhetene du genererte ved hjelp av funksjonene **Prediksjoner** eller **Egendefinerte modeller**.</span><span class="sxs-lookup"><span data-stu-id="03ddb-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="03ddb-184">I dialogboksen **Nytt hurtigsegment** velger du et attributt fra **Felt**-rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="03ddb-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="03ddb-185">Systemet gir noe ekstra innsikt som hjelper deg med å lage bedre segmenter av kundene.</span><span class="sxs-lookup"><span data-stu-id="03ddb-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="03ddb-186">Vi viser de 10 største kundeantallene for kategoriske felt.</span><span class="sxs-lookup"><span data-stu-id="03ddb-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="03ddb-187">Velg en **Verdi** og deretter **Gå gjennom**.</span><span class="sxs-lookup"><span data-stu-id="03ddb-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="03ddb-188">For et numerisk attributt vil systemet vise hvilken attributtverdi som faller under hver kundepersentil.</span><span class="sxs-lookup"><span data-stu-id="03ddb-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="03ddb-189">Velg en **Operator** og en **Verdi**, og velg deretter **Gå gjennom**.</span><span class="sxs-lookup"><span data-stu-id="03ddb-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="03ddb-190">Systemet gir deg en **Beregnet segmentstørrelse**.</span><span class="sxs-lookup"><span data-stu-id="03ddb-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="03ddb-191">Du kan velge om du vil generere segmentet du har definert, eller først gå til det igjen for å få en annen segmentstørrelse.</span><span class="sxs-lookup"><span data-stu-id="03ddb-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="03ddb-192">![Navn og beregning for et hurtigsegment](media/quick-segment-name.png "Navn og beregning for et hurtigsegment")</span><span class="sxs-lookup"><span data-stu-id="03ddb-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="03ddb-193">Angi et **Navn** for segmentet.</span><span class="sxs-lookup"><span data-stu-id="03ddb-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="03ddb-194">Alternativt kan du angi et **Visningsnavn**.</span><span class="sxs-lookup"><span data-stu-id="03ddb-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="03ddb-195">Velg **Lagre** for å opprette segmentet.</span><span class="sxs-lookup"><span data-stu-id="03ddb-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="03ddb-196">Når segmentet er ferdig behandlet, kan du vise det på samme måte som et hvilket som helst segment du har opprettet.</span><span class="sxs-lookup"><span data-stu-id="03ddb-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="03ddb-197">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="03ddb-197">Next steps</span></span>

<span data-ttu-id="03ddb-198">[Eksporter et segment](export-destinations.md) og utforsk [Kundekort](customer-card-add-in.md) og [Koblinger](export-power-bi.md) for å få innsikt på kundenivået.</span><span class="sxs-lookup"><span data-stu-id="03ddb-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
