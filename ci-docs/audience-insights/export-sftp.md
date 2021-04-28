---
title: Eksportere Customer Insights-data til SFTP-verter
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til en SFTP-plassering.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760431"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="f478a-103">Eksportere segmentlister og andre data til SFTP (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="f478a-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="f478a-104">Bruk kundedataene i tredjepartsprogrammer ved å eksportere dem til en plassering i Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="f478a-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="f478a-105">Forutsetninger for tilkobling</span><span class="sxs-lookup"><span data-stu-id="f478a-105">Prerequisites for connection</span></span>

- <span data-ttu-id="f478a-106">Tilgjengelighet av en SFTP-vert og tilsvarende legitimasjon.</span><span class="sxs-lookup"><span data-stu-id="f478a-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f478a-107">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="f478a-107">Known limitations</span></span>

- <span data-ttu-id="f478a-108">Kjøretiden for en eksport avhenger av systemytelsen.</span><span class="sxs-lookup"><span data-stu-id="f478a-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="f478a-109">Vi anbefaler to CPU-kjerner og 1 GB minne som minimal konfigurasjon av serveren.</span><span class="sxs-lookup"><span data-stu-id="f478a-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="f478a-110">Det kan ta tre timer å eksportere enheter med opptil 100 millioner kundeprofiler når du bruker den anbefalte minimumskonfigurasjonen av to CPU-kjerner og 1 GB minne.</span><span class="sxs-lookup"><span data-stu-id="f478a-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="f478a-111">Konfigurer tilkobling til SFTP</span><span class="sxs-lookup"><span data-stu-id="f478a-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="f478a-112">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="f478a-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f478a-113">Velg **Legg til tilkobling**, og velg **SFTP** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f478a-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="f478a-114">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="f478a-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f478a-115">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f478a-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f478a-116">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f478a-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f478a-117">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f478a-117">Choose who can use this connection.</span></span> <span data-ttu-id="f478a-118">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="f478a-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f478a-119">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f478a-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f478a-120">Angi et **brukernavn**, et **passord** og et **vertsnavn** og **eksportmappe** for SFTP-kontoen.</span><span class="sxs-lookup"><span data-stu-id="f478a-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="f478a-121">Velg **Bekreft** for å teste tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f478a-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="f478a-122">Velg om du vil eksportere dataene **Komprimert** eller **Pakket ut** og **feltskilletegnet** for de eksporterte filene.</span><span class="sxs-lookup"><span data-stu-id="f478a-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="f478a-123">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="f478a-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f478a-124">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f478a-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f478a-125">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="f478a-125">Configure an export</span></span>

<span data-ttu-id="f478a-126">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="f478a-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f478a-127">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f478a-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f478a-128">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="f478a-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f478a-129">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="f478a-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f478a-130">Velg en tilkobling fra SFTP-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="f478a-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="f478a-131">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="f478a-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f478a-132">Velg enhetene du vil eksportere, for eksempel segmenter.</span><span class="sxs-lookup"><span data-stu-id="f478a-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f478a-133">Hver valgte enhet blir delt opp i opptil fem utdatafiler når de eksporteres.</span><span class="sxs-lookup"><span data-stu-id="f478a-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="f478a-134">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="f478a-134">Select **Save**.</span></span>

<span data-ttu-id="f478a-135">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="f478a-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f478a-136">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f478a-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f478a-137">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f478a-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f478a-138">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="f478a-138">Data privacy and compliance</span></span>

<span data-ttu-id="f478a-139">Når du aktiverer Dynamics 365 Customer Insights for overføring av data via SFTP, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="f478a-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f478a-140">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at eksportmålet oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="f478a-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f478a-141">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f478a-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f478a-142">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="f478a-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
