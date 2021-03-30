---
title: Eksportere Customer Insights-data til Google Ads
description: Lær hvordan du konfigurerer tilkoblingen til Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598259"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="0904c-103">Kontakt for Google Ads (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="0904c-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="0904c-104">Eksporter segmenter av enhetlige kundeprofiler til Google Ads-målgruppelisten, og bruk dem til å annonsere på Google Search, Gmail, YouTube og Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="0904c-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0904c-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="0904c-105">Prerequisites</span></span>

-   <span data-ttu-id="0904c-106">Du har en [Google Ads-konto](https://ads.google.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="0904c-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0904c-107">Det finnes eksisterende målgrupper i Google Ads og de tilsvarende ID-ene.</span><span class="sxs-lookup"><span data-stu-id="0904c-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="0904c-108">Hvis du vil ha mer informasjon, kan du se [målgrupper i Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="0904c-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="0904c-109">Du har [konfigurerte segmenter](segments.md)</span><span class="sxs-lookup"><span data-stu-id="0904c-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="0904c-110">Enhetlige kundeprofiler i de eksporterte segmentene inneholder felt som representerer en e-postadresse, et fornavn og et etternavn</span><span class="sxs-lookup"><span data-stu-id="0904c-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="0904c-111">Koble til Google Ads</span><span class="sxs-lookup"><span data-stu-id="0904c-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="0904c-112">Gå til **Admin** > **Eksporter mål**.</span><span class="sxs-lookup"><span data-stu-id="0904c-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0904c-113">Under **Google Ads** velger du **Oppsett**.</span><span class="sxs-lookup"><span data-stu-id="0904c-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="0904c-114">Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="0904c-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0904c-115">Angi **[kunde-ID-en for Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="0904c-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="0904c-116">Skriv inn **[det godkjente utviklertokenet for Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="0904c-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="0904c-117">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="0904c-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0904c-118">Angi **[ID-en for Google Ads-målgruppen](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**, og velg **Koble til** for å initialisere tilkoblingen til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="0904c-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="0904c-119">Velg **Godkjenn med Google Ads**, og angi Google Ads-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="0904c-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="0904c-120">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="0904c-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Skjermbilde for eksport av Google Ads-tilkobling":::

1. <span data-ttu-id="0904c-122">Velg **Neste** for å konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="0904c-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0904c-123">Konfigurere koblingen</span><span class="sxs-lookup"><span data-stu-id="0904c-123">Configure the connector</span></span>

1. <span data-ttu-id="0904c-124">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="0904c-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0904c-125">Gjenta de samme trinnene for feltene **Fornavn** og **Etternavn**.</span><span class="sxs-lookup"><span data-stu-id="0904c-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="0904c-126">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="0904c-126">Select the segments you want to export.</span></span> <span data-ttu-id="0904c-127">Du kan eksportere opptil 1 million kundeprofiler totalt til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="0904c-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="0904c-128">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="0904c-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0904c-129">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="0904c-129">Export the data</span></span>

<span data-ttu-id="0904c-130">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0904c-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0904c-131">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0904c-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0904c-132">I Google Ads kan du nå finne segmentene under [Google Ads-målgrupper](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="0904c-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0904c-133">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="0904c-133">Known limitations</span></span>

- <span data-ttu-id="0904c-134">Opptil 1 million profiler per eksport til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="0904c-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="0904c-135">Eksport til Google Ads er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="0904c-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="0904c-136">Eksport av segmenter med totalt 1 million profiler kan ta opptil fem minutter på grunn av begrensninger på leverandørsiden.</span><span class="sxs-lookup"><span data-stu-id="0904c-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="0904c-137">Samsvaret i Google Ads kan ta opptil 48 timer.</span><span class="sxs-lookup"><span data-stu-id="0904c-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0904c-138">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="0904c-138">Data privacy and compliance</span></span>

<span data-ttu-id="0904c-139">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Google Ads, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="0904c-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0904c-140">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Google Ads oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="0904c-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0904c-141">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0904c-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0904c-142">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="0904c-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]