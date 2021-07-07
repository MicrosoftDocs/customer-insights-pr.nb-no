---
title: Opprett og administrer mål
description: Definer mål som skal analyseres og gjenspeile selskapets ytelse.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304813"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="c630e-103">Definere og administrere mål</span><span class="sxs-lookup"><span data-stu-id="c630e-103">Define and manage measures</span></span>

<span data-ttu-id="c630e-104">Tiltak hjelper deg med å få bedre forståelse av kundeatferd og forretningsytelse.</span><span class="sxs-lookup"><span data-stu-id="c630e-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="c630e-105">De ser på relevante verdier fra [enhetlige profiler](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c630e-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="c630e-106">En virksomhet vil for eksempel se *totalkostnaden per kunde* for å forstå en individuell kundes kjøpshistorikk eller måle *totalt salg av firmaet* for å forstå omsetningen på aggregert nivå i hele virksomheten.</span><span class="sxs-lookup"><span data-stu-id="c630e-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="c630e-107">Tiltak opprettes ved hjelp av måleverktøyet, en dataspørringsplattform med forskjellige operatorer og enkle tilordningsalternativer.</span><span class="sxs-lookup"><span data-stu-id="c630e-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="c630e-108">Den lar deg filtrere dataene, gruppere resultater, registrere [enhetsrelasjonsbaner](relationships.md) og forhåndsvise utdataene.</span><span class="sxs-lookup"><span data-stu-id="c630e-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="c630e-109">Bruk måleverktøyet til å planlegge forretningsaktiviteter ved å spørre etter kundedata og trekke ut innsikt.</span><span class="sxs-lookup"><span data-stu-id="c630e-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="c630e-110">Hvis du for eksempel oppretter et mål for *totalkostnad per kunde* og *total avkastning per kunde*, blir det enklere å identifisere en gruppe kunder med høy avkastning, men likevel høy avkastning.</span><span class="sxs-lookup"><span data-stu-id="c630e-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="c630e-111">Du kan [opprette et segment](segments.md) for å få de nest beste handlingene.</span><span class="sxs-lookup"><span data-stu-id="c630e-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="c630e-112">Bygg ditt eget mål fra bunnen av</span><span class="sxs-lookup"><span data-stu-id="c630e-112">Build your own measure from scratch</span></span>

<span data-ttu-id="c630e-113">Denne delen beskriver hvordan du oppretter et nytt mål fra bunnen av.</span><span class="sxs-lookup"><span data-stu-id="c630e-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="c630e-114">Du kan bygge et mål med dataattributter fra dataenheter som har en relasjon konfigurert til å koble til kundeenheten.</span><span class="sxs-lookup"><span data-stu-id="c630e-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="c630e-115">I Målgruppeinnsikt går du til **Mål**.</span><span class="sxs-lookup"><span data-stu-id="c630e-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="c630e-116">Velg **Ny** og deretter **Bygg din egen**.</span><span class="sxs-lookup"><span data-stu-id="c630e-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="c630e-117">Velg **Rediger navn**, og angi et **navn** for målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="c630e-118">Hvis den nye målkonfigurasjonen bare har to felter, for eksempel Kunde-ID og én beregning, legges utdataene til som en ny kolonne i den systemgenererte enheten Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="c630e-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="c630e-119">Du kan også se målets verdi i den enhetlige kundeprofilen.</span><span class="sxs-lookup"><span data-stu-id="c630e-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="c630e-120">Andre tiltak vil generere sine egne enheter.</span><span class="sxs-lookup"><span data-stu-id="c630e-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="c630e-121">Velg aggregasjonsfunksjon fra rullegardinlisten **Velg funksjon** i konfigurasjonsområdet.</span><span class="sxs-lookup"><span data-stu-id="c630e-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="c630e-122">Aggregasjonsfunksjonene omfatter:</span><span class="sxs-lookup"><span data-stu-id="c630e-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="c630e-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="c630e-123">**Sum**</span></span>
   - <span data-ttu-id="c630e-124">**Gjennomsnitt**</span><span class="sxs-lookup"><span data-stu-id="c630e-124">**Average**</span></span>
   - <span data-ttu-id="c630e-125">**Antall**</span><span class="sxs-lookup"><span data-stu-id="c630e-125">**Count**</span></span>
   - <span data-ttu-id="c630e-126">**Antall unike**</span><span class="sxs-lookup"><span data-stu-id="c630e-126">**Count Unique**</span></span>
   - <span data-ttu-id="c630e-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="c630e-127">**Max**</span></span>
   - <span data-ttu-id="c630e-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="c630e-128">**Min**</span></span>
   - <span data-ttu-id="c630e-129">**Første**: tar den første verdien i dataoppføringen</span><span class="sxs-lookup"><span data-stu-id="c630e-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="c630e-130">**Siste**: tar den siste verdien som ble lagt til i dataoppføringen</span><span class="sxs-lookup"><span data-stu-id="c630e-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorer for måleberegninger.":::

1. <span data-ttu-id="c630e-132">Velg **Legg til attributt** for å velge dataene du vil opprette dette målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="c630e-133">Velg fanen **Attributtene**.</span><span class="sxs-lookup"><span data-stu-id="c630e-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="c630e-134">Dataenhet: Velg enheten som inneholder attributtet du vil måle.</span><span class="sxs-lookup"><span data-stu-id="c630e-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="c630e-135">Dataattributt: Velg attributtet du vil bruke i aggregasjonsfunksjonen, for å beregne målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="c630e-136">Du kan bare velge ett attributt om gangen.</span><span class="sxs-lookup"><span data-stu-id="c630e-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="c630e-137">Du kan også velge et dataattributt fra et eksisterende mål ved å velge fanen **Mål**. Du kan også søke etter et enhets- eller målnavn.</span><span class="sxs-lookup"><span data-stu-id="c630e-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="c630e-138">Velg **Legg til** for å legge til det valgte attributtet i målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Velg et attributt som skal brukes i beregninger.":::

1. <span data-ttu-id="c630e-140">Hvis du vil bygge mer komplekse tiltak, kan du legge til flere attributter eller bruke operatorer for målefunksjon.</span><span class="sxs-lookup"><span data-stu-id="c630e-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Opprett et komplekst mål med matteoperatorer.":::

1. <span data-ttu-id="c630e-142">Hvis du vil legge til filtre, velger du **Filter** i konfigurasjonsområdet.</span><span class="sxs-lookup"><span data-stu-id="c630e-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="c630e-143">I delen **Legg til attributt** i **Filtre**-ruten velger du attributtet du vil bruke til å opprette filtre.</span><span class="sxs-lookup"><span data-stu-id="c630e-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="c630e-144">Angi filteroperatorene for å definere filteret for hvert valgte attributt.</span><span class="sxs-lookup"><span data-stu-id="c630e-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="c630e-145">Velg **Bruk** for å legge til filtrene i målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="c630e-146">Hvis du vil legge til dimensjoner, velger du **Dimensjon** i konfigurasjonsområdet.</span><span class="sxs-lookup"><span data-stu-id="c630e-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="c630e-147">Dimensjoner vises som kolonner i målutdataenheten.</span><span class="sxs-lookup"><span data-stu-id="c630e-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="c630e-148">Velg **Rediger dimensjoner** for å legge til dataattributter du vil gruppere målverdiene etter.</span><span class="sxs-lookup"><span data-stu-id="c630e-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="c630e-149">For eksempel poststed eller kjønn.</span><span class="sxs-lookup"><span data-stu-id="c630e-149">For example, city or gender.</span></span> <span data-ttu-id="c630e-150">Som standard velges *CustomerID*-dimensjonen for å opprette *mål på kundenivå*.</span><span class="sxs-lookup"><span data-stu-id="c630e-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="c630e-151">Du kan fjerne standarddimensjonen hvis du vil opprette *tiltak på forretningsnivå*.</span><span class="sxs-lookup"><span data-stu-id="c630e-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="c630e-152">Velg **Ferdig** for å legge til dimensjonene i målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="c630e-153">Hvis det finnes verdier i dataene som du må erstatte med et heltall, for eksempel erstatte *null* med *0*, velger du **Regler**.</span><span class="sxs-lookup"><span data-stu-id="c630e-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="c630e-154">Konfigurer regelen, og pass på at du bare velger hele tall som erstatning.</span><span class="sxs-lookup"><span data-stu-id="c630e-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="c630e-155">Hvis det finnes flere baner mellom dataenheten du tilordnet og *Kunde*-enheten, må du velge en av de identifiserte [enhetsrelasjonsbanene](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="c630e-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="c630e-156">Måleresultatene kan variere avhengig av den valgte banen.</span><span class="sxs-lookup"><span data-stu-id="c630e-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="c630e-157">Velg **Datainnstillinger**, og velg enhetsbanen som skal brukes til å identifisere målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="c630e-158">Hvis det bare finnes én enkelt bane til *Kunde*-enheten, vises ikke denne kontrollen.</span><span class="sxs-lookup"><span data-stu-id="c630e-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="c630e-159">Velg **Fullført** for å ta i bruk valget.</span><span class="sxs-lookup"><span data-stu-id="c630e-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Velg enhetsbanen for målet.":::

1. <span data-ttu-id="c630e-161">Hvis du vil legge til flere beregninger for målet, velger du **Ny beregning**.</span><span class="sxs-lookup"><span data-stu-id="c630e-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="c630e-162">Du kan bare bruke enheter i den samme enhetsbanen for nye beregninger.</span><span class="sxs-lookup"><span data-stu-id="c630e-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="c630e-163">Flere beregninger vises som nye kolonner i målutdataenheten.</span><span class="sxs-lookup"><span data-stu-id="c630e-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="c630e-164">Velg **...** i beregningen til **Duplikat**, **Gi nytt navn** eller **Fjern** en beregning fra et mål.</span><span class="sxs-lookup"><span data-stu-id="c630e-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="c630e-165">I området **Forhåndsvisning** vises dataskjemaet for målutdataenheten, inkludert filtre og dimensjoner.</span><span class="sxs-lookup"><span data-stu-id="c630e-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="c630e-166">Forhåndsvisningen reagerer dynamisk på endringer i konfigurasjonen.</span><span class="sxs-lookup"><span data-stu-id="c630e-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="c630e-167">Velg **Kjør** for å beregne resultater for det konfigurerte målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="c630e-168">Velg **Lagre og lukk** hvis du vil beholde gjeldende konfigurasjon og kjøre tiltaket senere.</span><span class="sxs-lookup"><span data-stu-id="c630e-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="c630e-169">Gå til **Mål** for å vise det nylig opprettede målet i listen.</span><span class="sxs-lookup"><span data-stu-id="c630e-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="c630e-170">Bruke en mal til å bygge et mål</span><span class="sxs-lookup"><span data-stu-id="c630e-170">Use a template to build a measure</span></span>

<span data-ttu-id="c630e-171">Du kan bruke forhåndsdefinerte maler for vanlige mål for å opprette dem.</span><span class="sxs-lookup"><span data-stu-id="c630e-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="c630e-172">Detaljerte beskrivelser av malene og en veiledet opplevelse hjelper deg med effektiv måloppretting.</span><span class="sxs-lookup"><span data-stu-id="c630e-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="c630e-173">Maler bygger på tilordnede data fra *Enhetlig aktivitet*-enheten.</span><span class="sxs-lookup"><span data-stu-id="c630e-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="c630e-174">Sørg derfor for at du har konfigurert [kundeaktiviteter](activities.md) før du oppretter et mål fra en mal.</span><span class="sxs-lookup"><span data-stu-id="c630e-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="c630e-175">Tilgjengelige målmaler:</span><span class="sxs-lookup"><span data-stu-id="c630e-175">Available measure templates:</span></span> 
- <span data-ttu-id="c630e-176">Gjennomsnittlig transaksjonsverdi (ATV)</span><span class="sxs-lookup"><span data-stu-id="c630e-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="c630e-177">Total transaksjonsverdi</span><span class="sxs-lookup"><span data-stu-id="c630e-177">Total transaction value</span></span>
- <span data-ttu-id="c630e-178">Gjennomsnittlig daglig omsetning</span><span class="sxs-lookup"><span data-stu-id="c630e-178">Average daily revenue</span></span>
- <span data-ttu-id="c630e-179">Gjennomsnittlig årlig omsetning</span><span class="sxs-lookup"><span data-stu-id="c630e-179">Average yearly revenue</span></span>
- <span data-ttu-id="c630e-180">Transaksjonstelling</span><span class="sxs-lookup"><span data-stu-id="c630e-180">Transaction count</span></span>
- <span data-ttu-id="c630e-181">Opptjente fordelspoeng</span><span class="sxs-lookup"><span data-stu-id="c630e-181">Loyalty points earned</span></span>
- <span data-ttu-id="c630e-182">Innløste fordelspoeng</span><span class="sxs-lookup"><span data-stu-id="c630e-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="c630e-183">Saldo for fordelspoeng</span><span class="sxs-lookup"><span data-stu-id="c630e-183">Loyalty points balance</span></span>
- <span data-ttu-id="c630e-184">Levetid for aktiv kunde</span><span class="sxs-lookup"><span data-stu-id="c630e-184">Active customer lifespan</span></span>
- <span data-ttu-id="c630e-185">Varighet for fordelsmedlemskap</span><span class="sxs-lookup"><span data-stu-id="c630e-185">Loyalty membership duration</span></span>
- <span data-ttu-id="c630e-186">Tid siden forrige kjøp</span><span class="sxs-lookup"><span data-stu-id="c630e-186">Time since last purchase</span></span>

<span data-ttu-id="c630e-187">Fremgangsmåten nedenfor beskriver hvordan du bygger et nytt mål ved hjelp av en mal.</span><span class="sxs-lookup"><span data-stu-id="c630e-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="c630e-188">I Målgruppeinnsikt går du til **Mål**.</span><span class="sxs-lookup"><span data-stu-id="c630e-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="c630e-189">Velg **Ny** og deretter **Velg en mal**.</span><span class="sxs-lookup"><span data-stu-id="c630e-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Skjermbilde av rullegardinmenyen når du oppretter et nytt mål med utheving på mal.":::

1. <span data-ttu-id="c630e-191">Finn malen du ønsker, og velg **Velg mal**.</span><span class="sxs-lookup"><span data-stu-id="c630e-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="c630e-192">Se gjennom de nødvendige dataene, og velg **Kom i gang** hvis du har alle dataene på plass.</span><span class="sxs-lookup"><span data-stu-id="c630e-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="c630e-193">Angi navnet på målet og utdataenheten i **Rediger navn**-ruten.</span><span class="sxs-lookup"><span data-stu-id="c630e-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="c630e-194">Velg **Ferdig**.</span><span class="sxs-lookup"><span data-stu-id="c630e-194">Select **Done**.</span></span>

1. <span data-ttu-id="c630e-195">I delen **Angi tidsperiode** definerer du tidsrammen for dataene som skal brukes.</span><span class="sxs-lookup"><span data-stu-id="c630e-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="c630e-196">Velg om du vil at det nye målet skal dekke hele datasett, ved å velge **Alle tider**, eller om du vil at målet skal fokusere på en **Bestemt tidsperiode**.</span><span class="sxs-lookup"><span data-stu-id="c630e-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Skjermbilde som viser tidsperiodedelen når du konfigurerer et mål fra en mal.":::

1. <span data-ttu-id="c630e-198">I den neste delen velger du **Legg til data** for å velge aktivitetene og tilordne de tilsvarende dataene fra enheten *Enhetlig aktivitet*.</span><span class="sxs-lookup"><span data-stu-id="c630e-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="c630e-199">Trinn 1 av 2: Under **Aktivitetstype** velger du typen enhet du vil bruke.</span><span class="sxs-lookup"><span data-stu-id="c630e-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="c630e-200">For **Aktiviteter** velger du enhetene du vil tilordne.</span><span class="sxs-lookup"><span data-stu-id="c630e-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="c630e-201">Trinn 2 av 2: Velg attributtet fra enheten *Enhetlig aktivitet* for komponenten som kreves av formelen.</span><span class="sxs-lookup"><span data-stu-id="c630e-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="c630e-202">For gjennomsnittlig transaksjonsverdi er det for eksempel attributtet som representerer transaksjonsverdien.</span><span class="sxs-lookup"><span data-stu-id="c630e-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="c630e-203">For **Aktivitetstidsstempel** velger du attributtet fra enheten Enhetlig aktivitet som representerer datoen og klokkeslettet for aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="c630e-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="c630e-204">Når datatilordningen er vellykket, kan du se statusen **Fullført** og navnet på de tilordnede aktivitetene og attributtene.</span><span class="sxs-lookup"><span data-stu-id="c630e-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Skjermbilde av en fullført målmalkonfigurasjon.":::

1. <span data-ttu-id="c630e-206">Du kan nå velge **Kjør** for å beregne resultatene av målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="c630e-207">Hvis du vil finjustere det senere, velger du **Lagre utkast**.</span><span class="sxs-lookup"><span data-stu-id="c630e-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="c630e-208">Administrer målene dine</span><span class="sxs-lookup"><span data-stu-id="c630e-208">Manage your measures</span></span>

<span data-ttu-id="c630e-209">Du finner mållisten på **Mål**-siden.</span><span class="sxs-lookup"><span data-stu-id="c630e-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="c630e-210">Du finner informasjon om måltypen, oppretteren, opprettingsdato, status og tilstand.</span><span class="sxs-lookup"><span data-stu-id="c630e-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="c630e-211">Når du velger et mål fra listen, kan du forhåndsvise utdataene og laste ned en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="c630e-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="c630e-212">Hvis du vil oppdatere alle målene samtidig, velger du **Oppdater alle** uten å velge et bestemt mål.</span><span class="sxs-lookup"><span data-stu-id="c630e-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c630e-213">![Handlinger for å administrere enkeltmål.](media/measure-actions.png "Handlinger for å administrere enkeltmål.")</span><span class="sxs-lookup"><span data-stu-id="c630e-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="c630e-214">Velg et mål fra listen for følgende alternativer:</span><span class="sxs-lookup"><span data-stu-id="c630e-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="c630e-215">Velg målnavnet for å vise detaljene.</span><span class="sxs-lookup"><span data-stu-id="c630e-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="c630e-216">**Rediger** konfigurasjonen av målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="c630e-217">**Oppdater** målet basert på de nyeste dataene.</span><span class="sxs-lookup"><span data-stu-id="c630e-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="c630e-218">**Gi nytt navn** til målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-218">**Rename** the measure.</span></span>
- <span data-ttu-id="c630e-219">**Slett** målet.</span><span class="sxs-lookup"><span data-stu-id="c630e-219">**Delete** the measure.</span></span>
- <span data-ttu-id="c630e-220">**Aktiver** eller **Deaktiver**.</span><span class="sxs-lookup"><span data-stu-id="c630e-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="c630e-221">Inaktive tiltak oppdateres ikke under en [planlagt oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c630e-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="c630e-222">Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser.</span><span class="sxs-lookup"><span data-stu-id="c630e-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c630e-223">De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c630e-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c630e-224">Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben.</span><span class="sxs-lookup"><span data-stu-id="c630e-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c630e-225">Når du har valgt **Se detaljer** for en av jobbens oppgaver, finner du ytterligere informasjon: behandlingstid, siste behandlingsdato og alle feil og advarsler knyttet til oppgaven.</span><span class="sxs-lookup"><span data-stu-id="c630e-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="c630e-226">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="c630e-226">Next step</span></span>

<span data-ttu-id="c630e-227">Du kan bruke eksisterende målinger til å opprette [et kundesegment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c630e-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
