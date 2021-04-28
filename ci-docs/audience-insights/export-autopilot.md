---
title: Eksportere Customer Insights-data til Autopilot
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760155"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="f1e60-103">Eksportere segmenter til Autopilot (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="f1e60-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="f1e60-104">Eksporter segmenter av enhetlige kundeprofiler til Autopilot, og bruk dem for e-postmarkedsføring i Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f1e60-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f1e60-105">Forutsetninger for en tilkobling</span><span class="sxs-lookup"><span data-stu-id="f1e60-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f1e60-106">Du har en [Autopilot-konto](https://www.autopilothq.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="f1e60-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f1e60-107">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="f1e60-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f1e60-108">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="f1e60-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f1e60-109">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="f1e60-109">Known limitations</span></span>

- <span data-ttu-id="f1e60-110">Du kan eksportere opptil 100 000 profiler totalt til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f1e60-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="f1e60-111">Eksport til Autopilot er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="f1e60-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="f1e60-112">Det kan ta opptil noen timer å eksportere opptil 100 000 profiler til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f1e60-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="f1e60-113">Antallet profiler du kan eksportere til Autopilot, er avhengig av og begrenset til kontrakten din med Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f1e60-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="f1e60-114">Konfigurere tilkobling til Autopilot</span><span class="sxs-lookup"><span data-stu-id="f1e60-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="f1e60-115">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="f1e60-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f1e60-116">Velg **Legg til tilkobling**, og velg **Autopilot** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f1e60-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="f1e60-117">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="f1e60-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f1e60-118">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f1e60-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f1e60-119">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f1e60-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f1e60-120">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f1e60-120">Choose who can use this connection.</span></span> <span data-ttu-id="f1e60-121">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="f1e60-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f1e60-122">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f1e60-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="f1e60-123">Angi [API-nøkkelen for Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="f1e60-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="f1e60-124">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="f1e60-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f1e60-125">Velg **Koble til** for å initialisere tilkoblingen til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f1e60-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="f1e60-126">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="f1e60-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f1e60-127">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f1e60-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f1e60-128">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="f1e60-128">Configure an export</span></span>

<span data-ttu-id="f1e60-129">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="f1e60-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f1e60-130">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f1e60-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f1e60-131">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="f1e60-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f1e60-132">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="f1e60-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f1e60-133">Velg en tilkobling fra Autopilot-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="f1e60-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="f1e60-134">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="f1e60-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="f1e60-135">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="f1e60-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f1e60-136">Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**.</span><span class="sxs-lookup"><span data-stu-id="f1e60-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="f1e60-137">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="f1e60-137">Select the segments you want to export.</span></span> <span data-ttu-id="f1e60-138">Vi **anbefaler på det sterkeste at du ikke eksporterer mer enn 100 000 kundeprofiler totalt** til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f1e60-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="f1e60-139">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="f1e60-139">Select **Save**.</span></span>

<span data-ttu-id="f1e60-140">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="f1e60-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f1e60-141">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f1e60-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f1e60-142">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f1e60-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f1e60-143">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="f1e60-143">Data privacy and compliance</span></span>

<span data-ttu-id="f1e60-144">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Autopilot, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger.</span><span class="sxs-lookup"><span data-stu-id="f1e60-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f1e60-145">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Autopilot oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="f1e60-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f1e60-146">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f1e60-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f1e60-147">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="f1e60-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
