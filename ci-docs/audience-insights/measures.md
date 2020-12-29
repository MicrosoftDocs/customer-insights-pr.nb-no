---
title: Opprett og rediger mål
description: Definere kunderelaterte tiltak for å analysere og gjenspeile ytelsen til bestemte forretningsområder.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406534"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="ce351-103">Definere og administrere mål</span><span class="sxs-lookup"><span data-stu-id="ce351-103">Define and manage measures</span></span>

<span data-ttu-id="ce351-104">**Mål** representerer viktige ytelsesindikatorer (KPI-er) som gjenspeiler ytelsen og tilstanden til bestemte forretningsområder.</span><span class="sxs-lookup"><span data-stu-id="ce351-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="ce351-105">Målgruppeinnsikt gir en intuitiv opplevelse for bygging av ulike typer mål, ved hjelp av et spørringsverktøy som ikke krever at du skriver kode eller validerer målene manuelt.</span><span class="sxs-lookup"><span data-stu-id="ce351-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="ce351-106">Du kan spore forretningsmålene på siden **Start**, se mål for bestemte kunder på **Kundekort** og bruke mål til å definere kundesegmenter på siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="ce351-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="ce351-107">Opprette et mål</span><span class="sxs-lookup"><span data-stu-id="ce351-107">Create a measure</span></span>

<span data-ttu-id="ce351-108">Denne delen veileder deg gjennom opprettingen av et mål fra bunnen av.</span><span class="sxs-lookup"><span data-stu-id="ce351-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="ce351-109">Du kan bygge tiltak med data fra flere datakilder som er koblet sammen via kundeenheten.</span><span class="sxs-lookup"><span data-stu-id="ce351-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="ce351-110">Enkelte [tjenestebegrensninger](service-limits.md) gjelder.</span><span class="sxs-lookup"><span data-stu-id="ce351-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="ce351-111">I Målgruppeinnsikt går du til **Mål**.</span><span class="sxs-lookup"><span data-stu-id="ce351-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="ce351-112">Velg **Nye mål**.</span><span class="sxs-lookup"><span data-stu-id="ce351-112">Select **New measure**.</span></span>

3. <span data-ttu-id="ce351-113">Velg målet **Type**:</span><span class="sxs-lookup"><span data-stu-id="ce351-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="ce351-114">**Kundeattributt**: Et enkelt felt per kunde som gjenspeiler en poengsum, en verdi eller en tilstand for kunden.</span><span class="sxs-lookup"><span data-stu-id="ce351-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="ce351-115">Kundeattributter opprettes som attributter i en ny systemgenerert enhet som kalles **Kundemål**.</span><span class="sxs-lookup"><span data-stu-id="ce351-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="ce351-116">**Kundemål**: Innsikt i kundeatferd med nedbryting etter valgte dimensjoner.</span><span class="sxs-lookup"><span data-stu-id="ce351-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="ce351-117">Det genereres en ny enhet for hvert mål, potensielt med flere oppføringer per kunde.</span><span class="sxs-lookup"><span data-stu-id="ce351-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="ce351-118">**Forretningsmål**: Sporer forretningsprestasjonen og tilstanden til virksomheten.</span><span class="sxs-lookup"><span data-stu-id="ce351-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="ce351-119">Forretningstiltak kan ha to forskjellige resultater: et numerisk resultat som vises på siden **Start** eller en ny enhet som du finner på siden **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="ce351-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="ce351-120">Angi et **Navn** og et valgfritt **Visningsnavn**, og velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="ce351-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="ce351-121">I delen **Enheter** velger du første enhet fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="ce351-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="ce351-122">Du bør nå bestemme om det skal brukes tilleggsenheter som en del av måldefinisjonen.</span><span class="sxs-lookup"><span data-stu-id="ce351-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ce351-123">![Måldefinisjon](media/measure-definition.png "Måldefinisjon")</span><span class="sxs-lookup"><span data-stu-id="ce351-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="ce351-124">Hvis du vil legge til flere enheter, velger du **Legg til enhet**, og velg enhetene du vil bruke for målet.</span><span class="sxs-lookup"><span data-stu-id="ce351-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ce351-125">Du kan bare velge enheter som har relasjoner til startenheten din.</span><span class="sxs-lookup"><span data-stu-id="ce351-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="ce351-126">Hvis du vil ha mer informasjon om hvordan du definerer relasjoner, se [Relasjoner](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="ce351-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="ce351-127">Du kan eventuelt konfigurere variabler.</span><span class="sxs-lookup"><span data-stu-id="ce351-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="ce351-128">I delen **Variabler** velger du **Ny variabel**.</span><span class="sxs-lookup"><span data-stu-id="ce351-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="ce351-129">Variabler er beregninger som gjøres for hver av de valgte oppføringene.</span><span class="sxs-lookup"><span data-stu-id="ce351-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="ce351-130">Eksempel: Sammendrag av salgssted (POS) og onlinesalg for hver av kundenes oppføringer.</span><span class="sxs-lookup"><span data-stu-id="ce351-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="ce351-131">Gi variabelen et **Navn**.</span><span class="sxs-lookup"><span data-stu-id="ce351-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="ce351-132">I området **Uttrykk** velger du et felt å begynne beregningen med.</span><span class="sxs-lookup"><span data-stu-id="ce351-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="ce351-133">Skriv inn et uttrykk i området **Uttrykk** mens du velger flere felt som skal tas med i beregningen.</span><span class="sxs-lookup"><span data-stu-id="ce351-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ce351-134">For øyeblikket støttes bare aritmetiske uttrykk.</span><span class="sxs-lookup"><span data-stu-id="ce351-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="ce351-135">I tillegg støttes ikke variabelberegning for enheter fra forskjellige [enhetsbaner](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="ce351-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="ce351-136">Velg **Ferdig**.</span><span class="sxs-lookup"><span data-stu-id="ce351-136">Select **Done**.</span></span>

11. <span data-ttu-id="ce351-137">I delen **Måldefinisjon** definerer du hvordan de valgte enhetene og de beregnede variablene samles i en ny målenhet eller et nytt attributt.</span><span class="sxs-lookup"><span data-stu-id="ce351-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="ce351-138">Velg **Ny dimensjon**.</span><span class="sxs-lookup"><span data-stu-id="ce351-138">Select **New dimension**.</span></span> <span data-ttu-id="ce351-139">Du kan tenke på en dimensjon som en *grupper etter*-funksjon.</span><span class="sxs-lookup"><span data-stu-id="ce351-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="ce351-140">Utdataene for målenheten eller attributtet blir gruppert etter alle de definerte dimensjonene.</span><span class="sxs-lookup"><span data-stu-id="ce351-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ce351-141">![Velg samlesyklus](media/measures-businessreport-measure-definition2.png "Velg samlesyklus")</span><span class="sxs-lookup"><span data-stu-id="ce351-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="ce351-142">Velg eller angi følgende informasjon som en del av dimensjonens definisjon:</span><span class="sxs-lookup"><span data-stu-id="ce351-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="ce351-143">**Enhet**: Hvis du angir en målenhet, må den inneholde minst ett attributt.</span><span class="sxs-lookup"><span data-stu-id="ce351-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="ce351-144">Hvis du angir et målattributt, vil det bare inneholde ett attributt som standard.</span><span class="sxs-lookup"><span data-stu-id="ce351-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="ce351-145">Dette valget handler om å velge enheten som inneholder det attributtet.</span><span class="sxs-lookup"><span data-stu-id="ce351-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="ce351-146">**Felt**: Velg det bestemte attributtet som skal inkluderes enten i målenheten eller i attributtet.</span><span class="sxs-lookup"><span data-stu-id="ce351-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="ce351-147">**Samling**: Velg om du vil samle data daglig, månedlig eller årlig.</span><span class="sxs-lookup"><span data-stu-id="ce351-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="ce351-148">Det er et nødvendig valg bare hvis du har valgt et datotype-attributt.</span><span class="sxs-lookup"><span data-stu-id="ce351-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="ce351-149">**Som**: Definerer navnet på det nye feltet.</span><span class="sxs-lookup"><span data-stu-id="ce351-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="ce351-150">**Visningsnavn**: Definerer visningsnavnet for feltet.</span><span class="sxs-lookup"><span data-stu-id="ce351-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce351-151">Forretningsmålet blir lagret som en enhet med ett tall og vises på siden **Start** mindre du legger til flere dimensjoner i målet.</span><span class="sxs-lookup"><span data-stu-id="ce351-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="ce351-152">Målet vil *ikke* vises på siden **Start** etter at du har lagt til flere dimensjoner.</span><span class="sxs-lookup"><span data-stu-id="ce351-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="ce351-153">Hvis du vil, kan du legge til aggregeringsfunksjoner.</span><span class="sxs-lookup"><span data-stu-id="ce351-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="ce351-154">Alle aggregasjoner du oppretter, fører til en ny verdi i målenheten eller attributtet.</span><span class="sxs-lookup"><span data-stu-id="ce351-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="ce351-155">Støttede aggregeringsfunksjoner er: **Min**, **Maks**, **Gjennomsnitt**, **Median**, **Sum**, **Antall unike**, **Første** (tar den første oppføringen for en dimensjonsverdi) og **Siste** (tar den siste oppføringen til en dimensjonsverdi).</span><span class="sxs-lookup"><span data-stu-id="ce351-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="ce351-156">Velg **Lagre** for å bruke endringene på målet.</span><span class="sxs-lookup"><span data-stu-id="ce351-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="ce351-157">Administrer målene dine</span><span class="sxs-lookup"><span data-stu-id="ce351-157">Manage your measures</span></span>

<span data-ttu-id="ce351-158">Etter at du har opprettet minst ett mål, vises en liste over mål på **Mål**-siden.</span><span class="sxs-lookup"><span data-stu-id="ce351-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="ce351-159">Du finner informasjon om måltypen, oppretteren, opprettelsesdato og -tidspunkt, dato og klokkeslett for siste redigering, status (om målet er aktivt, inaktivt eller mislykket), og dato og tidspunkt for siste oppdatering.</span><span class="sxs-lookup"><span data-stu-id="ce351-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="ce351-160">Når du velger et mål fra listen, kan du se en forhåndsvisning av utdataene.</span><span class="sxs-lookup"><span data-stu-id="ce351-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="ce351-161">Hvis du vil oppdatere alle målene samtidig, velger du **Oppdater alle** uten å velge et bestemt mål.</span><span class="sxs-lookup"><span data-stu-id="ce351-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce351-162">![Handlinger for å administrere enkeltmål](media/measure-actions.png "Handlinger for å administrere enkeltmål")</span><span class="sxs-lookup"><span data-stu-id="ce351-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="ce351-163">Alternativt kan du velge et mål fra listen og utføre én av følgende handlinger:</span><span class="sxs-lookup"><span data-stu-id="ce351-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="ce351-164">Velg målnavnet for å vise detaljene.</span><span class="sxs-lookup"><span data-stu-id="ce351-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="ce351-165">**Rediger** konfigurasjonen av målet.</span><span class="sxs-lookup"><span data-stu-id="ce351-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="ce351-166">**Gi nytt navn** til målet.</span><span class="sxs-lookup"><span data-stu-id="ce351-166">**Rename** the measure.</span></span>
- <span data-ttu-id="ce351-167">**Slett** målet.</span><span class="sxs-lookup"><span data-stu-id="ce351-167">**Delete** the measure.</span></span>
- <span data-ttu-id="ce351-168">Velg ellipsen (...), og deretter **Oppdater** for å starte oppdateringsprosessen for målet.</span><span class="sxs-lookup"><span data-stu-id="ce351-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="ce351-169">Velg ellipsen (...), og deretter **Last ned** for å hente en .CSV-fil for målet.</span><span class="sxs-lookup"><span data-stu-id="ce351-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="ce351-170">Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser.</span><span class="sxs-lookup"><span data-stu-id="ce351-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ce351-171">De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ce351-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ce351-172">Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben.</span><span class="sxs-lookup"><span data-stu-id="ce351-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ce351-173">Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.</span><span class="sxs-lookup"><span data-stu-id="ce351-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="ce351-174">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="ce351-174">Next step</span></span>

<span data-ttu-id="ce351-175">Du kan bruke eksisterende mål for å opprette ditt første kundesegment på siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="ce351-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="ce351-176">Du finner mer informasjon på [Segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ce351-176">For more information, see [Segments](segments.md).</span></span>
