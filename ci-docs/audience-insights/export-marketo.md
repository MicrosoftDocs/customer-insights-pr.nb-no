---
title: Eksportere Customer Insights-data til Marketo
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059328"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="1a919-103">Eksportere segmenter til Marketo (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="1a919-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="1a919-104">Du kan eksportere segmenter av enhetlige kundeprofiler for å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Marketo.</span><span class="sxs-lookup"><span data-stu-id="1a919-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1a919-105">Forutsetninger for tilkobling</span><span class="sxs-lookup"><span data-stu-id="1a919-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="1a919-106">Du har en [Marketo-konto](https://login.marketo.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="1a919-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1a919-107">Det finnes eksisterende lister i Marketo og de tilsvarende ID-ene.</span><span class="sxs-lookup"><span data-stu-id="1a919-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="1a919-108">Hvis du vil ha mer informasjon, kan du se [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="1a919-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="1a919-109">Du har [konfigurerte segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1a919-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="1a919-110">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="1a919-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1a919-111">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="1a919-111">Known limitations</span></span>

- <span data-ttu-id="1a919-112">Opptil 1 million profiler per eksport til Marketo.</span><span class="sxs-lookup"><span data-stu-id="1a919-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="1a919-113">Eksport til Marketo er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="1a919-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="1a919-114">Eksport av segmenter med totalt 1 million profiler kan ta opptil tre timer.</span><span class="sxs-lookup"><span data-stu-id="1a919-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="1a919-115">Antallet profiler du kan eksportere til Marketo, er avhengig av og begrenset til kontrakten din med Marketo.</span><span class="sxs-lookup"><span data-stu-id="1a919-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="1a919-116">Konfigurere tilkobling til Marketo</span><span class="sxs-lookup"><span data-stu-id="1a919-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="1a919-117">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="1a919-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1a919-118">Velg **Legg til tilkobling**, og velg **Marketo** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="1a919-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="1a919-119">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="1a919-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1a919-120">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="1a919-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1a919-121">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="1a919-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1a919-122">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="1a919-122">Choose who can use this connection.</span></span> <span data-ttu-id="1a919-123">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="1a919-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1a919-124">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1a919-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1a919-125">Angi **[Marketo-klient-ID-en, klienthemmeligheten og vertsnavnet for REST-endepunktet](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="1a919-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="1a919-126">REST-endepunktvertsnavnet er bare vertsnavnet, uten `https://`.</span><span class="sxs-lookup"><span data-stu-id="1a919-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="1a919-127">Eksempel: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="1a919-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="1a919-128">Velg **Jeg godtar** for å bekrefte **datapersonvern og -samsvar**, og velg **Koble til** for å initialisere tilkoblingen til Marketo.</span><span class="sxs-lookup"><span data-stu-id="1a919-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="1a919-129">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="1a919-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1a919-130">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="1a919-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1a919-131">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="1a919-131">Configure an export</span></span>

<span data-ttu-id="1a919-132">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="1a919-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1a919-133">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1a919-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1a919-134">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="1a919-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1a919-135">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="1a919-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1a919-136">Velg en tilkobling fra Marketo-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="1a919-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="1a919-137">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="1a919-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1a919-138">Angi **[ID-en for Marketo-listen](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="1a919-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="1a919-139">Liste-ID-en er en ren numerisk verdi.</span><span class="sxs-lookup"><span data-stu-id="1a919-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="1a919-140">Hvis Marketo-liste-ID-en for eksempel er ST12345A7, fjerner du tegnet før og etter tallene og angir `12345`.</span><span class="sxs-lookup"><span data-stu-id="1a919-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="1a919-141">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="1a919-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="1a919-142">Du kan eventuelt eksportere **Fornavn**, **Etternavn**, **Poststed**, **Delstat** og **Land/område** for å opprette mer tilpassede e-poster.</span><span class="sxs-lookup"><span data-stu-id="1a919-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="1a919-143">Velg **Legg til attributt** for å tilordne disse feltene.</span><span class="sxs-lookup"><span data-stu-id="1a919-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1a919-144">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="1a919-144">Select the segments you want to export.</span></span> <span data-ttu-id="1a919-145">Du kan eksportere opptil 1 million kundeprofiler totalt til Marketo.</span><span class="sxs-lookup"><span data-stu-id="1a919-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="1a919-146">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="1a919-146">Select **Save**.</span></span>

<span data-ttu-id="1a919-147">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="1a919-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1a919-148">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1a919-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1a919-149">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1a919-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="1a919-150">I Marketo kan du nå finne segmentene under [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="1a919-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1a919-151">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="1a919-151">Data privacy and compliance</span></span>

<span data-ttu-id="1a919-152">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Marketo, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="1a919-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1a919-153">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Marketo oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="1a919-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1a919-154">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1a919-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1a919-155">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="1a919-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
