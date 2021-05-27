---
title: Slå sammen enheter i dataforening
description: Slå sammen enheter for å opprette enhetlige kundeprofiler.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085588"
---
# <a name="merge-entities"></a><span data-ttu-id="41170-103">Slå sammen enheter</span><span class="sxs-lookup"><span data-stu-id="41170-103">Merge entities</span></span>

<span data-ttu-id="41170-104">Sammenslåingsfasen er den siste fasen i datasamlingsprosessen.</span><span class="sxs-lookup"><span data-stu-id="41170-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="41170-105">Formålet er avstemming av data er i konflikt.</span><span class="sxs-lookup"><span data-stu-id="41170-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="41170-106">Eksempler på motstridende data kan omfatte et kundenavn som finnes i to av datasettene, men som vises litt ulikt i hvert sett ("Kari Nordmann" kontra "Kari Nordman"), eller et telefonnummer som er forskjellig i format (617-803-091X kontra 617803091X).</span><span class="sxs-lookup"><span data-stu-id="41170-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="41170-107">Sammenslåing av de motstridende datapunktene utføres på attributtbasis.</span><span class="sxs-lookup"><span data-stu-id="41170-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Slå sammen-siden i dataforeningsprosessen som viser tabell med sammenslåtte felter som definerer den enhetlige kundeprofilen.":::

<span data-ttu-id="41170-109">Når du har fullført [samsvarsfasen](match-entities.md), kan du starte sammenslåingsfasen ved å velge flisen **Flett** på siden **Samle**.</span><span class="sxs-lookup"><span data-stu-id="41170-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="41170-110">Gå gjennom systemanbefalinger</span><span class="sxs-lookup"><span data-stu-id="41170-110">Review system recommendations</span></span>

<span data-ttu-id="41170-111">I **Data** > **Samle** > **Slå sammen** velger og utelater du attributter som skal slås sammen inn i enheten for enhetlig kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="41170-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="41170-112">Den enhetlige kundeprofilen er et resultat av dataforeningsprosessen.</span><span class="sxs-lookup"><span data-stu-id="41170-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="41170-113">Noen attributter blir automatisk slått sammen av systemet.</span><span class="sxs-lookup"><span data-stu-id="41170-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="41170-114">Hvis du vil vise attributtene som er inkludert i ett av de automatisk sammenslåtte attributtene, velger du det sammenslåtte attributtet i fanen **Kundefelter** i tabellen.</span><span class="sxs-lookup"><span data-stu-id="41170-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="41170-115">Attributtene som utgjør det sammenslåtte attributtet, vises i to nye rader under det flettede attributtet.</span><span class="sxs-lookup"><span data-stu-id="41170-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="41170-116">Del opp, gi nytt navn til, utelat og rediger sammenslåtte felter</span><span class="sxs-lookup"><span data-stu-id="41170-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="41170-117">Du kan endre hvordan systemet behandler sammenslåtte attributter for å generere den enhetlige kundeprofilen.</span><span class="sxs-lookup"><span data-stu-id="41170-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="41170-118">Velg **Vis mer** og velg hva du vil endre.</span><span class="sxs-lookup"><span data-stu-id="41170-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Alternativer i rullegardinlisten Vis mer for å behandle sammenslåtte attributter.":::

<span data-ttu-id="41170-120">Se følgende deler hvis du vil ha mer informasjon.</span><span class="sxs-lookup"><span data-stu-id="41170-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="41170-121">Del sammenslåtte felter</span><span class="sxs-lookup"><span data-stu-id="41170-121">Separate merged fields</span></span>

<span data-ttu-id="41170-122">Du skiller sammenslåtte felter ved å finne attributtet i tabellen.</span><span class="sxs-lookup"><span data-stu-id="41170-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="41170-123">Delte felter vises som individuelle datapunkter i den enhetlige kundeprofilen.</span><span class="sxs-lookup"><span data-stu-id="41170-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="41170-124">Velg det sammenslåtte feltet.</span><span class="sxs-lookup"><span data-stu-id="41170-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="41170-125">Velg **Vis mer** og velg **Del felter**.</span><span class="sxs-lookup"><span data-stu-id="41170-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="41170-126">Bekreft delingen.</span><span class="sxs-lookup"><span data-stu-id="41170-126">Confirm the separation.</span></span>

1. <span data-ttu-id="41170-127">Velg **Lagre** og **Kjør** for å behandle endringene.</span><span class="sxs-lookup"><span data-stu-id="41170-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="41170-128">Gi nytt navn til sammenslåtte felter</span><span class="sxs-lookup"><span data-stu-id="41170-128">Rename merged fields</span></span>

<span data-ttu-id="41170-129">Endre visningsnavnet for sammenslåtte attributter.</span><span class="sxs-lookup"><span data-stu-id="41170-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="41170-130">Du kan ikke endre navnet på utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="41170-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="41170-131">Velg det sammenslåtte feltet.</span><span class="sxs-lookup"><span data-stu-id="41170-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="41170-132">Velg **Vis mer** og velg **Gi nytt navn**.</span><span class="sxs-lookup"><span data-stu-id="41170-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="41170-133">Bekreft det endrede visningsnavnet.</span><span class="sxs-lookup"><span data-stu-id="41170-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="41170-134">Velg **Lagre** og **Kjør** for å behandle endringene.</span><span class="sxs-lookup"><span data-stu-id="41170-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="41170-135">Utelatt sammenslåtte felter</span><span class="sxs-lookup"><span data-stu-id="41170-135">Exclude merged fields</span></span>

<span data-ttu-id="41170-136">Utelat et attributt fra den enhetlige kundeprofilen.</span><span class="sxs-lookup"><span data-stu-id="41170-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="41170-137">Hvis feltet brukes i andre prosesser, for eksempel i et segment, fjerner du det fra disse prosessene før du utelater det fra kundeprofilen.</span><span class="sxs-lookup"><span data-stu-id="41170-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="41170-138">Velg det sammenslåtte feltet.</span><span class="sxs-lookup"><span data-stu-id="41170-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="41170-139">Velg **Vis mer** og velg **Utelat**.</span><span class="sxs-lookup"><span data-stu-id="41170-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="41170-140">Bekreft utelatelsen.</span><span class="sxs-lookup"><span data-stu-id="41170-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="41170-141">Velg **Lagre** og **Kjør** for å behandle endringene.</span><span class="sxs-lookup"><span data-stu-id="41170-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="41170-142">Velg **Utelatte felter** på **Slå sammen**-siden for å vise listen over alle utelatte felter.</span><span class="sxs-lookup"><span data-stu-id="41170-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="41170-143">I denne ruten kan du legge til utelatte felter på nytt.</span><span class="sxs-lookup"><span data-stu-id="41170-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="41170-144">Kombiner felter manuelt</span><span class="sxs-lookup"><span data-stu-id="41170-144">Manually combine fields</span></span>

<span data-ttu-id="41170-145">Angi et sammenslått attributt manuelt.</span><span class="sxs-lookup"><span data-stu-id="41170-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="41170-146">Velg **Kombiner felter** på **Slå sammen**-siden.</span><span class="sxs-lookup"><span data-stu-id="41170-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="41170-147">Angi et **navn** og et **navn på utdatafelt**.</span><span class="sxs-lookup"><span data-stu-id="41170-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="41170-148">Veg et felt du vil legge til.</span><span class="sxs-lookup"><span data-stu-id="41170-148">Choose a field to add.</span></span> <span data-ttu-id="41170-149">Velg **Legg til felter** for å kombinere flere felter.</span><span class="sxs-lookup"><span data-stu-id="41170-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="41170-150">Bekreft utelatelsen.</span><span class="sxs-lookup"><span data-stu-id="41170-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="41170-151">Velg **Lagre** og **Kjør** for å behandle endringene.</span><span class="sxs-lookup"><span data-stu-id="41170-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="41170-152">Endre rekkefølgen på feltene</span><span class="sxs-lookup"><span data-stu-id="41170-152">Change the order of fields</span></span>

<span data-ttu-id="41170-153">Noen enheter inneholder flere detaljer enn andre.</span><span class="sxs-lookup"><span data-stu-id="41170-153">Some entities contain more details than others.</span></span> <span data-ttu-id="41170-154">Hvis en enhet inneholder de nyeste dataene om et felt, kan du prioritere det over andre enheter ved å slå sammen verdier.</span><span class="sxs-lookup"><span data-stu-id="41170-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="41170-155">Velg det sammenslåtte feltet.</span><span class="sxs-lookup"><span data-stu-id="41170-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="41170-156">Velg **Vis mer** og velg **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="41170-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="41170-157">Velg **Flytt opp/ned** i **Kombiner felter**-ruten for å angi rekkefølgen, eller dra og slipp dem i ønsket posisjon.</span><span class="sxs-lookup"><span data-stu-id="41170-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="41170-158">Bekreft endringen.</span><span class="sxs-lookup"><span data-stu-id="41170-158">Confirm the change.</span></span>

1. <span data-ttu-id="41170-159">Velg **Lagre** og **Kjør** for å behandle endringene.</span><span class="sxs-lookup"><span data-stu-id="41170-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="41170-160">Kjøre flettingen</span><span class="sxs-lookup"><span data-stu-id="41170-160">Run your merge</span></span>

<span data-ttu-id="41170-161">Uansett om du slår sammen attributter manuelt eller lar programmet slå dem sammen, kan du alltid kjøre flettingen.</span><span class="sxs-lookup"><span data-stu-id="41170-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="41170-162">Velg **Kjør** på siden **Slå sammen** for å starte prosessen.</span><span class="sxs-lookup"><span data-stu-id="41170-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41170-163">![Lagre og kjøre datasammenslåing](media/configure-data-merge-save-run.png "Lagre og kjøre datasammenslåing")</span><span class="sxs-lookup"><span data-stu-id="41170-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="41170-164">Velg **Kjør bare fletting** hvis du bare vil vise utdataene i enheten for enhetlig kunde.</span><span class="sxs-lookup"><span data-stu-id="41170-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="41170-165">Nedstrømsprosesser oppdateres som [definert i oppdateringsplanen](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="41170-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="41170-166">Velg **Kjør fletting og nedstrømsprosesser** for å oppdatere systemet med endringene.</span><span class="sxs-lookup"><span data-stu-id="41170-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="41170-167">Alle prosesser, inkludert supplering, segmenter og mål, kjører på nytt automatisk.</span><span class="sxs-lookup"><span data-stu-id="41170-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="41170-168">Når alle nedstrømsprosesser er fullført, gjenspeiler kundeprofilene endringene du har gjort.</span><span class="sxs-lookup"><span data-stu-id="41170-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="41170-169">Hvis du vil gjøre flere endringer og kjøre trinnet på nytt, kan du avbryte en pågående fletting.</span><span class="sxs-lookup"><span data-stu-id="41170-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="41170-170">Velg **Oppdaterer ...**, og velg **Avbryt jobb** i sideruten som vises.</span><span class="sxs-lookup"><span data-stu-id="41170-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="41170-171">Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser.</span><span class="sxs-lookup"><span data-stu-id="41170-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="41170-172">De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="41170-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="41170-173">Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben.</span><span class="sxs-lookup"><span data-stu-id="41170-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="41170-174">Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.</span><span class="sxs-lookup"><span data-stu-id="41170-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="41170-175">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="41170-175">Next Step</span></span>

<span data-ttu-id="41170-176">Konfigurer [aktiviteter](activities.md), [supplering](enrichment-hub.md) eller [relasjoner](relationships.md) for å få mer informasjon om kundene.</span><span class="sxs-lookup"><span data-stu-id="41170-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="41170-177">Hvis du allerede har konfigurert aktiviteter, supplering eller segmenter, behandles de automatisk for å bruke de nyeste kundedataene.</span><span class="sxs-lookup"><span data-stu-id="41170-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
