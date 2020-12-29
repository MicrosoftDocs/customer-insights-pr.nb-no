---
title: Tilordne enheter for dataforening
description: Tilordne data for å opprette enhetlige kundeprofiler.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406528"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="443c5-103">Tilordne enheter og attributter</span><span class="sxs-lookup"><span data-stu-id="443c5-103">Map entities and attributes</span></span>

<span data-ttu-id="443c5-104">**Tilordning** er første trinn i dataforeningsprosessen i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="443c5-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="443c5-105">Tilordning består av tre faser:</span><span class="sxs-lookup"><span data-stu-id="443c5-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="443c5-106">*Valg av enhet*: Identifiser de enhetene som kan kombineres, som fører til et datasett med mer fullstendig informasjon om kundene.</span><span class="sxs-lookup"><span data-stu-id="443c5-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="443c5-107">*Attributtvalg*: For hver enhet identifiserer du kolononnene du vil kombinere, og avstemmer i fasene for *samsvar* og *sammenslåing*.</span><span class="sxs-lookup"><span data-stu-id="443c5-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="443c5-108">Disse kolonnene kalles *attributter*.</span><span class="sxs-lookup"><span data-stu-id="443c5-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="443c5-109">*Hovednøkkel og valg av semantisk type*: For hver enhet angir du et attributt du vil definere som primærnøkkel for enheten, og identifiser en semantisk type som best beskriver attributtet, for hvert attributt.</span><span class="sxs-lookup"><span data-stu-id="443c5-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="443c5-110">Hvis du vil ha mer informasjon om den generelle flyten for datasamling, se [Samle](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="443c5-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="443c5-111">Velge de første enhetene</span><span class="sxs-lookup"><span data-stu-id="443c5-111">Select the first entities</span></span>

1. <span data-ttu-id="443c5-112">I Målgruppeinnsikt går du til **Data** > **Samle** > **Tilordne**.</span><span class="sxs-lookup"><span data-stu-id="443c5-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="443c5-113">Start tilordningsfasen ved å velge **Velg enheter**.</span><span class="sxs-lookup"><span data-stu-id="443c5-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="443c5-114">Velg enhetene og attributtene du vil bruke i *samsvars*- og *sammenslåings*-fasene.</span><span class="sxs-lookup"><span data-stu-id="443c5-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="443c5-115">Du kan velge obligatoriske attributter enkeltvis fra en enhet eller inkludere alle attributter fra en enhet ved å merke av for **Inkluder alle felt** på enhetsnivå.</span><span class="sxs-lookup"><span data-stu-id="443c5-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="443c5-116">Vi anbefaler at du velger minst to enheter for å dra nytte av datasamlingsprosessen.</span><span class="sxs-lookup"><span data-stu-id="443c5-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="443c5-117">![Legg til enhet-eksempel](media/data-manager-configure-map-add-entities-example.png "Legg til enhet-eksempel")</span><span class="sxs-lookup"><span data-stu-id="443c5-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="443c5-118">I dette eksemplet skal vi legge til enhetene **eCommerceContacts** og **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="443c5-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="443c5-119">Ved å velge disse enhetene kan du avlede innsikt om hvilke av de elektroniske forretningskundene som er medlemmer av loyalitetsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="443c5-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="443c5-120">Du kan søke i nøkkelord på tvers av alle attributter og enheter for å velge de nødvendige attributtene du vil tilordne.</span><span class="sxs-lookup"><span data-stu-id="443c5-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="443c5-121">![Eksempler på søkefelt](media/data-manager-configure-map-search-fields-example.png "Eksempler på søkefelt")</span><span class="sxs-lookup"><span data-stu-id="443c5-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="443c5-122">Velg **Bruk** for å bekrefte valgene.</span><span class="sxs-lookup"><span data-stu-id="443c5-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="443c5-123">Velg primærnøkkel og semantisk type for attributter</span><span class="sxs-lookup"><span data-stu-id="443c5-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="443c5-124">Etter at du har valgt enhetene, viser **Tilordne**-siden de valgte enhetene for gjennomgang.</span><span class="sxs-lookup"><span data-stu-id="443c5-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="443c5-125">Definer primærnøkkelen for en enhet, og identifiser den semantiske typen for et attributt i enheten.</span><span class="sxs-lookup"><span data-stu-id="443c5-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="443c5-126">**Primærnøkkel**: Velg ett attributt som primærnøkkel for hver av enhetene.</span><span class="sxs-lookup"><span data-stu-id="443c5-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="443c5-127">For at et attributt skal være en gyldig primærnøkkel, bør den ikke inneholde duplikate verdier, manglende verdier eller nullverdier.</span><span class="sxs-lookup"><span data-stu-id="443c5-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="443c5-128">Attributter for datatypen streng, heltall og GUID støttes som primærnøkler, og vises i et felt du kan velge fra.</span><span class="sxs-lookup"><span data-stu-id="443c5-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="443c5-129">**Semantisk type for attributt**: Kategorier av attributter, for eksempel e-postadresse eller navn.</span><span class="sxs-lookup"><span data-stu-id="443c5-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="443c5-130">Hvis du vil bruke AI-modeller for smart prediksjon av semantikk, spare tid og forbedre nøyaktigheten, angir du **Intelligent tilordning** til **På**.</span><span class="sxs-lookup"><span data-stu-id="443c5-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="443c5-131">Intelligent tilordning fremhever AI-basert semantikkanbefaling i **Type**-feltet.</span><span class="sxs-lookup"><span data-stu-id="443c5-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="443c5-132">Hvis du setter den til **AV**, vil du se våre vanlige tilordningsanbefalinger.</span><span class="sxs-lookup"><span data-stu-id="443c5-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="443c5-133">Du kan velge en hvilken som helst semantisk type fra den tilgjengelige listen over alternativer og overstyre det foreslåtte valget.</span><span class="sxs-lookup"><span data-stu-id="443c5-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="443c5-134">![Attributtype og semantisk prediksjon](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attributtype og semantisk prediksjon")</span><span class="sxs-lookup"><span data-stu-id="443c5-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="443c5-135">Det er også mulig å legge til en egendefinert semantisk type.</span><span class="sxs-lookup"><span data-stu-id="443c5-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="443c5-136">Velg typefeltet for et attributt, og skriv inn det egendefinerte semantiske typenavnet.</span><span class="sxs-lookup"><span data-stu-id="443c5-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="443c5-137">På denne måten kan du også endre attributtypene som ble identifisert av systemet.</span><span class="sxs-lookup"><span data-stu-id="443c5-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="443c5-138">Alle attributter som en semantisk type identifiseres for, grupperes automatisk i delen **Se gjennom tilordnede felt**.</span><span class="sxs-lookup"><span data-stu-id="443c5-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="443c5-139">Se gjennom disse attributtene og de semantiske typene fordi de blir brukt til å kombinere enhetene i flettingstrinnet i datasamling.</span><span class="sxs-lookup"><span data-stu-id="443c5-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="443c5-140">Attributter som ikke tilordnes automatisk til en semantisk type, grupperes i delen **Definer dataene i feltene som ikke er tilordnet**.</span><span class="sxs-lookup"><span data-stu-id="443c5-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="443c5-141">Velg feltet for semantisk type for attributter som ikke er tilordnet, eller skriv inn det egendefinerte navnet på attributtet.</span><span class="sxs-lookup"><span data-stu-id="443c5-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="443c5-142">![Primærnøkkel og attributtype](media/data-manager-configure-map-add-attributes.png "Primærnøkkel og attributtype")</span><span class="sxs-lookup"><span data-stu-id="443c5-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="443c5-143">Ett felt må være tilordnet den semantiske typen Person.FullName for å fylle ut kundenavnet i kundekortet.</span><span class="sxs-lookup"><span data-stu-id="443c5-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="443c5-144">Ellers vises kundekortene uten navn.</span><span class="sxs-lookup"><span data-stu-id="443c5-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="443c5-145">Legge til og fjerne attributter og enheter</span><span class="sxs-lookup"><span data-stu-id="443c5-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="443c5-146">På **Samle** > **Tilordne** velger du **Rediger felt**.</span><span class="sxs-lookup"><span data-stu-id="443c5-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="443c5-147">Legg til eller Fjern attributter og enheter i **Rediger felt**-ruten.</span><span class="sxs-lookup"><span data-stu-id="443c5-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="443c5-148">Bruk søket eller rull for å finne og velge ønskede attributter og enheter.</span><span class="sxs-lookup"><span data-stu-id="443c5-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="443c5-149">Du kan ikke fjerne et attributt eller en enhet hvis de allerede er samsvart.</span><span class="sxs-lookup"><span data-stu-id="443c5-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="443c5-150">![Legge til eller fjerne attributter](media/configure-data-map-edit.png "Legge til eller fjerne attributter")</span><span class="sxs-lookup"><span data-stu-id="443c5-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="443c5-151">Velg **Bruk**.</span><span class="sxs-lookup"><span data-stu-id="443c5-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="443c5-152">Legge til bilder i profiler</span><span class="sxs-lookup"><span data-stu-id="443c5-152">Add images to profiles</span></span>

<span data-ttu-id="443c5-153">Hvis en enhet inneholder URL-adresser til offentlig tilgjengelige profilbilder eller logoer, kan du legge dem til i den enhetlige kundeprofilen.</span><span class="sxs-lookup"><span data-stu-id="443c5-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="443c5-154">Velg enheten, og finn feltet som inneholder URL-adressen til profilbildet.</span><span class="sxs-lookup"><span data-stu-id="443c5-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="443c5-155">Skriv inn følgende verdi manuelt i **Type**-inndatafeltet:</span><span class="sxs-lookup"><span data-stu-id="443c5-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="443c5-156">For en person: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="443c5-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="443c5-157">For en organisasjon: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="443c5-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="443c5-158">Fortsett med samlingstrinnene, og kontroller at attributtet som inneholder bilde-URL-adressen, også legges til i [flettings](merge-entities.md)-trinnet.</span><span class="sxs-lookup"><span data-stu-id="443c5-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="443c5-159">Angi attributter for organisasjoner</span><span class="sxs-lookup"><span data-stu-id="443c5-159">Set attributes for organizations</span></span>

<span data-ttu-id="443c5-160">For organisasjoner (forhåndsvisning) må attributtypen tilordnes "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="443c5-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="443c5-161">![Primærnøkkel og attributtype B2B](media/configure-data-map-edit-b2b.png "Primærnøkkel og attributtype B2B")</span><span class="sxs-lookup"><span data-stu-id="443c5-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="443c5-162">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="443c5-162">Next step</span></span>

<span data-ttu-id="443c5-163">Som en del av datasamlingsprosessen går du til **Samsvar**-siden.</span><span class="sxs-lookup"><span data-stu-id="443c5-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="443c5-164">Gå [**Samsvar**](match-entities.md) for å lære om dette trinnet.</span><span class="sxs-lookup"><span data-stu-id="443c5-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="443c5-165">Se følgende video: [Komme i gang: Opprette en enhetlig kundeprofil](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="443c5-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
