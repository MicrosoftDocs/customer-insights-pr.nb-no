---
title: Eksportere data fra Customer Insights
description: Administrer eksporter for å dele data.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253052"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="5dc88-103">Oversikt over Eksporter (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="5dc88-103">Exports (preview) overview</span></span>

<span data-ttu-id="5dc88-104">**Eksporter**-siden viser alle konfigurerte eksporter.</span><span class="sxs-lookup"><span data-stu-id="5dc88-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="5dc88-105">Eksporter deler bestemte data med forskjellige programmer.</span><span class="sxs-lookup"><span data-stu-id="5dc88-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="5dc88-106">De kan omfatte kundeprofiler eller enheter, skjemaer og tilordningsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="5dc88-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="5dc88-107">Hver eksport krever en [tilkobling, konfigurert av en administrator, for å administrere godkjenning og tilgang](connections.md).</span><span class="sxs-lookup"><span data-stu-id="5dc88-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="5dc88-108">Gå til **Data** > **Eksporter** for å vise eksportsiden.</span><span class="sxs-lookup"><span data-stu-id="5dc88-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="5dc88-109">Alle brukerroller har tilgang til å vise konfigurerte eksporter.</span><span class="sxs-lookup"><span data-stu-id="5dc88-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="5dc88-110">Bruk av søkefeltet på kommandolinjen til å søke etter eksporter etter navn, tilkoblingsnavn eller tilkoblingstype.</span><span class="sxs-lookup"><span data-stu-id="5dc88-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="5dc88-111">Konfigurer en ny eksport</span><span class="sxs-lookup"><span data-stu-id="5dc88-111">Set up a new export</span></span>

<span data-ttu-id="5dc88-112">Hvis du vil konfigurere eller redigere en eksport, må du ha tilkoblinger tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="5dc88-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="5dc88-113">Tilkoblinger avhenger av [brukerrollen din](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="5dc88-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="5dc88-114">Administratorer har tilgang til alle tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="5dc88-114">Administrators have access to all connections.</span></span> <span data-ttu-id="5dc88-115">De kan også opprette nye tilkoblinger når de konfigurerer en eksport.</span><span class="sxs-lookup"><span data-stu-id="5dc88-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="5dc88-116">Bidragsytere kan ha tilgang til bestemte tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="5dc88-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="5dc88-117">De er avhengig av administratorer for å konfigurere og dele tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="5dc88-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="5dc88-118">Eksporter-listen viser bidragsytere om de kan redigere eller bare vise en eksport, i kolonnen **Tillatelsene dine**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="5dc88-119">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5dc88-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="5dc88-120">Visningsprogrammer kan bare vise eksisterende eksporter, men ikke opprette dem.</span><span class="sxs-lookup"><span data-stu-id="5dc88-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="5dc88-121">Definere en ny eksport</span><span class="sxs-lookup"><span data-stu-id="5dc88-121">Define a new export</span></span>

1. <span data-ttu-id="5dc88-122">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5dc88-123">Velg **Legg til eksport** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="5dc88-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="5dc88-124">Velg hvilken tilkobling som skal brukes, i ruten **Konfigurer eksport**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="5dc88-125">[Tilkoblinger](connections.md) administreres av administratorer.</span><span class="sxs-lookup"><span data-stu-id="5dc88-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="5dc88-126">Oppgi de nødvendige detaljene, og velg **Lagre** for å opprette eksporten.</span><span class="sxs-lookup"><span data-stu-id="5dc88-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="5dc88-127">Definere en ny eksport basert på en eksisterende eksport</span><span class="sxs-lookup"><span data-stu-id="5dc88-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="5dc88-128">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5dc88-129">Velg eksporten du vil duplisere, i listen over eksporter.</span><span class="sxs-lookup"><span data-stu-id="5dc88-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="5dc88-130">Velg **Opprett duplikat** på kommandolinjen for å åpne ruten **Konfigurer eksport** med detaljene for den valgte eksporten.</span><span class="sxs-lookup"><span data-stu-id="5dc88-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="5dc88-131">Se gjennom og tilpass eksporten, og velg **Lagre** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="5dc88-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="5dc88-132">Rediger en eksport</span><span class="sxs-lookup"><span data-stu-id="5dc88-132">Edit an export</span></span>

1. <span data-ttu-id="5dc88-133">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5dc88-134">Velg eksporten du vil redigere, i listen over eksporter.</span><span class="sxs-lookup"><span data-stu-id="5dc88-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="5dc88-135">Velg **Rediger** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="5dc88-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="5dc88-136">Endre verdiene du vil oppdatere, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="5dc88-137">Vise eksporter og eksportdetaljer</span><span class="sxs-lookup"><span data-stu-id="5dc88-137">View exports and export details</span></span>

<span data-ttu-id="5dc88-138">Når du har opprettet eksportmål, vises de i **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="5dc88-139">Alle brukere kan se hvilke data som deles, og den nyeste statusen.</span><span class="sxs-lookup"><span data-stu-id="5dc88-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="5dc88-140">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5dc88-141">Brukere uten redigeringstillatelser velger **Vis** i stedet for **Rediger** for å se eksportdetaljene.</span><span class="sxs-lookup"><span data-stu-id="5dc88-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="5dc88-142">Sideruten viser konfigurasjonen av en eksport.</span><span class="sxs-lookup"><span data-stu-id="5dc88-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="5dc88-143">Du kan ikke endre verdier uten redigeringstillatelser.</span><span class="sxs-lookup"><span data-stu-id="5dc88-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="5dc88-144">Velg **Lukk** for å gå tilbake til eksportsiden.</span><span class="sxs-lookup"><span data-stu-id="5dc88-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="5dc88-145">Planlegge og kjøre eksporter</span><span class="sxs-lookup"><span data-stu-id="5dc88-145">Schedule and run exports</span></span>

<span data-ttu-id="5dc88-146">Hver eksport du konfigurerer, har en oppdateringsplan.</span><span class="sxs-lookup"><span data-stu-id="5dc88-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="5dc88-147">Under en oppdatering ser systemet etter nye eller oppdaterte data som skal tas med i en eksport.</span><span class="sxs-lookup"><span data-stu-id="5dc88-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="5dc88-148">Eksporter kjører som standard som en del av hver [planlagte systemoppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5dc88-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5dc88-149">Du kan tilpasse oppdateringsplanen eller deaktivere den for å kjøre eksporter manuelt.</span><span class="sxs-lookup"><span data-stu-id="5dc88-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="5dc88-150">Eksportplaner er avhengig av tilstanden til miljøet.</span><span class="sxs-lookup"><span data-stu-id="5dc88-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="5dc88-151">Hvis [avhengigheter](system.md#refresh-policies) oppdateres når en planlagt eksport skal starte, fullfører systemet oppdateringene for avhengighetene først, og deretter kjører det eksporten.</span><span class="sxs-lookup"><span data-stu-id="5dc88-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="5dc88-152">Du kan se når en eksport sist ble oppdatert, i kolonnen **Oppdatert**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="5dc88-153">Planlegge eksporter</span><span class="sxs-lookup"><span data-stu-id="5dc88-153">Schedule exports</span></span>

<span data-ttu-id="5dc88-154">Du kan definere egendefinerte oppdateringsplaner for individuelle eksporter eller flere eksporter samtidig.</span><span class="sxs-lookup"><span data-stu-id="5dc88-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="5dc88-155">Den gjeldende definerte tidsplanen vises i **Tidsplan**-kolonnen i eksportlisten.</span><span class="sxs-lookup"><span data-stu-id="5dc88-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="5dc88-156">Tillatelsen til å endre tidsplanen er den samme som for [redigering og definisjon av eksporter](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5dc88-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="5dc88-157">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5dc88-158">Velg eksporten du vil planlegge.</span><span class="sxs-lookup"><span data-stu-id="5dc88-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="5dc88-159">Velg **Planlegg** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="5dc88-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="5dc88-160">Sett **Planlegg kjøring** til **På** i ruten **Planlegg eksport** for å kjøre eksporten automatisk.</span><span class="sxs-lookup"><span data-stu-id="5dc88-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="5dc88-161">Sett den til **Av** for å oppdatere den manuelt.</span><span class="sxs-lookup"><span data-stu-id="5dc88-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="5dc88-162">Velg en verdi for **Gjentakelse** for automatisk oppdaterte eksporter, og angi detaljene for den.</span><span class="sxs-lookup"><span data-stu-id="5dc88-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="5dc88-163">Den angitte tiden gjelder for alle forekomster av en gjentakelse.</span><span class="sxs-lookup"><span data-stu-id="5dc88-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="5dc88-164">Det tidspunktet når en eksport skal begynne å oppdateres.</span><span class="sxs-lookup"><span data-stu-id="5dc88-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="5dc88-165">Bruk og aktiver endringene ved å velge **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="5dc88-166">Når du redigerer tidsplanen for flere eksporter, må du foreta et valg under **Behold eller overstyr tidsplaner**:</span><span class="sxs-lookup"><span data-stu-id="5dc88-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="5dc88-167">**Behold individuelle tidsplaner**: Behold den tidligere definerte tidsplanen for de valgte eksportene, og bare deaktiver eller aktiver dem.</span><span class="sxs-lookup"><span data-stu-id="5dc88-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="5dc88-168">**Definer ny tidsplan for alle valgte eksporter**: Overstyr de eksisterende tidsplanene for de valgte eksportene.</span><span class="sxs-lookup"><span data-stu-id="5dc88-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="5dc88-169">Kjør eksporter ved behov</span><span class="sxs-lookup"><span data-stu-id="5dc88-169">Run exports on demand</span></span>

<span data-ttu-id="5dc88-170">Hvis du vil eksportere data uten å vente på en planlagt oppdatering, går du til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="5dc88-171">Hvis du vil kjøre alle eksporter, velger du **Kjør alle** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="5dc88-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="5dc88-172">Denne handlingen kjører bare eksporter som har en aktiv tidsplan.</span><span class="sxs-lookup"><span data-stu-id="5dc88-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="5dc88-173">Hvis du vil kjøre én eksport, merker du den i listen og velger **Kjør** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="5dc88-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="5dc88-174">Det er slik du kjører eksporter uten en aktiv tidsplan.</span><span class="sxs-lookup"><span data-stu-id="5dc88-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="5dc88-175">Fjerne en eksport</span><span class="sxs-lookup"><span data-stu-id="5dc88-175">Remove an Export</span></span>

1. <span data-ttu-id="5dc88-176">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="5dc88-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5dc88-177">Velg eksporten du vil fjerne.</span><span class="sxs-lookup"><span data-stu-id="5dc88-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="5dc88-178">Velg **Fjern** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="5dc88-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="5dc88-179">Bekreft fjerningen ved å velge **Fjern** i bekreftelsesdialogboksen.</span><span class="sxs-lookup"><span data-stu-id="5dc88-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
