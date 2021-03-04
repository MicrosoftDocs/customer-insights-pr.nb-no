---
title: Vise kundeprofiler
description: Få en kombinert visning av dine enhetlige kundedata.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a5d928ae518f3cb1afbf8e2b197e51b27665f6e0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269756"
---
# <a name="customer-profiles"></a><span data-ttu-id="948d6-103">Kundeprofiler</span><span class="sxs-lookup"><span data-stu-id="948d6-103">Customer profiles</span></span>

<span data-ttu-id="948d6-104">**Kunder**-siden viser en kombinert visning av kundene, basert på profildata som samles inn fra [alle datakilder](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="948d6-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="948d6-105">Kundeprofiler er tilgjengelige når du [oppretter den enhetlige kundeenheten](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="948d6-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="948d6-106">Sørg for at du fullfører datasamlingsprosessen for å få rikere visninger av kundene.</span><span class="sxs-lookup"><span data-stu-id="948d6-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="948d6-107">Du kan også bruke siden til å søke etter kunder.</span><span class="sxs-lookup"><span data-stu-id="948d6-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="948d6-108">Kunder kan være enkeltpersoner eller organisasjoner (forhåndsvisning).</span><span class="sxs-lookup"><span data-stu-id="948d6-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="948d6-109">Hver kunde eller organisasjonsprofil representeres av en flis.</span><span class="sxs-lookup"><span data-stu-id="948d6-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="948d6-110">Velg en flis for å vise ytterligere informasjon om den bestemte kunden eller organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="948d6-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="948d6-111">Bruk pagineringskontrollene nederst på siden for å vise flere oppføringer.</span><span class="sxs-lookup"><span data-stu-id="948d6-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="948d6-112">![B2C-kundeprofiler](media/profiles-customers.png "B2C-kundeprofiler")</span><span class="sxs-lookup"><span data-stu-id="948d6-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="948d6-113">Organisasjoner (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="948d6-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="948d6-114">![B2B-kundeprofiler](media/profile-customers-b2b.png "B2B-kundeprofiler")</span><span class="sxs-lookup"><span data-stu-id="948d6-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="948d6-115">Hvis du ikke kan se flisene når du velger **Kunder** i navigasjon, må administrator [definere minst ett søkbart attributt](search-filter-index.md) i **søk- og filterindeksen**.</span><span class="sxs-lookup"><span data-stu-id="948d6-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="948d6-116">Søke etter kunder</span><span class="sxs-lookup"><span data-stu-id="948d6-116">Search for customers</span></span>

<span data-ttu-id="948d6-117">Søk etter kunder ved å angi et navn eller et annet attributt i søkeboksen.</span><span class="sxs-lookup"><span data-stu-id="948d6-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="948d6-118">Søket fungerer bare i kundeprofilenheten som ble opprettet i løpet av datasamlingsprosessen.</span><span class="sxs-lookup"><span data-stu-id="948d6-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="948d6-119">Som administrator kan du konfigurere de søkbare attributtene ved hjelp av siden **Søk- og filterindeks**.</span><span class="sxs-lookup"><span data-stu-id="948d6-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="948d6-120">Du finner mer informasjon under [Behandle søk- og filterindeks](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="948d6-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="948d6-121">Filtrere kunder</span><span class="sxs-lookup"><span data-stu-id="948d6-121">Filter customers</span></span>

<span data-ttu-id="948d6-122">Du kan filtrere kunder etter feltene i kundeprofilenheten.</span><span class="sxs-lookup"><span data-stu-id="948d6-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="948d6-123">På samme måte som i søk må administratoren først definere feltene som filtrererbare ved hjelp av siden **Søk- og filterindeks**.</span><span class="sxs-lookup"><span data-stu-id="948d6-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="948d6-124">Velg **Filtrer** på **Kunder**-siden.</span><span class="sxs-lookup"><span data-stu-id="948d6-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="948d6-125">Merk av i boksene ved siden av attributtene du vil filtrere kunder etter.</span><span class="sxs-lookup"><span data-stu-id="948d6-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="948d6-126">![Kundeprofiler](media/profiles-customers3.png "Kundeprofiler")</span><span class="sxs-lookup"><span data-stu-id="948d6-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="948d6-127">Fjern filtrene ved å velge **Fjern filtre** på **Kunder**-siden.</span><span class="sxs-lookup"><span data-stu-id="948d6-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="948d6-128">Kundedetaljer-siden</span><span class="sxs-lookup"><span data-stu-id="948d6-128">Customer details page</span></span>

<span data-ttu-id="948d6-129">Velg en hvilken som helst av kundeflisene for å åpne **Kundedetaljer**-siden.</span><span class="sxs-lookup"><span data-stu-id="948d6-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="948d6-130">Denne visningen inneholder enhetlig informasjon om den valgte kunden.</span><span class="sxs-lookup"><span data-stu-id="948d6-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="948d6-131">Kundedetaljene inkluderer:</span><span class="sxs-lookup"><span data-stu-id="948d6-131">Customer details include:</span></span>

-   <span data-ttu-id="948d6-132">**Kundeprofilflis:** Denne flisen viser de forskjellige verdiene fra den enhetlige kundeprofilenheten.</span><span class="sxs-lookup"><span data-stu-id="948d6-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="948d6-133">Disse detaljene kan omfatte e-postadresse, navn, poststed og så videre.</span><span class="sxs-lookup"><span data-stu-id="948d6-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="948d6-134">**Potensielle interesser, potensielle merker:** Viser om du har konfigurert en førsteparts supplering.</span><span class="sxs-lookup"><span data-stu-id="948d6-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="948d6-135">Det representerer potensielle interesser og tiltrekning for merker en kunde med en profil som ligner på denne kunden, kan ha.</span><span class="sxs-lookup"><span data-stu-id="948d6-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="948d6-136">Hvis du vil ha mer informasjon, kan du se [Supplere kundeprofiler med merke- og interesseaffiniteter](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="948d6-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="948d6-137">**Mål:** Viser om du har konfigurert ett eller flere mål for en bestemt type: kundeattributtmål.</span><span class="sxs-lookup"><span data-stu-id="948d6-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="948d6-138">De inkluderer beregnede KPI-er rundt kundene på det enkelte kundenivået.</span><span class="sxs-lookup"><span data-stu-id="948d6-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="948d6-139">Hvis du vil ha mer informasjon, kan du se [Definere og behandle mål](measures.md).</span><span class="sxs-lookup"><span data-stu-id="948d6-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="948d6-140">**Aktivitetstidslinje:** Vises om du har konfigurert aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="948d6-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="948d6-141">Tidslinjevisningen inneholder kronologisk sorterte aktiviteter av denne kunden, og starter med den nyeste aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="948d6-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="948d6-142">Hvis du vil ha mer informasjon, kan du se [Kundeaktiviteter](activities.md).</span><span class="sxs-lookup"><span data-stu-id="948d6-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="948d6-143">Velg **Tilbake til Kunder** for å gå tilbake til kundesøkesiden.</span><span class="sxs-lookup"><span data-stu-id="948d6-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="948d6-144">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="948d6-144">Next steps</span></span>

<span data-ttu-id="948d6-145">[Legge til flere datakilder](data-sources.md) eller [opprette kundesegmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="948d6-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]