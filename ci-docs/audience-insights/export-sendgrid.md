---
title: Eksportere Customer Insights-data til SendGrid
description: Lær hvordan du konfigurerer tilkoblingen til SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268744"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="aa602-103">Kontakt for SendGrid (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="aa602-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="aa602-104">Eksporter segmenter av enhetlige kundeprofiler til SendGrid-kontaktliser, og bruk dem for kampanjer og e-postmarkedsføring i SendGrid.</span><span class="sxs-lookup"><span data-stu-id="aa602-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="aa602-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="aa602-105">Prerequisites</span></span>

-   <span data-ttu-id="aa602-106">Du har en [SendGrid-konto](https://sendgrid.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="aa602-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="aa602-107">Det finnes eksisterende kontaktlister i SendGrid og de tilsvarende ID-ene.</span><span class="sxs-lookup"><span data-stu-id="aa602-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="aa602-108">Hvis du vil ha mer informasjon, kan du se [SendGrid – administrer kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="aa602-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="aa602-109">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="aa602-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="aa602-110">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="aa602-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="aa602-111">Koble til SendGrid</span><span class="sxs-lookup"><span data-stu-id="aa602-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="aa602-112">Gå til **Admin** > **Eksporter mål**.</span><span class="sxs-lookup"><span data-stu-id="aa602-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="aa602-113">Under **SendGrid** velger du **Oppsett**.</span><span class="sxs-lookup"><span data-stu-id="aa602-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="aa602-114">Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="aa602-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Ruten SendGrid-eksportkonfigurasjon.":::

1. <span data-ttu-id="aa602-116">Angi **API-nøkkelen for SendGrid** [API-nøkkel for SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="aa602-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="aa602-117">Angi **[ID-en for SendGrid-listen](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="aa602-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="aa602-118">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="aa602-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="aa602-119">Velg **Koble til** for å initialisere tilkoblingen til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="aa602-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="aa602-120">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="aa602-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="aa602-121">Velg **Neste** for å konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="aa602-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="aa602-122">Konfigurere koblingen</span><span class="sxs-lookup"><span data-stu-id="aa602-122">Configure the connector</span></span>

1. <span data-ttu-id="aa602-123">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="aa602-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="aa602-124">Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**, **Land/område**, **Delstat**, **Sted** og **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="aa602-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="aa602-125">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="aa602-125">Select the segments you want to export.</span></span> <span data-ttu-id="aa602-126">Vi **anbefaler på det sterkeste at du ikke eksporterer mer enn 100 000 kundeprofiler totalt** til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="aa602-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="aa602-127">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="aa602-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="aa602-128">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="aa602-128">Export the data</span></span>

<span data-ttu-id="aa602-129">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="aa602-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="aa602-130">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="aa602-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="aa602-131">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="aa602-131">Known limitations</span></span>

- <span data-ttu-id="aa602-132">Totalt opptil 100 000 profiler til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="aa602-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="aa602-133">Eksport til SendGrid er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="aa602-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="aa602-134">Det kan ta opptil noen timer å eksportere opptil 100 000 profiler til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="aa602-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="aa602-135">Antallet profiler du kan eksportere til SendGrid, er avhengig av og begrenset til kontrakten din med SendGrid.</span><span class="sxs-lookup"><span data-stu-id="aa602-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="aa602-136">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="aa602-136">Data privacy and compliance</span></span>

<span data-ttu-id="aa602-137">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til SendGrid, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger.</span><span class="sxs-lookup"><span data-stu-id="aa602-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="aa602-138">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at SendGrid oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="aa602-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="aa602-139">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="aa602-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="aa602-140">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="aa602-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]