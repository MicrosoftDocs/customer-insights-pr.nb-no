---
title: Administrasjon av brukertillatelser
description: Lær om tillatelser og brukerroller.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689232"
---
# <a name="user-permissions"></a><span data-ttu-id="8e552-103">Brukertillatelser</span><span class="sxs-lookup"><span data-stu-id="8e552-103">User permissions</span></span>

<span data-ttu-id="8e552-104">På **Tillatelser**-siden kan du konfigurere roller og tillatelser for bruk av målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="8e552-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="8e552-105">Du må ha administratortillatelse for å se siden.</span><span class="sxs-lookup"><span data-stu-id="8e552-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="8e552-106">For å få tilgang til tillatelsessiden i målgruppeinnsikt går du til **Administrasjon** > **Tillatelser**.</span><span class="sxs-lookup"><span data-stu-id="8e552-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="8e552-107">Det finnes tre typer roller:</span><span class="sxs-lookup"><span data-stu-id="8e552-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="8e552-108">Visningsprogram</span><span class="sxs-lookup"><span data-stu-id="8e552-108">Viewer</span></span>

- <span data-ttu-id="8e552-109">Utforsk innsikt og segmenter på sidene **Start** og **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="8e552-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="8e552-110">Søk etter og filtrer kundeprofiler på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="8e552-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="8e552-111">Feltene må være søkbare.</span><span class="sxs-lookup"><span data-stu-id="8e552-111">Fields must be searchable.</span></span>
- <span data-ttu-id="8e552-112">Vise og utforske siden **Supplering**.</span><span class="sxs-lookup"><span data-stu-id="8e552-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="8e552-113">Utforsk og eksporter enheter på siden **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="8e552-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="8e552-114">Vis statusen for systemprosesser ved hjelp av siden **System**.</span><span class="sxs-lookup"><span data-stu-id="8e552-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="8e552-115">Eksporter segmenter fra **Segmenter**-siden.</span><span class="sxs-lookup"><span data-stu-id="8e552-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="8e552-116">Installer og bruk instrumentbordet i **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="8e552-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="8e552-117">Bidragsyter</span><span class="sxs-lookup"><span data-stu-id="8e552-117">Contributor</span></span>

- <span data-ttu-id="8e552-118">Alle tillatelser som er tilgjengelige for visningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="8e552-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="8e552-119">Last inn og transformer data ved hjelp av siden **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="8e552-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="8e552-120">Fyll ut delene *Datasamling* (**Tilordne**, **Samsvar** og **Slå sammen**), som fører til en samlet kundeprofilenhet.</span><span class="sxs-lookup"><span data-stu-id="8e552-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="8e552-121">Definere **Relasjoner** og **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="8e552-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="8e552-122">Opprett segmenter ved hjelp siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="8e552-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="8e552-123">Opprett mål ved hjelp siden **Mål**.</span><span class="sxs-lookup"><span data-stu-id="8e552-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="8e552-124">Administrer konfigurasjon og suppler kundeprofiler fra **Supplering**-siden (bare for førsteparts suppleringer).</span><span class="sxs-lookup"><span data-stu-id="8e552-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="8e552-125">Administrator</span><span class="sxs-lookup"><span data-stu-id="8e552-125">Administrator</span></span>

- <span data-ttu-id="8e552-126">Alle tillatelser som er tilgjengelige for bidragsyteren.</span><span class="sxs-lookup"><span data-stu-id="8e552-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="8e552-127">Endre innstillinger på siden **System**, inkludert arbeidsspråket, og oppdater planer for systemprosessene.</span><span class="sxs-lookup"><span data-stu-id="8e552-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="8e552-128">Vis og legg til tillatelser ved hjelp av siden **Tillatelser**.</span><span class="sxs-lookup"><span data-stu-id="8e552-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="8e552-129">Angi søke- og filtreringdefinisjoner for Kunder-siden ved å bruke siden **Søk- og filterindeks** (tilgjengelig via **Kunder**-siden).</span><span class="sxs-lookup"><span data-stu-id="8e552-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="8e552-130">Definer Dynamics 365 Sales-segmentdestinasjoner ved hjelp av siden **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="8e552-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="8e552-131">Administrer konfigurasjon og suppler kundeprofiler fra **Supplering**-siden (for alle suppleringer).</span><span class="sxs-lookup"><span data-stu-id="8e552-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="8e552-132">Installere og bruk **Tillegg for kundekort**.</span><span class="sxs-lookup"><span data-stu-id="8e552-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="8e552-133">Legg til og bruk **Power Apps-koblingen**.</span><span class="sxs-lookup"><span data-stu-id="8e552-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="8e552-134">Aktiver bruk av [API-er for Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="8e552-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="8e552-135">Tilordne roller og tillatelser</span><span class="sxs-lookup"><span data-stu-id="8e552-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="8e552-136">I Målgruppeinnsikt går du til **Administrasjon** > **Tillatelser**.</span><span class="sxs-lookup"><span data-stu-id="8e552-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="8e552-137">Velg **Legg til brukere** for å åpne ruten **Legg til / rediger tillatelser**.</span><span class="sxs-lookup"><span data-stu-id="8e552-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="8e552-138">Bruk **Søk**-feltet til å finne Azure Active Directory-brukeren eller -gruppen som du vil justere tillatelser for.</span><span class="sxs-lookup"><span data-stu-id="8e552-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="8e552-139">Velg en **Rolle** som skal tilordnes brukeren eller gruppen.</span><span class="sxs-lookup"><span data-stu-id="8e552-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="8e552-140">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="8e552-140">Select **Save**.</span></span> <span data-ttu-id="8e552-141">Det gjeldende miljøet deles automatisk med brukeren eller medlemmene av gruppen som du har endret tillatelser for.</span><span class="sxs-lookup"><span data-stu-id="8e552-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="8e552-142">Brukere kan få tilgang til Customer Insights-appen og arbeide i henhold til den angitte rollen.</span><span class="sxs-lookup"><span data-stu-id="8e552-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="8e552-143">Vise gjeldende tillatelser</span><span class="sxs-lookup"><span data-stu-id="8e552-143">View current permissions</span></span>

<span data-ttu-id="8e552-144">I målgruppeinnsikt går du til **Administrasjon** > **Tillatelser** for å se hvilke rolletildelinger som er aktive for øyeblikket.</span><span class="sxs-lookup"><span data-stu-id="8e552-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="8e552-145">Kolonnen **Type** angir én bruker, én gruppe eller ett program.</span><span class="sxs-lookup"><span data-stu-id="8e552-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="8e552-146">Systemet støtter individuelle brukere og grupper.</span><span class="sxs-lookup"><span data-stu-id="8e552-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="8e552-147">Roller er angitt under kolonnen **Rolle**.</span><span class="sxs-lookup"><span data-stu-id="8e552-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="8e552-148">Velg en kolonnetittel for å sortere resultatene etter verdien i kolonnen.</span><span class="sxs-lookup"><span data-stu-id="8e552-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="8e552-149">Bruk **Søk**-feltet øverst på siden for å finne bestemte brukere.</span><span class="sxs-lookup"><span data-stu-id="8e552-149">Use the **Search** field at the top of the page to locate specific users.</span></span>
