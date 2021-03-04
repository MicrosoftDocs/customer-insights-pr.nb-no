---
title: Eksportere Customer Insights-data til Facebook-annonseadministrasjon
description: Lær hvordan du konfigurerer tilkoblingen til Facebook-annonseadministrasjon.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269986"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="83a6a-103">Kobling for Facebook-annonseadministrasjon (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="83a6a-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="83a6a-104">Eksporter segmenter for enhetlige kundeprofiler til Facebook-annonseadministrasjon for å opprette kampanjer på Facebook og Instagram.</span><span class="sxs-lookup"><span data-stu-id="83a6a-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83a6a-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="83a6a-105">Prerequisites</span></span>

- <span data-ttu-id="83a6a-106">Du må ha en [**Facebook-annonsekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) som inkluderer en [**Facebook-bedriftskonto**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="83a6a-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="83a6a-107">Du må være administrator på [**Facebook-annonsekontoen**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="83a6a-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="83a6a-108">Koble til Facebook-annonseadministrasjon</span><span class="sxs-lookup"><span data-stu-id="83a6a-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="83a6a-109">Gå til **Admin** > **Eksporter mål**.</span><span class="sxs-lookup"><span data-stu-id="83a6a-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="83a6a-110">Under **Facebook-annonseadministrasjon** velger du **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="83a6a-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="83a6a-111">Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="83a6a-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="83a6a-112">Velg **Fortsett med Facebook** for å logge på Facebook-annonsekontoen din.</span><span class="sxs-lookup"><span data-stu-id="83a6a-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="83a6a-113">Tillat **ads_management**-tillatelsen etter godkjenning med Facebook.</span><span class="sxs-lookup"><span data-stu-id="83a6a-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="83a6a-114">Velg **Facebook-annonsekontoen** du vil arbeide med.</span><span class="sxs-lookup"><span data-stu-id="83a6a-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="83a6a-115">Velg en **eksisterende egendefinert målgruppe** fra rullegardinlisten, eller opprett et **ny egendefinert målgruppe**.</span><span class="sxs-lookup"><span data-stu-id="83a6a-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="83a6a-116">Hvis du vil ha mer informasjon, kan du se [**Målgrupper i Facebook-annonseadministrasjon**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="83a6a-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="83a6a-117">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="83a6a-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="83a6a-118">Velg **Neste** for å konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="83a6a-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="83a6a-119">Konfigurere koblingen</span><span class="sxs-lookup"><span data-stu-id="83a6a-119">Configure the connector</span></span>

1. <span data-ttu-id="83a6a-120">I feltet **Velg nøkkelidentifikator** velger du **E-post**, **Navn og adresse** eller **Telefon** som skal sendes til Facebook-annonseadministrasjon.</span><span class="sxs-lookup"><span data-stu-id="83a6a-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="83a6a-121">Tilordne de tilsvarende attributtene fra den enhetlige kundeenheten for den valgte nøkkelidentifikatoren.</span><span class="sxs-lookup"><span data-stu-id="83a6a-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="83a6a-122">[TIPS] Den beste muligheten for et treff oppstår hvis du velger **E-post** som nøkkelidentifikator.</span><span class="sxs-lookup"><span data-stu-id="83a6a-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="83a6a-123">Hvis du legger til flere identifikatorer, kan du få bedre samsvar.</span><span class="sxs-lookup"><span data-stu-id="83a6a-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="83a6a-124">Velg **Legg til attributt** for å tilordne flere attributter som skal sendes til Facebook-annonseadministrasjon.</span><span class="sxs-lookup"><span data-stu-id="83a6a-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="83a6a-125">Attributter fra Facebook-administrasjon tilordnes til følgende brukervennlige navn: **FN** = **Fornavn**, **LN** = **Etternavn**, **FI** = **Første initial**, **PHONE** = **Telefon**, **GEN** = **Kjønn**, **DOB** = **Fødselsdato**, **ST** = **Delstat**, **CT** = **Poststed**, **ZIP** = **Postnummer**, **COUNTRY** = **Land/distrikt**</span><span class="sxs-lookup"><span data-stu-id="83a6a-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="83a6a-126">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="83a6a-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="83a6a-127">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="83a6a-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="83a6a-128">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="83a6a-128">Export the data</span></span>

<span data-ttu-id="83a6a-129">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="83a6a-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="83a6a-130">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="83a6a-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="83a6a-131">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="83a6a-131">Known limitations</span></span>

- <span data-ttu-id="83a6a-132">Opptil 10 millioner kundeprofiler per eksport til Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="83a6a-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="83a6a-133">Eksport til Facebook Ads Manager er begrenset til segmenter</span><span class="sxs-lookup"><span data-stu-id="83a6a-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="83a6a-134">Eksport av segmenter med totalt 10 million profiler kan ta opptil tre timer å fullføre</span><span class="sxs-lookup"><span data-stu-id="83a6a-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="83a6a-135">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="83a6a-135">Data privacy and compliance</span></span>

<span data-ttu-id="83a6a-136">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Facebook-annonseadministrasjon, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="83a6a-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="83a6a-137">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Facebook-annonseadministrasjon oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="83a6a-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="83a6a-138">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="83a6a-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="83a6a-139">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="83a6a-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]