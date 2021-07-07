---
title: Supplering for adresseforbedring
description: Suppler og normaliser adresseinformasjonen for kundeprofiler med Microsofts modeller.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305444"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="6c955-103">Supplering av kundeprofiler med forbedrede adresser</span><span class="sxs-lookup"><span data-stu-id="6c955-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="6c955-104">Adresser i dataene kan være ustrukturerte, ufullstendige eller feil.</span><span class="sxs-lookup"><span data-stu-id="6c955-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="6c955-105">Bruk Microsofts modeller til å normalisere og forbedre adressene i [Common Data Model-formatet](/common-data-model/schema/core/applicationcommon/address) for bedre nøyaktighet og innsikt.</span><span class="sxs-lookup"><span data-stu-id="6c955-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="6c955-106">Slik forbedrer vi adressene</span><span class="sxs-lookup"><span data-stu-id="6c955-106">How we enhance addresses</span></span>

<span data-ttu-id="6c955-107">Modellen vår går gjennom en totrinnsprosess for å forbedre en adresse.</span><span class="sxs-lookup"><span data-stu-id="6c955-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="6c955-108">Først analyseres adressen for å identifisere komponentene og plassere dem i et strukturert format.</span><span class="sxs-lookup"><span data-stu-id="6c955-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="6c955-109">Deretter bruker vi AI til å korrigere, fullføre og standardisere verdiene i adressen.</span><span class="sxs-lookup"><span data-stu-id="6c955-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="6c955-110">Eksempel</span><span class="sxs-lookup"><span data-stu-id="6c955-110">Example</span></span>

<span data-ttu-id="6c955-111">Adresseinformasjon kan være i et format som ikke er standard, og inneholder stavefeil.</span><span class="sxs-lookup"><span data-stu-id="6c955-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="6c955-112">Modellen kan løse disse problemene og opprette ensartede adresser i enhetlige kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="6c955-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="6c955-113">Begrensninger</span><span class="sxs-lookup"><span data-stu-id="6c955-113">Limitations</span></span>

<span data-ttu-id="6c955-114">Forbedrede adresser fungerer bare med verdiene som allerede finnes i de innlagte adressedataene.</span><span class="sxs-lookup"><span data-stu-id="6c955-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="6c955-115">Modellen vil ikke:</span><span class="sxs-lookup"><span data-stu-id="6c955-115">The model doesn't:</span></span> 

1. <span data-ttu-id="6c955-116">kontrollere om adressen er en gyldig adresse</span><span class="sxs-lookup"><span data-stu-id="6c955-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="6c955-117">kontrollere om noen av verdiene, for eksempel postnumre eller gatenavn, er gyldige</span><span class="sxs-lookup"><span data-stu-id="6c955-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="6c955-118">endre verdier den ikke gjenkjenner</span><span class="sxs-lookup"><span data-stu-id="6c955-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="6c955-119">Modellen bruker maskinlæringsbaserte teknikker for å forbedre adressene.</span><span class="sxs-lookup"><span data-stu-id="6c955-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="6c955-120">Selv om vi bruker en terskel for høy konfidens for når modellen endrer en inndataverdi, på samme måte som med alle maskinlæringsbaserte modeller, er ikke 100 prosent nøyaktighet garantert.</span><span class="sxs-lookup"><span data-stu-id="6c955-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="6c955-121">Støttede land eller områder</span><span class="sxs-lookup"><span data-stu-id="6c955-121">Supported countries or regions</span></span>

<span data-ttu-id="6c955-122">Vi støtter for øyeblikket supplering av adresser i disse landene eller områdene:</span><span class="sxs-lookup"><span data-stu-id="6c955-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="6c955-123">Australia</span><span class="sxs-lookup"><span data-stu-id="6c955-123">Australia</span></span>
- <span data-ttu-id="6c955-124">Canada</span><span class="sxs-lookup"><span data-stu-id="6c955-124">Canada</span></span>
- <span data-ttu-id="6c955-125">Storbritannia</span><span class="sxs-lookup"><span data-stu-id="6c955-125">United Kingdom</span></span>
- <span data-ttu-id="6c955-126">USA</span><span class="sxs-lookup"><span data-stu-id="6c955-126">United States</span></span>

<span data-ttu-id="6c955-127">Adresser må inneholde en land-/områdeverdi.</span><span class="sxs-lookup"><span data-stu-id="6c955-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="6c955-128">Vi behandler ikke adresser for land eller områder som ikke støttes, og adresser som ikke har angitt land eller område.</span><span class="sxs-lookup"><span data-stu-id="6c955-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="6c955-129">Konfigurere suppleringen</span><span class="sxs-lookup"><span data-stu-id="6c955-129">Configure the enrichment</span></span>

1. <span data-ttu-id="6c955-130">Gå til **Data** > **Supplering**.</span><span class="sxs-lookup"><span data-stu-id="6c955-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="6c955-131">Velg **Suppler dataene mine** på flisen **Forbedrede adresser**.</span><span class="sxs-lookup"><span data-stu-id="6c955-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Skjermbilde av flisen Forbedrede adresser.":::

1. <span data-ttu-id="6c955-133">Velg **kundedatasettet**, og velg enheten som inneholder adressene du vil supplere.</span><span class="sxs-lookup"><span data-stu-id="6c955-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="6c955-134">Du kan velge *kundeenheten* for å supplere adressene i alle kundeprofilene, eller velge en segmentenhet for å supplere adresser bare i kundeprofiler i det segmentet.</span><span class="sxs-lookup"><span data-stu-id="6c955-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="6c955-135">Velg hvordan adresser formateres i datasettet.</span><span class="sxs-lookup"><span data-stu-id="6c955-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="6c955-136">Velg **Adresse for enkeltattributt** hvis adressene i dataene bruker ett enkelt felt.</span><span class="sxs-lookup"><span data-stu-id="6c955-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="6c955-137">Velg **Adresse for flere attributter** hvis adressene i dataene bruker mer enn ett datafelt.</span><span class="sxs-lookup"><span data-stu-id="6c955-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6c955-138">Land/område er obligatorisk både i adresser med enkeltattributter og flere attributter.</span><span class="sxs-lookup"><span data-stu-id="6c955-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="6c955-139">Adresser som ikke inneholder gyldige eller støttede land-/områdeverdier, blir ikke supplert.</span><span class="sxs-lookup"><span data-stu-id="6c955-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="6c955-140">Tilordne adressefeltene fra enheten for enhetlig kunde.</span><span class="sxs-lookup"><span data-stu-id="6c955-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Forbedret adresse-felttilordningsside.":::

1. <span data-ttu-id="6c955-142">Velg **Neste** for å fullføre felttilordningen.</span><span class="sxs-lookup"><span data-stu-id="6c955-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="6c955-143">Angi et navn for suppleringen og utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="6c955-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="6c955-144">Velg **Lagre supplering** etter at du har sett gjennom valgene.</span><span class="sxs-lookup"><span data-stu-id="6c955-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="6c955-145">Resultater av supplering</span><span class="sxs-lookup"><span data-stu-id="6c955-145">Enrichment results</span></span>

<span data-ttu-id="6c955-146">Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="6c955-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="6c955-147">Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6c955-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6c955-148">Behandlingstiden avhenger av størrelsen på kundedataene.</span><span class="sxs-lookup"><span data-stu-id="6c955-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="6c955-149">Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**.</span><span class="sxs-lookup"><span data-stu-id="6c955-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="6c955-150">I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.</span><span class="sxs-lookup"><span data-stu-id="6c955-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="6c955-151">Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.</span><span class="sxs-lookup"><span data-stu-id="6c955-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c955-152">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="6c955-152">Next steps</span></span>

<span data-ttu-id="6c955-153">Bygg på toppen av de supplerte kundedataene.</span><span class="sxs-lookup"><span data-stu-id="6c955-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="6c955-154">Opprett [segmenter](segments.md) og [mål](measures.md), og [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.</span><span class="sxs-lookup"><span data-stu-id="6c955-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
