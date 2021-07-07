---
title: Berikelse med tredjeparts supplering fra Experian
description: Generell informasjon om tredjeparts Experian-supplering.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309832"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="95da6-103">Supplere kundeprofiler med demografi fra Experian (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="95da6-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="95da6-104">Experian er en global leder innen kredittrapportering og markedsføringstjenester for forbruker og selskap.</span><span class="sxs-lookup"><span data-stu-id="95da6-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="95da6-105">Med Experian-datasuppleringstjenester kan du bygge en dypere forståelse av kundene ved å berike kundeprofilene med demografiske data som størrelsen på kunden, inntekter og annet.</span><span class="sxs-lookup"><span data-stu-id="95da6-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="95da6-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="95da6-106">Prerequisites</span></span>

<span data-ttu-id="95da6-107">Følgende forutsetninger må være oppfylt for at du skal kunne konfigurere Experian:</span><span class="sxs-lookup"><span data-stu-id="95da6-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="95da6-108">Du må ha et aktivt abonnement på Experian.</span><span class="sxs-lookup"><span data-stu-id="95da6-108">You have an active Experian subscription.</span></span> <span data-ttu-id="95da6-109">Hvis du vil ha et abonnement, [kontakter du Experian](https://www.experian.com/marketing-services/contact) direkte.</span><span class="sxs-lookup"><span data-stu-id="95da6-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="95da6-110">[Finn ut mer om Experian-datasupplering](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="95da6-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="95da6-111">En Experian-tilkobling er allerede konfigurert av en administrator, *eller* du har [administrator](permissions.md#administrator)-tillatelser.</span><span class="sxs-lookup"><span data-stu-id="95da6-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="95da6-112">Du må også ha bruker-ID, parts-ID og modellnummer for den SSH-aktiverte ST-kontoen (Secure Transport) som Experian har opprettet for deg.</span><span class="sxs-lookup"><span data-stu-id="95da6-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="95da6-113">Støttede land/områder</span><span class="sxs-lookup"><span data-stu-id="95da6-113">Supported countries/regions</span></span>

<span data-ttu-id="95da6-114">Vi støtter for øyeblikket bare supplering av kundeprofiler i USA.</span><span class="sxs-lookup"><span data-stu-id="95da6-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="95da6-115">Konfigurere suppleringen</span><span class="sxs-lookup"><span data-stu-id="95da6-115">Configure the enrichment</span></span>

1. <span data-ttu-id="95da6-116">Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.</span><span class="sxs-lookup"><span data-stu-id="95da6-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="95da6-117">Velg **Suppler dataene** på Experian-flisen.</span><span class="sxs-lookup"><span data-stu-id="95da6-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="95da6-118">![Experian flis](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="95da6-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="95da6-119">Velg en [tilkobling](connections.md) fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="95da6-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="95da6-120">Kontakt en administrator hvis ingen tilkobling er tilgjengelig.</span><span class="sxs-lookup"><span data-stu-id="95da6-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="95da6-121">Hvis du er en administrator, kan du opprette en tilkobling ved å velge **Legg til tilkobling** og velge Experian fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="95da6-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="95da6-122">Velg **Koble til Experian** for å bekrefte valget av tilkobling.</span><span class="sxs-lookup"><span data-stu-id="95da6-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="95da6-123">Velg **Neste**, og velg **Kundedatasettet** du vil supplere ned demografiske data fra Experian.</span><span class="sxs-lookup"><span data-stu-id="95da6-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="95da6-124">Du kan velge **kundeenheten** for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="95da6-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. <span data-ttu-id="95da6-126">Velg **Neste**, og definer hvilken type felt fra de enhetlige profilene som skal brukes til å se etter samsvarende demografiske data fra Experian.</span><span class="sxs-lookup"><span data-stu-id="95da6-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="95da6-127">Minst ett av feltene **Navn og adresse**, **Telefon** eller **E-post** er obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="95da6-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="95da6-128">Hvis du vil ha høyere nøyaktighet for treff, kan du legge til opptil to andre felt.</span><span class="sxs-lookup"><span data-stu-id="95da6-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="95da6-129">Dette valget påvirker tilordningsfeltene du har tilgang til i neste trinn.</span><span class="sxs-lookup"><span data-stu-id="95da6-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="95da6-130">Flere nøkkelidentifikatorattributter som sendes til Experian, gir sannsynligvis høyere samsvarsrate.</span><span class="sxs-lookup"><span data-stu-id="95da6-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="95da6-131">Velg **Neste** for å starte felttilordningen.</span><span class="sxs-lookup"><span data-stu-id="95da6-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="95da6-132">Definer hvilken felt fra de enhetlige profilene som skal brukes til å se etter samsvarende demografiske data fra Experian.</span><span class="sxs-lookup"><span data-stu-id="95da6-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="95da6-133">Obligatoriske felt er merket.</span><span class="sxs-lookup"><span data-stu-id="95da6-133">Required fields are marked.</span></span>

1. <span data-ttu-id="95da6-134">Angi et navn for suppleringen og et navn for utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="95da6-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="95da6-135">Velg **Lagre supplering** etter at du har sett gjennom valgene.</span><span class="sxs-lookup"><span data-stu-id="95da6-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="95da6-136">Konfigurere tilkoblingen for Experian</span><span class="sxs-lookup"><span data-stu-id="95da6-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="95da6-137">Du må være en administrator for å konfigurere tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="95da6-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="95da6-138">Velg **Legg til tilkobling** når du konfigurerer en supplering *eller* gå til **Administrator** > **Tilkoblinger**, og velg **Konfigurer** på Experian-flisen.</span><span class="sxs-lookup"><span data-stu-id="95da6-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="95da6-139">Velg **Komme i gang**.</span><span class="sxs-lookup"><span data-stu-id="95da6-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="95da6-140">Skriv inn et navn på tilkoblingen i **Visningsnavn**-boksen.</span><span class="sxs-lookup"><span data-stu-id="95da6-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="95da6-141">Angi gyldig bruker-ID, part-ID og modellnummer for Experian ST-kontoen.</span><span class="sxs-lookup"><span data-stu-id="95da6-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="95da6-142">Gå gjennom og gi ditt samtykke til **Datapersonvern og -samsvar** ved å velge **Jeg er enig**.</span><span class="sxs-lookup"><span data-stu-id="95da6-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="95da6-143">Velg **Bekreft** for å validere konfigurasjonen.</span><span class="sxs-lookup"><span data-stu-id="95da6-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="95da6-144">Velg **Lagre** etter at verifiseringen er fullført.</span><span class="sxs-lookup"><span data-stu-id="95da6-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian-tilkoblingskonfigurasjonsruten.":::

## <a name="enrichment-results"></a><span data-ttu-id="95da6-146">Resultater av supplering</span><span class="sxs-lookup"><span data-stu-id="95da6-146">Enrichment results</span></span>

<span data-ttu-id="95da6-147">Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="95da6-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="95da6-148">Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="95da6-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="95da6-149">Behandlingstiden avhenger av størrelsen på kundedataene og suppleringsprosessene som er konfigurert for forretningsforbindelsen din etter Experian.</span><span class="sxs-lookup"><span data-stu-id="95da6-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="95da6-150">Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**.</span><span class="sxs-lookup"><span data-stu-id="95da6-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="95da6-151">I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.</span><span class="sxs-lookup"><span data-stu-id="95da6-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="95da6-152">Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.</span><span class="sxs-lookup"><span data-stu-id="95da6-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="95da6-153">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="95da6-153">Next steps</span></span>

<span data-ttu-id="95da6-154">Bygg på toppen av de supplerte kundedataene.</span><span class="sxs-lookup"><span data-stu-id="95da6-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="95da6-155">Opprett [segmenter](segments.md) og [mål](measures.md), og [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.</span><span class="sxs-lookup"><span data-stu-id="95da6-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="95da6-156">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="95da6-156">Data privacy and compliance</span></span>

<span data-ttu-id="95da6-157">Når du gjør det mulig for Dynamics 365 Customer Insights å overføre data til Experian, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data som personlige data.</span><span class="sxs-lookup"><span data-stu-id="95da6-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="95da6-158">Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Experian oppfyller personvern- eller sikkerhetsforpliktelser du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="95da6-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="95da6-159">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="95da6-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="95da6-160">Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="95da6-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
