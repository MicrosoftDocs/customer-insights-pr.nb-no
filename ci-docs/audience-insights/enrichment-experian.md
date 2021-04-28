---
title: Berike med tredjeparts supplering fra Experian
description: Generell informasjon om tredjeparts supplering fra Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896385"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="29a30-103">Supplere kundeprofiler med demografidata fra Experian (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="29a30-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="29a30-104">Experian er en global leder innen forbruker- og forretningskredittrapportering og markedsføringstjenester.</span><span class="sxs-lookup"><span data-stu-id="29a30-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="29a30-105">Ved hjelp Experians datasuppleringstjenester kan du bygge opp en dypere forståelse av kundene ved å supplere kundeprofilene med demografiske data, for eksempel husholdningsstørrelse, inntekt og så videre.</span><span class="sxs-lookup"><span data-stu-id="29a30-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="29a30-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="29a30-106">Prerequisites</span></span>

<span data-ttu-id="29a30-107">For å konfigurere Experian må følgende forutsetninger være oppfylt:</span><span class="sxs-lookup"><span data-stu-id="29a30-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="29a30-108">Du har et aktivt Experian-abonnement.</span><span class="sxs-lookup"><span data-stu-id="29a30-108">You have an active Experian subscription.</span></span> <span data-ttu-id="29a30-109">Hvis du vil ha et abonnement, [kontakter du Experian](https://www.experian.com/marketing-services/contact) direkte.</span><span class="sxs-lookup"><span data-stu-id="29a30-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="29a30-110">[Finn ut mer om Experian-datasupplering](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="29a30-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="29a30-111">En Experian-tilkobling er allerede konfigurert av en *administrator*, eller du har [administrator](permissions.md#administrator)-tillatelser.</span><span class="sxs-lookup"><span data-stu-id="29a30-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="29a30-112">Du må også ha bruker-ID-en, parts-ID-en og modellnummeret for den SSH-aktiverte ST-kontoen (Secure Transport) som Experian opprettet for deg.</span><span class="sxs-lookup"><span data-stu-id="29a30-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="29a30-113">Konfigurere suppleringen</span><span class="sxs-lookup"><span data-stu-id="29a30-113">Configure the enrichment</span></span>

1. <span data-ttu-id="29a30-114">Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.</span><span class="sxs-lookup"><span data-stu-id="29a30-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="29a30-115">Velg **Suppler dataene** på Experian-flisen.</span><span class="sxs-lookup"><span data-stu-id="29a30-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="29a30-116">![Experian-flis](media/experian-tile.png "Experian-flis")</span><span class="sxs-lookup"><span data-stu-id="29a30-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="29a30-117">Velg en [tilkobling](connections.md) fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="29a30-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="29a30-118">Kontakt en administrator hvis ingen tilkobling er tilgjengelig.</span><span class="sxs-lookup"><span data-stu-id="29a30-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="29a30-119">Hvis du er en administrator, kan du opprette en tilkobling ved å velge **Legg til tilkobling** og velge Experian fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="29a30-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="29a30-120">Velg **Koble til Experian** for å bekrefte valget av tilkobling.</span><span class="sxs-lookup"><span data-stu-id="29a30-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="29a30-121">Velg **Neste**, og velg **kundedatasettet** du vil supplere med demografiske data fra Experian.</span><span class="sxs-lookup"><span data-stu-id="29a30-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="29a30-122">Du kan velge **kundeenheten** for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="29a30-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. <span data-ttu-id="29a30-124">Velg **Neste** og definer hvilken type felt fra de enhetlige profilene som skal brukes til å lete etter samsvarende demografiske data fra Experian.</span><span class="sxs-lookup"><span data-stu-id="29a30-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="29a30-125">Minst ett av feltene **Navn og adresse**, **Telefon** eller **E-post** er obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="29a30-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="29a30-126">Hvis du vil ha høyere nøyaktighet for treff, kan du legge til opptil to andre felt.</span><span class="sxs-lookup"><span data-stu-id="29a30-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="29a30-127">Dette valget påvirker tilordningsfeltene du har tilgang til i neste trinn.</span><span class="sxs-lookup"><span data-stu-id="29a30-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="29a30-128">Flere nøkkel-ID-attributter som sendes til Experian, vil sannsynligvis gi en høyere samsvarsrate.</span><span class="sxs-lookup"><span data-stu-id="29a30-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="29a30-129">Velg **Neste** for å starte felttilordningen.</span><span class="sxs-lookup"><span data-stu-id="29a30-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="29a30-130">Definer hvilke felt fra de enhetlige profilene som skal brukes til å lete etter samsvarende demografiske data fra Experian.</span><span class="sxs-lookup"><span data-stu-id="29a30-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="29a30-131">Obligatoriske felt er merket.</span><span class="sxs-lookup"><span data-stu-id="29a30-131">Required fields are marked.</span></span>

1. <span data-ttu-id="29a30-132">Angi et navn for suppleringen og et navn for utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="29a30-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="29a30-133">Velg **Lagre supplering** etter at du har sett gjennom valgene.</span><span class="sxs-lookup"><span data-stu-id="29a30-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="29a30-134">Konfigurere tilkoblingen for Experian</span><span class="sxs-lookup"><span data-stu-id="29a30-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="29a30-135">Du må være en administrator for å konfigurere tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="29a30-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="29a30-136">Velg **Legg til tilkobling** når du konfigurerer en supplering *eller* gå til **Administrasjon** > **Tilkoblinger** og velg **Konfigurer** i Experian-filen.</span><span class="sxs-lookup"><span data-stu-id="29a30-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="29a30-137">Velg **Komme i gang**.</span><span class="sxs-lookup"><span data-stu-id="29a30-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="29a30-138">Skriv inn et navn på tilkoblingen i **Visningsnavn**-boksen.</span><span class="sxs-lookup"><span data-stu-id="29a30-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="29a30-139">Angi gyldig bruker-ID, parts-ID og modellnummer for Secure Transport-kontoen for Experian.</span><span class="sxs-lookup"><span data-stu-id="29a30-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="29a30-140">Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**</span><span class="sxs-lookup"><span data-stu-id="29a30-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="29a30-141">Velg **Bekreft** for å validere konfigurasjonen.</span><span class="sxs-lookup"><span data-stu-id="29a30-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="29a30-142">Velg **Lagre** etter at verifiseringen er fullført.</span><span class="sxs-lookup"><span data-stu-id="29a30-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Rute for konfigurasjon av Experian-tilkobling.":::

## <a name="enrichment-results"></a><span data-ttu-id="29a30-144">Resultater av supplering</span><span class="sxs-lookup"><span data-stu-id="29a30-144">Enrichment results</span></span>

<span data-ttu-id="29a30-145">Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="29a30-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="29a30-146">Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="29a30-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="29a30-147">Behandlingstiden avhenger av størrelsen på kundedataene og suppleringsprosessene som er satt opp for kontoen din av Experian.</span><span class="sxs-lookup"><span data-stu-id="29a30-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="29a30-148">Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**.</span><span class="sxs-lookup"><span data-stu-id="29a30-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="29a30-149">I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.</span><span class="sxs-lookup"><span data-stu-id="29a30-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="29a30-150">Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.</span><span class="sxs-lookup"><span data-stu-id="29a30-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="29a30-151">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="29a30-151">Next steps</span></span>

<span data-ttu-id="29a30-152">Bygg på toppen av de supplerte kundedataene.</span><span class="sxs-lookup"><span data-stu-id="29a30-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="29a30-153">Opprett [segmenter](segments.md), [mål](measures.md) og til og med [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.</span><span class="sxs-lookup"><span data-stu-id="29a30-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="29a30-154">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="29a30-154">Data privacy and compliance</span></span>

<span data-ttu-id="29a30-155">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Experian, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="29a30-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="29a30-156">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Experian oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="29a30-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="29a30-157">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="29a30-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="29a30-158">Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="29a30-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
