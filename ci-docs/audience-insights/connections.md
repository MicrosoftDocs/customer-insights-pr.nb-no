---
title: Tilkoblinger til andre tjenester fra Customer Insights.
description: Del data med andre tjenester.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304984"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="eec58-103">Oversikt over tilkoblinger (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="eec58-103">Connections (preview) overview</span></span>

<span data-ttu-id="eec58-104">Tilkoblinger er nøkkelen til å aktivere datadeling til og fra Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eec58-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="eec58-105">Hver tilkobling oppretter datadeling med en bestemt tjeneste.</span><span class="sxs-lookup"><span data-stu-id="eec58-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="eec58-106">Tilkoblinger er grunnlaget for å [konfigurere suppleringer fra tredjeparter](enrichment-hub.md) og [konfigurere eksporter](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="eec58-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="eec58-107">Den samme tilkoblingen kan brukes flere ganger.</span><span class="sxs-lookup"><span data-stu-id="eec58-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="eec58-108">Én tilkobling til Dynamics 365 Marketing fungerer for eksempel for flere eksporter, og én Leadspace-tilkobling kan brukes til flere suppleringer.</span><span class="sxs-lookup"><span data-stu-id="eec58-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="eec58-109">Gå til **Administrator** > **Tilkoblinger** for å opprette og vise tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="eec58-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="eec58-110">Kategorien **Tilkoblinger** viser alle aktive tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="eec58-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="eec58-111">Listen viser en rad for hver tilkobling.</span><span class="sxs-lookup"><span data-stu-id="eec58-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="eec58-112">Få en rask oversikt, beskrivelse og finn ut hva du kan gjøre med hvert utvidelsesalternativ i kategorien **Oppdag**.</span><span class="sxs-lookup"><span data-stu-id="eec58-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="eec58-113">Eksporter</span><span class="sxs-lookup"><span data-stu-id="eec58-113">Exports</span></span>

<span data-ttu-id="eec58-114">Bare administratorer kan konfigurere nye tilkoblinger, men de kan gi tilgang til bidragsytere for å bruke eksisterende tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="eec58-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="eec58-115">Administratorer kontrollerer hvor data kan gå, bidragsytere definerer nyttelasten og frekvensen som passer til deres behov.</span><span class="sxs-lookup"><span data-stu-id="eec58-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="eec58-116">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="eec58-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="eec58-117">Suppleringer</span><span class="sxs-lookup"><span data-stu-id="eec58-117">Enrichments</span></span>

<span data-ttu-id="eec58-118">Bare administratorer kan konfigurere nye tilkoblinger, men de opprettede tilkoblingene er alltid tilgjengelige for både administratorer og bidragsytere.</span><span class="sxs-lookup"><span data-stu-id="eec58-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="eec58-119">Administratorer administrerer legitimasjon og gir samtykke til dataoverføringer.</span><span class="sxs-lookup"><span data-stu-id="eec58-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="eec58-120">Tilkoblingene kan deretter brukes til suppleringer av både administratorer og bidragsytere.</span><span class="sxs-lookup"><span data-stu-id="eec58-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="eec58-121">Legg til en ny tilkobling</span><span class="sxs-lookup"><span data-stu-id="eec58-121">Add a new connection</span></span>

<span data-ttu-id="eec58-122">Hvis du vil legge til tilkoblinger, må du ha [administratortillatelser](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="eec58-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="eec58-123">Hvis du kobler til andre Microsoft-tjenester, antar vi at begge tjenestene er i samme organisasjon.</span><span class="sxs-lookup"><span data-stu-id="eec58-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="eec58-124">Gå til **Administrator** > **Tilkoblinger (forhåndsversjon)**.</span><span class="sxs-lookup"><span data-stu-id="eec58-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="eec58-125">Gå til kategorien **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="eec58-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="eec58-126">Velg **Legg til tilkobling** for å opprette en ny tilkobling.</span><span class="sxs-lookup"><span data-stu-id="eec58-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="eec58-127">Velg hvilken tilkoblingstype du vil opprette, i rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="eec58-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="eec58-128">Angi de nødvendige detaljene i ruten **Konfigurer tilkobling**.</span><span class="sxs-lookup"><span data-stu-id="eec58-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="eec58-129">**Visningsnavnet** og tilkoblingstypen beskriver en tilkobling.</span><span class="sxs-lookup"><span data-stu-id="eec58-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="eec58-130">Vi anbefaler at du velger et navn som forklarer formålet med og målet for denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="eec58-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="eec58-131">De nøyaktige feltene avhenger av hvilken tjeneste du kobler til.</span><span class="sxs-lookup"><span data-stu-id="eec58-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="eec58-132">Du kan lære om detaljer om en bestemt tilkoblingstype i artikkelen om måltjenesten.</span><span class="sxs-lookup"><span data-stu-id="eec58-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="eec58-133">Velg **Lagre** for å opprette tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="eec58-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="eec58-134">Du kan også velge **Konfigurer** på en flis i kategorien **Oppdag**.</span><span class="sxs-lookup"><span data-stu-id="eec58-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="eec58-135">Tillat bidragsytere å bruke en tilkobling for eksporter</span><span class="sxs-lookup"><span data-stu-id="eec58-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="eec58-136">Når du definerer eller redigerer en eksporttilkobling, velger du hvilke brukere som har tillatelse til å bruke denne bestemte tilkoblingen til å definere [eksporter](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="eec58-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="eec58-137">Som standard er en tilkobling tilgjengelig for brukere med en administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="eec58-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="eec58-138">Du kan endre denne innstillingen under **Velg hvem som kan bruke denne tilkoblingen**, og la brukere med bidragsyterrolle bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="eec58-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="eec58-139">Bidragsytere kan ikke vise eller redigere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="eec58-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="eec58-140">De vil bare se visningsnavn og dens type når du oppretter en eksport.</span><span class="sxs-lookup"><span data-stu-id="eec58-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="eec58-141">Ved å dele en tilkobling tillater du at bidragsytere bruker en tilkobling.</span><span class="sxs-lookup"><span data-stu-id="eec58-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="eec58-142">Bidragsytere vil se delte tilkoblinger når de konfigurerer eksporter.</span><span class="sxs-lookup"><span data-stu-id="eec58-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="eec58-143">De kan administrere hver eksport som bruker denne spesifikke tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="eec58-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="eec58-144">Du kan endre denne innstillingen samtidig som du beholder eksportene som allerede er definert av bidragsytere.</span><span class="sxs-lookup"><span data-stu-id="eec58-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="eec58-145">Redigere en tilkobling</span><span class="sxs-lookup"><span data-stu-id="eec58-145">Edit a connection</span></span>

1. <span data-ttu-id="eec58-146">Gå til **Administrator** > **Tilkoblinger (forhåndsversjon)**.</span><span class="sxs-lookup"><span data-stu-id="eec58-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="eec58-147">Gå til kategorien **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="eec58-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="eec58-148">Velg den loddrette ellipsen for tilkoblingen du vil redigere.</span><span class="sxs-lookup"><span data-stu-id="eec58-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="eec58-149">Velg **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="eec58-149">Select **Edit**.</span></span>

1. <span data-ttu-id="eec58-150">Endre verdiene du vil oppdatere, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="eec58-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="eec58-151">Fjerne en tilkobling</span><span class="sxs-lookup"><span data-stu-id="eec58-151">Remove a connection</span></span>

<span data-ttu-id="eec58-152">Hvis tilkoblingen du fjerner, brukes av suppleringer eller eksport, må du først koble fra eller fjerne dem.</span><span class="sxs-lookup"><span data-stu-id="eec58-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="eec58-153">Dialogboksen for fjerning vil lede deg til de relevante suppleringene eller eksportene.</span><span class="sxs-lookup"><span data-stu-id="eec58-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="eec58-154">Frakoblede suppleringer og eksporter blir inaktive.</span><span class="sxs-lookup"><span data-stu-id="eec58-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="eec58-155">Du aktiverer dem på nytt ved å legge til en annen tilkobling til dem på siden [Suppleringer](enrichment-hub.md) eller [Eksporter](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="eec58-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="eec58-156">Gå til **Administrator** > **Tilkoblinger (forhåndsversjon)**.</span><span class="sxs-lookup"><span data-stu-id="eec58-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="eec58-157">Gå til kategorien **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="eec58-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="eec58-158">Velg den loddrette ellipsen for tilkoblingen du vil fjerne.</span><span class="sxs-lookup"><span data-stu-id="eec58-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="eec58-159">Velg **Fjern** fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="eec58-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="eec58-160">En bekreftelsesdialogboks vises.</span><span class="sxs-lookup"><span data-stu-id="eec58-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="eec58-161">Hvis det er suppleringer eller eksporterer som bruker denne tilkoblingen, velger du knappen for å se hva som bruker tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="eec58-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="eec58-162">**Eksporter:** Du kan velge å fjerne eller koble fra eksportene for å kunne fjerne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="eec58-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="eec58-163">Administratorer kan bruke **Koble fra**-handlingen for å koble fra en eksport.</span><span class="sxs-lookup"><span data-stu-id="eec58-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="eec58-164">Denne handlingen er tilgjengelig for individuelle og flere valgte eksporter.</span><span class="sxs-lookup"><span data-stu-id="eec58-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="eec58-165">Ved å koble fra beholder du eksportkonfigurasjonen, men den kjøres ikke før en annen tilkobling er lagt til i den.</span><span class="sxs-lookup"><span data-stu-id="eec58-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="eec58-166">**Suppleringer:** Du kan velge å fjerne eller deaktivere suppleringene for å kunne fjerne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="eec58-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="eec58-167">Når tilkoblingen ikke har flere avhengigheter, går du tilbake til **Administrator** > **Tilkoblinger** og prøver å fjerne tilkoblingen på nytt.</span><span class="sxs-lookup"><span data-stu-id="eec58-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="eec58-168">Velg **Fjern** for å bekrefte slettingen.</span><span class="sxs-lookup"><span data-stu-id="eec58-168">To confirm the deletion, select **Remove**.</span></span>

