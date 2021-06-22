---
title: Eksportere Customer Insights-data til Omnisend
description: Finn ut hvordan du konfigurerer tilkoblingen og eksporterer til Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124529"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="5a8d3-103">Eksportere segmenter til Omnisend (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="5a8d3-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="5a8d3-104">Eksporter segmenter av enhetlige kundeprofiler til Omnisend, og bruk dem til markedsføringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a8d3-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="5a8d3-105">Prerequisites</span></span>

-   <span data-ttu-id="5a8d3-106">Du har en [Omnisend-konto](https://www.omnisend.com/) og tilhørende administratorlegitimasjon.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5a8d3-107">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5a8d3-108">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5a8d3-109">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="5a8d3-109">Known limitations</span></span>

- <span data-ttu-id="5a8d3-110">Du kan eksportere opptil 1 million profiler per eksport til Omnisend, og det kan ta opptil 4 timer å fullføre den.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="5a8d3-111">Eksport til Omnisend er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="5a8d3-112">Antall profiler du kan eksportere til Omnisend, avhenger av kontrakten med Omnisend.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="5a8d3-113">Konfigurere tilkobling til Omnisend</span><span class="sxs-lookup"><span data-stu-id="5a8d3-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="5a8d3-114">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5a8d3-115">Velg **Legg til tilkobling**, og velg **Omnisend** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="5a8d3-116">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5a8d3-117">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5a8d3-118">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5a8d3-119">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-119">Choose who can use this connection.</span></span> <span data-ttu-id="5a8d3-120">Som standard er det bare administratorer.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-120">By default it's only administrators.</span></span> <span data-ttu-id="5a8d3-121">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5a8d3-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5a8d3-122">Angi [API-nøkkel for Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="5a8d3-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="5a8d3-123">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5a8d3-124">Velg **Koble til** for å initialisere tilkoblingen til Omnisend.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="5a8d3-125">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5a8d3-126">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5a8d3-127">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="5a8d3-127">Configure an export</span></span>

<span data-ttu-id="5a8d3-128">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5a8d3-129">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5a8d3-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5a8d3-130">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5a8d3-131">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5a8d3-132">Velg en tilkobling fra Omnisend-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="5a8d3-133">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5a8d3-134">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5a8d3-135">Det kreves for å eksportere segmenter til Omnisend.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="5a8d3-136">Du kan eventuelt eksportere Fornavn, Etternavn, Adresse, Land/område, Delstat, Poststed og Postnummer for å opprette mer tilpassede e-poster.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="5a8d3-137">Velg **Legg til attributt** for å tilordne disse feltene.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="5a8d3-138">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-138">Select **Save**.</span></span>

<span data-ttu-id="5a8d3-139">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5a8d3-140">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5a8d3-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5a8d3-141">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5a8d3-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5a8d3-142">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="5a8d3-142">Data privacy and compliance</span></span>

<span data-ttu-id="5a8d3-143">Når du aktiverer Dynamics 365 Customer Insights for å overføre data til Ommisend, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5a8d3-144">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Omnisend oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5a8d3-145">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5a8d3-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5a8d3-146">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="5a8d3-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
