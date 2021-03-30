---
title: Eksportere Customer Insights-data til Autopilot
description: Lær hvordan du konfigurerer tilkoblingen til Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596143"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="812bb-103">Kontakt for Autopilot (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="812bb-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="812bb-104">Eksporter segmenter av enhetlige kundeprofiler til Autopilot, og bruk dem for e-postmarkedsføring i Autopilot.</span><span class="sxs-lookup"><span data-stu-id="812bb-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="812bb-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="812bb-105">Prerequisites</span></span>

-   <span data-ttu-id="812bb-106">Du har en [Autopilot-konto](https://www.autopilothq.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="812bb-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="812bb-107">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="812bb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="812bb-108">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="812bb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="812bb-109">Koble til Autopilot</span><span class="sxs-lookup"><span data-stu-id="812bb-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="812bb-110">Gå til **Admin** > **Eksporter mål**.</span><span class="sxs-lookup"><span data-stu-id="812bb-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="812bb-111">Under **Autopilot** velger du **Oppsett**.</span><span class="sxs-lookup"><span data-stu-id="812bb-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="812bb-112">Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="812bb-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurasjonsrute for Autopilot-tilkobling.":::

1. <span data-ttu-id="812bb-114">Angi **API-nøkkelen for Autopilot** [API-nøkkel for Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="812bb-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="812bb-115">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="812bb-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="812bb-116">Velg **Koble til** for å initialisere tilkoblingen til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="812bb-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="812bb-117">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="812bb-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="812bb-118">Velg **Neste** for å konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="812bb-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="812bb-119">Konfigurere koblingen</span><span class="sxs-lookup"><span data-stu-id="812bb-119">Configure the connector</span></span>

1. <span data-ttu-id="812bb-120">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="812bb-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="812bb-121">Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**.</span><span class="sxs-lookup"><span data-stu-id="812bb-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="812bb-122">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="812bb-122">Select the segments you want to export.</span></span> <span data-ttu-id="812bb-123">Vi **anbefaler på det sterkeste at du ikke eksporterer mer enn 100 000 kundeprofiler totalt** til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="812bb-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="812bb-124">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="812bb-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="812bb-125">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="812bb-125">Export the data</span></span>

<span data-ttu-id="812bb-126">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="812bb-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="812bb-127">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="812bb-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="812bb-128">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="812bb-128">Known limitations</span></span>

- <span data-ttu-id="812bb-129">Du kan eksportere opptil 100 000 profiler totalt til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="812bb-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="812bb-130">Eksport til Autopilot er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="812bb-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="812bb-131">Det kan ta opptil noen timer å eksportere opptil 100 000 profiler til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="812bb-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="812bb-132">Antallet profiler du kan eksportere til Autopilot, er avhengig av og begrenset til kontrakten din med Autopilot.</span><span class="sxs-lookup"><span data-stu-id="812bb-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="812bb-133">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="812bb-133">Data privacy and compliance</span></span>

<span data-ttu-id="812bb-134">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Autopilot, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger.</span><span class="sxs-lookup"><span data-stu-id="812bb-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="812bb-135">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Autopilot oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="812bb-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="812bb-136">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="812bb-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="812bb-137">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="812bb-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]