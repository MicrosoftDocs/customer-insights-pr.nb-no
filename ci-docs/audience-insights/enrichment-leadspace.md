---
title: Supplering av firmaprofiler med tredjeparts supplering fra Leadspace
description: Generell informasjon om tredjeparts supplering fra Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597661"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="5a548-103">Supplering av firmaprofiler med Leadspace (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="5a548-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="5a548-104">Leadspace er et datavitenskapsfirma som tilbyr en B2B-kundedataplattform.</span><span class="sxs-lookup"><span data-stu-id="5a548-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="5a548-105">Den gjør det mulig for kunder med enhetlige kundeprofiler for selskaper å berike dataene sine.</span><span class="sxs-lookup"><span data-stu-id="5a548-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="5a548-106">Suppleringer omfatter ekstra attributter, for eksempel selskapsstørrelse, sted, bransje og mer.</span><span class="sxs-lookup"><span data-stu-id="5a548-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a548-107">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="5a548-107">Prerequisites</span></span>

<span data-ttu-id="5a548-108">Følgende forutsetninger må være oppfylt for at du skal kunne konfigurere Leadspace:</span><span class="sxs-lookup"><span data-stu-id="5a548-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5a548-109">Du har en aktiv Leadspace-lisens og en "permanent nøkkel" (henvist til som **Leadspace-token**).</span><span class="sxs-lookup"><span data-stu-id="5a548-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="5a548-110">Kontakt [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direkte for detaljer om produktet.</span><span class="sxs-lookup"><span data-stu-id="5a548-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="5a548-111">Du har [administratortillatelser](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="5a548-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="5a548-112">Du har [enhetlige kundeprofiler](customer-profiles.md) for selskaper.</span><span class="sxs-lookup"><span data-stu-id="5a548-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="5a548-113">Konfigurasjon</span><span class="sxs-lookup"><span data-stu-id="5a548-113">Configuration</span></span>

1. <span data-ttu-id="5a548-114">I Målgruppeinnsikt går du til **Data** > **Supplering**.</span><span class="sxs-lookup"><span data-stu-id="5a548-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="5a548-115">Velg **Suppler dataene** på Leadspace-flisen.</span><span class="sxs-lookup"><span data-stu-id="5a548-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skjermbilde av Leadspace-flisen.":::

1. <span data-ttu-id="5a548-117">Velg **Kom i gang**, og angi deretter et aktivt **Leadspace-token** (permanent nøkkel).</span><span class="sxs-lookup"><span data-stu-id="5a548-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="5a548-118">Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**.</span><span class="sxs-lookup"><span data-stu-id="5a548-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="5a548-119">Bekreft begge inndataene ved å velge **Koble til Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="5a548-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="5a548-120">Velg **Tilordne data**, og velg datasettet du vil supplere med selskapsdata fra Leadspace.</span><span class="sxs-lookup"><span data-stu-id="5a548-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="5a548-121">Du kan velge *kundeenheten* for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="5a548-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Velg mellom kundeprofil og segmentsupplering.":::

1. <span data-ttu-id="5a548-123">Klikk på **Neste**, og definer hvilke felt fra de enhetlige profilene som skal brukes til å søke etter samsvarende firmadata fra Leadspace.</span><span class="sxs-lookup"><span data-stu-id="5a548-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="5a548-124">Feltet **Navn på selskap** feltet er obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="5a548-124">The **Name of company** field is required.</span></span> <span data-ttu-id="5a548-125">For høyere nøyaktighet kan opptil to andre felter, **Selskapets nettsted** og **Selskapssted**, legges til.</span><span class="sxs-lookup"><span data-stu-id="5a548-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Tilordningsrute i Leadspace-felt.":::
   
1. <span data-ttu-id="5a548-127">Velg **Bruk** for å fullføre felttilordningen.</span><span class="sxs-lookup"><span data-stu-id="5a548-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="5a548-128">Velg **Kjør** for å supplere firmaprofilene.</span><span class="sxs-lookup"><span data-stu-id="5a548-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="5a548-129">Hvor lang tid en supplering tar, avhenger av antallet enhetlige kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="5a548-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="5a548-130">Resultater av supplering</span><span class="sxs-lookup"><span data-stu-id="5a548-130">Enrichment results</span></span>

<span data-ttu-id="5a548-131">Etter at du har oppdatert suppleringen, kan du gå gjennom de nylig supplerte firmadataene under [Mine suppleringer](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="5a548-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="5a548-132">Du kan finne tidspunktet for siste oppdatering og antall supplerte profiler.</span><span class="sxs-lookup"><span data-stu-id="5a548-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="5a548-133">Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.</span><span class="sxs-lookup"><span data-stu-id="5a548-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="5a548-134">Hvis du vil ha mer informasjon, kan du se [API-er for Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="5a548-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5a548-135">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="5a548-135">Next steps</span></span>

<span data-ttu-id="5a548-136">Bygg på toppen av de supplerte kundedataene.</span><span class="sxs-lookup"><span data-stu-id="5a548-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="5a548-137">Opprett [segmenter](segments.md), [mål](measures.md) og til og med [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.</span><span class="sxs-lookup"><span data-stu-id="5a548-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5a548-138">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="5a548-138">Data privacy and compliance</span></span>

<span data-ttu-id="5a548-139">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Leadspace, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="5a548-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5a548-140">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Leadspace oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="5a548-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5a548-141">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5a548-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5a548-142">Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="5a548-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]