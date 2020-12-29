---
title: Søke etter og filtrere kundeprofiler
description: Finn informasjon raskt om enhetlige kundeprofiler, og filtrer etter bestemte attributter.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406538"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="76875-103">Kundeprofiler: Søk- og filterindeks</span><span class="sxs-lookup"><span data-stu-id="76875-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="76875-104">Resultatet av å samle kundedata er en kundeprofilenhet som gir en enhetlig visning av den totale kundebasen.</span><span class="sxs-lookup"><span data-stu-id="76875-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="76875-105">Hvis du raskt vil [finne informasjon om en bestemt kunde eller kundegruppe](customer-profiles.md), kan du konfigurere funksjonene **Søk** og **Filter** på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="76875-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="76875-106">Les videre for å finne ut hvordan administratorer kan redigere attributtene på siden **Søk- og filterindeks**, som er tilgjengelige for brukere for søk og filtrering.</span><span class="sxs-lookup"><span data-stu-id="76875-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="76875-107">![Søkefilter](media/search-filter.png "Søkefilter")</span><span class="sxs-lookup"><span data-stu-id="76875-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="76875-108">Legge til felt og angi attributter</span><span class="sxs-lookup"><span data-stu-id="76875-108">Add fields and specify attributes</span></span>

<span data-ttu-id="76875-109">Hvis det er første gang du definerer søkbare attributter som en administrator, må du først definere indekserte felt.</span><span class="sxs-lookup"><span data-stu-id="76875-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="76875-110">Vi foreslår at du velger alle attributtene som brukere kan søke og filtrere kunder etter på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="76875-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="76875-111">Du kan bare angi attributter som finnes i kundeprofilenheten du opprettet i løpet av datasamlingsprosessen.</span><span class="sxs-lookup"><span data-stu-id="76875-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="76875-112">Åpne **Kunder**-siden, og velg **Søk- og filterindeks**.</span><span class="sxs-lookup"><span data-stu-id="76875-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="76875-113">Vi oppretter en standard konfigurasjon for søkeindeks på de tilgjengelige attributtene i kundeenheten fra følgende semantiske typer, slik det er definert på tilordningssiden.</span><span class="sxs-lookup"><span data-stu-id="76875-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="76875-114">Personens fornavn, etternavn, mellomnavn, fullt navn</span><span class="sxs-lookup"><span data-stu-id="76875-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="76875-115">Navn på organisasjon</span><span class="sxs-lookup"><span data-stu-id="76875-115">Organization Name</span></span>
> - <span data-ttu-id="76875-116">E-postadresse</span><span class="sxs-lookup"><span data-stu-id="76875-116">Email address</span></span>
> - <span data-ttu-id="76875-117">Telefon</span><span class="sxs-lookup"><span data-stu-id="76875-117">Phone number</span></span>
> - <span data-ttu-id="76875-118">Plasseringsinformasjon</span><span class="sxs-lookup"><span data-stu-id="76875-118">Location information</span></span>

2. <span data-ttu-id="76875-119">Velg **+ Legg til** for å angi de indekserte feltene.</span><span class="sxs-lookup"><span data-stu-id="76875-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="76875-120">Velg attributtene på listen du vil legge til som indekserte felt.</span><span class="sxs-lookup"><span data-stu-id="76875-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="76875-121">Du kan alltid legge til flere attributter ved å velge **Legg til**.</span><span class="sxs-lookup"><span data-stu-id="76875-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="76875-122">Du kan også fjerne valgte attributter ved å velge **Fjern**-symbolet.</span><span class="sxs-lookup"><span data-stu-id="76875-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="76875-123">Utforsk tabellen for indekserte kundefelt</span><span class="sxs-lookup"><span data-stu-id="76875-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="76875-124">Følgende informasjon vises i tabellen.</span><span class="sxs-lookup"><span data-stu-id="76875-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="76875-125">**Navn**: Representerer navnet på attributtet slik det vises i kundeprofilenheten.</span><span class="sxs-lookup"><span data-stu-id="76875-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="76875-126">**Datatype**: Angir om datatypen er en streng, et tall eller en dato.</span><span class="sxs-lookup"><span data-stu-id="76875-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="76875-127">**Inkludert i søk**: Angir om dette attributtet kan brukes til å søke etter kunder på siden **Kunder** ved hjelp av feltet **Søk**.</span><span class="sxs-lookup"><span data-stu-id="76875-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="76875-128">**Legg til filter**: Kontroll for å definere hvordan dette attributtet kan brukes til filtrering på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="76875-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="76875-129">Redigere filtreringsalternativer for et gitt attributt</span><span class="sxs-lookup"><span data-stu-id="76875-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="76875-130">Menyen **Filter** på siden **Kunder** kan inneholde et varierende antall attributtnivåer (for eksempel forskjellige aldersgrupper for å filtrere kunder etter).</span><span class="sxs-lookup"><span data-stu-id="76875-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="76875-131">Velg **Legg til filter** for et gitt attributt på siden **Søk- og filterindeks**.</span><span class="sxs-lookup"><span data-stu-id="76875-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="76875-132">Du kan definere antall resultater og rekkefølgen de skal organiseres i.</span><span class="sxs-lookup"><span data-stu-id="76875-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="76875-133">Avhengig av datatypen for attributtet vises én av følgende ruter.</span><span class="sxs-lookup"><span data-stu-id="76875-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="76875-134">Strengattributter: Angi antall ønskede resultater i ruten **Alternativer for strengfilter** og ordrepolicyen de skal organiseres etter.</span><span class="sxs-lookup"><span data-stu-id="76875-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="76875-135">Numeriske attributter: Angi intervallene som er inkludert i ruten **Alternativer for nummerfiltrering** og ordrepolicyen de skal organiseres etter.</span><span class="sxs-lookup"><span data-stu-id="76875-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="76875-136">Datoattributter: Angi intervallene som er inkludert i ruten **Alternativer for datofilter** og ordrepolicyen de skal organiseres etter.</span><span class="sxs-lookup"><span data-stu-id="76875-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="76875-137">Velg **Lagre** for å ta i bruk endringene.</span><span class="sxs-lookup"><span data-stu-id="76875-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="76875-138">Velg **Kjør** når du er klar til å bruke innstillingene.</span><span class="sxs-lookup"><span data-stu-id="76875-138">Select **Run** once you're ready to apply your settings.</span></span>
