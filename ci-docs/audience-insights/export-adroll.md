---
title: Eksporter Customer Insights-data til AdRoll
description: Lær hvordan du konfigurerer tilkoblingen til AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697086"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="b1e68-103">Kontakt for AdRoll (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="b1e68-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="b1e68-104">Eksporter segmenter av enhetlige kundeprofiler til AdRoll, og bruk dem for reklame.</span><span class="sxs-lookup"><span data-stu-id="b1e68-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b1e68-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="b1e68-105">Prerequisites</span></span>

-   <span data-ttu-id="b1e68-106">Du har en [AdRoll-konto](https://www.adroll.com/) og tilhørende legitimasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="b1e68-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b1e68-107">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="b1e68-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b1e68-108">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="b1e68-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="b1e68-109">Koble til AdRoll</span><span class="sxs-lookup"><span data-stu-id="b1e68-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="b1e68-110">Gå til **Admin** > **Eksporter mål**.</span><span class="sxs-lookup"><span data-stu-id="b1e68-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b1e68-111">Under **AdRoll** velger du **Oppsett**.</span><span class="sxs-lookup"><span data-stu-id="b1e68-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="b1e68-112">Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="b1e68-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfigurasjonsrute for AdRoll-tilkobling.":::

1. <span data-ttu-id="b1e68-114">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="b1e68-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b1e68-115">Velg **Koble til** for å initialisere tilkoblingen til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b1e68-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="b1e68-116">Velg **Godkjenn med AdRoll**, og angi administratorlegitimasjonen din for AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b1e68-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="b1e68-117">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="b1e68-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b1e68-118">Angi **annonsør-ID-en din for AdRoll** [AdRoll-annonsør](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="b1e68-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="b1e68-119">Velg **Neste** for å konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="b1e68-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b1e68-120">Konfigurere koblingen</span><span class="sxs-lookup"><span data-stu-id="b1e68-120">Configure the connector</span></span>

1. <span data-ttu-id="b1e68-121">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="b1e68-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b1e68-122">Dette kreves for å eksportere segmenter til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b1e68-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="b1e68-123">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="b1e68-123">Select the segments you want to export.</span></span> <span data-ttu-id="b1e68-124">Velg et segment med minst 100 medlemmer.</span><span class="sxs-lookup"><span data-stu-id="b1e68-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="b1e68-125">Du kan ikke eksportere mindre segmenter.</span><span class="sxs-lookup"><span data-stu-id="b1e68-125">You can't export smaller segments.</span></span> <span data-ttu-id="b1e68-126">I tillegg er maksimumsstørrelsen for et segment som skal eksporteres, 250 000 medlemmer per eksport.</span><span class="sxs-lookup"><span data-stu-id="b1e68-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="b1e68-127">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="b1e68-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b1e68-128">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="b1e68-128">Export the data</span></span>

<span data-ttu-id="b1e68-129">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b1e68-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b1e68-130">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b1e68-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b1e68-131">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="b1e68-131">Known limitations</span></span>

- <span data-ttu-id="b1e68-132">Du kan eksportere opptil 250 000 profiler per eksport til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b1e68-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="b1e68-133">Du kan ikke eksportere segmenter med færre enn 100 profiler til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b1e68-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="b1e68-134">Eksport til AdRoll er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="b1e68-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="b1e68-135">Det kan ta opptil 10 minutter å eksportere opptil 250 000 profiler til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b1e68-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="b1e68-136">Antallet profiler du kan eksportere til AdRoll, er avhengig av og begrenset til kontrakten din med AdRoll.</span><span class="sxs-lookup"><span data-stu-id="b1e68-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b1e68-137">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="b1e68-137">Data privacy and compliance</span></span>

<span data-ttu-id="b1e68-138">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til AdRoll, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="b1e68-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b1e68-139">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at AdRoll oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="b1e68-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b1e68-140">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b1e68-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b1e68-141">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="b1e68-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
