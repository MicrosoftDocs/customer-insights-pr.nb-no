---
title: Eksportere Customer Insights-data til Microsoft Advertising
description: Finn ut hvordan du konfigurerer tilkoblingen og eksporten til Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124528"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="e8b08-103">Eksportere segmenter til Microsoft Advertising (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="e8b08-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="e8b08-104">Eksporter Customer Insights-segmenter til Microsoft Advertising for å opprette Customer Match-målgrupper.</span><span class="sxs-lookup"><span data-stu-id="e8b08-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="e8b08-105">Bruk disse målgruppene for annonsekampanjene.</span><span class="sxs-lookup"><span data-stu-id="e8b08-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e8b08-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="e8b08-106">Prerequisites</span></span>

-   <span data-ttu-id="e8b08-107">En [Microsoft Advertising-konto](https://ads.microsoft.com/) og tilhørende administratorlegitimasjon.</span><span class="sxs-lookup"><span data-stu-id="e8b08-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e8b08-108">Du har godtatt vilkårene for bruk for Customer Match.</span><span class="sxs-lookup"><span data-stu-id="e8b08-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="e8b08-109">[Konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="e8b08-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e8b08-110">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt med en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="e8b08-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e8b08-111">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="e8b08-111">Known limitations</span></span>

- <span data-ttu-id="e8b08-112">Du kan eksportere opptil 500 000 profiler per eksport til Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e8b08-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="e8b08-113">Eksport til Microsoft Advertising er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="e8b08-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="e8b08-114">Det kan ta opptil 10 minutter å eksportere 500 000 profiler til Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e8b08-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="e8b08-115">Konfigurere tilkoblingen til Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="e8b08-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="e8b08-116">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="e8b08-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e8b08-117">Velg **Legg til tilkobling**, og velg **Microsoft Advertising** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="e8b08-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="e8b08-118">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="e8b08-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e8b08-119">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="e8b08-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e8b08-120">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="e8b08-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e8b08-121">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="e8b08-121">Choose who can use this connection.</span></span> <span data-ttu-id="e8b08-122">Standarden er administratorer.</span><span class="sxs-lookup"><span data-stu-id="e8b08-122">The default is administrators.</span></span> <span data-ttu-id="e8b08-123">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e8b08-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e8b08-124">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="e8b08-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e8b08-125">Velg **Koble til** for å initialisere tilkoblingen til Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e8b08-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="e8b08-126">Velg **Godkjenn med Microsoft Advertising**, og angi legitimasjonen for administrator for Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e8b08-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="e8b08-127">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="e8b08-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e8b08-128">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="e8b08-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e8b08-129">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="e8b08-129">Configure an export</span></span>

<span data-ttu-id="e8b08-130">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="e8b08-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e8b08-131">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e8b08-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e8b08-132">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="e8b08-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e8b08-133">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="e8b08-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e8b08-134">Velg en tilkobling fra Microsoft Advertising-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="e8b08-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="e8b08-135">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="e8b08-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e8b08-136">Velg segmentene som skal eksporteres.</span><span class="sxs-lookup"><span data-stu-id="e8b08-136">Select the segments to export.</span></span> <span data-ttu-id="e8b08-137">Customer Match-målgruppene i Microsoft Advertising opprettes automatisk med navnet på segmentene som er valgt for eksport.</span><span class="sxs-lookup"><span data-stu-id="e8b08-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="e8b08-138">Hvert segment fører til en egen Customer Match-målgruppe.</span><span class="sxs-lookup"><span data-stu-id="e8b08-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="e8b08-139">Angi **Kunde-ID og konto-ID for Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="e8b08-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="e8b08-140">Du finner kunde-ID-en (`cid`) og konto-ID-en (`aid`) i parameterne for nettadressen når du er logget på Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e8b08-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="e8b08-141">Velg feltet i den enhetlige kundeprofilen med e-postadressen til en kunde i feltet **E-post** i delen **Datasamsvar**.</span><span class="sxs-lookup"><span data-stu-id="e8b08-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="e8b08-142">Det kreves for å eksportere segmenter til Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e8b08-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="e8b08-143">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="e8b08-143">Select **Save**.</span></span>

<span data-ttu-id="e8b08-144">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="e8b08-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e8b08-145">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e8b08-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e8b08-146">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e8b08-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e8b08-147">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="e8b08-147">Data privacy and compliance</span></span>

<span data-ttu-id="e8b08-148">Når du aktiverer Dynamics 365 Customer Insights for å overføre data til Microsoft Advertising, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger.</span><span class="sxs-lookup"><span data-stu-id="e8b08-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e8b08-149">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Microsoft Advertising oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="e8b08-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e8b08-150">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e8b08-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e8b08-151">Administratoren for Dynamics 365 Customer Insights kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="e8b08-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
