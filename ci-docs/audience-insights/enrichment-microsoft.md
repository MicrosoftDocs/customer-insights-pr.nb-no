---
title: Supplere kundeprofiler med data fra Microsoft
description: Bruk proprietære data fra Microsoft til å supplere kundedataene med merke- og interesseaffiniteter.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064903"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="a0a97-103">Supplere kundeprofiler med merke- og interesseaffiniteter (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="a0a97-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="a0a97-104">Bruk proprietære data fra Microsoft til å supplere kundedataene med merke- og interesseaffiniteter.</span><span class="sxs-lookup"><span data-stu-id="a0a97-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="a0a97-105">Disse affinitetene fastsettes basert på data fra personer med liknende demografiske data som kundene dine.</span><span class="sxs-lookup"><span data-stu-id="a0a97-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="a0a97-106">Ved hjelp av denne informasjonen kan du bedre forstå og segmentere kunder basert på deres affinitet til bestemte merker og interesser.</span><span class="sxs-lookup"><span data-stu-id="a0a97-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="a0a97-107">I målgruppeinnsikt går du til **Data** > **Supplering** for å [konfigurere og vise suppleringer](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="a0a97-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="a0a97-108">Hvis du vil konfigurere merkeaffinitet som skal berikes, går du til kategorien **Utforsk** og velger **Suppler dataene** på **Merker**-flisen.</span><span class="sxs-lookup"><span data-stu-id="a0a97-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="a0a97-109">Hvis du vil konfigurere interesseaffinitet som skal berikes, går du til kategorien **Utforsk** og velger **Suppler dataene** på **Interesser**-flisen.</span><span class="sxs-lookup"><span data-stu-id="a0a97-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a0a97-110">![Fliser for merker og interesser](media/BrandsInterest-tile-Hub.png "Fliser for merker og interesser")</span><span class="sxs-lookup"><span data-stu-id="a0a97-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="a0a97-111">Slik avgjør vi affiniteter</span><span class="sxs-lookup"><span data-stu-id="a0a97-111">How we determine affinities</span></span>

<span data-ttu-id="a0a97-112">Vi bruker Microsofts søkedata på Internett til å finne affiniteter for merker og interesser i ulike demografiske segmenter (definert av alder, kjønn eller sted).</span><span class="sxs-lookup"><span data-stu-id="a0a97-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="a0a97-113">Det elektroniske søkevolumet for et merke eller en interesse avgjør hvor mye affinitet et demografisk segment, sammenlignet med andre segmenter, har til merket eller interessen.</span><span class="sxs-lookup"><span data-stu-id="a0a97-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="a0a97-114">Affinitetsnivå og poengsum</span><span class="sxs-lookup"><span data-stu-id="a0a97-114">Affinity level and score</span></span>

<span data-ttu-id="a0a97-115">For hver supplerte kundeprofil oppgir vi to relaterte verdier – affinitetsnivå og affinitetspoengsum.</span><span class="sxs-lookup"><span data-stu-id="a0a97-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="a0a97-116">Disse verdiene hjelper deg med å bestemme hvor sterkt affiniteten er for den profilens demografiske segment, for et merke eller en interesse sammenlignet med andre demografiske segmenter.</span><span class="sxs-lookup"><span data-stu-id="a0a97-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="a0a97-117">*Affinitetsnivået* består av fire nivåer, og *affinitetspoengsummen* beregnes på en 100-punkts skala som tilordnes til affinitetsnivåene.</span><span class="sxs-lookup"><span data-stu-id="a0a97-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="a0a97-118">Affinitetsnivå</span><span class="sxs-lookup"><span data-stu-id="a0a97-118">Affinity level</span></span> |<span data-ttu-id="a0a97-119">Affinitetspoengsum</span><span class="sxs-lookup"><span data-stu-id="a0a97-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="a0a97-120">Svært høyt</span><span class="sxs-lookup"><span data-stu-id="a0a97-120">Very high</span></span>     | <span data-ttu-id="a0a97-121">85–100</span><span class="sxs-lookup"><span data-stu-id="a0a97-121">85-100</span></span>       |
|<span data-ttu-id="a0a97-122">Høy</span><span class="sxs-lookup"><span data-stu-id="a0a97-122">High</span></span>     | <span data-ttu-id="a0a97-123">70–84</span><span class="sxs-lookup"><span data-stu-id="a0a97-123">70-84</span></span>        |
|<span data-ttu-id="a0a97-124">Middels</span><span class="sxs-lookup"><span data-stu-id="a0a97-124">Medium</span></span>     | <span data-ttu-id="a0a97-125">35–69</span><span class="sxs-lookup"><span data-stu-id="a0a97-125">35-69</span></span>        |
|<span data-ttu-id="a0a97-126">Lav</span><span class="sxs-lookup"><span data-stu-id="a0a97-126">Low</span></span>     | <span data-ttu-id="a0a97-127">1–34</span><span class="sxs-lookup"><span data-stu-id="a0a97-127">1-34</span></span>        |

<span data-ttu-id="a0a97-128">Avhengig av detaljnivået du ønsker for å måle affiniteten, kan du bruke enten affinitetsnivå eller poengsum.</span><span class="sxs-lookup"><span data-stu-id="a0a97-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="a0a97-129">Affinitetspoengsummen gir deg mer nøyaktig kontroll.</span><span class="sxs-lookup"><span data-stu-id="a0a97-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="a0a97-130">Støttede land/områder</span><span class="sxs-lookup"><span data-stu-id="a0a97-130">Supported countries/regions</span></span>

<span data-ttu-id="a0a97-131">Vi støtter for øyeblikket følgende alternativer for land/område: Australia, Canada (engelsk), Frankrike, Tyskland, Storbritannia eller USA (engelsk).</span><span class="sxs-lookup"><span data-stu-id="a0a97-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="a0a97-132">Du velger et land ved å åpne **Merkesupplering** eller **Interessesupplering** og velger **Endre** ved siden av **Land/område**.</span><span class="sxs-lookup"><span data-stu-id="a0a97-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="a0a97-133">Velg et alternativ i ruten **Innstillinger for land/område**, og velg **Bruk**.</span><span class="sxs-lookup"><span data-stu-id="a0a97-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="a0a97-134">Implikasjoner knyttet til valg av land</span><span class="sxs-lookup"><span data-stu-id="a0a97-134">Implications related to country selection</span></span>

- <span data-ttu-id="a0a97-135">Når du [velger dine egne merker](#define-your-brands-or-interests), gir systemet forslag basert på det valgte landet eller området.</span><span class="sxs-lookup"><span data-stu-id="a0a97-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="a0a97-136">Når du [velger en bransje](#define-your-brands-or-interests), får du de mest relevante merkene eller interessene basert på det valgte landet eller området.</span><span class="sxs-lookup"><span data-stu-id="a0a97-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="a0a97-137">Når du [supplerer profiler](#refresh-enrichment), blir alle kundeprofilene supplert, og vi får data for de valgte merkene og interessene.</span><span class="sxs-lookup"><span data-stu-id="a0a97-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="a0a97-138">Inkludering av profiler som ikke er i det valgte landet eller området.</span><span class="sxs-lookup"><span data-stu-id="a0a97-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="a0a97-139">Hvis du for eksempel valgte Tyskland, vil vi supplere profiler i USA hvis vi har data tilgjengelig for de valgte merkene og interessene i USA.</span><span class="sxs-lookup"><span data-stu-id="a0a97-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="a0a97-140">Konfigurere supplering</span><span class="sxs-lookup"><span data-stu-id="a0a97-140">Configure Enrichment</span></span>

<span data-ttu-id="a0a97-141">En veiledet opplevelse hjelper deg gjennom konfigurasjonen av suppleringene.</span><span class="sxs-lookup"><span data-stu-id="a0a97-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="a0a97-142">Definer merker og interesser</span><span class="sxs-lookup"><span data-stu-id="a0a97-142">Define your brands or interests</span></span>

<span data-ttu-id="a0a97-143">Velg ett av følgende alternativer:</span><span class="sxs-lookup"><span data-stu-id="a0a97-143">Select one of the following options:</span></span>

- <span data-ttu-id="a0a97-144">**Bransje**: Systemet identifiserer de mest populære merkene og interessene som er relevante for bransjen, og supplerer kundedataene med dem.</span><span class="sxs-lookup"><span data-stu-id="a0a97-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="a0a97-145">**Velg dine egne**: Velg opptil fem elementer fra listen over merker og interesser som er mest relevante for organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="a0a97-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="a0a97-146">Hvis du vil legge til et merke eller en interesse, angir du det i inndataområdet for å få forslag basert på samsvarende betingelser.</span><span class="sxs-lookup"><span data-stu-id="a0a97-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="a0a97-147">Hvis vi ikke viser et merke eller en interesse du leter etter, kan du sende oss tilbakemelding ved hjelp av **Foreslå**-koblingen.</span><span class="sxs-lookup"><span data-stu-id="a0a97-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="a0a97-148">Se gjennom innstillinger for supplering</span><span class="sxs-lookup"><span data-stu-id="a0a97-148">Review enrichment preferences</span></span>

<span data-ttu-id="a0a97-149">Se gjennom standardinnstillingene for supplering, og oppdater dem etter behov.</span><span class="sxs-lookup"><span data-stu-id="a0a97-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skjermbilde av vinduet for innstillinger for supplering.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="a0a97-151">Velg enhet som skal suppleres</span><span class="sxs-lookup"><span data-stu-id="a0a97-151">Select entity to enrich</span></span>

<span data-ttu-id="a0a97-152">Velg **Supplert enhet**, og velg kundedatasettet du vil supplere med firmadata fra Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a0a97-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="a0a97-153">Du kan velge kundeenheten for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="a0a97-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="a0a97-154">Tilordne feltene</span><span class="sxs-lookup"><span data-stu-id="a0a97-154">Map your fields</span></span>

<span data-ttu-id="a0a97-155">Tilordne felter fra enheten for enhetlige kunder for å definere det demografiske segmentet du vil at systemet skal bruke til supplering av kundedataene.</span><span class="sxs-lookup"><span data-stu-id="a0a97-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="a0a97-156">Tilordne land/område og minst attributtene Fødselsdato eller Kjønn.</span><span class="sxs-lookup"><span data-stu-id="a0a97-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="a0a97-157">I tillegg må du tilordne minst én by (og delstat/område) eller ett postnummer.</span><span class="sxs-lookup"><span data-stu-id="a0a97-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="a0a97-158">Velg **Rediger** for å definere tilordningen av feltene, og velg **Bruk** når du er ferdig.</span><span class="sxs-lookup"><span data-stu-id="a0a97-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="a0a97-159">Velg **Lagre** for å fullføre felttilordningen.</span><span class="sxs-lookup"><span data-stu-id="a0a97-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="a0a97-160">Følgende formater og verdier støttes (det skilles ikke mellom små og store bokstaver i verdier):</span><span class="sxs-lookup"><span data-stu-id="a0a97-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="a0a97-161">**Fødselsdato**: Vi anbefaler at fødselsdatoen konverteres til en DateTime-type under datainntak.</span><span class="sxs-lookup"><span data-stu-id="a0a97-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="a0a97-162">Alternativt kan den være en streng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-formatet «ÅÅÅÅ-MM-DD» eller «ÅÅÅÅ-MM-DDTtt:mm:ssZ».</span><span class="sxs-lookup"><span data-stu-id="a0a97-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="a0a97-163">**Kjønn**: hann, hunn, ukjent</span><span class="sxs-lookup"><span data-stu-id="a0a97-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="a0a97-164">**Postnummer**: Femsifrede postnumre for USA, standard postnummer alle andre steder</span><span class="sxs-lookup"><span data-stu-id="a0a97-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="a0a97-165">**Sted**: Navn på poststed på engelsk</span><span class="sxs-lookup"><span data-stu-id="a0a97-165">**City**: City name in English</span></span>
- <span data-ttu-id="a0a97-166">**Delstat/område**: Forkortelse på to bokstaver for USA og Canada.</span><span class="sxs-lookup"><span data-stu-id="a0a97-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="a0a97-167">Forkortelse på to eller tre bokstaver for Australia.</span><span class="sxs-lookup"><span data-stu-id="a0a97-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="a0a97-168">Gjelder ikke for Frankrike, Tyskland eller Storbritannia.</span><span class="sxs-lookup"><span data-stu-id="a0a97-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="a0a97-169">**Land/område**:</span><span class="sxs-lookup"><span data-stu-id="a0a97-169">**Country/Region**:</span></span>

  - <span data-ttu-id="a0a97-170">US: Amerikas forente stater, De forente stater, USA, US, Amerika</span><span class="sxs-lookup"><span data-stu-id="a0a97-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="a0a97-171">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="a0a97-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="a0a97-172">GB: Storbritannia, UK, Great Britain, GB, Det forente kongerike Storbritannia og Nord-Irland, United Kingdom of Great Britain</span><span class="sxs-lookup"><span data-stu-id="a0a97-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="a0a97-173">AU: Australia, AU, Commonwealth of Australia</span><span class="sxs-lookup"><span data-stu-id="a0a97-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="a0a97-174">FR: Frankrike, FR, Republikken Frankrike</span><span class="sxs-lookup"><span data-stu-id="a0a97-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="a0a97-175">DE: Tyskland, German, Deutschland, Allemagne, DE, Forbundsrepublikken Tyskland, Republic of Germany</span><span class="sxs-lookup"><span data-stu-id="a0a97-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="a0a97-176">Se gjennom og gi navn til suppleringen</span><span class="sxs-lookup"><span data-stu-id="a0a97-176">Review and name the enrichment</span></span>

<span data-ttu-id="a0a97-177">Til slutt får du se gjennom informasjonen og angi et navn for suppleringen.</span><span class="sxs-lookup"><span data-stu-id="a0a97-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Side for å se gjennom og gi navn til interesser.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="a0a97-179">Oppdatere supplering</span><span class="sxs-lookup"><span data-stu-id="a0a97-179">Refresh enrichment</span></span>

<span data-ttu-id="a0a97-180">Kjør suppleringen etter å ha konfigurert merker, interesser og felttilordningen for demografi.</span><span class="sxs-lookup"><span data-stu-id="a0a97-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="a0a97-181">Hvis du vil starte prosessen, velger du **Kjør** på siden for merke- eller interessekonfigurasjon.</span><span class="sxs-lookup"><span data-stu-id="a0a97-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="a0a97-182">I tillegg kan du la systemet kjøre suppleringen automatisk som en del av en planlagt oppdatering.</span><span class="sxs-lookup"><span data-stu-id="a0a97-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="a0a97-183">Avhengig av størrelsen på kundedataene kan det ta flere minutter å fullføre en supplering.</span><span class="sxs-lookup"><span data-stu-id="a0a97-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="a0a97-184">Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser.</span><span class="sxs-lookup"><span data-stu-id="a0a97-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a0a97-185">De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a0a97-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a0a97-186">Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben.</span><span class="sxs-lookup"><span data-stu-id="a0a97-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a0a97-187">Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.</span><span class="sxs-lookup"><span data-stu-id="a0a97-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a0a97-188">Resultater av supplering</span><span class="sxs-lookup"><span data-stu-id="a0a97-188">Enrichment results</span></span>

<span data-ttu-id="a0a97-189">Når du har kjørt suppleringsprosessen, går du til **Mine suppleringer** for å se du gjennom det totale antallet supplerte kunder, og en analyse over merker og interesser i de supplerte kundeprofilene.</span><span class="sxs-lookup"><span data-stu-id="a0a97-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Forhåndsvisning av resultater etter kjøring av suppleringsprosessen":::

<span data-ttu-id="a0a97-191">Se gjennom de supplerte dataene ved å velge **Vis supplerte data** i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="a0a97-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="a0a97-192">Supplerte data for merker går til **BrandAffinityFromMicrosoft**-enheten.</span><span class="sxs-lookup"><span data-stu-id="a0a97-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="a0a97-193">Data for interesser er i **InterestAffinityFromMicrosoft**-enheten.</span><span class="sxs-lookup"><span data-stu-id="a0a97-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="a0a97-194">Du finner også disse enhetene oppført i gruppen **Supplering** i **Data** > **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="a0a97-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="a0a97-195">Vise supplerte data på kundekortet</span><span class="sxs-lookup"><span data-stu-id="a0a97-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="a0a97-196">Merke- og interesseaffiniteter kan også vises på individuelle kundekort.</span><span class="sxs-lookup"><span data-stu-id="a0a97-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="a0a97-197">Gå til **Kunder**, og velg en kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="a0a97-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="a0a97-198">På kundekortet finner du diagrammer for merker eller interesser som personer i kundens demografiske profil har affinitet for.</span><span class="sxs-lookup"><span data-stu-id="a0a97-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundekort med supplerte data":::

## <a name="next-steps"></a><span data-ttu-id="a0a97-200">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="a0a97-200">Next steps</span></span>

<span data-ttu-id="a0a97-201">Bygg på toppen av de supplerte kundedataene.</span><span class="sxs-lookup"><span data-stu-id="a0a97-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a0a97-202">Opprett [segmenter](segments.md), [mål](measures.md) og til og med [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.</span><span class="sxs-lookup"><span data-stu-id="a0a97-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
