---
title: Eksportere Customer Insights-data til Marketo
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759833"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="bb6e4-103">Eksportere segmenter til Marketo (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="bb6e4-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="bb6e4-104">Du kan eksportere segmenter av enhetlige kundeprofiler for å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Marketo.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="bb6e4-105">Forutsetninger for tilkobling</span><span class="sxs-lookup"><span data-stu-id="bb6e4-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="bb6e4-106">Du har en [Marketo-konto](https://login.marketo.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bb6e4-107">Det finnes eksisterende lister i Marketo og de tilsvarende ID-ene.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="bb6e4-108">Hvis du vil ha mer informasjon, kan du se [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="bb6e4-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="bb6e4-109">Du har [konfigurerte segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bb6e4-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="bb6e4-110">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bb6e4-111">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="bb6e4-111">Known limitations</span></span>

- <span data-ttu-id="bb6e4-112">Opptil 1 million profiler per eksport til Marketo.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="bb6e4-113">Eksport til Marketo er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="bb6e4-114">Eksport av segmenter med totalt 1 million profiler kan ta opptil tre timer.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="bb6e4-115">Antallet profiler du kan eksportere til Marketo, er avhengig av og begrenset til kontrakten din med Marketo.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="bb6e4-116">Konfigurere tilkobling til Marketo</span><span class="sxs-lookup"><span data-stu-id="bb6e4-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="bb6e4-117">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bb6e4-118">Velg **Legg til tilkobling**, og velg **Marketo** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="bb6e4-119">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bb6e4-120">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bb6e4-121">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bb6e4-122">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-122">Choose who can use this connection.</span></span> <span data-ttu-id="bb6e4-123">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bb6e4-124">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bb6e4-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bb6e4-125">Angi **[Marketo-klient-ID-en, klienthemmeligheten og vertsnavnet for REST-endepunktet](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="bb6e4-126">Velg **Jeg godtar** for å bekrefte **datapersonvern og -samsvar**, og velg **Koble til** for å initialisere tilkoblingen til Marketo.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="bb6e4-127">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bb6e4-128">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bb6e4-129">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="bb6e4-129">Configure an export</span></span>

<span data-ttu-id="bb6e4-130">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bb6e4-131">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bb6e4-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bb6e4-132">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bb6e4-133">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bb6e4-134">Velg en tilkobling fra Marketo-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="bb6e4-135">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bb6e4-136">Angi **[ID-en for Marketo-listen](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="bb6e4-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="bb6e4-137">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="bb6e4-138">Du kan eventuelt eksportere **Fornavn**, **Etternavn**, **Poststed**, **Delstat** og **Land/område** for å opprette mer tilpassede e-poster.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="bb6e4-139">Velg **Legg til attributt** for å tilordne disse feltene.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="bb6e4-140">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-140">Select the segments you want to export.</span></span> <span data-ttu-id="bb6e4-141">Du kan eksportere opptil 1 million kundeprofiler totalt til Marketo.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="bb6e4-142">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-142">Select **Save**.</span></span>

<span data-ttu-id="bb6e4-143">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bb6e4-144">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb6e4-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bb6e4-145">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bb6e4-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="bb6e4-146">I Marketo kan du nå finne segmentene under [Marketo-lister](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="bb6e4-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bb6e4-147">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="bb6e4-147">Data privacy and compliance</span></span>

<span data-ttu-id="bb6e4-148">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Marketo, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bb6e4-149">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Marketo oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bb6e4-150">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bb6e4-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bb6e4-151">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="bb6e4-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]