---
title: Segmentinnsikt for eksisterende segmenter
description: Få innsikt om eksisterende segmenter for å se forskjeller og felles trekk.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270032"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="6aae4-103">Segmentinnsikt (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="6aae4-103">Segment insights (preview)</span></span>

<span data-ttu-id="6aae4-104">Oppdag mer informasjon og innsikt rundt eksisterende segmenter.</span><span class="sxs-lookup"><span data-stu-id="6aae4-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="6aae4-105">Finn ut hva som skiller to segmenter fra hverandre, eller hva de har til felles.</span><span class="sxs-lookup"><span data-stu-id="6aae4-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="6aae4-106">Segmentoverlapping</span><span class="sxs-lookup"><span data-stu-id="6aae4-106">Segment overlap</span></span>

<span data-ttu-id="6aae4-107">Analyse av segmentoverlapping viser hvor mange og hvilke kunder som er felles for to eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="6aae4-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="6aae4-108">For eksempel hvordan et segment med hyppige kunder overlapper med et segment som inneholder kunder som er fornøyd med servicen eller produktet.</span><span class="sxs-lookup"><span data-stu-id="6aae4-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="6aae4-109">Du kan også analysere hvordan overlappingen endres for bestemte attributter.</span><span class="sxs-lookup"><span data-stu-id="6aae4-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="6aae4-110">Kjøre en overlappingsanalyse</span><span class="sxs-lookup"><span data-stu-id="6aae4-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="6aae4-111">Gå til **Segmenter**, og velg kategorien **Innsikt (forhåndsversjon)**.</span><span class="sxs-lookup"><span data-stu-id="6aae4-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="6aae4-112">Velg **Ny**, og velg alternativet **Overlapping** i ruten **Velg innsiktstype**.</span><span class="sxs-lookup"><span data-stu-id="6aae4-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="6aae4-113">Velg segmentene av interesse, og velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="6aae4-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="6aae4-114">Hvis du vil, kan du velge ett eller flere felt av interesse for å analysere overlapping for alle mulige feltverdier og velge **Neste**.</span><span class="sxs-lookup"><span data-stu-id="6aae4-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="6aae4-115">Oppgi et navn for overlappingsanalysen, et valgfritt visningsnavn og en beskrivelse.</span><span class="sxs-lookup"><span data-stu-id="6aae4-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="6aae4-116">Velg **Lagre** for å starte analysen.</span><span class="sxs-lookup"><span data-stu-id="6aae4-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="6aae4-117">Overlappingsanalysen er klar når statusen endres fra Oppdaterer til Vellykket.</span><span class="sxs-lookup"><span data-stu-id="6aae4-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="6aae4-118">Vise og optimalisere en overlappingsanalyse</span><span class="sxs-lookup"><span data-stu-id="6aae4-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="6aae4-119">Etter at du har fullført analysen, finner du mer informasjon om denne innsikten i **Segmenter** > **Innsikt (forhåndsversjon)**.</span><span class="sxs-lookup"><span data-stu-id="6aae4-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Innsiktsdetaljer om segmentoverlapping":::

<span data-ttu-id="6aae4-121">Velg en innsikt for å vise analyseresultatene:</span><span class="sxs-lookup"><span data-stu-id="6aae4-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="6aae4-122">Antall medlemmer som overlapper segmentene som er valgt for analyse.</span><span class="sxs-lookup"><span data-stu-id="6aae4-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="6aae4-123">Antall medlemmer som er inkludert i ett av segmentene, men ikke i resten av segmentene.</span><span class="sxs-lookup"><span data-stu-id="6aae4-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="6aae4-124">Hvis du valgte felt under konfigurasjon av overlappingsanalysen, finner du dem i de tilsvarende kategoriene.</span><span class="sxs-lookup"><span data-stu-id="6aae4-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="6aae4-125">Du kan bruke rullegardinlisten Filter til å velge et attributtnivå av interessere, og tabellen nederst viser de tilsvarende dataene.</span><span class="sxs-lookup"><span data-stu-id="6aae4-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="6aae4-126">Segmentdifferensiatorer</span><span class="sxs-lookup"><span data-stu-id="6aae4-126">Segment differentiators</span></span>

<span data-ttu-id="6aae4-127">Ved hjelp av segmentdifferensiatorer kan du finne ut hva som skiller et segment fra resten av kundene eller fra et annet segment.</span><span class="sxs-lookup"><span data-stu-id="6aae4-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="6aae4-128">Du trenger bare å velge et segment, og systemet identifiserer profilattributter og mål som skiller det valgte segmentet.</span><span class="sxs-lookup"><span data-stu-id="6aae4-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="6aae4-129">Kjøre en differensiatoranalyse</span><span class="sxs-lookup"><span data-stu-id="6aae4-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="6aae4-130">Gå til **Segmenter**, og velg kategorien **Innsikt (forhåndsversjon)**.</span><span class="sxs-lookup"><span data-stu-id="6aae4-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="6aae4-131">Velg **Ny**, og velg alternativet **Overlapping** i ruten **Velg innsiktstype**.</span><span class="sxs-lookup"><span data-stu-id="6aae4-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="6aae4-132">Velg segmentet du vil analysere, som **Primært segment**, og velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="6aae4-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="6aae4-133">Velg **Alle kunder** eller et **Sekundært segment** for å sammenligne hovedsegmentet med, og velg deretter **Neste**.</span><span class="sxs-lookup"><span data-stu-id="6aae4-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="6aae4-134">Hvis du vil, kan du velge ett eller flere felt av interesse for å fokusere analysen på bestemte attributter og deretter velge **Neste**.</span><span class="sxs-lookup"><span data-stu-id="6aae4-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="6aae4-135">Oppgi et navn for overlappingsanalysen, et valgfritt visningsnavn og en beskrivelse.</span><span class="sxs-lookup"><span data-stu-id="6aae4-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="6aae4-136">Velg **Lagre** for å starte analysen.</span><span class="sxs-lookup"><span data-stu-id="6aae4-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="6aae4-137">Overlappingsanalysen er klar når statusen endres fra Oppdaterer til Vellykket.</span><span class="sxs-lookup"><span data-stu-id="6aae4-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="6aae4-138">Vise og optimalisere en differensiatoranalyse</span><span class="sxs-lookup"><span data-stu-id="6aae4-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="6aae4-139">Etter at du har fullført analysen, finner du mer informasjon om denne innsikten i **Segmenter** > **Innsikt (forhåndsversjon)**.</span><span class="sxs-lookup"><span data-stu-id="6aae4-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Innsiktsdetaljer om segmentdifferensiator":::

<span data-ttu-id="6aae4-141">Velg en innsikt for å vise analyseresultatene.</span><span class="sxs-lookup"><span data-stu-id="6aae4-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="6aae4-142">En differensiatoranalyse inneholder to kategorier.</span><span class="sxs-lookup"><span data-stu-id="6aae4-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="6aae4-143">Kategorien **Attributter** viser profilattributter vurdert som differensiatorer.</span><span class="sxs-lookup"><span data-stu-id="6aae4-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="6aae4-144">Kategorien **Mål** viser differensiatorer.</span><span class="sxs-lookup"><span data-stu-id="6aae4-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="6aae4-145">Hver kategori inkluderer følgende detaljer:</span><span class="sxs-lookup"><span data-stu-id="6aae4-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="6aae4-146">Rangert liste over differensiatorer, sortert etter differansepoengsum.</span><span class="sxs-lookup"><span data-stu-id="6aae4-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="6aae4-147">**Differansepoengsummen** for hver differensiator.</span><span class="sxs-lookup"><span data-stu-id="6aae4-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="6aae4-148">Differansepoengsummen representerer graden av fifferanse for et attributt mellom to segmenter.</span><span class="sxs-lookup"><span data-stu-id="6aae4-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="6aae4-149">Jo høyere differansepoengsum, jo mer forskjellig er attributtene mellom de to segmentene.</span><span class="sxs-lookup"><span data-stu-id="6aae4-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="6aae4-150">Velg en poengsum for å åpne ruten **Differansepoengsum** med fordelingen av verdier for dette attributtet.</span><span class="sxs-lookup"><span data-stu-id="6aae4-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="6aae4-151">Behandle segmentinnsikt</span><span class="sxs-lookup"><span data-stu-id="6aae4-151">Manage segment insights</span></span>

<span data-ttu-id="6aae4-152">Du kan bruke følgende alternativer i innsikten fra kommandolinjen:</span><span class="sxs-lookup"><span data-stu-id="6aae4-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="6aae4-153">**Tilbake** for å gå tilbake til listen over innsikt</span><span class="sxs-lookup"><span data-stu-id="6aae4-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="6aae4-154">**Oppdater** for å kjøre analysen på nytt</span><span class="sxs-lookup"><span data-stu-id="6aae4-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="6aae4-155">**Slett** for å fjerne denne innsikten</span><span class="sxs-lookup"><span data-stu-id="6aae4-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]