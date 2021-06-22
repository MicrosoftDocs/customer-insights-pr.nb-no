---
title: Eksportere Customer Insights-data til Constant Contact
description: Lær hvordan du konfigurerer tilkoblingen og eksporten til Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124285"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="79cfa-103">Eksportere segmenter til Constant Contact (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="79cfa-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="79cfa-104">Eksporter segmenter av enhetlige kundeprofiler til Constant Contact, og bruk dem for markedsføringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="79cfa-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="79cfa-105">Forutsetninger for en tilkobling</span><span class="sxs-lookup"><span data-stu-id="79cfa-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="79cfa-106">Du har en [Constant Contact-konto](https://www.constantcontact.com/account-home) og tilhørende administratorlegitimasjon.</span><span class="sxs-lookup"><span data-stu-id="79cfa-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="79cfa-107">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="79cfa-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="79cfa-108">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="79cfa-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="79cfa-109">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="79cfa-109">Known limitations</span></span>

- <span data-ttu-id="79cfa-110">Du kan eksportere opptil 1 million profiler per eksport til Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="79cfa-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="79cfa-111">Eksport til Constant Contact er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="79cfa-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="79cfa-112">Det kan ta opptil 1 time å eksportere 1 million profiler til Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="79cfa-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="79cfa-113">Antall profiler du kan eksportere til Constant Contact, er avhengig av og begrenset av kontrakten med Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="79cfa-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="79cfa-114">Konfigurer tilkobling til Constant Contact</span><span class="sxs-lookup"><span data-stu-id="79cfa-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="79cfa-115">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="79cfa-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="79cfa-116">Velg **Legg til tilkobling**, og velg **Constant Contact** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="79cfa-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="79cfa-117">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="79cfa-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="79cfa-118">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="79cfa-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="79cfa-119">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="79cfa-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="79cfa-120">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="79cfa-120">Choose who can use this connection.</span></span> <span data-ttu-id="79cfa-121">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="79cfa-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="79cfa-122">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="79cfa-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="79cfa-123">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="79cfa-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="79cfa-124">Velg **Koble til** for å initialisere tilkoblingen til Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="79cfa-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="79cfa-125">Velg **Godkjenn med AdRoll**, og angi legitimasjonen for administrator for Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="79cfa-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="79cfa-126">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="79cfa-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="79cfa-127">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="79cfa-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="79cfa-128">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="79cfa-128">Configure an export</span></span>

<span data-ttu-id="79cfa-129">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="79cfa-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="79cfa-130">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="79cfa-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="79cfa-131">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="79cfa-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="79cfa-132">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="79cfa-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="79cfa-133">Velg en tilkobling fra Constant Contact-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="79cfa-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="79cfa-134">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="79cfa-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="79cfa-135">Angi [**liste-IDen for Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="79cfa-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="79cfa-136">Åpne en liste i Constant Contact for å finne liste-IDen i URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="79cfa-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="79cfa-137">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="79cfa-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="79cfa-138">Det kreves for å eksportere segmenter til Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="79cfa-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="79cfa-139">Du kan eventuelt eksportere Fornavn og Etternavn som tilleggsfelt for å opprette mer tilpassede e-postmeldinger.</span><span class="sxs-lookup"><span data-stu-id="79cfa-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="79cfa-140">Velg **Legg til attributt** for å tilordne disse feltene.</span><span class="sxs-lookup"><span data-stu-id="79cfa-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="79cfa-141">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="79cfa-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="79cfa-142">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="79cfa-142">Select **Save**.</span></span>

<span data-ttu-id="79cfa-143">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="79cfa-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="79cfa-144">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="79cfa-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="79cfa-145">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="79cfa-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="79cfa-146">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="79cfa-146">Data privacy and compliance</span></span>

<span data-ttu-id="79cfa-147">Når du aktiverer Dynamics 365 Customer Insights for å overføre data til Constant Contact, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, for eksempel personlige opplysninger.</span><span class="sxs-lookup"><span data-stu-id="79cfa-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="79cfa-148">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Constant Contact oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="79cfa-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="79cfa-149">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="79cfa-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="79cfa-150">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="79cfa-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
