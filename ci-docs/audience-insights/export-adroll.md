---
title: Eksporter Customer Insights-data til AdRoll
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304845"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="97c27-103">Eksportere segmenter til AdRoll (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="97c27-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="97c27-104">Eksporter segmenter av enhetlige kundeprofiler til AdRoll, og bruk dem for reklame.</span><span class="sxs-lookup"><span data-stu-id="97c27-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="97c27-105">Forutsetninger for en tilkobling</span><span class="sxs-lookup"><span data-stu-id="97c27-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="97c27-106">Du har en [AdRoll-konto](https://www.adroll.com/) og tilhørende legitimasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="97c27-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="97c27-107">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="97c27-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="97c27-108">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="97c27-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="97c27-109">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="97c27-109">Known limitations</span></span>

- <span data-ttu-id="97c27-110">Du kan eksportere opptil 250 000 profiler om gangen til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="97c27-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="97c27-111">Du kan ikke eksportere segmenter med færre enn 100 profiler til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="97c27-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="97c27-112">Eksport til AdRoll er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="97c27-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="97c27-113">Det kan ta opptil 10 minutter å eksportere opptil 250 000 profiler til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="97c27-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="97c27-114">Antall profiler du kan eksportere til AdRoll, avhenger av kontrakten med AdRoll.</span><span class="sxs-lookup"><span data-stu-id="97c27-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="97c27-115">Konfigurer tilkobling til AdRoll</span><span class="sxs-lookup"><span data-stu-id="97c27-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="97c27-116">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="97c27-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="97c27-117">Velg **Legg til tilkobling**, og velg **AdRoll** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="97c27-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="97c27-118">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="97c27-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="97c27-119">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="97c27-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="97c27-120">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="97c27-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="97c27-121">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="97c27-121">Choose who can use this connection.</span></span> <span data-ttu-id="97c27-122">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="97c27-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="97c27-123">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="97c27-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="97c27-124">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="97c27-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="97c27-125">Velg **Koble til** for å initialisere tilkoblingen til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="97c27-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="97c27-126">Velg **Godkjenn med AdRoll**, og angi administratorlegitimasjonen din for AdRoll.</span><span class="sxs-lookup"><span data-stu-id="97c27-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="97c27-127">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="97c27-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="97c27-128">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="97c27-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="97c27-129">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="97c27-129">Configure an export</span></span>

<span data-ttu-id="97c27-130">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="97c27-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="97c27-131">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="97c27-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="97c27-132">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="97c27-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="97c27-133">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="97c27-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="97c27-134">Velg en tilkobling fra AdRoll-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="97c27-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="97c27-135">Hvis navnet på denne delen ikke vises, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="97c27-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="97c27-136">Angi **ID for AdRoll-annonsør**.</span><span class="sxs-lookup"><span data-stu-id="97c27-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="97c27-137">Hvis du vil ha mer informasjon, kan du se [AdRoll-annonsørprofiler](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="97c27-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="97c27-138">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="97c27-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="97c27-139">Dette kreves for å eksportere segmenter til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="97c27-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="97c27-140">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="97c27-140">Select the segments you want to export.</span></span> <span data-ttu-id="97c27-141">Velg et segment med minst 100 medlemmer.</span><span class="sxs-lookup"><span data-stu-id="97c27-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="97c27-142">Du kan ikke eksportere mindre segmenter.</span><span class="sxs-lookup"><span data-stu-id="97c27-142">You can't export smaller segments.</span></span> <span data-ttu-id="97c27-143">I tillegg er maksimumsstørrelsen for et segment som skal eksporteres, 250 000 medlemmer per eksport.</span><span class="sxs-lookup"><span data-stu-id="97c27-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="97c27-144">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="97c27-144">Select **Save**.</span></span>

<span data-ttu-id="97c27-145">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="97c27-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="97c27-146">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="97c27-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="97c27-147">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="97c27-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="97c27-148">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="97c27-148">Data privacy and compliance</span></span>

<span data-ttu-id="97c27-149">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til AdRoll, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="97c27-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="97c27-150">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at AdRoll oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="97c27-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="97c27-151">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="97c27-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="97c27-152">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="97c27-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
