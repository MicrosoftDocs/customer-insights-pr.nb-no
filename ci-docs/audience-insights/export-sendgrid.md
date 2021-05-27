---
title: Eksportere Customer Insights-data til SendGrid
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976928"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="0e74b-103">Eksportere segmenter til SendGrid (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="0e74b-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="0e74b-104">Eksporter segmenter av enhetlige kundeprofiler til SendGrid-kontaktliser, og bruk dem for kampanjer og e-postmarkedsføring i SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0e74b-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="0e74b-105">Forutsetninger for en tilkobling</span><span class="sxs-lookup"><span data-stu-id="0e74b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="0e74b-106">Du har en [SendGrid-konto](https://sendgrid.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="0e74b-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0e74b-107">Det finnes eksisterende kontaktlister i SendGrid og de tilsvarende ID-ene.</span><span class="sxs-lookup"><span data-stu-id="0e74b-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="0e74b-108">Hvis du vil ha mer informasjon, kan du se [SendGrid – administrer kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="0e74b-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="0e74b-109">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="0e74b-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0e74b-110">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="0e74b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0e74b-111">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="0e74b-111">Known limitations</span></span>

- <span data-ttu-id="0e74b-112">Totalt opptil 100 000 profiler til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0e74b-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="0e74b-113">Eksport til SendGrid er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="0e74b-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="0e74b-114">Det kan ta opptil noen timer å eksportere opptil 100 000 profiler til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0e74b-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="0e74b-115">Antallet profiler du kan eksportere til SendGrid, er avhengig av og begrenset til kontrakten din med SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0e74b-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="0e74b-116">Konfigurere tilkobling til SendGrid</span><span class="sxs-lookup"><span data-stu-id="0e74b-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="0e74b-117">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="0e74b-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0e74b-118">Velg **Legg til tilkobling**, og velg **SendGrid** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0e74b-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="0e74b-119">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="0e74b-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0e74b-120">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0e74b-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0e74b-121">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0e74b-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0e74b-122">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0e74b-122">Choose who can use this connection.</span></span> <span data-ttu-id="0e74b-123">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="0e74b-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0e74b-124">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0e74b-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0e74b-125">Angi **API-nøkkelen for SendGrid** [API-nøkkel for SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="0e74b-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="0e74b-126">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="0e74b-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0e74b-127">Velg **Koble til** for å initialisere tilkoblingen til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0e74b-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="0e74b-128">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="0e74b-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0e74b-129">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0e74b-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0e74b-130">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="0e74b-130">Configure an export</span></span>

<span data-ttu-id="0e74b-131">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="0e74b-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0e74b-132">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0e74b-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0e74b-133">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="0e74b-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0e74b-134">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="0e74b-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0e74b-135">Velg en tilkobling fra SendGrid-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="0e74b-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="0e74b-136">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="0e74b-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0e74b-137">Angi **[ID-en for SendGrid-listen](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="0e74b-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="0e74b-138">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="0e74b-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0e74b-139">Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**, **Land/område**, **Delstat**, **Sted** og **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="0e74b-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="0e74b-140">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="0e74b-140">Select the segments you want to export.</span></span> <span data-ttu-id="0e74b-141">Vi **anbefaler på det sterkeste at du ikke eksporterer mer enn 100 000 kundeprofiler totalt** til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0e74b-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="0e74b-142">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="0e74b-142">Select **Save**.</span></span>

<span data-ttu-id="0e74b-143">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="0e74b-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0e74b-144">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0e74b-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0e74b-145">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0e74b-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0e74b-146">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="0e74b-146">Data privacy and compliance</span></span>

<span data-ttu-id="0e74b-147">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til SendGrid, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger.</span><span class="sxs-lookup"><span data-stu-id="0e74b-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0e74b-148">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at SendGrid oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="0e74b-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0e74b-149">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0e74b-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0e74b-150">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="0e74b-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]