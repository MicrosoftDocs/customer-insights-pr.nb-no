---
title: Berike med tredjeparts supplering fra Experian
description: Generell informasjon om tredjeparts supplering fra Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668824"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="80da5-103">Supplere kundeprofiler med demografidata fra Experian (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="80da5-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="80da5-104">Experian er en global leder innen forbruker- og forretningskredittrapportering og markedsføringstjenester.</span><span class="sxs-lookup"><span data-stu-id="80da5-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="80da5-105">Ved hjelp Experians datasuppleringstjenester kan du bygge opp en dypere forståelse av kundene ved å supplere kundeprofilene med demografiske data, for eksempel husholdningsstørrelse, inntekt og så videre.</span><span class="sxs-lookup"><span data-stu-id="80da5-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80da5-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="80da5-106">Prerequisites</span></span>

<span data-ttu-id="80da5-107">For å konfigurere Experian må følgende forutsetninger være oppfylt:</span><span class="sxs-lookup"><span data-stu-id="80da5-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="80da5-108">Du har et aktivt Experian-abonnement.</span><span class="sxs-lookup"><span data-stu-id="80da5-108">You have an active Experian subscription.</span></span> <span data-ttu-id="80da5-109">Hvis du vil ha et abonnement, [kontakter du Experian](https://www.experian.com/marketing-services/contact) direkte.</span><span class="sxs-lookup"><span data-stu-id="80da5-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="80da5-110">[Finn ut mer om Experian-datasupplering](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="80da5-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="80da5-111">Du har bruker-ID, part-ID og modellnummer for SSH-aktivert ST-konto (Secure Transport) som Experian opprettet for deg.</span><span class="sxs-lookup"><span data-stu-id="80da5-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="80da5-112">Du har [administratortillatelser](permissions.md#administrator) tillatelser i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="80da5-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="80da5-113">Konfigurasjon</span><span class="sxs-lookup"><span data-stu-id="80da5-113">Configuration</span></span>

1. <span data-ttu-id="80da5-114">Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.</span><span class="sxs-lookup"><span data-stu-id="80da5-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="80da5-115">Velg **Suppler dataene** på Experian-flisen.</span><span class="sxs-lookup"><span data-stu-id="80da5-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80da5-116">![Experian-flis](media/experian-tile.png "Experian-flis")</span><span class="sxs-lookup"><span data-stu-id="80da5-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="80da5-117">Velg **Start**, og angi bruker-ID, part-ID og modellnummer for Experian Secure Transport-kontoen.</span><span class="sxs-lookup"><span data-stu-id="80da5-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="80da5-118">Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**.</span><span class="sxs-lookup"><span data-stu-id="80da5-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="80da5-119">Bekreft alle inndata ved å velge **Bruk**.</span><span class="sxs-lookup"><span data-stu-id="80da5-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="80da5-120">Tilordne feltene</span><span class="sxs-lookup"><span data-stu-id="80da5-120">Map your fields</span></span>

1. <span data-ttu-id="80da5-121">Velg **Legg til data**, og velg nøkkelidentifikatorer fra **Navn og adresse**, **E-post** eller **Telefon** for å sende til Experian for identitetsløsning.</span><span class="sxs-lookup"><span data-stu-id="80da5-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="80da5-122">Flere nøkkel-ID-attributter som sendes til Experian, vil sannsynligvis gi en høyere samsvarsrate.</span><span class="sxs-lookup"><span data-stu-id="80da5-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="80da5-123">Velg **Neste**, og tilordne de tilsvarende attributtene fra den enhetlige kundeenheten for de valgte nøkkel-ID-feltene.</span><span class="sxs-lookup"><span data-stu-id="80da5-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="80da5-124">Velg **Legg til attributt** for å tilordne eventuelle tilleggsattributter du ønsker å sende til Experian.</span><span class="sxs-lookup"><span data-stu-id="80da5-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="80da5-125">Velg **Lagre** for å fullføre felttilordningen.</span><span class="sxs-lookup"><span data-stu-id="80da5-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80da5-126">![Experian-felttilordning](media/experian-field-mapping.png "Experian-felttilordning")</span><span class="sxs-lookup"><span data-stu-id="80da5-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="80da5-127">Resultater av supplering</span><span class="sxs-lookup"><span data-stu-id="80da5-127">Enrichment results</span></span>

<span data-ttu-id="80da5-128">Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="80da5-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="80da5-129">Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="80da5-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="80da5-130">Behandlingstiden avhenger av størrelsen på kundedataene og suppleringsprosessene som er satt opp for kontoen din av Experian.</span><span class="sxs-lookup"><span data-stu-id="80da5-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="80da5-131">Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**.</span><span class="sxs-lookup"><span data-stu-id="80da5-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="80da5-132">I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.</span><span class="sxs-lookup"><span data-stu-id="80da5-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="80da5-133">Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.</span><span class="sxs-lookup"><span data-stu-id="80da5-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="80da5-134">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="80da5-134">Next steps</span></span>

<span data-ttu-id="80da5-135">Bygg på toppen av de supplerte kundedataene.</span><span class="sxs-lookup"><span data-stu-id="80da5-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="80da5-136">Opprett [segmenter](segments.md), [mål](measures.md) og til og med [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.</span><span class="sxs-lookup"><span data-stu-id="80da5-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="80da5-137">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="80da5-137">Data privacy and compliance</span></span>

<span data-ttu-id="80da5-138">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Experian, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="80da5-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="80da5-139">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Experian oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="80da5-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="80da5-140">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="80da5-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="80da5-141">Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="80da5-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
