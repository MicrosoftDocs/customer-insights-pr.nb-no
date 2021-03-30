---
title: Finn lignende kunder med kunstig intelligens
description: Finn lignende kundesegmenter med kunstig intelligens.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596787"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="18ad2-103">Lignende kunder (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="18ad2-103">Similar Customers (preview)</span></span>

<span data-ttu-id="18ad2-104">Denne funksjonen gjør det mulig for deg å finne lignende kunder i kundebasen ved hjelp av kunstig intelligens.</span><span class="sxs-lookup"><span data-stu-id="18ad2-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="18ad2-105">Du må ha minst ett opprettet segment for å bruke denne funksjonen.</span><span class="sxs-lookup"><span data-stu-id="18ad2-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="18ad2-106">Ved å utvide kriteriene for et eksisterende segment kan du finne kunder som ligner på dette segmentet.</span><span class="sxs-lookup"><span data-stu-id="18ad2-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="18ad2-107">*Finn lignende kunder* bruker automatiske metoder til å evaluere data og lage prognoser basert på dataene, og kan derfor brukes som en metode for profilering, slik denne termen defineres av EUs personvernforordning ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="18ad2-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="18ad2-108">Kundens bruk av denne funksjonen til å behandle data kan være underlagt GDPR eller andre lover eller bestemmelser.</span><span class="sxs-lookup"><span data-stu-id="18ad2-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="18ad2-109">Du er ansvarlig for å sikre at bruken av Dynamics 365 Customer Insights, inkludert prognoser, samsvarer med alle gjeldende lover og bestemmelser, inkludert lover som er relatert til personvern, personlige data, biometriske data, databeskyttelse og konfidensialitet for kommunikasjon.</span><span class="sxs-lookup"><span data-stu-id="18ad2-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="18ad2-110">Finne lignende kunder</span><span class="sxs-lookup"><span data-stu-id="18ad2-110">Finding similar customers</span></span>

1. <span data-ttu-id="18ad2-111">I målgruppeinnsikt går du til **Segmenter** og velger segmentet du vil basere det nye segmentet på.</span><span class="sxs-lookup"><span data-stu-id="18ad2-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="18ad2-112">Dette er *kildesegmentet*.</span><span class="sxs-lookup"><span data-stu-id="18ad2-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="18ad2-113">På handlingslinjen velger du **Finn lignende kunder**.</span><span class="sxs-lookup"><span data-stu-id="18ad2-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="18ad2-114">Se gjennom det foreslåtte navnet på det nye segmentet, og endre det hvis det er nødvendig.</span><span class="sxs-lookup"><span data-stu-id="18ad2-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="18ad2-115">Se gjennom feltene som definerer det nye segmentet.</span><span class="sxs-lookup"><span data-stu-id="18ad2-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="18ad2-116">Disse feltene definerer grunnlaget for når systemet skal prøve å finne lignende kunder i kildesegmentet.</span><span class="sxs-lookup"><span data-stu-id="18ad2-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="18ad2-117">Systemet velger anbefalte felt som standard.</span><span class="sxs-lookup"><span data-stu-id="18ad2-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="18ad2-118">Felt som kan redusere modellytelsen betydelig, blir automatisk utelatt:</span><span class="sxs-lookup"><span data-stu-id="18ad2-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="18ad2-119">Felt med følgende datatyper: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="18ad2-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="18ad2-120">Felt med en kardinalitet (antall elementer i et felt) under 2 eller over 30</span><span class="sxs-lookup"><span data-stu-id="18ad2-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="18ad2-121">Velg om du vil inkludere **alle kunder** eller bare kunder i et **spesifikt eksisterende segment** i det nye segmentet.</span><span class="sxs-lookup"><span data-stu-id="18ad2-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="18ad2-122">Utelat kunder i kildesegmentet ved å merke av for **Utelat alle i kildesegment**.</span><span class="sxs-lookup"><span data-stu-id="18ad2-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="18ad2-123">Som standard foreslår systemet en inkludering på bare 20 % av målgruppestørrelsen i utdataene.</span><span class="sxs-lookup"><span data-stu-id="18ad2-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="18ad2-124">Rediger denne terskelen etter behov.</span><span class="sxs-lookup"><span data-stu-id="18ad2-124">Edit this threshold as needed.</span></span> <span data-ttu-id="18ad2-125">Hvis du øker terskelen, reduseres presisjonen.</span><span class="sxs-lookup"><span data-stu-id="18ad2-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="18ad2-126">Velg **Kjør** nederst på siden for å starte en binær klassifiseringsoppgave (en metode for maskinlæring) som analyserer datasettet.</span><span class="sxs-lookup"><span data-stu-id="18ad2-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="18ad2-127">Vise det lignende segmentet</span><span class="sxs-lookup"><span data-stu-id="18ad2-127">View the similar segment</span></span>

<span data-ttu-id="18ad2-128">Etter at du har behandlet det lignende segmentet, finner du det nye segmentet som vises på **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="18ad2-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="18ad2-129">![Segmentet Lignende kunder](media/expanded-segment.png "Segmentet Lignende kunder")</span><span class="sxs-lookup"><span data-stu-id="18ad2-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="18ad2-130">Velg **Vis** på handlingslinjen for å åpne segmentdetaljene.</span><span class="sxs-lookup"><span data-stu-id="18ad2-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="18ad2-131">Denne visningen inneholder informasjon om resultatfordelingen på tvers av [likhetsresultater](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="18ad2-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="18ad2-132">Du finner også likhetspoengsummene i **Forhåndsvisning av segmentmedlemmer**.</span><span class="sxs-lookup"><span data-stu-id="18ad2-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="18ad2-133">Bruke utdataene for et lignende segment</span><span class="sxs-lookup"><span data-stu-id="18ad2-133">Use the output of a similar segment</span></span>

<span data-ttu-id="18ad2-134">Du kan [arbeide med utdataene fra et lignende segment](segments.md) som du gjør med andre segmenter.</span><span class="sxs-lookup"><span data-stu-id="18ad2-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="18ad2-135">Du kan for eksempel eksportere segmentet eller bygge et mål.</span><span class="sxs-lookup"><span data-stu-id="18ad2-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="18ad2-136">Oppdatere og redigere et lignende segment</span><span class="sxs-lookup"><span data-stu-id="18ad2-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="18ad2-137">Hvis du vil oppdatere et lignende segment, velger du det på **Segmenter**-siden og velger **Oppdater** på handlingslinjen.</span><span class="sxs-lookup"><span data-stu-id="18ad2-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="18ad2-138">Når du redigerer et lignende segment, behandles dataene på nytt.</span><span class="sxs-lookup"><span data-stu-id="18ad2-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="18ad2-139">Det tidligere opprettede segmentet blir oppdatert med oppdaterte data.</span><span class="sxs-lookup"><span data-stu-id="18ad2-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="18ad2-140">Hvis du vil redigere et lignende segment, velger du det på **Segmenter**-siden og velger **Rediger** på handlingslinjen.</span><span class="sxs-lookup"><span data-stu-id="18ad2-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="18ad2-141">Ta i bruk endringene, og velg **Kjør** for å starte behandlingen.</span><span class="sxs-lookup"><span data-stu-id="18ad2-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="18ad2-142">Slette et lignende segment</span><span class="sxs-lookup"><span data-stu-id="18ad2-142">Delete a similar segment</span></span>

<span data-ttu-id="18ad2-143">Slett segmentet på **Segmenter**-siden og velg **Slett** på handlingslinjen.</span><span class="sxs-lookup"><span data-stu-id="18ad2-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="18ad2-144">Bekreft deretter slettingen.</span><span class="sxs-lookup"><span data-stu-id="18ad2-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="18ad2-145">Likhetsresultater</span><span class="sxs-lookup"><span data-stu-id="18ad2-145">About similarity scores</span></span>

<span data-ttu-id="18ad2-146">Maskinlæringsmodellen for binær klassifisering tilordner en poengsum til kunder i det lignende segmentet.</span><span class="sxs-lookup"><span data-stu-id="18ad2-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="18ad2-147">Poengsummen er basert på likheten med kunder i kildesegmentet.</span><span class="sxs-lookup"><span data-stu-id="18ad2-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="18ad2-148">Likhetsresultater under 0,55 er kunder som systemet har klassifisert som *ikke lik* kunder i kildesegmentet</span><span class="sxs-lookup"><span data-stu-id="18ad2-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="18ad2-149">Likhetsresultater mellom 0,55 og 0,7 klassifiseres som *ligner litt*</span><span class="sxs-lookup"><span data-stu-id="18ad2-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="18ad2-150">Likhetsresultater mellom 0,7 og 0,85 klassifiseres som *ligner*</span><span class="sxs-lookup"><span data-stu-id="18ad2-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="18ad2-151">Likhetsresultater mellom 0,85 og 1 er kunder som systemet har klassifisert som *svært like*</span><span class="sxs-lookup"><span data-stu-id="18ad2-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="18ad2-152">Kunder med likhetsresultater under 0,4, tas ikke med i modellutdataene.</span><span class="sxs-lookup"><span data-stu-id="18ad2-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="18ad2-153">Systemet betrakter ikke de som like nok kildesegmentet.</span><span class="sxs-lookup"><span data-stu-id="18ad2-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]