---
title: Kundeaktiviteter
description: Definer kundeaktiviteter og vis dem på kundetidslinjen.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267444"
---
# <a name="customer-activities"></a><span data-ttu-id="eca01-103">Kundeaktiviteter</span><span class="sxs-lookup"><span data-stu-id="eca01-103">Customer activities</span></span>

<span data-ttu-id="eca01-104">Kombiner kundeaktiviteter fra [forskjellige datakilder](data-sources.md) i Dynamics 365 Customer Insights for å opprette en kundetidslinje som viser aktivitetene i kronologisk rekkefølge.</span><span class="sxs-lookup"><span data-stu-id="eca01-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="eca01-105">Du kan ta med tidslinjen i Customer Engagement-apper i Dynamics 365 via [kundekorttillegget](customer-card-add-in.md) eller på et Power BI-instrumentbord.</span><span class="sxs-lookup"><span data-stu-id="eca01-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="eca01-106">Definere en aktivitet</span><span class="sxs-lookup"><span data-stu-id="eca01-106">Define an activity</span></span>

<span data-ttu-id="eca01-107">Datakildene inneholder enheter med transaksjons- og aktivitetsdata fra flere datakilder.</span><span class="sxs-lookup"><span data-stu-id="eca01-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="eca01-108">Identifiser disse enhetene, og velg aktivitetene du vil vise på kundens tidslinje.</span><span class="sxs-lookup"><span data-stu-id="eca01-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="eca01-109">Velg enheten som inneholder målaktiviteten eller -aktivitetene.</span><span class="sxs-lookup"><span data-stu-id="eca01-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="eca01-110">I Målgruppeinnsikt går du til **Data** > **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="eca01-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="eca01-111">Velg **Legg til aktivitet**.</span><span class="sxs-lookup"><span data-stu-id="eca01-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="eca01-112">En enhet må ha minst ett attributt av typen **Dato** som inkluderes på en kundetidslinje, og du kan ikke legge til enheter uten **Dato**-feltene.</span><span class="sxs-lookup"><span data-stu-id="eca01-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="eca01-113">Kontrollen **Legg til aktivitet** er deaktivert hvis det ikke finnes en slik enhet.</span><span class="sxs-lookup"><span data-stu-id="eca01-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="eca01-114">Angi verdiene for følgende felt, i ruten **Legg til aktivitet**:</span><span class="sxs-lookup"><span data-stu-id="eca01-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="eca01-115">**Enhet**: Velg en enhet som inkluderer transaksjons- eller aktivitetsdata.</span><span class="sxs-lookup"><span data-stu-id="eca01-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="eca01-116">**Primærnøkkel**: Velg feltet som unikt identifiserer en oppføring.</span><span class="sxs-lookup"><span data-stu-id="eca01-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="eca01-117">Den skal ikke inneholde duplikat verdier, tomme verdier eller manglende verdier.</span><span class="sxs-lookup"><span data-stu-id="eca01-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="eca01-118">**Tidsstempel**: Velg feltet som representerer starttidspunktet for aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="eca01-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="eca01-119">**Hendelse**: Velg feltet som er hendelsen for aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="eca01-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="eca01-120">**Webadresse**: Velg feltet som representerer en URL-adresse som gir tilleggsinformasjon om denne aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="eca01-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="eca01-121">For eksempel transaksjonssystemet som er kilde for denne aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="eca01-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="eca01-122">Denne URL-adressen kan være et hvilket som helst felt fra datakilde, eller den kan konstrueres som et nytt felt ved hjelp av en Power Query-transformasjon.</span><span class="sxs-lookup"><span data-stu-id="eca01-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="eca01-123">Disse URL-dataene blir lagret i Enhetlig aktivitet-enheten, som kan forbrukes nedstrøms med API-er.</span><span class="sxs-lookup"><span data-stu-id="eca01-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="eca01-124">**Detaljer**: Velg eventuelt feltet som er lagt til for ytterligere detaljer.</span><span class="sxs-lookup"><span data-stu-id="eca01-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="eca01-125">**Ikon**: Velg eventuelt ikonet som representerer denne aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="eca01-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="eca01-126">**Aktivitetstype**: Definer aktivitetstypereferansen til Common Data Model som best beskriver den semantiske definisjonen av aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="eca01-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="eca01-127">I delen **Konfigurer relasjon** konfigurerer du detaljer for å koble aktivitetsdataene til den tilsvarende kunden.</span><span class="sxs-lookup"><span data-stu-id="eca01-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="eca01-128">**Feltet Aktivitetsenhet**: Velg feltet i aktivitetsenheten som skal brukes til å opprette en relasjon til en annen enhet.</span><span class="sxs-lookup"><span data-stu-id="eca01-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="eca01-129">**Kundeenhet**: Velg den tilsvarende kildekundeenheten som aktivitetsenheten skal være i relasjon til.</span><span class="sxs-lookup"><span data-stu-id="eca01-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="eca01-130">Du kan bare relatere til de kildekundeenhetene som brukes i datasamlingsprosessen.</span><span class="sxs-lookup"><span data-stu-id="eca01-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="eca01-131">**Feltet Kundeenhet**: Dette feltet viser primærnøkkelen for kildekundeenheten som er valgt i tilordningsprosessen.</span><span class="sxs-lookup"><span data-stu-id="eca01-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="eca01-132">Dette hovednøkkelfeltet i kildekundeenheten brukes til å opprette en relasjon med aktivitetsenheten.</span><span class="sxs-lookup"><span data-stu-id="eca01-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="eca01-133">**Navn**: Hvis det allerede finnes en relasjon mellom denne aktivitetsenheten og den valgte kildekundeenheten, vil relasjonsnavnet være i skrivebeskyttet modus.</span><span class="sxs-lookup"><span data-stu-id="eca01-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="eca01-134">Hvis det ikke finnes en slik relasjon, blir det opprettet en ny relasjon med navnet som er angitt her.</span><span class="sxs-lookup"><span data-stu-id="eca01-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="eca01-135">![Definere enhetsrelasjonen](media/activities-entities-define.png "Definere enhetsrelasjonen")</span><span class="sxs-lookup"><span data-stu-id="eca01-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="eca01-136">Velg **Lagre** for å ta i bruk endringene.</span><span class="sxs-lookup"><span data-stu-id="eca01-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="eca01-137">På siden **Aktiviteter** velger du **Kjør**.</span><span class="sxs-lookup"><span data-stu-id="eca01-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="eca01-138">Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser.</span><span class="sxs-lookup"><span data-stu-id="eca01-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="eca01-139">De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="eca01-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="eca01-140">Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben.</span><span class="sxs-lookup"><span data-stu-id="eca01-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="eca01-141">Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.</span><span class="sxs-lookup"><span data-stu-id="eca01-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="eca01-142">Redigere en aktivitet</span><span class="sxs-lookup"><span data-stu-id="eca01-142">Edit an activity</span></span>

1. <span data-ttu-id="eca01-143">I Målgruppeinnsikt går du til **Data** > **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="eca01-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="eca01-144">Velg aktivitetsenheten du vil redigere, og velg **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="eca01-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="eca01-145">Du kan også holde pekeren over enhetsraden og velge **Rediger**-ikonet.</span><span class="sxs-lookup"><span data-stu-id="eca01-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="eca01-146">Klikk på **Rediger**-ikonet.</span><span class="sxs-lookup"><span data-stu-id="eca01-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="eca01-147">I ruten **Rediger aktivitet** oppdaterer du verdiene og velger **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="eca01-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="eca01-148">På siden **Aktiviteter** velger du **Kjør**.</span><span class="sxs-lookup"><span data-stu-id="eca01-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="eca01-149">Slette en aktivitet</span><span class="sxs-lookup"><span data-stu-id="eca01-149">Delete an activity</span></span>

1. <span data-ttu-id="eca01-150">I Målgruppeinnsikt går du til **Data** > **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="eca01-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="eca01-151">Velg aktivitetsenheten du vil fjerne, og velg **Slett**.</span><span class="sxs-lookup"><span data-stu-id="eca01-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="eca01-152">Du kan også holde pekeren over enhetsraden og velge **Slett**-ikonet.</span><span class="sxs-lookup"><span data-stu-id="eca01-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="eca01-153">Du kan også velge at flere aktivitetsenheter skal slettes samtidig.</span><span class="sxs-lookup"><span data-stu-id="eca01-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="eca01-154">![Redigere eller slette enhetsrelasjonen](media/activities-entities-edit-delete.png "Redigere eller slette enhetsrelasjonen")</span><span class="sxs-lookup"><span data-stu-id="eca01-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="eca01-155">Velg **Slett**-ikonet.</span><span class="sxs-lookup"><span data-stu-id="eca01-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="eca01-156">Bekreft slettingen.</span><span class="sxs-lookup"><span data-stu-id="eca01-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]