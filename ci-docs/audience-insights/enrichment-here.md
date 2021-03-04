---
title: Berike med tredjeparts supplering fra HERE Technologies
description: Generell informasjon om tredjeparts supplering fra HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269526"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="dbcd6-103">Supplering av kundeprofiler med HERE Technologies (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="dbcd6-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="dbcd6-104">HERE Technologies er et lokasjonsplattformfirma som tilbyr lokasjonssentrerte data og tjenester.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="dbcd6-105">Ved hjelp av tjenester for datasupplering fra HERE Technologies kan du bygge et mer nøyaktig stedsforståelse av kundene med adressenormalisering, bredde- og lengdegradsuttrekking og så videre.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dbcd6-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="dbcd6-106">Prerequisites</span></span>

<span data-ttu-id="dbcd6-107">For å konfigure HERE Technologies-suppleringer må følgende forhåndskrav være oppfylt:</span><span class="sxs-lookup"><span data-stu-id="dbcd6-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dbcd6-108">Du har et aktivt abonnement på HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="dbcd6-109">Hvis du vil ha et abonnement, kan du [registrere deg her](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkte.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="dbcd6-110">Finn ut mer om lokasjonssupplement fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="dbcd6-111">Du har API-nøkkelen for HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="dbcd6-112">Du har [administratortillatelser](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="dbcd6-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="dbcd6-113">Konfigurasjon</span><span class="sxs-lookup"><span data-stu-id="dbcd6-113">Configuration</span></span>

1. <span data-ttu-id="dbcd6-114">Gå til **Data** > **Supplering**.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="dbcd6-115">Velg **Suppler dataene** på HERE Technologies-flisen.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dbcd6-116">![HERE Technologies-flis](media/HERE-tile.png "HERE Technologies-flis")</span><span class="sxs-lookup"><span data-stu-id="dbcd6-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="dbcd6-117">Angi en aktiv **API-nøkkel for HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="dbcd6-118">Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="dbcd6-119">Bekreft begge inndataene ved å velge **Koble til HERE**.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="dbcd6-120">Velg **Legg til data**, og velg **kundedatasettet** du vil supplere med plasseringsdata fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="dbcd6-121">Du kan velge **kundeenheten** for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. <span data-ttu-id="dbcd6-123">Velg om du vil tilordne felter til den primære og/eller sekundære adressen.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="dbcd6-124">Du kan angi en felttilordning for begge adressene (for eksempel en privatadresse og en firmaadresse), og du kan supplere profilene hver for seg.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="dbcd6-125">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-125">Select **Next**.</span></span>

1. <span data-ttu-id="dbcd6-126">Definer hvilke felt fra de enhetlige profilene som skal brukes til å søke etter samsvarende stedsdata fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="dbcd6-127">Feltene **Gate/vei 1** og **Postnummer** kreves for den valgte primære og/eller sekundære adressen.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="dbcd6-128">Flere felt kan legges til for å oppnå høyere nøyaktighet.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dbcd6-129">![Konfigurasjonsside for HERE Technologies-supplering](media/enrichment-HERE-configuration.png "Konfigurasjonsside for HERE Technologies-supplering")</span><span class="sxs-lookup"><span data-stu-id="dbcd6-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="dbcd6-130">Velg **Bruk** for å fullføre felttilordningen.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="dbcd6-131">Resultater av supplering</span><span class="sxs-lookup"><span data-stu-id="dbcd6-131">Enrichment results</span></span>

<span data-ttu-id="dbcd6-132">Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="dbcd6-133">Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dbcd6-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dbcd6-134">Behandlingstiden avhenger av størrelsen på kundedataene og API-responstidene fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="dbcd6-135">Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="dbcd6-136">I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dbcd6-137">Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dbcd6-138">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="dbcd6-138">Next steps</span></span>

<span data-ttu-id="dbcd6-139">Bygg på toppen av de supplerte kundedataene.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dbcd6-140">Opprett [segmenter](segments.md), [mål](measures.md) og til og med [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dbcd6-141">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="dbcd6-141">Data privacy and compliance</span></span>

<span data-ttu-id="dbcd6-142">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til HERE Technologies, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dbcd6-143">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at HERE Technologies oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dbcd6-144">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dbcd6-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dbcd6-145">Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="dbcd6-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]