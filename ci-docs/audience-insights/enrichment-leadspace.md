---
title: Supplering av firmaprofiler med tredjeparts supplering fra Leadspace
description: Generell informasjon om tredjeparts supplering fra Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895925"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="706dc-103">Supplering av firmaprofiler med Leadspace (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="706dc-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="706dc-104">Leadspace er et datavitenskapsfirma som tilbyr en B2B-kundedataplattform.</span><span class="sxs-lookup"><span data-stu-id="706dc-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="706dc-105">Den gjør det mulig for kunder med enhetlige kundeprofiler for selskaper å berike dataene sine.</span><span class="sxs-lookup"><span data-stu-id="706dc-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="706dc-106">Suppleringer inkluderer flere attributter, for eksempel firmastørrelse, sted, bransje og mer.</span><span class="sxs-lookup"><span data-stu-id="706dc-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="706dc-107">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="706dc-107">Prerequisites</span></span>

<span data-ttu-id="706dc-108">Følgende forutsetninger må være oppfylt for at du skal kunne konfigurere Leadspace:</span><span class="sxs-lookup"><span data-stu-id="706dc-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="706dc-109">Du har en aktiv Leadspace-lisens.</span><span class="sxs-lookup"><span data-stu-id="706dc-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="706dc-110">Du har [enhetlige kundeprofiler](customer-profiles.md) for selskaper.</span><span class="sxs-lookup"><span data-stu-id="706dc-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="706dc-111">En Leadspace-tilkobling er allerede konfigurert av en administrator, eller du har [administrator](permissions.md#administrator)-tillatelser og den "permanente nøkkelen" (kalt **Leadspace-token**).</span><span class="sxs-lookup"><span data-stu-id="706dc-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="706dc-112">Kontakt [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direkte hvis du vil ha mer informasjon om produktet.</span><span class="sxs-lookup"><span data-stu-id="706dc-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="706dc-113">Konfigurere suppleringen</span><span class="sxs-lookup"><span data-stu-id="706dc-113">Configure the enrichment</span></span>

1. <span data-ttu-id="706dc-114">I Målgruppeinnsikt går du til **Data** > **Supplering**.</span><span class="sxs-lookup"><span data-stu-id="706dc-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="706dc-115">Velg **Suppler dataene** på Leadspace-flisen, og velg **Kom i gang**.</span><span class="sxs-lookup"><span data-stu-id="706dc-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skjermbilde av Leadspace-flisen.":::

1. <span data-ttu-id="706dc-117">Velg en [tilkobling](connections.md) fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="706dc-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="706dc-118">Kontakt en administrator hvis ingen tilkobling er tilgjengelig.</span><span class="sxs-lookup"><span data-stu-id="706dc-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="706dc-119">Hvis du er en administrator, kan du opprette en tilkobling ved å velge **Legg til tilkobling** og deretter **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="706dc-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="706dc-120">Velg **Koble til Leadspace** for å bekrefte tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="706dc-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="706dc-121">Velg **Neste**, og velg **kundedatasettet** du vil supplere med firmadata fra Leadspace.</span><span class="sxs-lookup"><span data-stu-id="706dc-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="706dc-122">Du kan velge **kundeenheten** for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="706dc-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. <span data-ttu-id="706dc-124">Velg **Neste** og definer hvilken type felt fra de enhetlige profilene som skal brukes til å lete etter samsvarende firmadata fra Leadspace.</span><span class="sxs-lookup"><span data-stu-id="706dc-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="706dc-125">Feltet **Navn på selskap** feltet er obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="706dc-125">The **Name of company** field is required.</span></span> <span data-ttu-id="706dc-126">For høyere nøyaktighet kan opptil to andre felter, **Selskapets nettsted** og **Selskapssted**, legges til.</span><span class="sxs-lookup"><span data-stu-id="706dc-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Tilordningsrute i Leadspace-felt.":::

1. <span data-ttu-id="706dc-128">Velg **Neste** for å fullføre felttilordningen.</span><span class="sxs-lookup"><span data-stu-id="706dc-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="706dc-129">Angi et navn for suppleringen, og velg **Lagre supplering** etter at du har sett gjennom valgene.</span><span class="sxs-lookup"><span data-stu-id="706dc-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="706dc-130">Konfigurere tilkoblingen for Leadspace</span><span class="sxs-lookup"><span data-stu-id="706dc-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="706dc-131">Du må være en administrator for å konfigurere tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="706dc-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="706dc-132">Velg **Legg til tilkobling** når du konfigurerer en supplering *eller* gå til **Administrasjon** > **Tilkoblinger** og velg **Konfigurer** i Leadspace-flisen.</span><span class="sxs-lookup"><span data-stu-id="706dc-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="706dc-133">Velg **Kom i gang**</span><span class="sxs-lookup"><span data-stu-id="706dc-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="706dc-134">Skriv inn et navn på tilkoblingen i **Visningsnavn**-boksen.</span><span class="sxs-lookup"><span data-stu-id="706dc-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="706dc-135">Angi et gyldig Leadspace-token.</span><span class="sxs-lookup"><span data-stu-id="706dc-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="706dc-136">Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**</span><span class="sxs-lookup"><span data-stu-id="706dc-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="706dc-137">Velg **Bekreft** for å validere konfigurasjonen.</span><span class="sxs-lookup"><span data-stu-id="706dc-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="706dc-138">Velg **Lagre** etter at verifiseringen er fullført.</span><span class="sxs-lookup"><span data-stu-id="706dc-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Konfigurasjonsside for Leadspace-tilkobling.":::

## <a name="enrichment-results"></a><span data-ttu-id="706dc-140">Resultater av supplering</span><span class="sxs-lookup"><span data-stu-id="706dc-140">Enrichment results</span></span>

<span data-ttu-id="706dc-141">Etter at du har oppdatert suppleringen, kan du gå gjennom de nylig supplerte firmadataene under [Mine suppleringer](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="706dc-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="706dc-142">Du kan finne tidspunktet for siste oppdatering og antall supplerte profiler.</span><span class="sxs-lookup"><span data-stu-id="706dc-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="706dc-143">Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.</span><span class="sxs-lookup"><span data-stu-id="706dc-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="706dc-144">Hvis du vil ha mer informasjon, kan du se [API-er for Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="706dc-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="706dc-145">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="706dc-145">Next steps</span></span>

<span data-ttu-id="706dc-146">Bygg på toppen av de supplerte kundedataene.</span><span class="sxs-lookup"><span data-stu-id="706dc-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="706dc-147">Opprett [segmenter](segments.md), [mål](measures.md) og til og med [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.</span><span class="sxs-lookup"><span data-stu-id="706dc-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="706dc-148">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="706dc-148">Data privacy and compliance</span></span>

<span data-ttu-id="706dc-149">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Leadspace, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="706dc-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="706dc-150">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Leadspace oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="706dc-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="706dc-151">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="706dc-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="706dc-152">Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="706dc-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
