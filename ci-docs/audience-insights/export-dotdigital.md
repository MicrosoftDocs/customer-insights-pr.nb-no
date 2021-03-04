---
title: Eksportere Customer Insights-data til DotDigital
description: Lær hvordan du konfigurerer tilkoblingen til DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269112"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="3bf31-103">Kontakt for DotDigital (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="3bf31-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="3bf31-104">Eksporter segmenter med enhetlige kundeprofiler til DotDigital-adressebøker, og bruk dem for kampanjer, e-postmarkedsføring og til å bygge kundesegmenter med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="3bf31-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3bf31-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="3bf31-105">Prerequisites</span></span>

-   <span data-ttu-id="3bf31-106">Du har en [DotDigital-konto](https://dotdigital.com/) og tilhørende påloggingsinformasjon for administrator.</span><span class="sxs-lookup"><span data-stu-id="3bf31-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3bf31-107">Det finnes eksisterende adressebøker i DotDigital og de tilsvarende ID-ene.</span><span class="sxs-lookup"><span data-stu-id="3bf31-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="3bf31-108">Du kan finne ID-en i URL-adressen når du velger og åpner en adressebok.</span><span class="sxs-lookup"><span data-stu-id="3bf31-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="3bf31-109">Hvis du vil ha mer informasjon, kan du se [DotDigital-adressebøker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="3bf31-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="3bf31-110">Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="3bf31-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3bf31-111">Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="3bf31-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="3bf31-112">Koble til DotDigital</span><span class="sxs-lookup"><span data-stu-id="3bf31-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="3bf31-113">Gå til **Admin** > **Eksporter mål**.</span><span class="sxs-lookup"><span data-stu-id="3bf31-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3bf31-114">Under **DotDigital** velger du **Oppsett**.</span><span class="sxs-lookup"><span data-stu-id="3bf31-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="3bf31-115">Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="3bf31-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigurasjonsrute for DotDigital-eksport.":::

1. <span data-ttu-id="3bf31-117">Angi **brukernavnet og passordet for DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="3bf31-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="3bf31-118">Angi **[ID-en for DotDigital-adresseboken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="3bf31-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="3bf31-119">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="3bf31-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3bf31-120">Velg **Koble til** for å initialisere tilkoblingen til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="3bf31-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="3bf31-121">Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.</span><span class="sxs-lookup"><span data-stu-id="3bf31-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3bf31-122">Velg **Neste** for å konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="3bf31-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="3bf31-123">Konfigurere koblingen</span><span class="sxs-lookup"><span data-stu-id="3bf31-123">Configure the connector</span></span>

1. <span data-ttu-id="3bf31-124">I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse.</span><span class="sxs-lookup"><span data-stu-id="3bf31-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3bf31-125">Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**, **Fullt navn**, **Kjønn** og **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="3bf31-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="3bf31-126">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="3bf31-126">Select the segments you want to export.</span></span> <span data-ttu-id="3bf31-127">Du kan eksportere opptil 1 million kundeprofiler totalt til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="3bf31-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="3bf31-128">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="3bf31-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3bf31-129">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="3bf31-129">Export the data</span></span>

<span data-ttu-id="3bf31-130">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3bf31-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3bf31-131">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3bf31-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3bf31-132">I DotDigital kan du nå finne segmentene i [DotDigital-adressebøker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="3bf31-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3bf31-133">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="3bf31-133">Known limitations</span></span>

- <span data-ttu-id="3bf31-134">Opptil 1 million profiler per eksport til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="3bf31-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="3bf31-135">Eksport til DotDigital er begrenset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="3bf31-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="3bf31-136">Eksport av segmenter med totalt 1 million profiler kan ta opptil tre timer på grunn av begrensninger på leverandørsiden.</span><span class="sxs-lookup"><span data-stu-id="3bf31-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="3bf31-137">Antallet profiler du kan eksportere til DotDigital, er avhengig av og begrenset til kontrakten din med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="3bf31-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3bf31-138">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="3bf31-138">Data privacy and compliance</span></span>

<span data-ttu-id="3bf31-139">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til DotDigital, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="3bf31-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3bf31-140">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at DotDigital oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="3bf31-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="3bf31-141">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3bf31-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3bf31-142">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="3bf31-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]