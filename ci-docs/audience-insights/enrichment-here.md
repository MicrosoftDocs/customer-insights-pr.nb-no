---
title: Berikelse med tredjeparts supplering fra HERE Technologies
description: Generell informasjon om tredjeparts supplering fra HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305306"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="8cb4c-103">Supplering av kundeprofiler med HERE Technologies (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="8cb4c-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="8cb4c-104">HERE Technologies er et lokasjonsplattformfirma som tilbyr lokasjonssentrerte data og tjenester.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="8cb4c-105">Ved hjelp av tjenester for datasupplering fra HERE Technologies kan du bygge et mer nøyaktig stedsforståelse av kundene med adressenormalisering, bredde- og lengdegradsuttrekking og så videre.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8cb4c-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="8cb4c-106">Prerequisites</span></span>

<span data-ttu-id="8cb4c-107">For å konfigure HERE Technologies-suppleringer må følgende forhåndskrav være oppfylt:</span><span class="sxs-lookup"><span data-stu-id="8cb4c-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8cb4c-108">Du har et aktivt abonnement på HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="8cb4c-109">Hvis du vil ha et abonnement, kan du [registrere deg her](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkte.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="8cb4c-110">Finn ut mer om lokasjonssupplement fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="8cb4c-111">En HERE [-tilkobling](connections.md) er tilgjengelig, *eller* du har [administrator](permissions.md#administrator)- tillatelser og API-nøkkelen for HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="8cb4c-112">Konfigurere suppleringen</span><span class="sxs-lookup"><span data-stu-id="8cb4c-112">Configure the enrichment</span></span>

1. <span data-ttu-id="8cb4c-113">Gå til **Data** > **Supplering**.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="8cb4c-114">Velg **Suppler dataene** på HERE Technologies-flisen, og velg **Kom i gang**.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8cb4c-115">![HERE Technologies-flis](media/HERE-tile.png "HERE Technologies-flis")</span><span class="sxs-lookup"><span data-stu-id="8cb4c-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="8cb4c-116">Velg en [tilkobling](connections.md) fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="8cb4c-117">Kontakt en administrator hvis ingen tilkobling er tilgjengelig.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="8cb4c-118">Hvis du er en administrator, kan du opprette en tilkobling ved å velge **Legg til tilkobling**.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="8cb4c-119">Velg **HERE Technologies** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="8cb4c-120">Velg **Koble til HERE Technologies** for å bekrefte valget.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="8cb4c-121">Velg **Neste**, og velg **kundedatasettet** du vil supplere med stedsdata fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="8cb4c-122">Du kan velge **kundeenheten** for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. <span data-ttu-id="8cb4c-124">Velg om du vil tilordne felter til den primære og/eller sekundære adressen.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="8cb4c-125">Du kan angi en felttilordning for begge adressene og supplere profilene for begge adressene separat.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="8cb4c-126">Hvis det for eksempel finnes en hjemme- og en forretningsadresse.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="8cb4c-127">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-127">Select **Next**.</span></span>

1. <span data-ttu-id="8cb4c-128">Definer hvilke felt fra de enhetlige profilene som skal brukes til å søke etter samsvarende stedsdata fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="8cb4c-129">Feltene **Gate/vei 1** og **Postnummer** kreves for den valgte primære og/eller sekundære adressen.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="8cb4c-130">Flere felt kan legges til for å oppnå høyere nøyaktighet.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8cb4c-131">![Konfigurasjonsside for HERE Technologies-supplering](media/enrichment-HERE-configuration.png "Konfigurasjonsside for HERE Technologies-supplering")</span><span class="sxs-lookup"><span data-stu-id="8cb4c-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="8cb4c-132">Velg **Neste** for å fullføre felttilordningen.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="8cb4c-133">Angi et navn for suppleringen.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="8cb4c-134">Velg **Lagre supplering** etter at du har sett gjennom valgene.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="8cb4c-135">Konfigurere tilkoblingen for HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="8cb4c-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="8cb4c-136">Du må være en administrator for å konfigurere tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="8cb4c-137">Velg **Legg til tilkobling** når du konfigurerer en supplering *eller* gå til **Administrasjon** > **Tilkoblinger** og velg **Konfigurer** i HERE technologies-filen.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="8cb4c-138">Skriv inn et navn på tilkoblingen i **Visningsnavn**-boksen.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="8cb4c-139">Angi en gyldig API-nøkkel for HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="8cb4c-140">Gå gjennom og gi ditt samtykke til **Datapersonvern og -samsvar** ved å velge **Jeg er enig**.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="8cb4c-141">Velg **Bekreft** for å validere konfigurasjonen.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="8cb4c-142">Velg **Lagre** etter at verifiseringen er fullført.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8cb4c-143">![Konfigurasjonsside for HERE technologies-tilkobling](media/enrichment-HERE-connection.png "Konfigurasjonsside for HERE technologies-tilkobling")</span><span class="sxs-lookup"><span data-stu-id="8cb4c-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="8cb4c-144">Resultater av supplering</span><span class="sxs-lookup"><span data-stu-id="8cb4c-144">Enrichment results</span></span>

<span data-ttu-id="8cb4c-145">Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8cb4c-146">Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8cb4c-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8cb4c-147">Behandlingstiden avhenger av størrelsen på kundedataene og API-responstidene fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="8cb4c-148">Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8cb4c-149">I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8cb4c-150">Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8cb4c-151">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="8cb4c-151">Next steps</span></span>

<span data-ttu-id="8cb4c-152">Bygg på toppen av de supplerte kundedataene.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8cb4c-153">Opprett [segmenter](segments.md) og [mål](measures.md), og [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8cb4c-154">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="8cb4c-154">Data privacy and compliance</span></span>

<span data-ttu-id="8cb4c-155">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til HERE Technologies, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8cb4c-156">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at HERE Technologies oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8cb4c-157">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8cb4c-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8cb4c-158">Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="8cb4c-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
