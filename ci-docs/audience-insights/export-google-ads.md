---
title: Eksportere Customer Insights-data til Google Ads
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976330"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="85606-103">Eksportere segmenter til Google Ads (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="85606-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="85606-104">Eksporter segmenter av enhetlige kundeprofiler til Google Ads-målgruppelisten, og bruk dem til å annonsere på Google Search, Gmail, YouTube og Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="85606-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="85606-105">Forutsetninger for tilkobling</span><span class="sxs-lookup"><span data-stu-id="85606-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="85606-106">Du har en [Google Ads-konto](https://ads.google.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="85606-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="85606-107">Du har et [godkjent utviklertoken for Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="85606-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="85606-108">Du oppfyller kravene i [retningslinjene for kundesamsvar](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="85606-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="85606-109">Du oppfyller kravene i [størrelsene for remarkedsføringsliste](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="85606-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="85606-110">Det finnes eksisterende målgrupper i Google Ads og de tilsvarende ID-ene.</span><span class="sxs-lookup"><span data-stu-id="85606-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="85606-111">Hvis du vil ha mer informasjon, kan du se [målgrupper i Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="85606-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="85606-112">Du har [konfigurerte segmenter](segments.md)</span><span class="sxs-lookup"><span data-stu-id="85606-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="85606-113">Enhetlige kundeprofiler i de eksporterte segmentene inneholder felt som representerer en e-postadresse, et fornavn og et etternavn</span><span class="sxs-lookup"><span data-stu-id="85606-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="85606-114">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="85606-114">Known limitations</span></span>

- <span data-ttu-id="85606-115">Opptil 1 million profiler per eksport til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="85606-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="85606-116">Eksport til Google Ads er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="85606-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="85606-117">Eksport av segmenter med totalt 1 million profiler kan ta opptil fem minutter på grunn av begrensninger på leverandørsiden.</span><span class="sxs-lookup"><span data-stu-id="85606-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="85606-118">Samsvaret i Google Ads kan ta opptil 48 timer.</span><span class="sxs-lookup"><span data-stu-id="85606-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="85606-119">Konfigurer tilkobling til Google Ads</span><span class="sxs-lookup"><span data-stu-id="85606-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="85606-120">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="85606-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="85606-121">Velg **Legg til tilkobling**, og velg **Google Ads** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="85606-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="85606-122">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="85606-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="85606-123">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="85606-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="85606-124">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="85606-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="85606-125">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="85606-125">Choose who can use this connection.</span></span> <span data-ttu-id="85606-126">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="85606-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="85606-127">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="85606-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="85606-128">Angi **[kunde-ID-en for Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="85606-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="85606-129">Skriv inn **[det godkjente utviklertokenet for Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="85606-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="85606-130">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="85606-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="85606-131">Velg **Godkjenn med Google Ads**, og angi Google Ads-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="85606-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="85606-132">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="85606-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="85606-133">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="85606-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="85606-134">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="85606-134">Configure an export</span></span>

<span data-ttu-id="85606-135">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="85606-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="85606-136">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="85606-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="85606-137">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="85606-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="85606-138">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="85606-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="85606-139">Velg en tilkobling fra Google Ads-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="85606-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="85606-140">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="85606-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="85606-141">Angi **[ID-en for Google Ads-målgruppen](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**, og velg **Koble til** for å initialisere tilkoblingen til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="85606-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="85606-142">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="85606-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="85606-143">Gjenta de samme trinnene for feltene **Fornavn** og **Etternavn**.</span><span class="sxs-lookup"><span data-stu-id="85606-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="85606-144">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="85606-144">Select the segments you want to export.</span></span> <span data-ttu-id="85606-145">Du kan eksportere opptil 1 million kundeprofiler totalt til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="85606-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="85606-146">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="85606-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="85606-147">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="85606-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="85606-148">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="85606-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="85606-149">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="85606-149">Data privacy and compliance</span></span>

<span data-ttu-id="85606-150">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Google Ads, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="85606-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="85606-151">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Google Ads oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="85606-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="85606-152">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="85606-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="85606-153">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="85606-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
