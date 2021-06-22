---
title: Eksportere Customer Insights-data til LinkedIn-annonser
description: Finn ut hvordan du konfigurerer tilkoblingen og eksporterer til LinkedIn-annonser.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124530"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="8c457-103">Eksportere segmenter til LinkedIn-annonser (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="8c457-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="8c457-104">Eksporter segmenter av enhetlige kundeprofiler til LinkedIn-annonser for å opprette samsvarende målgrupper.</span><span class="sxs-lookup"><span data-stu-id="8c457-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="8c457-105">Bruk de samsvarende målgruppene til firmamålretting og kontaktmålretting.</span><span class="sxs-lookup"><span data-stu-id="8c457-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c457-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="8c457-106">Prerequisites</span></span>

-   <span data-ttu-id="8c457-107">Du har en [LinkedIn Campaign Manager-konto](https://business.linkedin.com/marketing-solutions/ads) og tilhørende administratorlegitimasjon.</span><span class="sxs-lookup"><span data-stu-id="8c457-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8c457-108">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="8c457-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8c457-109">Kundeprofiler i de eksporterte segmentene inneholder et felt med en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="8c457-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8c457-110">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="8c457-110">Known limitations</span></span>

- <span data-ttu-id="8c457-111">Du kan eksportere opptil 100 000 profiler per eksport til LinkedIn-annonser.</span><span class="sxs-lookup"><span data-stu-id="8c457-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="8c457-112">Eksport til LinkedIn-annonser er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="8c457-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="8c457-113">Det kan ta opptil 10 minutter å eksportere opptil 100 000 profiler til LinkedIn-annonser.</span><span class="sxs-lookup"><span data-stu-id="8c457-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="8c457-114">Konfigurere tilkoblingen til LinkedIn-annonser</span><span class="sxs-lookup"><span data-stu-id="8c457-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="8c457-115">I målgruppeinnsikt går du til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="8c457-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8c457-116">Velg **Legg til tilkobling**, og velg **LinkedIn-annonser** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8c457-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="8c457-117">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="8c457-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8c457-118">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8c457-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8c457-119">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8c457-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8c457-120">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8c457-120">Choose who can use this connection.</span></span> <span data-ttu-id="8c457-121">Hvis du ikke gjør noe, er standarden administratorer.</span><span class="sxs-lookup"><span data-stu-id="8c457-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="8c457-122">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8c457-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8c457-123">Angi [konto-ID-en for LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="8c457-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="8c457-124">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="8c457-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8c457-125">Velg **Koble til** for å initialisere tilkoblingen til Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="8c457-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="8c457-126">Velg **Godkjenn med LinkedIn**, og angi legitimasjonen for administrator for LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="8c457-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="8c457-127">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="8c457-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8c457-128">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8c457-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8c457-129">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="8c457-129">Configure an export</span></span>

<span data-ttu-id="8c457-130">Du kan konfigurere en eksport hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="8c457-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="8c457-131">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8c457-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8c457-132">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="8c457-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8c457-133">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="8c457-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8c457-134">Velg en tilkobling fra delen LinkedIn-annonse i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="8c457-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="8c457-135">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="8c457-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8c457-136">Velg om du vil eksportere data for å foreta [kontaktmålretting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) eller [firmamålretting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) på LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="8c457-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="8c457-137">Velg feltet i den enhetlige kundeprofilen som representerer e-postadressen til en kunde, i feltet E-post i delen **Datasamsvar**.</span><span class="sxs-lookup"><span data-stu-id="8c457-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8c457-138">Det kreves for å eksportere segmenter til LinkedIn-annonser.</span><span class="sxs-lookup"><span data-stu-id="8c457-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="8c457-139">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="8c457-139">Select the segments you want to export.</span></span> <span data-ttu-id="8c457-140">De samsvarende målgruppene i LinkedIn Campaign Manager blir opprettet automatisk med navnet på segmentene du valgte å eksportere.</span><span class="sxs-lookup"><span data-stu-id="8c457-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="8c457-141">Hvert segment fører til en egen samsvarende målgruppe.</span><span class="sxs-lookup"><span data-stu-id="8c457-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="8c457-142">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="8c457-142">Select **Save**.</span></span>

<span data-ttu-id="8c457-143">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="8c457-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8c457-144">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8c457-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8c457-145">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8c457-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8c457-146">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="8c457-146">Data privacy and compliance</span></span>

<span data-ttu-id="8c457-147">Når du aktiverer Dynamics 365 Customer Insights for å overføre data til LinkedIn-annonser, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger.</span><span class="sxs-lookup"><span data-stu-id="8c457-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8c457-148">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at LinkedIn-annonser oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="8c457-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8c457-149">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8c457-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8c457-150">Administratoren for Dynamics 365 Customer Insights kan fjerne dette eksportmålet når som helst for stoppe bruken av denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="8c457-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
