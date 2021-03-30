---
title: LiveRamp-kobling
description: Lær hvordan du eksporterer data til LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597569"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="ac994-103">Kobling for LiveRamp&reg; (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="ac994-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="ac994-104">Aktiver dataene i LiveRamp for å koble til over 500 plattformer på tvers av digitale og sosiale systemer og TV-økosystemer.</span><span class="sxs-lookup"><span data-stu-id="ac994-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="ac994-105">Du kan arbeide med dataene dine i LiveRamp for å målrette, undertrykke og tilpasse annonsekampanjer.</span><span class="sxs-lookup"><span data-stu-id="ac994-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac994-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="ac994-106">Prerequisites</span></span>

- <span data-ttu-id="ac994-107">Du må ha et LiveRamp-abonnement for å bruke denne koblingen.</span><span class="sxs-lookup"><span data-stu-id="ac994-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="ac994-108">Hvis du vil ha et abonnement, [kontakter du LiveRamp](https://liveramp.com/contact/) direkte.</span><span class="sxs-lookup"><span data-stu-id="ac994-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="ac994-109">[Finn ut mer om LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="ac994-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="ac994-110">Koble til LiveRamp</span><span class="sxs-lookup"><span data-stu-id="ac994-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="ac994-111">I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="ac994-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ac994-112">I **LiveRamp**-flisen velger du **Oppsett**.</span><span class="sxs-lookup"><span data-stu-id="ac994-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="ac994-113">Gi målet et gjenkjennelig navn i feltet **Visningsnavn**.</span><span class="sxs-lookup"><span data-stu-id="ac994-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ac994-114">Angi et **brukernavn** og **passord** for din LiveRamp sikker FTP (SFTP)-konto.</span><span class="sxs-lookup"><span data-stu-id="ac994-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="ac994-115">Denne legitimasjonen kan være forskjellig fra din LiveRamp Onboarding-legitimasjon.</span><span class="sxs-lookup"><span data-stu-id="ac994-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="ac994-116">Velg **Bekreft** for å teste tilkoblingen til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="ac994-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="ac994-117">Etter vellykket verifisering må du gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**.</span><span class="sxs-lookup"><span data-stu-id="ac994-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="ac994-118">Velg **Neste** for å konfigurere LiveRamp-koblingen.</span><span class="sxs-lookup"><span data-stu-id="ac994-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ac994-119">Konfigurere koblingen</span><span class="sxs-lookup"><span data-stu-id="ac994-119">Configure the connector</span></span>

1. <span data-ttu-id="ac994-120">I feltet **Velg nøkkelidentifikator** velger du **E-post**, **Navn og adresse** eller **Telefon** for å sende til LiveRamp for identitetsløsning.</span><span class="sxs-lookup"><span data-stu-id="ac994-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="ac994-121">Tilordne de tilsvarende attributtene fra den enhetlige kundeenheten for den valgte nøkkelidentifikatoren.</span><span class="sxs-lookup"><span data-stu-id="ac994-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="ac994-122">Velg **Legg til attributt** for å tilordne flere attributter som skal sendes til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="ac994-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="ac994-123">Det å sende flere nøkkelidentifikatorattributter til LiveRamp gir deg sannsynligvis en høyere samsvarsrate.</span><span class="sxs-lookup"><span data-stu-id="ac994-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="ac994-124">Velg segmentene du vil eksportere til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="ac994-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="ac994-125">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="ac994-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac994-126">![LiveRamp-kobling med attributtilordning](media/export-liveramp-segments.png "LiveRamp-kobling med attributtilordning")</span><span class="sxs-lookup"><span data-stu-id="ac994-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ac994-127">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="ac994-127">Export the data</span></span>

<span data-ttu-id="ac994-128">Eksporten starter om kort tid hvis alle forhåndskravene for eksport er fullført.</span><span class="sxs-lookup"><span data-stu-id="ac994-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="ac994-129">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ac994-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="ac994-130">Når eksporten er fullført, kan du logge på LiveRamp Onboarding for å aktivere og distribuere dataene.</span><span class="sxs-lookup"><span data-stu-id="ac994-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ac994-131">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="ac994-131">Data privacy and compliance</span></span>

<span data-ttu-id="ac994-132">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til LiveRamp, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="ac994-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ac994-133">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at LiveRamp oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="ac994-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ac994-134">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ac994-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ac994-135">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="ac994-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]