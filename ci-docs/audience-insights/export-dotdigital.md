---
title: Eksportere Customer Insights-data til DotDigital
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976858"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="20555-103">Eksportere segmentlister til DotDigital (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="20555-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="20555-104">Eksporter segmenter med enhetlige kundeprofiler til DotDigital-adressebøker, og bruk dem for kampanjer, e-postmarkedsføring og til å bygge kundesegmenter med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="20555-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="20555-105">Forutsetninger for en tilkobling</span><span class="sxs-lookup"><span data-stu-id="20555-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="20555-106">Du har en [DotDigital-konto](https://dotdigital.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="20555-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="20555-107">Det finnes eksisterende adressebøker i DotDigital og de tilsvarende ID-ene.</span><span class="sxs-lookup"><span data-stu-id="20555-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="20555-108">Du kan finne ID-en i URL-adressen når du velger og åpner en adressebok.</span><span class="sxs-lookup"><span data-stu-id="20555-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="20555-109">Hvis du vil ha mer informasjon, kan du se [DotDigital-adressebøker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="20555-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="20555-110">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="20555-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="20555-111">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="20555-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="20555-112">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="20555-112">Known limitations</span></span>

- <span data-ttu-id="20555-113">Opptil 1 million profiler per eksport til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="20555-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="20555-114">Eksport til DotDigital er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="20555-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="20555-115">Eksport av segmenter med totalt 1 million profiler kan ta opptil tre timer på grunn av begrensninger på leverandørsiden.</span><span class="sxs-lookup"><span data-stu-id="20555-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="20555-116">Antallet profiler du kan eksportere til DotDigital, er avhengig av og begrenset til kontrakten din med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="20555-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="20555-117">Konfigurere tilkobling til DotDigital</span><span class="sxs-lookup"><span data-stu-id="20555-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="20555-118">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="20555-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="20555-119">Velg **Legg til tilkobling**, og velg **DotDigital** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="20555-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="20555-120">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="20555-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="20555-121">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="20555-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="20555-122">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="20555-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="20555-123">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="20555-123">Choose who can use this connection.</span></span> <span data-ttu-id="20555-124">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="20555-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="20555-125">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="20555-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="20555-126">Angi **brukernavnet og passordet for DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="20555-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="20555-127">Angi **[ID-en for DotDigital-adresseboken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="20555-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="20555-128">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="20555-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="20555-129">Velg **Koble til** for å initialisere tilkoblingen til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="20555-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="20555-130">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="20555-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="20555-131">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="20555-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="20555-132">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="20555-132">Configure an export</span></span>

<span data-ttu-id="20555-133">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="20555-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="20555-134">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="20555-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="20555-135">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="20555-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="20555-136">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="20555-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="20555-137">Velg en tilkobling fra DotDigital-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="20555-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="20555-138">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="20555-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="20555-139">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="20555-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="20555-140">Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**, **Fullt navn**, **Kjønn** og **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="20555-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="20555-141">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="20555-141">Select the segments you want to export.</span></span> <span data-ttu-id="20555-142">Du kan eksportere opptil 1 million kundeprofiler totalt til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="20555-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="20555-143">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="20555-143">Select **Save**.</span></span>

<span data-ttu-id="20555-144">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="20555-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="20555-145">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="20555-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="20555-146">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="20555-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="20555-147">I DotDigital kan du nå finne segmentene i [DotDigital-adressebøker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="20555-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="20555-148">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="20555-148">Data privacy and compliance</span></span>

<span data-ttu-id="20555-149">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til DotDigital, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="20555-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="20555-150">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at DotDigital oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="20555-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="20555-151">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="20555-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="20555-152">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="20555-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
