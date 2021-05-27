---
title: Eksportere Customer Insights-data til Facebook-annonseadministrasjon
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976054"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="db6c4-103">Eksportere segmentlister til Facebook Ads Manager (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="db6c4-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="db6c4-104">Eksporter segmenter for enhetlige kundeprofiler til Facebook-annonseadministrasjon for å opprette kampanjer på Facebook og Instagram.</span><span class="sxs-lookup"><span data-stu-id="db6c4-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="db6c4-105">Forutsetninger for tilkobling</span><span class="sxs-lookup"><span data-stu-id="db6c4-105">Prerequisites for connection</span></span>

- <span data-ttu-id="db6c4-106">Du må ha en [**Facebook-annonsekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) som inkluderer en [**Facebook -forretningskonto**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="db6c4-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="db6c4-107">Du må være administrator på [**Facebook-annonsekontoen**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="db6c4-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="db6c4-108">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="db6c4-108">Known limitations</span></span>

- <span data-ttu-id="db6c4-109">Opptil 10 millioner kundeprofiler per eksport til Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="db6c4-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="db6c4-110">Eksport til Facebook Ads Manager er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="db6c4-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="db6c4-111">Opprett eller oppdater egendefinerte målgrupper i Facebook bare av typen *kundeliste*.</span><span class="sxs-lookup"><span data-stu-id="db6c4-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="db6c4-112">Eksport av segmenter med totalt 10 million profiler kan ta opptil 90 minutter å fullføre.</span><span class="sxs-lookup"><span data-stu-id="db6c4-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="db6c4-113">Konfigurer tilkobling til Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="db6c4-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="db6c4-114">Før brukere kan opprette en eksport, må en administrator konfigurere tilkoblingen til tjenesten og la bidragsytere bruke tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="db6c4-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="db6c4-115">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="db6c4-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="db6c4-116">Velg **Legg til tilkobling**, og velg **Facebook Ads Manager** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="db6c4-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="db6c4-117">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="db6c4-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="db6c4-118">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="db6c4-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="db6c4-119">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="db6c4-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="db6c4-120">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="db6c4-120">Choose who can use this connection.</span></span> <span data-ttu-id="db6c4-121">Hvis du ikke gjør noe, vil standarden være **Administratorer**.</span><span class="sxs-lookup"><span data-stu-id="db6c4-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="db6c4-122">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="db6c4-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="db6c4-123">Godkjenn med Facebook-annonser:</span><span class="sxs-lookup"><span data-stu-id="db6c4-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="db6c4-124">Velg **Fortsett med Facebook** for å logge på Facebook-annonsekontoen din.</span><span class="sxs-lookup"><span data-stu-id="db6c4-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="db6c4-125">Tillat **ads_management**-tillatelsen etter godkjenning med Facebook.</span><span class="sxs-lookup"><span data-stu-id="db6c4-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="db6c4-126">Velg **Facebook-annonsekontoen** du vil arbeide med.</span><span class="sxs-lookup"><span data-stu-id="db6c4-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="db6c4-127">Velg en **eksisterende egendefinert målgruppe** fra rullegardinlisten, eller opprett et **ny egendefinert målgruppe**.</span><span class="sxs-lookup"><span data-stu-id="db6c4-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="db6c4-128">Hvis du vil ha mer informasjon, kan du se [**Målgrupper i Facebook-annonseadministrasjon**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="db6c4-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="db6c4-129">Du kan bare opprette eller oppdatere egendefinerte målgrupper på Facebook av typen *kundeliste* med denne eksporten.</span><span class="sxs-lookup"><span data-stu-id="db6c4-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="db6c4-130">I noen tilfeller ser du egendefinerte målgrupper av forskjellige typer i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="db6c4-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="db6c4-131">Hvis du velger en annen type enn *kundeliste*, fører det til en mislykket eksport.</span><span class="sxs-lookup"><span data-stu-id="db6c4-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="db6c4-132">Se gjennom **Datapersonvern og -samsvar**, og velg **Jeg godtar**.</span><span class="sxs-lookup"><span data-stu-id="db6c4-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="db6c4-133">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="db6c4-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="db6c4-134">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="db6c4-134">Configure an export</span></span>

<span data-ttu-id="db6c4-135">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="db6c4-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="db6c4-136">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="db6c4-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="db6c4-137">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="db6c4-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="db6c4-138">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="db6c4-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="db6c4-139">I **Tilkobling for eksport** velger du en tilkobling fra delen **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="db6c4-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="db6c4-140">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="db6c4-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="db6c4-141">I feltet **Velg nøkkelidentifikator** velger du **E-post**, **Navn og adresse** eller **Telefon** som skal sendes til Facebook-annonseadministrasjon.</span><span class="sxs-lookup"><span data-stu-id="db6c4-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="db6c4-142">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="db6c4-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="db6c4-143">Tilordne de tilsvarende attributtene fra den enhetlige kundeenheten for den valgte nøkkelidentifikatoren.</span><span class="sxs-lookup"><span data-stu-id="db6c4-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="db6c4-144">[TIPS] Den beste muligheten for et treff oppstår hvis du velger **E-post** som nøkkelidentifikator.</span><span class="sxs-lookup"><span data-stu-id="db6c4-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="db6c4-145">Hvis du legger til flere identifikatorer, kan du få bedre samsvar.</span><span class="sxs-lookup"><span data-stu-id="db6c4-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="db6c4-146">Velg **Legg til attributt** for å tilordne flere attributter som skal sendes til Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="db6c4-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="db6c4-147">Attributter fra Facebook-administrasjon tilordnes til følgende brukervennlige navn: **FN** = **Fornavn**, **LN** = **Etternavn**, **FI** = **Første initial**, **PHONE** = **Telefon**, **GEN** = **Kjønn**, **DOB** = **Fødselsdato**, **ST** = **Delstat**, **CT** = **Poststed**, **ZIP** = **Postnummer**, **COUNTRY** = **Land/distrikt**</span><span class="sxs-lookup"><span data-stu-id="db6c4-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="db6c4-148">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="db6c4-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="db6c4-149">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="db6c4-149">Select **Save**.</span></span>

<span data-ttu-id="db6c4-150">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="db6c4-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="db6c4-151">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="db6c4-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="db6c4-152">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="db6c4-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="db6c4-153">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="db6c4-153">Data privacy and compliance</span></span>

<span data-ttu-id="db6c4-154">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Facebook-annonseadministrasjon, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="db6c4-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="db6c4-155">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Facebook-annonseadministrasjon oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="db6c4-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="db6c4-156">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="db6c4-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="db6c4-157">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="db6c4-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
