---
title: Eksportere Customer Insights-data til Sendinblue
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314652"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="1fa49-103">Eksportere segmenter til Sendinblue (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="1fa49-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="1fa49-104">Eksporter segmenter for enhetlige kundeprofiler for å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="1fa49-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1fa49-105">Forutsetninger for tilkobling</span><span class="sxs-lookup"><span data-stu-id="1fa49-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="1fa49-106">Du har en [Sendinblue-konto](https://www.sendinblue.com/) og tilsvarende administratorlegitimasjon.</span><span class="sxs-lookup"><span data-stu-id="1fa49-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1fa49-107">Det finnes eksisterende lister i Sendinblue og de tilhørende IDene.</span><span class="sxs-lookup"><span data-stu-id="1fa49-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="1fa49-108">Du har [konfigurerte segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1fa49-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="1fa49-109">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="1fa49-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1fa49-110">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="1fa49-110">Known limitations</span></span>

- <span data-ttu-id="1fa49-111">Opptil 1 million profiler per eksport til Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="1fa49-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="1fa49-112">Eksport til Sendinblue er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="1fa49-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="1fa49-113">Det kan ta opptil 90 minutter å eksportere segmenter med totalt 1 million profiler.</span><span class="sxs-lookup"><span data-stu-id="1fa49-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="1fa49-114">Antall profiler du kan eksportere til Sendinblue, er avhengig av og begrenset til kontrakten med Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="1fa49-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="1fa49-115">Konfigurere tilkobling til Sendinblue</span><span class="sxs-lookup"><span data-stu-id="1fa49-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="1fa49-116">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="1fa49-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1fa49-117">Velg **Legg til tilkobling**, og velg **Sendinblue** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="1fa49-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="1fa49-118">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="1fa49-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1fa49-119">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="1fa49-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1fa49-120">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="1fa49-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1fa49-121">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="1fa49-121">Choose who can use this connection.</span></span> <span data-ttu-id="1fa49-122">Som standard er det bare administratorer.</span><span class="sxs-lookup"><span data-stu-id="1fa49-122">By default it's only administrators.</span></span> <span data-ttu-id="1fa49-123">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1fa49-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1fa49-124">Angi **[API-nøkkelen for SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="1fa49-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="1fa49-125">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar** og velg **Koble til** for å initialisere tilkoblingen til Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="1fa49-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="1fa49-126">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="1fa49-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1fa49-127">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="1fa49-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1fa49-128">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="1fa49-128">Configure an export</span></span>

<span data-ttu-id="1fa49-129">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="1fa49-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1fa49-130">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1fa49-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1fa49-131">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="1fa49-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1fa49-132">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="1fa49-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1fa49-133">Velg feltet **Tilkobling for eksport**, og velg en tilkobling fra Sendinblue-delen.</span><span class="sxs-lookup"><span data-stu-id="1fa49-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="1fa49-134">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="1fa49-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1fa49-135">Angi **Sendinblue-liste-IDen**</span><span class="sxs-lookup"><span data-stu-id="1fa49-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="1fa49-136">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="1fa49-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="1fa49-137">Du kan eventuelt eksportere **Fornavn**, **Etternavn** og **Telefon** for å opprette mer tilpassede e-postmeldinger.</span><span class="sxs-lookup"><span data-stu-id="1fa49-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="1fa49-138">Velg **Legg til attributt** for å tilordne disse feltene.</span><span class="sxs-lookup"><span data-stu-id="1fa49-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1fa49-139">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="1fa49-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="1fa49-140">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="1fa49-140">Select **Save**.</span></span>

<span data-ttu-id="1fa49-141">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="1fa49-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1fa49-142">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1fa49-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1fa49-143">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1fa49-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1fa49-144">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="1fa49-144">Data privacy and compliance</span></span>

<span data-ttu-id="1fa49-145">Når du gjør det mulig for Dynamics 365 Customer Insights å overføre data til Sendinblue, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data som personlige data.</span><span class="sxs-lookup"><span data-stu-id="1fa49-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1fa49-146">Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Sendinblue oppfyller personvern- eller sikkerhetsforpliktelser du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="1fa49-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1fa49-147">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1fa49-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1fa49-148">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="1fa49-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
