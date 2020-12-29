---
title: Slå sammen enheter i dataforening
description: Slå sammen enheter for å opprette enhetlige kundeprofiler.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406531"
---
# <a name="merge-entities"></a><span data-ttu-id="42678-103">Slå sammen enheter</span><span class="sxs-lookup"><span data-stu-id="42678-103">Merge entities</span></span>

<span data-ttu-id="42678-104">Sammenslåingsfasen er den siste fasen i datasamlingsprosessen.</span><span class="sxs-lookup"><span data-stu-id="42678-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="42678-105">Formålet er avstemming av data er i konflikt.</span><span class="sxs-lookup"><span data-stu-id="42678-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="42678-106">Eksempler på motstridende data kan omfatte et kundenavn som finnes i to av datasettene, men som vises litt ulikt i hvert sett ("Kari Nordmann" kontra "Kari Nordman"), eller et telefonnummer som er forskjellig i format (617-803-091X kontra 617803091X).</span><span class="sxs-lookup"><span data-stu-id="42678-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="42678-107">Sammenslåing av de motstridende datapunktene utføres på attributtbasis.</span><span class="sxs-lookup"><span data-stu-id="42678-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="42678-108">Når du har fullført [samsvarsfasen](match-entities.md), kan du starte sammenslåingsfasen ved å velge flisen **Flett** på siden **Samle**.</span><span class="sxs-lookup"><span data-stu-id="42678-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="42678-109">Gå gjennom systemanbefalinger</span><span class="sxs-lookup"><span data-stu-id="42678-109">Review system recommendations</span></span>

<span data-ttu-id="42678-110">På siden **Flett** velger og utelater du attributter som skal slås sammen i den enhetlige kundeprofilenheten (resultatet av konfigurasjonsprosessen).</span><span class="sxs-lookup"><span data-stu-id="42678-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="42678-111">Noen attributter blir automatisk slått sammen av systemet.</span><span class="sxs-lookup"><span data-stu-id="42678-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="42678-112">Vise sammenslåtte attributter</span><span class="sxs-lookup"><span data-stu-id="42678-112">View merged attributes</span></span>

<span data-ttu-id="42678-113">Hvis du vil vise attributtene som er inkludert i et av de automatisk sammenslåtte attributtene, velger du det sammenslåtte attributtet.</span><span class="sxs-lookup"><span data-stu-id="42678-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="42678-114">De to attributtene som utgjør det flettede attributtet, vises i to nye rader under det flettede attributtet.</span><span class="sxs-lookup"><span data-stu-id="42678-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42678-115">![Velg sammenslått attributt](media/configure-data-merge-profile-attributes.png "Velge sammenslått attributt")</span><span class="sxs-lookup"><span data-stu-id="42678-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="42678-116">Separat sammenslåtte attributter</span><span class="sxs-lookup"><span data-stu-id="42678-116">Separate merged attributes</span></span>

<span data-ttu-id="42678-117">Hvis du vil skille eller fjerne sammenslåingen av noen av de automatisk flettede attributtene, kan du finne attributtet i tabellen **Profilattributter**.</span><span class="sxs-lookup"><span data-stu-id="42678-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="42678-118">Merk elliseknappen (...).</span><span class="sxs-lookup"><span data-stu-id="42678-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="42678-119">Velg **Separate felt** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="42678-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="42678-120">Fjerne sammenslåtte attributter</span><span class="sxs-lookup"><span data-stu-id="42678-120">Remove merged attributes</span></span>

<span data-ttu-id="42678-121">Hvis du vil utelate et attributt fra den endelige kundeprofilenheten, finner du det i tabellen **Profilattributter**.</span><span class="sxs-lookup"><span data-stu-id="42678-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="42678-122">Merk elliseknappen (...).</span><span class="sxs-lookup"><span data-stu-id="42678-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="42678-123">Velg **Ikke slå sammen** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="42678-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="42678-124">Attributtet flyttes til delen **Fjernet fra kundeoppføring**.</span><span class="sxs-lookup"><span data-stu-id="42678-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="42678-125">Legge til et flettet attributt manuelt</span><span class="sxs-lookup"><span data-stu-id="42678-125">Manually add a merged attribute</span></span>

<span data-ttu-id="42678-126">Hvis du vil legge til et flettet attributt, går du til siden **Slå sammen**.</span><span class="sxs-lookup"><span data-stu-id="42678-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="42678-127">Velg **Legg til sammenslått attributt**.</span><span class="sxs-lookup"><span data-stu-id="42678-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="42678-128">Angi et **Navn** for å identifisere det på siden **Slå sammen** senere.</span><span class="sxs-lookup"><span data-stu-id="42678-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="42678-129">Du kan eventuelt angi et **Visningsnavn** som skal vises i den enhetlige kundeprofilenheten.</span><span class="sxs-lookup"><span data-stu-id="42678-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="42678-130">Konfigurer **Velg duplikatattributter** for å velge attributtene du vil slå sammen, fra de samsvarende enhetene.</span><span class="sxs-lookup"><span data-stu-id="42678-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="42678-131">Du kan også søke etter attributter.</span><span class="sxs-lookup"><span data-stu-id="42678-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="42678-132">Angi **Ranger etter viktighet** for å prioritere ett attributt over de andre.</span><span class="sxs-lookup"><span data-stu-id="42678-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="42678-133">Hvis for eksempel enheten *WebAccountCSV* inneholder de mest nøyaktige dataene om attributtet *Fullt navn*, kan du prioritere denne enheten over *ContactCSV* ved å velge *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="42678-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="42678-134">Som et resultat flytter *WebAccountCSV* til førsteprioritet, mens *ContactCSV* flytter til andreprioritet når det hentes verdier for attributet *Fullt navn*.</span><span class="sxs-lookup"><span data-stu-id="42678-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="42678-135">Kjøre flettingen</span><span class="sxs-lookup"><span data-stu-id="42678-135">Run your merge</span></span>

<span data-ttu-id="42678-136">Uansett om du slår sammen attributter manuelt eller lar programmet slå dem sammen, kan du alltid kjøre flettingen.</span><span class="sxs-lookup"><span data-stu-id="42678-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="42678-137">Velg **Kjør** på siden **Slå sammen** for å starte prosessen.</span><span class="sxs-lookup"><span data-stu-id="42678-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42678-138">![Lagre og kjøre datasammenslåing](media/configure-data-merge-save-run.png "Lagre og kjøre datasammenslåing")</span><span class="sxs-lookup"><span data-stu-id="42678-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="42678-139">Hvis du vil gjøre flere endringer og kjøre trinnet på nytt, kan du annullere en sammenslåing som pågår.</span><span class="sxs-lookup"><span data-stu-id="42678-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="42678-140">Velg **Oppdaterer ...**, og velg **Avbryt jobb** i sideruten som vises.</span><span class="sxs-lookup"><span data-stu-id="42678-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="42678-141">Etter at teksten **Oppdaterer ...** endres til **Vellykket**, har sammenslåingen fullført og løst motstridende data i henhold til policyene du definerte.</span><span class="sxs-lookup"><span data-stu-id="42678-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="42678-142">Sammenslåtte og ikke-sammenslåtte attributter er inkludert i den enhetlige profilenheten.</span><span class="sxs-lookup"><span data-stu-id="42678-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="42678-143">Utelukkede attributter er ikke inkludert i den enhetlige profilenheten.</span><span class="sxs-lookup"><span data-stu-id="42678-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="42678-144">Hvis det ikke var første gang du kjørte en sammenslåing, vil alle nedstrømsprosesser, inkludert supplering, segmentering og tiltak, kjøres på nytt automatisk.</span><span class="sxs-lookup"><span data-stu-id="42678-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="42678-145">Når alle nedstrømsprosessene er kjørt på nytt, gjenspeiler kundeprofilene eventuelle endringer du har gjort.</span><span class="sxs-lookup"><span data-stu-id="42678-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="42678-146">Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser.</span><span class="sxs-lookup"><span data-stu-id="42678-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="42678-147">De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="42678-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="42678-148">Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben.</span><span class="sxs-lookup"><span data-stu-id="42678-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="42678-149">Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.</span><span class="sxs-lookup"><span data-stu-id="42678-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="42678-150">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="42678-150">Next Step</span></span>

<span data-ttu-id="42678-151">Konfigurer [aktiviteter](activities.md), [supplering](enrichment-microsoft-graph.md) eller [relasjoner](relationships.md) for å få mer informasjon om kundene.</span><span class="sxs-lookup"><span data-stu-id="42678-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="42678-152">Hvis du allerede har konfigurert aktiviteter, suppleringer eller relasjoner, eller hvis du definerte segmenter, blir de automatisk behandlet for å bruke de nyeste kundedataene.</span><span class="sxs-lookup"><span data-stu-id="42678-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


