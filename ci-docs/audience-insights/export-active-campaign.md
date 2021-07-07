---
title: Eksportere Customer Insights-data til ActiveCampaign
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314653"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="36086-103">Eksportere segmenter til ActiveCampaign (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="36086-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="36086-104">Eksporter segmenter av enhetlige kundeprofiler til ActiveCampaign, og bruk dem for markedsføringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="36086-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36086-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="36086-105">Prerequisites</span></span>

-   <span data-ttu-id="36086-106">Du har en [ActiveCampaign-konto](https://www.activecampaign.com/) og tilsvarende administratorlegitimasjon.</span><span class="sxs-lookup"><span data-stu-id="36086-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="36086-107">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="36086-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="36086-108">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt med en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="36086-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="36086-109">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="36086-109">Known limitations</span></span>

- <span data-ttu-id="36086-110">Du kan eksportere opptil 1 million profiler per eksport til ActiveCampaign, og det kan ta opptil 90 minutter å fullføre den.</span><span class="sxs-lookup"><span data-stu-id="36086-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="36086-111">Eksport til ActiveCampaign er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="36086-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="36086-112">Antall profiler du kan eksportere til ActiveCampaign, avhenger av kontrakten med ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="36086-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="36086-113">Konfigurere tilkobling til ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="36086-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="36086-114">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="36086-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="36086-115">Velg **Legg til tilkobling**, og velg **ActiveCampaign** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="36086-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="36086-116">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="36086-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="36086-117">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="36086-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="36086-118">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="36086-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="36086-119">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="36086-119">Choose who can use this connection.</span></span> <span data-ttu-id="36086-120">Som standard er det bare administratorer.</span><span class="sxs-lookup"><span data-stu-id="36086-120">By default, it's only administrators.</span></span> <span data-ttu-id="36086-121">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="36086-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="36086-122">Angi [ActiveCampaign-API-nøkkel og vertsnavn for REST-endepunkt](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="36086-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="36086-123">REST-endepunktvertsnavnet er bare vertsnavnet, uten https://.</span><span class="sxs-lookup"><span data-stu-id="36086-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="36086-124">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="36086-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="36086-125">Velg **Koble til** for å starte tilkoblingen til ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="36086-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="36086-126">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="36086-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="36086-127">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="36086-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="36086-128">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="36086-128">Configure an export</span></span>

<span data-ttu-id="36086-129">Du kan konfigurere en eksport hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="36086-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="36086-130">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="36086-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="36086-131">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="36086-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="36086-132">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="36086-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="36086-133">Velg feltet **Tilkobling for eksport**, og velg en tilkobling fra ActiveCampaign-delen.</span><span class="sxs-lookup"><span data-stu-id="36086-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="36086-134">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="36086-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="36086-135">Angi [**ActiveCampaign-liste-IDen**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="36086-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="36086-136">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="36086-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="36086-137">Det kreves at du eksporterer segmenter til ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="36086-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="36086-138">Du kan eventuelt eksportere Fornavn, Etternavn og Telefon for å opprette mer tilpassede e-postmeldinger.</span><span class="sxs-lookup"><span data-stu-id="36086-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="36086-139">Velg Legg til attributt for å tilordne disse feltene.</span><span class="sxs-lookup"><span data-stu-id="36086-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="36086-140">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="36086-140">Select **Save**.</span></span>

<span data-ttu-id="36086-141">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="36086-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="36086-142">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="36086-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="36086-143">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="36086-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="36086-144">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="36086-144">Data privacy and compliance</span></span>

<span data-ttu-id="36086-145">Når du gjør det mulig for Dynamics 365 Customer Insights å overføre data til ActiveCampaign, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data som personlige data.</span><span class="sxs-lookup"><span data-stu-id="36086-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="36086-146">Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at ActiveCampaign oppfyller personvern- eller sikkerhetsforpliktelser du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="36086-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="36086-147">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="36086-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="36086-148">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="36086-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
