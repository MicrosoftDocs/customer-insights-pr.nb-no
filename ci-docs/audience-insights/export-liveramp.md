---
title: LiveRamp-kobling
description: Lær hvordan du konfigurerer tilkoblingen og eksporten til LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760339"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="80cf6-103">Eksportere segmenter til LiveRamp&reg; (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="80cf6-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="80cf6-104">Aktiver dataene i LiveRamp for å koble til over 500 plattformer på tvers av digitale og sosiale systemer og TV-er.</span><span class="sxs-lookup"><span data-stu-id="80cf6-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="80cf6-105">Du kan arbeide med dataene dine i LiveRamp for å målrette, undertrykke og tilpasse annonsekampanjer.</span><span class="sxs-lookup"><span data-stu-id="80cf6-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="80cf6-106">Forutsetninger for en tilkobling</span><span class="sxs-lookup"><span data-stu-id="80cf6-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="80cf6-107">Du må ha et LiveRamp-abonnement for å bruke denne koblingen.</span><span class="sxs-lookup"><span data-stu-id="80cf6-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="80cf6-108">Hvis du vil ha et abonnement, [kontakter du LiveRamp](https://liveramp.com/contact/) direkte.</span><span class="sxs-lookup"><span data-stu-id="80cf6-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="80cf6-109">[Finn ut mer om LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="80cf6-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="80cf6-110">Konfigurere tilkobling til LiveRamp</span><span class="sxs-lookup"><span data-stu-id="80cf6-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="80cf6-111">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="80cf6-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="80cf6-112">Velg **Legg til tilkobling**, og velg **LiveRamp** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="80cf6-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="80cf6-113">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="80cf6-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="80cf6-114">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="80cf6-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="80cf6-115">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="80cf6-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="80cf6-116">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="80cf6-116">Choose who can use this connection.</span></span> <span data-ttu-id="80cf6-117">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="80cf6-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="80cf6-118">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="80cf6-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="80cf6-119">Angi et **brukernavn** og **passord** for din LiveRamp sikker FTP (SFTP)-konto.</span><span class="sxs-lookup"><span data-stu-id="80cf6-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="80cf6-120">Denne legitimasjonen kan være forskjellig fra din LiveRamp Onboarding-legitimasjon.</span><span class="sxs-lookup"><span data-stu-id="80cf6-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="80cf6-121">Velg **Bekreft** for å teste tilkoblingen til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="80cf6-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="80cf6-122">Etter vellykket verifisering må du gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**.</span><span class="sxs-lookup"><span data-stu-id="80cf6-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="80cf6-123">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="80cf6-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="80cf6-124">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="80cf6-124">Configure an export</span></span>

<span data-ttu-id="80cf6-125">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="80cf6-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="80cf6-126">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="80cf6-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="80cf6-127">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="80cf6-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="80cf6-128">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="80cf6-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="80cf6-129">Velg en tilkobling fra LiveRamp-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="80cf6-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="80cf6-130">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="80cf6-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="80cf6-131">I feltet **Velg nøkkelidentifikator** velger du **E-post**, **Navn og adresse** eller **Telefon** for å sende til LiveRamp for identitetsløsning.</span><span class="sxs-lookup"><span data-stu-id="80cf6-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80cf6-132">![LiveRamp-kobling med attributtilordning](media/export-liveramp-segments.png "LiveRamp-kobling med attributtilordning")</span><span class="sxs-lookup"><span data-stu-id="80cf6-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="80cf6-133">Tilordne de tilsvarende attributtene fra den enhetlige kundeenheten for den valgte nøkkelidentifikatoren.</span><span class="sxs-lookup"><span data-stu-id="80cf6-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="80cf6-134">Velg **Legg til attributt** for å tilordne flere attributter som skal sendes til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="80cf6-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="80cf6-135">Det å sende flere nøkkelidentifikatorattributter til LiveRamp gir deg sannsynligvis en høyere samsvarsrate.</span><span class="sxs-lookup"><span data-stu-id="80cf6-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="80cf6-136">Velg segmentene du vil eksportere til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="80cf6-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="80cf6-137">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="80cf6-137">Select **Save**.</span></span>

<span data-ttu-id="80cf6-138">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="80cf6-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="80cf6-139">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="80cf6-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="80cf6-140">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="80cf6-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="80cf6-141">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="80cf6-141">Data privacy and compliance</span></span>

<span data-ttu-id="80cf6-142">Når du aktiverer Dynamics 365 Customer Insights for overføring av data til LiveRamp, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="80cf6-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="80cf6-143">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at LiveRamp oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="80cf6-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="80cf6-144">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="80cf6-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="80cf6-145">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="80cf6-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
