---
title: Opprett og administrer mål
description: Definer mål som skal analyseres og gjenspeile selskapets ytelse.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654744"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="8060c-103">Definere og administrere mål</span><span class="sxs-lookup"><span data-stu-id="8060c-103">Define and manage measures</span></span>

<span data-ttu-id="8060c-104">Tiltak hjelper deg med å få bedre forståelse av kundeatferd og forretningsytelse ved å hente relevante verdier fra [enhetlige profiler](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="8060c-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="8060c-105">En virksomhet vil for eksempel se *totalkostnaden per kunde* for å forstå den enkelte kundes kjøpshistorikk.</span><span class="sxs-lookup"><span data-stu-id="8060c-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="8060c-106">Du kan også måle *det totale salget i selskapet* for å forstå omsetningen på aggregatnivå i hele selskapet.</span><span class="sxs-lookup"><span data-stu-id="8060c-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="8060c-107">Tiltak opprettes ved hjelp av måleverktøyet, en dataspørringsplattform med forskjellige operatorer og enkle tilordningsalternativer.</span><span class="sxs-lookup"><span data-stu-id="8060c-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="8060c-108">Den lar deg filtrere dataene, gruppere resultater, registrere [enhetsrelasjonsbaner](relationships.md) og forhåndsvise utdataene.</span><span class="sxs-lookup"><span data-stu-id="8060c-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="8060c-109">Bruk måleverktøyet til å planlegge forretningsaktiviteter ved å spørre etter kundedata og trekke ut innsikt.</span><span class="sxs-lookup"><span data-stu-id="8060c-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="8060c-110">Hvis du for eksempel oppretter et mål for *totalkostnad per kunde* og *total avkastning per kunde*, blir det enklere å identifisere en gruppe kunder med høy avkastning, men likevel høy avkastning.</span><span class="sxs-lookup"><span data-stu-id="8060c-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="8060c-111">Du kan [opprette et segment](segments.md) for å få de nest beste handlingene.</span><span class="sxs-lookup"><span data-stu-id="8060c-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="8060c-112">Opprette et mål</span><span class="sxs-lookup"><span data-stu-id="8060c-112">Create a measure</span></span>

<span data-ttu-id="8060c-113">Denne delen beskriver hvordan du oppretter et nytt mål fra bunnen av.</span><span class="sxs-lookup"><span data-stu-id="8060c-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="8060c-114">Du kan bygge et mål med dataattributter fra dataenheter som har en relasjon konfigurert til å koble til kundeenheten.</span><span class="sxs-lookup"><span data-stu-id="8060c-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="8060c-115">I Målgruppeinnsikt går du til **Mål**.</span><span class="sxs-lookup"><span data-stu-id="8060c-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="8060c-116">Velg **Ny**.</span><span class="sxs-lookup"><span data-stu-id="8060c-116">Select **New**.</span></span>

1. <span data-ttu-id="8060c-117">Velg **Rediger navn**, og angi et **navn** for målet.</span><span class="sxs-lookup"><span data-stu-id="8060c-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="8060c-118">Hvis den nye målkonfigurasjonen bare har to felter, for eksempel CustomerID og en beregning, blir utdataene lagt til som en ny kolonne i den systemgenererte enheten kalt Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="8060c-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="8060c-119">Du kan også se målets verdi i den enhetlige kundeprofilen.</span><span class="sxs-lookup"><span data-stu-id="8060c-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="8060c-120">Andre tiltak vil generere sine egne enheter.</span><span class="sxs-lookup"><span data-stu-id="8060c-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="8060c-121">Velg sammensettingsfunksjonen fra rullegardinlisten **Velg funksjon** i konfigurasjonsområdet.</span><span class="sxs-lookup"><span data-stu-id="8060c-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="8060c-122">Aggregasjonsfunksjonene omfatter:</span><span class="sxs-lookup"><span data-stu-id="8060c-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="8060c-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="8060c-123">**Sum**</span></span>
   - <span data-ttu-id="8060c-124">**Gjennomsnitt**</span><span class="sxs-lookup"><span data-stu-id="8060c-124">**Average**</span></span>
   - <span data-ttu-id="8060c-125">**Antall**</span><span class="sxs-lookup"><span data-stu-id="8060c-125">**Count**</span></span>
   - <span data-ttu-id="8060c-126">**Antall unike**</span><span class="sxs-lookup"><span data-stu-id="8060c-126">**Count Unique**</span></span>
   - <span data-ttu-id="8060c-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="8060c-127">**Max**</span></span>
   - <span data-ttu-id="8060c-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="8060c-128">**Min**</span></span>
   - <span data-ttu-id="8060c-129">**Første**: tar den første verdien i dataoppføringen</span><span class="sxs-lookup"><span data-stu-id="8060c-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="8060c-130">**Siste**: tar den siste verdien som ble lagt til i dataoppføringen</span><span class="sxs-lookup"><span data-stu-id="8060c-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorer for måleberegninger.":::

1. <span data-ttu-id="8060c-132">Velg **Legg til attributt** for å velge dataene du vil opprette dette målet.</span><span class="sxs-lookup"><span data-stu-id="8060c-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="8060c-133">Velg fanen **Attributtene**.</span><span class="sxs-lookup"><span data-stu-id="8060c-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="8060c-134">Dataenhet: Velg enheten som inneholder attributtet du vil måle.</span><span class="sxs-lookup"><span data-stu-id="8060c-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="8060c-135">Dataattributt: Velg attributtet du vil bruke i aggregasjonsfunksjonen, for å beregne målet.</span><span class="sxs-lookup"><span data-stu-id="8060c-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="8060c-136">Du kan bare velge ett attributt om gangen.</span><span class="sxs-lookup"><span data-stu-id="8060c-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="8060c-137">Du kan også velge et dataattributt fra et eksisterende mål ved å velge fanen **Mål**. Du kan også søke etter et enhets- eller målnavn.</span><span class="sxs-lookup"><span data-stu-id="8060c-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="8060c-138">Velg **Legg til** for å legge til det valgte attributtet i målet.</span><span class="sxs-lookup"><span data-stu-id="8060c-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Velg et attributt som skal brukes i beregninger.":::

1. <span data-ttu-id="8060c-140">Hvis du vil bygge mer komplekse tiltak, kan du legge til flere attributter eller bruke operatorer for målefunksjon.</span><span class="sxs-lookup"><span data-stu-id="8060c-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Opprett et komplekst mål med matteoperatorer.":::

1. <span data-ttu-id="8060c-142">Hvis du vil legge til filtre, velger du **Filter** i konfigurasjonsområdet.</span><span class="sxs-lookup"><span data-stu-id="8060c-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="8060c-143">I delen **Legg til attributt** i **Filtre**-ruten velger du attributtet du vil bruke til å opprette filtre.</span><span class="sxs-lookup"><span data-stu-id="8060c-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="8060c-144">Angi filteroperatorene for å definere filteret for hvert valgte attributt.</span><span class="sxs-lookup"><span data-stu-id="8060c-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="8060c-145">Velg **Bruk** for å legge til filtrene i målet.</span><span class="sxs-lookup"><span data-stu-id="8060c-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="8060c-146">Hvis du vil legge til dimensjoner, velger du **Dimensjon** i konfigurasjonsområdet.</span><span class="sxs-lookup"><span data-stu-id="8060c-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="8060c-147">Dimensjoner vises som kolonner i målutdataenheten.</span><span class="sxs-lookup"><span data-stu-id="8060c-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="8060c-148">Velg **Rediger dimensjoner** for å legge til dataattributter du vil gruppere målverdiene etter.</span><span class="sxs-lookup"><span data-stu-id="8060c-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="8060c-149">For eksempel poststed eller kjønn.</span><span class="sxs-lookup"><span data-stu-id="8060c-149">For example, city or gender.</span></span> <span data-ttu-id="8060c-150">Som standard velges *CustomerID*-dimensjonen for å opprette *mål på kundenivå*.</span><span class="sxs-lookup"><span data-stu-id="8060c-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="8060c-151">Du kan fjerne standarddimensjonen hvis du vil opprette *tiltak på forretningsnivå*.</span><span class="sxs-lookup"><span data-stu-id="8060c-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="8060c-152">Velg **Ferdig** for å legge til dimensjonene i målet.</span><span class="sxs-lookup"><span data-stu-id="8060c-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="8060c-153">Hvis det finnes flere baner mellom dataenheten du tilordnet og *Kunde*-enheten, må du velge en av de identifiserte [enhetsrelasjonsbanene](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="8060c-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="8060c-154">Måleresultatene kan variere avhengig av den valgte banen.</span><span class="sxs-lookup"><span data-stu-id="8060c-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="8060c-155">Velg **Datainnstillinger**, og velg enhetsbanen som skal brukes til å identifisere målet.</span><span class="sxs-lookup"><span data-stu-id="8060c-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="8060c-156">Hvis det bare finnes én enkelt bane til *Kunde*-enheten, vises ikke denne kontrollen.</span><span class="sxs-lookup"><span data-stu-id="8060c-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="8060c-157">Velg **Fullført** for å ta i bruk valget.</span><span class="sxs-lookup"><span data-stu-id="8060c-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Velg enhetsbanen for målet.":::

1. <span data-ttu-id="8060c-159">Hvis du vil legge til flere beregninger for målet, velger du **Ny beregning**.</span><span class="sxs-lookup"><span data-stu-id="8060c-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="8060c-160">Du kan bare bruke enheter i den samme enhetsbanen for nye beregninger.</span><span class="sxs-lookup"><span data-stu-id="8060c-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="8060c-161">Flere beregninger vises som nye kolonner i målutdataenheten.</span><span class="sxs-lookup"><span data-stu-id="8060c-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="8060c-162">Velg **...** i beregningen til **Duplikat**, **Gi nytt navn** eller **Fjern** en beregning fra et mål.</span><span class="sxs-lookup"><span data-stu-id="8060c-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="8060c-163">I området **Forhåndsvisning** vises dataskjemaet for målutdataenheten, inkludert filtre og dimensjoner.</span><span class="sxs-lookup"><span data-stu-id="8060c-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="8060c-164">Forhåndsvisningen reagerer dynamisk på endringer i konfigurasjonen.</span><span class="sxs-lookup"><span data-stu-id="8060c-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="8060c-165">Velg **Kjør** for å beregne resultater for det konfigurerte målet.</span><span class="sxs-lookup"><span data-stu-id="8060c-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="8060c-166">Velg **Lagre og lukk** hvis du vil beholde gjeldende konfigurasjon og kjøre tiltaket senere.</span><span class="sxs-lookup"><span data-stu-id="8060c-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="8060c-167">Gå til **Mål** for å vise det nylig opprettede målet i listen.</span><span class="sxs-lookup"><span data-stu-id="8060c-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="8060c-168">Administrer målene dine</span><span class="sxs-lookup"><span data-stu-id="8060c-168">Manage your measures</span></span>

<span data-ttu-id="8060c-169">Etter at du har [opprettet et mål](#create-a-measure), vises en liste over mål på **Mål**-siden.</span><span class="sxs-lookup"><span data-stu-id="8060c-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="8060c-170">Du finner informasjon om måltypen, oppretteren, opprettingsdato, status og tilstand.</span><span class="sxs-lookup"><span data-stu-id="8060c-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="8060c-171">Når du velger et mål fra listen, kan du forhåndsvise utdataene og laste ned en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="8060c-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="8060c-172">Hvis du vil oppdatere alle målene samtidig, velger du **Oppdater alle** uten å velge et bestemt mål.</span><span class="sxs-lookup"><span data-stu-id="8060c-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8060c-173">![Handlinger for å administrere enkeltmål](media/measure-actions.png "Handlinger for å administrere enkeltmål")</span><span class="sxs-lookup"><span data-stu-id="8060c-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="8060c-174">Velg et mål fra listen for følgende alternativer:</span><span class="sxs-lookup"><span data-stu-id="8060c-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="8060c-175">Velg målnavnet for å vise detaljene.</span><span class="sxs-lookup"><span data-stu-id="8060c-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="8060c-176">**Rediger** konfigurasjonen av målet.</span><span class="sxs-lookup"><span data-stu-id="8060c-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="8060c-177">**Oppdater** målet basert på de nyeste dataene.</span><span class="sxs-lookup"><span data-stu-id="8060c-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="8060c-178">**Gi nytt navn** til målet.</span><span class="sxs-lookup"><span data-stu-id="8060c-178">**Rename** the measure.</span></span>
- <span data-ttu-id="8060c-179">**Slett** målet.</span><span class="sxs-lookup"><span data-stu-id="8060c-179">**Delete** the measure.</span></span>
- <span data-ttu-id="8060c-180">**Aktiver** eller **Deaktiver**.</span><span class="sxs-lookup"><span data-stu-id="8060c-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="8060c-181">Inaktive tiltak oppdateres ikke under en [planlagt oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8060c-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="8060c-182">Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser.</span><span class="sxs-lookup"><span data-stu-id="8060c-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="8060c-183">De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="8060c-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="8060c-184">Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben.</span><span class="sxs-lookup"><span data-stu-id="8060c-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="8060c-185">Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.</span><span class="sxs-lookup"><span data-stu-id="8060c-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="8060c-186">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="8060c-186">Next step</span></span>

<span data-ttu-id="8060c-187">Du kan bruke eksisterende tiltak til å opprette [et kundesegment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8060c-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]