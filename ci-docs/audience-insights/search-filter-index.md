---
title: Søke etter og filtrere kundeprofiler
description: Finn informasjon raskt om enhetlige kundeprofiler, og filtrer etter bestemte attributter.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270078"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="84ae5-103">Kundeprofiler: Søk- og filterindeks</span><span class="sxs-lookup"><span data-stu-id="84ae5-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="84ae5-104">Resultatet av å samle kundedata er en kundeprofilenhet som gir en enhetlig visning av den totale kundebasen.</span><span class="sxs-lookup"><span data-stu-id="84ae5-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="84ae5-105">Hvis du raskt vil [finne informasjon om en bestemt kunde eller kundegruppe](customer-profiles.md), kan du konfigurere funksjonene **Søk** og **Filter** på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="84ae5-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="84ae5-106">Les videre for å finne ut hvordan administratorer kan redigere attributtene på siden **Søk- og filterindeks**, som er tilgjengelige for brukere for søk og filtrering.</span><span class="sxs-lookup"><span data-stu-id="84ae5-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="84ae5-107">![Søkefilter](media/search-filter.png "Søkefilter")</span><span class="sxs-lookup"><span data-stu-id="84ae5-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="84ae5-108">Legge til felt og angi attributter</span><span class="sxs-lookup"><span data-stu-id="84ae5-108">Add fields and specify attributes</span></span>

<span data-ttu-id="84ae5-109">Hvis det er første gang du definerer søkbare attributter som en administrator, må du først definere indekserte felt.</span><span class="sxs-lookup"><span data-stu-id="84ae5-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="84ae5-110">Vi foreslår at du velger alle attributtene som brukere kan søke og filtrere kunder etter på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="84ae5-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="84ae5-111">Du kan bare angi attributter som finnes i kundeprofilenheten du opprettet i løpet av datasamlingsprosessen.</span><span class="sxs-lookup"><span data-stu-id="84ae5-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="84ae5-112">Åpne **Kunder**-siden, og velg **Søk- og filterindeks**.</span><span class="sxs-lookup"><span data-stu-id="84ae5-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="84ae5-113">Velg **+ Legg til** for å angi de indekserte feltene.</span><span class="sxs-lookup"><span data-stu-id="84ae5-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="84ae5-114">Velg attributtene på listen du vil legge til som indekserte felt.</span><span class="sxs-lookup"><span data-stu-id="84ae5-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="84ae5-115">Du kan alltid legge til flere attributter ved å velge **Legg til**.</span><span class="sxs-lookup"><span data-stu-id="84ae5-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="84ae5-116">Du kan også fjerne valgte attributter ved å velge **Fjern**-symbolet.</span><span class="sxs-lookup"><span data-stu-id="84ae5-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="84ae5-117">Utforsk tabellen for indekserte kundefelt</span><span class="sxs-lookup"><span data-stu-id="84ae5-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="84ae5-118">Følgende informasjon vises i tabellen.</span><span class="sxs-lookup"><span data-stu-id="84ae5-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="84ae5-119">**Navn**: Representerer navnet på attributtet slik det vises i kundeprofilenheten.</span><span class="sxs-lookup"><span data-stu-id="84ae5-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="84ae5-120">**Datatype**: Angir om datatypen er en streng, et tall eller en dato.</span><span class="sxs-lookup"><span data-stu-id="84ae5-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="84ae5-121">**Inkludert i søk**: Angir om dette attributtet kan brukes til å søke etter kunder på siden **Kunder** ved hjelp av feltet **Søk**.</span><span class="sxs-lookup"><span data-stu-id="84ae5-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="84ae5-122">**Legg til filter**: Kontroll for å definere hvordan dette attributtet kan brukes til filtrering på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="84ae5-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="84ae5-123">Redigere filtreringsalternativer for et gitt attributt</span><span class="sxs-lookup"><span data-stu-id="84ae5-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="84ae5-124">Menyen **Filter** på siden **Kunder** kan inneholde et varierende antall attributtnivåer (for eksempel forskjellige aldersgrupper for å filtrere kunder etter).</span><span class="sxs-lookup"><span data-stu-id="84ae5-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="84ae5-125">Velg **Legg til filter** for et gitt attributt på siden **Søk- og filterindeks**.</span><span class="sxs-lookup"><span data-stu-id="84ae5-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="84ae5-126">Du kan definere antall resultater og rekkefølgen de skal organiseres i.</span><span class="sxs-lookup"><span data-stu-id="84ae5-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="84ae5-127">Avhengig av datatypen for attributtet vises én av følgende ruter.</span><span class="sxs-lookup"><span data-stu-id="84ae5-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="84ae5-128">Strengattributter: Angi antall ønskede resultater i ruten **Alternativer for strengfilter** og ordrepolicyen de skal organiseres etter.</span><span class="sxs-lookup"><span data-stu-id="84ae5-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="84ae5-129">Numeriske attributter: Angi intervallene som er inkludert i ruten **Alternativer for nummerfiltrering** og ordrepolicyen de skal organiseres etter.</span><span class="sxs-lookup"><span data-stu-id="84ae5-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="84ae5-130">Datoattributter: Angi intervallene som er inkludert i ruten **Alternativer for datofilter** og ordrepolicyen de skal organiseres etter.</span><span class="sxs-lookup"><span data-stu-id="84ae5-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="84ae5-131">Velg **Lagre** for å ta i bruk endringene.</span><span class="sxs-lookup"><span data-stu-id="84ae5-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="84ae5-132">Velg **Kjør** når du er klar til å bruke innstillingene.</span><span class="sxs-lookup"><span data-stu-id="84ae5-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="84ae5-133">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="84ae5-133">Next steps</span></span>

<span data-ttu-id="84ae5-134">Gå til **Kunder**-siden for å søke etter kundeprofiler, eller bruk de indekserte feltene til å vise et delsett med alle kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="84ae5-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]