---
title: Foreslåtte segmenter basert på aktivitet.
description: La maskinlæring hjelpe deg med å finne nye og interessante segmenter basert på kundeaktivitet.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034099"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="04dae-103">Foreslåtte segmenter basert på aktivitsdata (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="04dae-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="04dae-104">Oppdag interessante segmenter av kundene basert på kundeaktivitetsdata som er hentet inn i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="04dae-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="04dae-105">Eksempler på aktivitetsdata er transaksjoner, samtalevarighet, kjøp eller returer.</span><span class="sxs-lookup"><span data-stu-id="04dae-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="04dae-106">For å foreslå segmenter analyseres aktivitetsdata for nylighet, hyppighet og pengeverdi (eller varighet).</span><span class="sxs-lookup"><span data-stu-id="04dae-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="04dae-107">Du kan også generere [foreslåtte segmenter for å forbedre et mål, eller bedre forstå hva som har innvirkning på et attributt](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="04dae-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Fanen Foreslåtte segmenter som viser segmentforslag for aktivitetsbaserte og attributtbaserte segmenter.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="04dae-109">Kategoriser kunder etter aktivitet</span><span class="sxs-lookup"><span data-stu-id="04dae-109">Categorize customers by activity</span></span>

<span data-ttu-id="04dae-110">Med [aktivitetsdata](activities.md) tilgjengelige i Customer Insights kan vi generere forslag som representerer kundegrupper:</span><span class="sxs-lookup"><span data-stu-id="04dae-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="04dae-111">mest aktive kunder</span><span class="sxs-lookup"><span data-stu-id="04dae-111">most active customers</span></span> 
- <span data-ttu-id="04dae-112">kunder som har gjort flest kjøp</span><span class="sxs-lookup"><span data-stu-id="04dae-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="04dae-113">kunder som genererte mest omsetning</span><span class="sxs-lookup"><span data-stu-id="04dae-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="04dae-114">kunder som ikke har vært aktive i det siste</span><span class="sxs-lookup"><span data-stu-id="04dae-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="04dae-115">kunder som ofte samhandler med virksomheten din</span><span class="sxs-lookup"><span data-stu-id="04dae-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="04dae-116">Hvis du har en detaljvirksomhet, kan du finne ut hvilke kunder som genererer størst omsetning, og belønne dem med en rabattkuponger.</span><span class="sxs-lookup"><span data-stu-id="04dae-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="04dae-117">Du kan også identifisere tilfeldige kunder og tilby dem å delta i et belønningsprogram, slik at de oftere besøker bedriften.</span><span class="sxs-lookup"><span data-stu-id="04dae-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="04dae-118">Hvis du er i helsebransjen som leverer offentlige helsetjenester og målet er å redusere utgiftene for enkeltpasienter.</span><span class="sxs-lookup"><span data-stu-id="04dae-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="04dae-119">En måte å gjøre dette på kan være å redusere regelmessige besøk ved å gi best mulig pleie i så få besøk som mulig.</span><span class="sxs-lookup"><span data-stu-id="04dae-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="04dae-120">I dette tilfellet er målet å holde besøksfrekvensen lav og redusere regelmessige kostnader for pasientene.</span><span class="sxs-lookup"><span data-stu-id="04dae-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="04dae-121">Du kan også identifisere segmenter av pasienter som har hyppige avtaler og høye regelmessige kostnader, og analysere disse sakene for å forbedre behandling av den enkelte.</span><span class="sxs-lookup"><span data-stu-id="04dae-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="04dae-122">Obligatoriske data</span><span class="sxs-lookup"><span data-stu-id="04dae-122">Required data</span></span>

<span data-ttu-id="04dae-123">Forslagene genereres basert på de valgte inndataene.</span><span class="sxs-lookup"><span data-stu-id="04dae-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="04dae-124">Kundeprofiler: Alle kunder eller medlemmer i et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="04dae-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="04dae-125">Tidsperiode: Siste måned, forrige år eller egendefinerte tidsrammer.</span><span class="sxs-lookup"><span data-stu-id="04dae-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="04dae-126">Aktivitetstype: kjøp, detaljhandelstransaksjoner, elektroniske transaksjoner, kundestøttesaker, abonnementer og så videre.</span><span class="sxs-lookup"><span data-stu-id="04dae-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="04dae-127">Enhet i Customer Insights som inneholder aktivitetsdataene: UnifiedActivity-enheten eller enheten for en bestemt aktivitet.</span><span class="sxs-lookup"><span data-stu-id="04dae-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="04dae-128">Dimensjonene som skal inkluderes: Nylighet, hyppighet eller pengedimensjon, avhengig av forretningskravene.</span><span class="sxs-lookup"><span data-stu-id="04dae-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="04dae-129">Generer foreslåtte segmenter</span><span class="sxs-lookup"><span data-stu-id="04dae-129">Generate suggested segments</span></span>

1. <span data-ttu-id="04dae-130">Gå til **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="04dae-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="04dae-131">Velg fanen **Forslag (forhåndsversjon)**.</span><span class="sxs-lookup"><span data-stu-id="04dae-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="04dae-132">Velg **Finn nye forslag** og velg **Se eller forvent kundevirkemåte**.</span><span class="sxs-lookup"><span data-stu-id="04dae-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="04dae-133">Velg **Start** for å kjøre den veiledede opplevelsen.</span><span class="sxs-lookup"><span data-stu-id="04dae-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Første trinn i konfigurasjonsveiviseren for et foreslått segment basert på aktivitet.":::

1. <span data-ttu-id="04dae-135">Angi de nødvendige inndataene og velg **Neste** for å fortsette.</span><span class="sxs-lookup"><span data-stu-id="04dae-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="04dae-136">Velg kunder: Inkluder alle kunder eller et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="04dae-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="04dae-137">Velg aktivitet: Velg aktivitetstypen og enhetene som beskriver aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="04dae-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="04dae-138">Innstillinger: Angi tidsperioden som skal vurderes, faktorer for forslag og tilordne attributtene.</span><span class="sxs-lookup"><span data-stu-id="04dae-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="04dae-139">Gå gjennom inndataene og velg **Kjør** for å kjøre modellen og generere forslag.</span><span class="sxs-lookup"><span data-stu-id="04dae-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="04dae-140">Det kan ta noen minutter å fullføre, avhengig av antall kundeprofiler og valgte aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="04dae-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="04dae-141">Når du har generert forslagene, kan du filtrere dem etter dimensjonen eller verdien du er mest interessert i.</span><span class="sxs-lookup"><span data-stu-id="04dae-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="04dae-142">Vis detaljer for et foreslått segment</span><span class="sxs-lookup"><span data-stu-id="04dae-142">View details of a suggested segment</span></span>

<span data-ttu-id="04dae-143">Når forslagene er generert, finner du dem oppført i **Segmenter** > **Forslag (forhåndsversjon)** i delen **Aktivitetsbaserte forslag**.</span><span class="sxs-lookup"><span data-stu-id="04dae-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Utvidet siderute som viser detaljerte data for et foreslått segment.":::

<span data-ttu-id="04dae-145">Velg **Se forslag** i et foreslått segment for å vise detaljene for det segmentet.</span><span class="sxs-lookup"><span data-stu-id="04dae-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="04dae-146">Sideruten inneholder detaljer som omfanget av hver dimensjon sammenlignet med målgruppen.</span><span class="sxs-lookup"><span data-stu-id="04dae-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="04dae-147">Den fremhever også antall potensielle medlemmer i segmentet og den tilsvarende prosentandelen av totalkundene.</span><span class="sxs-lookup"><span data-stu-id="04dae-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="04dae-148">Hvis du vil beholde forslaget som et segment, velger du **Opprett segment**.</span><span class="sxs-lookup"><span data-stu-id="04dae-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="04dae-149">Lagre et forslag som et segment</span><span class="sxs-lookup"><span data-stu-id="04dae-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="04dae-150">Gå til **Segmenter** > **Forslag (forhåndsversjon)**.</span><span class="sxs-lookup"><span data-stu-id="04dae-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="04dae-151">Velg segmentet du vil lagre.</span><span class="sxs-lookup"><span data-stu-id="04dae-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="04dae-152">Velg **Opprett segment** i sideruten.</span><span class="sxs-lookup"><span data-stu-id="04dae-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="04dae-153">Når du har lagret segmentet, vises det i listen over segmenter i fanen **Alle segmenter**. Den kan nå [oppdateres eller slettes som alle andre segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="04dae-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="04dae-154">Du kan ikke redigere segmentdetaljene.</span><span class="sxs-lookup"><span data-stu-id="04dae-154">You can't edit the segment details.</span></span> <span data-ttu-id="04dae-155">Du kan imidlertid endre inndatavilkårene for forslagene og generere ulike forslag.</span><span class="sxs-lookup"><span data-stu-id="04dae-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="04dae-156">Oppdater eller rediger et sett med forslag</span><span class="sxs-lookup"><span data-stu-id="04dae-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="04dae-157">Gå til **Segmenter** > **Forslag (forhåndsversjon)**, og se etter segmentet i delen **Aktivitetsbaserte forslag**.</span><span class="sxs-lookup"><span data-stu-id="04dae-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="04dae-158">Velg **Oppdater forslag** for å oppdatere forslagene samtidig som du beholder konfigurerte attributter.</span><span class="sxs-lookup"><span data-stu-id="04dae-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="04dae-159">Du kan også velge **Rediger forslag** for å endre de konfigurerte attributtene.</span><span class="sxs-lookup"><span data-stu-id="04dae-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="04dae-160">Systemet kjører prosessen på nytt, genererer segmentforslag basert på de nyeste dataene og erstatter de gjeldende forslagene.</span><span class="sxs-lookup"><span data-stu-id="04dae-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
