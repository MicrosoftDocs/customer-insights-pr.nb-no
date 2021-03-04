---
title: Eksportere Customer Insights-data til Marketo
description: Lær hvordan du konfigurerer tilkoblingen til Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267093"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="a69ce-103">Kontakt for Marketo (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="a69ce-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="a69ce-104">Du kan eksportere segmenter av enhetlige kundeprofiler for å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Marketo.</span><span class="sxs-lookup"><span data-stu-id="a69ce-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a69ce-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="a69ce-105">Prerequisites</span></span>

-   <span data-ttu-id="a69ce-106">Du har en [Marketo-konto](https://login.marketo.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="a69ce-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a69ce-107">Det finnes eksisterende lister i Marketo og de tilsvarende ID-ene.</span><span class="sxs-lookup"><span data-stu-id="a69ce-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="a69ce-108">Hvis du vil ha mer informasjon, kan du se [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a69ce-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="a69ce-109">Du har [konfigurerte segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a69ce-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="a69ce-110">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="a69ce-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="a69ce-111">Koble til Marketo</span><span class="sxs-lookup"><span data-stu-id="a69ce-111">Connect to Marketo</span></span>

1. <span data-ttu-id="a69ce-112">Gå til **Admin** > **Eksporter mål**.</span><span class="sxs-lookup"><span data-stu-id="a69ce-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a69ce-113">Under **Marketo** velger du **Oppsett**.</span><span class="sxs-lookup"><span data-stu-id="a69ce-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="a69ce-114">Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="a69ce-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a69ce-115">Angi **[Marketo-klient-ID-en, klienthemmeligheten og vertsnavnet for REST-endepunktet](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="a69ce-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="a69ce-116">Angi **[ID-en for Marketo-listen](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="a69ce-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="a69ce-117">Velg **Jeg godtar** for å bekrefte **datapersonvern og -samsvar**, og velg **Koble til** for å initialisere tilkoblingen til Marketo.</span><span class="sxs-lookup"><span data-stu-id="a69ce-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="a69ce-118">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="a69ce-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Skjermbilde for eksport av Marketo-tilkobling":::

1. <span data-ttu-id="a69ce-120">Velg **Neste** for å konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="a69ce-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a69ce-121">Konfigurere koblingen</span><span class="sxs-lookup"><span data-stu-id="a69ce-121">Configure the connector</span></span>

1. <span data-ttu-id="a69ce-122">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="a69ce-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="a69ce-123">Du kan eventuelt eksportere **Fornavn**, **Etternavn**, **Poststed**, **Delstat** og **Land/område** som tilleggsfelt for å opprette mer tilpassede e-postmeldinger.</span><span class="sxs-lookup"><span data-stu-id="a69ce-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="a69ce-124">Velg **Legg til attributt** for å tilordne disse feltene.</span><span class="sxs-lookup"><span data-stu-id="a69ce-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a69ce-125">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="a69ce-125">Select the segments you want to export.</span></span> <span data-ttu-id="a69ce-126">Du kan eksportere opptil 1 million kundeprofiler totalt til Marketo.</span><span class="sxs-lookup"><span data-stu-id="a69ce-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Velg felt og segmenter som skal eksporteres til Marketo":::

1. <span data-ttu-id="a69ce-128">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="a69ce-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a69ce-129">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="a69ce-129">Export the data</span></span>

<span data-ttu-id="a69ce-130">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a69ce-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a69ce-131">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a69ce-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a69ce-132">I Marketo kan du nå finne segmentene under [Marketo-lister](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a69ce-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a69ce-133">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="a69ce-133">Known limitations</span></span>

- <span data-ttu-id="a69ce-134">Opptil 1 million profiler per eksport til Marketo.</span><span class="sxs-lookup"><span data-stu-id="a69ce-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="a69ce-135">Eksport til Marketo er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="a69ce-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="a69ce-136">Eksport av segmenter med totalt 1 million profiler kan ta opptil tre timer.</span><span class="sxs-lookup"><span data-stu-id="a69ce-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="a69ce-137">Antallet profiler du kan eksportere til Marketo, er avhengig av og begrenset til kontrakten din med Marketo.</span><span class="sxs-lookup"><span data-stu-id="a69ce-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a69ce-138">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="a69ce-138">Data privacy and compliance</span></span>

<span data-ttu-id="a69ce-139">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Marketo, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="a69ce-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a69ce-140">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Marketo oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="a69ce-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a69ce-141">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a69ce-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a69ce-142">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="a69ce-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]