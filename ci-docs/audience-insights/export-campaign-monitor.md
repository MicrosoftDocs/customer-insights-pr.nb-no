---
title: Eksportere Customer Insights-data til Campaign Monitor
description: Lær hvordan du konfigurerer tilkoblingen og eksporten til Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124193"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="e659f-103">Eksportere segmenter til Campaign Monitor (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="e659f-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="e659f-104">Eksporter segmenter av enhetlige kundeprofiler til Campaign Monitor, og bruk dem for markedsføringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="e659f-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e659f-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="e659f-105">Prerequisites</span></span>

-   <span data-ttu-id="e659f-106">Du har en [Campaign Monitor-konto](https://www.campaignmonitor.com/) og tilhørende administratorlegitimasjon.</span><span class="sxs-lookup"><span data-stu-id="e659f-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e659f-107">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="e659f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e659f-108">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="e659f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e659f-109">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="e659f-109">Known limitations</span></span>

- <span data-ttu-id="e659f-110">Du kan eksportere opptil 1 million profiler per eksport til Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e659f-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="e659f-111">Eksport til Campaign Monitor er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="e659f-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="e659f-112">Det kan ta opptil 20 minutter å eksportere 1 million profiler til Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e659f-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="e659f-113">Antall profiler du kan eksportere til Campaign Monitor, er avhengig av og begrenset av kontrakten med Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e659f-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="e659f-114">Konfigurer tilkoblingen til Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="e659f-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="e659f-115">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="e659f-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e659f-116">Velg **Legg til tilkobling**, og velg **Campaign Monitor** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="e659f-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="e659f-117">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="e659f-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e659f-118">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="e659f-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e659f-119">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="e659f-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e659f-120">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="e659f-120">Choose who can use this connection.</span></span> <span data-ttu-id="e659f-121">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="e659f-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e659f-122">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e659f-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e659f-123">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="e659f-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e659f-124">Velg **Koble til** for å initialisere tilkoblingen til Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e659f-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="e659f-125">Velg **Godkjenn med Campaign Monitor**, og angi legitimasjonen for administrator for Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e659f-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="e659f-126">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="e659f-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e659f-127">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="e659f-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e659f-128">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="e659f-128">Configure an export</span></span>

<span data-ttu-id="e659f-129">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="e659f-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e659f-130">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e659f-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e659f-131">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="e659f-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e659f-132">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="e659f-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e659f-133">Velg en tilkobling fra Campaign Monitor-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="e659f-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="e659f-134">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="e659f-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e659f-135">Angi [**liste-ID-en for Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="e659f-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="e659f-136">[Generer API-nøkkelen](https://www.campaignmonitor.com/api/getting-started/) fra **Kontoinnstillinger** i Campaign Monitor først for å vise API-liste-IDen.</span><span class="sxs-lookup"><span data-stu-id="e659f-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="e659f-137">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="e659f-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e659f-138">Det kreves for å eksportere segmenter til Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e659f-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="e659f-139">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="e659f-139">Select **Save**.</span></span>

<span data-ttu-id="e659f-140">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="e659f-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e659f-141">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e659f-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e659f-142">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e659f-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e659f-143">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="e659f-143">Data privacy and compliance</span></span>

<span data-ttu-id="e659f-144">Når du aktiverer Dynamics 365 Customer Insights for å overføre data til Campaign Monitor, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, for eksempel personlige opplysninger.</span><span class="sxs-lookup"><span data-stu-id="e659f-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e659f-145">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Campaign Monitor oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="e659f-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e659f-146">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e659f-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e659f-147">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="e659f-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
