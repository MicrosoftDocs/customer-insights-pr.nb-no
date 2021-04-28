---
title: Eksportere Customer Insights-data til Snapchat
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760595"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="2502a-103">Eksportere segmentlister til Snapchat (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="2502a-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="2502a-104">Eksporter segmenter av enhetlige kundeprofiler til Snapchat, og bruk dem til reklame.</span><span class="sxs-lookup"><span data-stu-id="2502a-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="2502a-105">Forutsetninger for en tilkobling</span><span class="sxs-lookup"><span data-stu-id="2502a-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="2502a-106">Du har en [Snapchat-forretningskonto](https://business.snapchat.com/), en [Snapchat-annonsekonto](https://ads.snapchat.com/) og tilsvarende administratorlegitimasjon.</span><span class="sxs-lookup"><span data-stu-id="2502a-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2502a-107">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="2502a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2502a-108">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="2502a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2502a-109">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="2502a-109">Known limitations</span></span>

- <span data-ttu-id="2502a-110">Eksport til Snapchat er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="2502a-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="2502a-111">Det kan ta opptil 15 minutter å eksportere opptil 1 million profiler til Snapchat.</span><span class="sxs-lookup"><span data-stu-id="2502a-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="2502a-112">Konfigurere tilkobling til Snapchat</span><span class="sxs-lookup"><span data-stu-id="2502a-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="2502a-113">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="2502a-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2502a-114">Velg **Legg til tilkobling**, og velg **Snapchat** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="2502a-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="2502a-115">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="2502a-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2502a-116">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="2502a-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2502a-117">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="2502a-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2502a-118">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="2502a-118">Choose who can use this connection.</span></span> <span data-ttu-id="2502a-119">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="2502a-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2502a-120">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2502a-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2502a-121">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="2502a-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2502a-122">Velg **Koble til** for å initialisere tilkoblingen til Snapchat.</span><span class="sxs-lookup"><span data-stu-id="2502a-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="2502a-123">Velg **Godkjenn med Snapchat**, og angi legitimasjonen for administrator for Snapchat.</span><span class="sxs-lookup"><span data-stu-id="2502a-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="2502a-124">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="2502a-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2502a-125">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="2502a-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2502a-126">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="2502a-126">Configure an export</span></span>

<span data-ttu-id="2502a-127">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="2502a-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2502a-128">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2502a-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2502a-129">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="2502a-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2502a-130">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="2502a-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2502a-131">Velg en tilkobling fra Snapchat-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="2502a-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="2502a-132">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="2502a-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2502a-133">Angi [**ID for Snapchat-målgruppe**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="2502a-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="2502a-134">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="2502a-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2502a-135">Det kreves for å eksportere segmenter til Snapchat.</span><span class="sxs-lookup"><span data-stu-id="2502a-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="2502a-136">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="2502a-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="2502a-137">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="2502a-137">Select **Save**.</span></span>

<span data-ttu-id="2502a-138">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="2502a-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2502a-139">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2502a-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2502a-140">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2502a-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2502a-141">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="2502a-141">Data privacy and compliance</span></span>

<span data-ttu-id="2502a-142">Når du aktiverer Dynamics 365 Customer Insights for å overføre data til Snapchat, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, for eksempel personlige opplysninger.</span><span class="sxs-lookup"><span data-stu-id="2502a-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2502a-143">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Snapchat oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="2502a-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2502a-144">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2502a-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="2502a-145">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="2502a-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
