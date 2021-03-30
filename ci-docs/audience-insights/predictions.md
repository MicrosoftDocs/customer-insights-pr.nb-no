---
title: Fullføre delvise data ved hjelp av prognoser
description: Bruk prognoser til å fylle ut ufullstendige kundedata.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595913"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="41aec-103">Fyll ut de delvise dataene med prognoser</span><span class="sxs-lookup"><span data-stu-id="41aec-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="41aec-104">Med prognoser er det mulig å enkelt opprette predisjonsverdier som kan forbedre forståelsen av en kunde.</span><span class="sxs-lookup"><span data-stu-id="41aec-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="41aec-105">På siden **Intelligens** > **Prediksjoner** kan du velge **Mine prediksjoner** for å se prediksjoner som du har konfigurert i andre deler av målgruppeinnsikt, og du kan tilpasse dem ytterligere.</span><span class="sxs-lookup"><span data-stu-id="41aec-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="41aec-106">Du kan ikke bruke denne funksjonen hvis miljøet ditt bruker Azure Data Lake Gen 2-lagring.</span><span class="sxs-lookup"><span data-stu-id="41aec-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="41aec-107">Prognosefunksjonen bruker automatiske gjennomsnitt for å evaluere data og foreta prognoser basert på disse dataene, og har derfor mulighet til å bruke dem som en profileringsmetode, slik termen defineres av EUs personvernforordning ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="41aec-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="41aec-108">Kundens bruk av denne funksjonen til å behandle data kan være underlagt GDPR eller andre lover eller bestemmelser.</span><span class="sxs-lookup"><span data-stu-id="41aec-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="41aec-109">Du er ansvarlig for å sikre at bruken av Dynamics 365 Customer Insights, inkludert prognoser, samsvarer med alle gjeldende lover og bestemmelser, inkludert lover som er relatert til personvern, personlige data, biometriske data, databeskyttelse og konfidensialitet for kommunikasjon.</span><span class="sxs-lookup"><span data-stu-id="41aec-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="41aec-110">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="41aec-110">Prerequisites</span></span>

<span data-ttu-id="41aec-111">Før organisasjonen kan bruke prognosefunksjonen, må du kontrollere at følgende forhåndskrav er oppfylt:</span><span class="sxs-lookup"><span data-stu-id="41aec-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="41aec-112">Organisasjonen har en forekomst [konfigurert i Common Data Service](/ai-builder/build-model#prerequisites), og den er i samme organisasjon som Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="41aec-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="41aec-113">Miljøet ditt er knyttet til Common Data Service-forekomsten din.</span><span class="sxs-lookup"><span data-stu-id="41aec-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="41aec-114">Hvis du [oppretter et nytt miljø](manage-environments.md), konfigurerer du det i dialogboksen **Opprett et miljø** og velger **Avansert**.</span><span class="sxs-lookup"><span data-stu-id="41aec-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="41aec-115">Hvis du allerede har opprettet et miljø, går du til innstillingene og velger **Avansert**.</span><span class="sxs-lookup"><span data-stu-id="41aec-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="41aec-116">Uansett går du til delen **Bruk prediksjoner** og angir URL-adressen til Common Data Service-forekomsten som du vil knytte miljøet ditt til.</span><span class="sxs-lookup"><span data-stu-id="41aec-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="41aec-117">Opprette en prognose i kundeenheten</span><span class="sxs-lookup"><span data-stu-id="41aec-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="41aec-118">I Målgruppeinnsikt går du til **Data** > **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="41aec-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="41aec-119">Velg enheten **Kunde**.</span><span class="sxs-lookup"><span data-stu-id="41aec-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="41aec-120">I enheten **Customer: CustomerInsights** velger du i fanen **Felt**.</span><span class="sxs-lookup"><span data-stu-id="41aec-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="41aec-121">Finn attributtnavnet du vil forutsi verdier for, og velg deretter ikonet **Oversikt** i kolonnen **Sammendrag**.</span><span class="sxs-lookup"><span data-stu-id="41aec-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41aec-122">![Oversikt-ikon](media/intelligence-overviewicon.png "Oversikt-ikon")</span><span class="sxs-lookup"><span data-stu-id="41aec-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="41aec-123">Hvis det er mange manglende verdier for attributtet, velger du **Forutsi manglende verdier** for å fortsette med prognosen.</span><span class="sxs-lookup"><span data-stu-id="41aec-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41aec-124">![Oversiktsstatus med knappen for å forutsi manglende verdier](media/intelligence-overviewpredictmissingvalues.png "Oversiktsstatus med knappen for å forutsi manglende verdier")</span><span class="sxs-lookup"><span data-stu-id="41aec-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="41aec-125">Angi et **Visningsnavn** og et **Navn på utdataenhet** for resultatet av prognosen.</span><span class="sxs-lookup"><span data-stu-id="41aec-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="41aec-126">En forhåndsvalgt liste over alternativer viser hvor du kan tilordne verdiene til en prognosekategori.</span><span class="sxs-lookup"><span data-stu-id="41aec-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="41aec-127">I dette tilfellet vil de eneste kategorialternativene være 0 eller 1 fordi de tilordnes til den sanne/usanne eller binære typen av prognosen.</span><span class="sxs-lookup"><span data-stu-id="41aec-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="41aec-128">I kolonnen Kategori tilordner du feltverdiene du vil klassifisere som "0" i den endelige prognosen, til "0", og elementene du vil klassifisere som "1" i den siste prognosen, til "1".</span><span class="sxs-lookup"><span data-stu-id="41aec-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41aec-129">![Eksempel på tilordnede feltverdier i kategorier](media/intelligence-categorymapping.png "Eksempel på tilordnede feltverdier i kategorier")</span><span class="sxs-lookup"><span data-stu-id="41aec-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="41aec-130">Velg **Ferdig**, og prognosen blir behandlet.</span><span class="sxs-lookup"><span data-stu-id="41aec-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="41aec-131">Behandlingen vil ta litt tid, avhengig av størrelsen på og kompleksiteten av data.</span><span class="sxs-lookup"><span data-stu-id="41aec-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="41aec-132">Resultater er tilgjengelige i en ny enhet basert på **Navn på utdataenhet** til den opprettede prognosen.</span><span class="sxs-lookup"><span data-stu-id="41aec-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="41aec-133">Opprette en prognose når du oppretter et segment</span><span class="sxs-lookup"><span data-stu-id="41aec-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="41aec-134">Det er også mulig å forutsi manglende verdier for et bestemt attributt når et segment opprettes.</span><span class="sxs-lookup"><span data-stu-id="41aec-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="41aec-135">Spesielt når du raskt oppretter et segment basert på enten den enhetlige kundeenheten eller kundemålenheten.</span><span class="sxs-lookup"><span data-stu-id="41aec-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="41aec-136">Som en del av denne flyten velger du et spesifikt attributt som du vil basere segmentet på, for eksempel Kundetilfredshet eller Kjøpsbeløp.</span><span class="sxs-lookup"><span data-stu-id="41aec-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="41aec-137">Når segmentet er opprettet, vil systemet foreslå en metode for å forutse manglende verdier for dette attributtet.</span><span class="sxs-lookup"><span data-stu-id="41aec-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="41aec-138">I Målgruppeinnsikt går du til **Segmenter** og velger **Profiler**-flisen.</span><span class="sxs-lookup"><span data-stu-id="41aec-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="41aec-139">Velg et **Felt** du vil opprette et segment på, velg en **Operator**, og velg deretter **Gå gjennom**.</span><span class="sxs-lookup"><span data-stu-id="41aec-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="41aec-140">Angi et **Navn** og et **Visningsnavn** for segmentet.</span><span class="sxs-lookup"><span data-stu-id="41aec-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="41aec-141">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="41aec-141">Select **Save**.</span></span>

5. <span data-ttu-id="41aec-142">Hvis segmentet du opprettet, har ufullstendige data i kildefeltet, kan du velge å forutsi de manglende verdiene.</span><span class="sxs-lookup"><span data-stu-id="41aec-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41aec-143">![Prognose-knapp](media/segments-predictoption.png "Prognose-knapp")</span><span class="sxs-lookup"><span data-stu-id="41aec-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="41aec-144">Angi et **Visningsnavn** og et **Navn på utdataenhet** for resultatet av prognosen.</span><span class="sxs-lookup"><span data-stu-id="41aec-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="41aec-145">Velg **Ferdig**.</span><span class="sxs-lookup"><span data-stu-id="41aec-145">Select **Done**.</span></span> <span data-ttu-id="41aec-146">Prognosen genereres snart i en ny enhet med navnet du angav for **Navn på utdataenhet**.</span><span class="sxs-lookup"><span data-stu-id="41aec-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="41aec-147">Vise en prognose</span><span class="sxs-lookup"><span data-stu-id="41aec-147">View a prediction</span></span>

1. <span data-ttu-id="41aec-148">I Målgruppeinnsikt går du til **Intelligens** > **Prediksjoner** > **Mine prediksjoner**.</span><span class="sxs-lookup"><span data-stu-id="41aec-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="41aec-149">Velg prognosen du vil gå gjennom.</span><span class="sxs-lookup"><span data-stu-id="41aec-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="41aec-150">Velg en ellipse i kolonnen **Handlinger**, og velg **Visning**.</span><span class="sxs-lookup"><span data-stu-id="41aec-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="41aec-151">Det vises en rekke datapunkter i visningen i prognosen.</span><span class="sxs-lookup"><span data-stu-id="41aec-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41aec-152">![Prognoser-side](media/intelligence-predictionsviewpage.png "Prognoser-side")</span><span class="sxs-lookup"><span data-stu-id="41aec-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="41aec-153">**Forespeilede verdier** viser tilordningen du opprettet under fasen for Felt-verdi til Kategoritilordning.</span><span class="sxs-lookup"><span data-stu-id="41aec-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="41aec-154">Dette er verdiene i datasettet som er tilordnet en bestemt kategori.</span><span class="sxs-lookup"><span data-stu-id="41aec-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="41aec-155">-**Beste påvirkere** er faktorene i datasettet som mest sannsynlig vil påvirke prognosens konfidens til feltverdien som tilordnes en spesifikk kategori.</span><span class="sxs-lookup"><span data-stu-id="41aec-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="41aec-156">**Ytelse** angir hvordan prognoser gjør det.</span><span class="sxs-lookup"><span data-stu-id="41aec-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="41aec-157">Klikk koblingen for å finne ut mer.</span><span class="sxs-lookup"><span data-stu-id="41aec-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="41aec-158">**Forhåndsvisning** viser eksempler på utdatasettet fra prognosen og sannsynligheten, eller vår konfidens, for den anslåtte verdien, der 0 er usikker og 1 er sikker.</span><span class="sxs-lookup"><span data-stu-id="41aec-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="41aec-159">Oppdatere en prognose</span><span class="sxs-lookup"><span data-stu-id="41aec-159">Update a prediction</span></span>

1. <span data-ttu-id="41aec-160">I Målgruppeinnsikt går du til **Intelligens** > **Prediksjoner** > **Mine prediksjoner**.</span><span class="sxs-lookup"><span data-stu-id="41aec-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="41aec-161">Velg hvilken prognose du vil oppdatere, og velg ikonet **Oppdater**.</span><span class="sxs-lookup"><span data-stu-id="41aec-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="41aec-162">Prognosen blir planlagt for behandling.</span><span class="sxs-lookup"><span data-stu-id="41aec-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="41aec-163">Du kan se tiden den sist ble oppdatert, i kolonnen **Oppdatert** på siden **Prognoser**.</span><span class="sxs-lookup"><span data-stu-id="41aec-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="41aec-164">Redigere en prognose</span><span class="sxs-lookup"><span data-stu-id="41aec-164">Edit a prediction</span></span>

<span data-ttu-id="41aec-165">Når du har opprettet en prognose, kan du tilpasse modellen i AI Builder for å øke effektiviteten i modellen.</span><span class="sxs-lookup"><span data-stu-id="41aec-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="41aec-166">I Målgruppeinnsikt går du til **Intelligens** > **Prediksjoner** > **Mine prediksjoner**.</span><span class="sxs-lookup"><span data-stu-id="41aec-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="41aec-167">Merk prognosen du vil redigere.</span><span class="sxs-lookup"><span data-stu-id="41aec-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="41aec-168">Velg en ellipse i kolonnen **Handlinger**, og velg **Visning**.</span><span class="sxs-lookup"><span data-stu-id="41aec-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="41aec-169">Velg **Tilpass i AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="41aec-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="41aec-170">Oppdater modellen i AI Builder.</span><span class="sxs-lookup"><span data-stu-id="41aec-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="41aec-171">[Lær mer om behandling av modeller i AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="41aec-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="41aec-172">Neste kjøring av prognosen vil bruke den oppdaterte modellen du har opprettet.</span><span class="sxs-lookup"><span data-stu-id="41aec-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="41aec-173">Nye modeller som opprettes i AI Builder, vises ikke i målgruppeinsights hvis ikke modellen ble opprettet fra opplevelsene som er oppført ovenfor.</span><span class="sxs-lookup"><span data-stu-id="41aec-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="41aec-174">Fjerne en prognose</span><span class="sxs-lookup"><span data-stu-id="41aec-174">Remove a prediction</span></span>

1. <span data-ttu-id="41aec-175">I Målgruppeinnsikt går du til **Intelligens** > **Prediksjoner** > **Mine prediksjoner**.</span><span class="sxs-lookup"><span data-stu-id="41aec-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="41aec-176">Velg prognosen du vil slette.</span><span class="sxs-lookup"><span data-stu-id="41aec-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="41aec-177">Velg en ellipse i kolonnen **Handlinger**, og velg **Slett**.</span><span class="sxs-lookup"><span data-stu-id="41aec-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="41aec-178">Bekreft slettingen.</span><span class="sxs-lookup"><span data-stu-id="41aec-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="41aec-179">Feilsøking</span><span class="sxs-lookup"><span data-stu-id="41aec-179">Troubleshooting</span></span>

<span data-ttu-id="41aec-180">Hvis du ikke kan fullføre tilleggsprosessen for Common Data Service på grunn av en feil, kan du prøve å fullføre prosessen manuelt.</span><span class="sxs-lookup"><span data-stu-id="41aec-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="41aec-181">Det finnes to kjente problemer som kan oppstå i tilleggsprosessen:</span><span class="sxs-lookup"><span data-stu-id="41aec-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="41aec-182">Kundekort-tillegget er ikke installert.</span><span class="sxs-lookup"><span data-stu-id="41aec-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="41aec-183">Fullfør instruksjonene for å [installere og konfigurere løsningen](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="41aec-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="41aec-184">Apptillatelser blir ikke innvilget.</span><span class="sxs-lookup"><span data-stu-id="41aec-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="41aec-185">Gå til [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="41aec-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="41aec-186">Velg **Miljøer**.</span><span class="sxs-lookup"><span data-stu-id="41aec-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="41aec-187">Velg ellipsen ved siden av miljøet du vil legge til tillatelsen i, og velg **Innstillinger**.</span><span class="sxs-lookup"><span data-stu-id="41aec-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="41aec-188">Utvid **Brukere + tillatelser**, og velg **Brukere**.</span><span class="sxs-lookup"><span data-stu-id="41aec-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="41aec-189">Velg **+ Ny**, og velg **Bruker**.</span><span class="sxs-lookup"><span data-stu-id="41aec-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="41aec-190">Velg **Programbruker** hvis det ikke allerede er valgt, og angi følgende informasjon:</span><span class="sxs-lookup"><span data-stu-id="41aec-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="41aec-191">**Brukernavn:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="41aec-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="41aec-192">**Program-ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="41aec-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="41aec-193">**Fornavn:** Kunde</span><span class="sxs-lookup"><span data-stu-id="41aec-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="41aec-194">**Etternavn:** Innsikt</span><span class="sxs-lookup"><span data-stu-id="41aec-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="41aec-195">**Primær e-post:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="41aec-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="41aec-196">Velg **Lagre og lukk**.</span><span class="sxs-lookup"><span data-stu-id="41aec-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="41aec-197">Velg brukeren du nettopp opprettet.</span><span class="sxs-lookup"><span data-stu-id="41aec-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="41aec-198">Velg **Administrer roller** på den øverste menylinjen.</span><span class="sxs-lookup"><span data-stu-id="41aec-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="41aec-199">Velg **Systemadministrator**, og velg deretter **OK**.</span><span class="sxs-lookup"><span data-stu-id="41aec-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]