---
title: Eksportere Customer Insights-data til Mailchimp
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976167"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="0bbc8-103">Eksportere segmentlister til Mailchimp (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="0bbc8-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="0bbc8-104">Eksporter segmenter av enhetlige kundeprofiler til MailChimp for å opprette nyhetsbrev og e-postkampanjer.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0bbc8-105">Forutsetninger for tilkobling</span><span class="sxs-lookup"><span data-stu-id="0bbc8-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="0bbc8-106">Du har en [Mailchimp-konto](https://mailchimp.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0bbc8-107">Det finnes eksisterende målgrupper i Mailchimp og de tilsvarende ID-ene.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="0bbc8-108">Hvis du vil ha mer informasjon, kan du se [målgrupper i Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="0bbc8-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="0bbc8-109">Du har [konfigurerte segmenter](segments.md)</span><span class="sxs-lookup"><span data-stu-id="0bbc8-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="0bbc8-110">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0bbc8-111">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="0bbc8-111">Known limitations</span></span>

- <span data-ttu-id="0bbc8-112">Opptil 1 million profiler per eksport til Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="0bbc8-113">Eksport til Mailchimp er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="0bbc8-114">Det kan ta opptil tre timer å eksportere segmenter med 1 million profiler.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="0bbc8-115">Antallet profiler du kan eksportere til Mailchimp, er avhengig av og begrenset til kontrakten din med Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="0bbc8-116">Konfigurer tilkoblingen til Mailchimp</span><span class="sxs-lookup"><span data-stu-id="0bbc8-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="0bbc8-117">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0bbc8-118">Velg **Legg til tilkobling**, og velg **Autopilot** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="0bbc8-119">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0bbc8-120">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0bbc8-121">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0bbc8-122">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-122">Choose who can use this connection.</span></span> <span data-ttu-id="0bbc8-123">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0bbc8-124">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0bbc8-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0bbc8-125">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0bbc8-126">Velg **Koble til** for å initialisere tilkoblingen til Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="0bbc8-127">Velg **Godkjenn med Mailchimp**, og angi Mailchimp-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="0bbc8-128">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0bbc8-129">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="0bbc8-130">Konfigurere koblingen</span><span class="sxs-lookup"><span data-stu-id="0bbc8-130">Configure the connector</span></span>

<span data-ttu-id="0bbc8-131">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0bbc8-132">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0bbc8-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0bbc8-133">Gå til **Data**> **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="0bbc8-134">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0bbc8-135">Velg en tilkobling fra Mailchimp-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="0bbc8-136">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0bbc8-137">Angi **[ID for Mailchimp-målgruppe](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="0bbc8-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="0bbc8-138">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0bbc8-139">Du kan eventuelt eksportere **fornavn** og **etternavn** for å opprette mer tilpassede e-poster.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="0bbc8-140">Velg **Legg til attributt** for å tilordne disse feltene.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0bbc8-141">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-141">Select the segments you want to export.</span></span> <span data-ttu-id="0bbc8-142">Du kan eksportere opptil 1 million kundeprofiler totalt til Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="0bbc8-143">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-143">Select **Save**.</span></span>

<span data-ttu-id="0bbc8-144">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0bbc8-145">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0bbc8-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0bbc8-146">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0bbc8-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0bbc8-147">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="0bbc8-147">Data privacy and compliance</span></span>

<span data-ttu-id="0bbc8-148">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Mailchimp, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0bbc8-149">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Mailchimp oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0bbc8-150">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0bbc8-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0bbc8-151">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="0bbc8-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
