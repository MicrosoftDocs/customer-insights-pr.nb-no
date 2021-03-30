---
title: Eksportere Customer Insights-data til SFTP-verter
description: Lær hvordan du konfigurerer tilkoblingen til en SFTP-vert.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598397"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="e74cf-103">Kobling for SFTP (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="e74cf-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="e74cf-104">Bruk kundedata i tredjepartsprogrammer ved å eksportere dem til en SFTP-vert (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="e74cf-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e74cf-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="e74cf-105">Prerequisites</span></span>

- <span data-ttu-id="e74cf-106">Tilgjengelighet av en SFTP-vert og tilsvarende legitimasjon.</span><span class="sxs-lookup"><span data-stu-id="e74cf-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="e74cf-107">Koble til SFTP</span><span class="sxs-lookup"><span data-stu-id="e74cf-107">Connect to SFTP</span></span>

1. <span data-ttu-id="e74cf-108">Gå til **Admin** > **Eksporter mål**.</span><span class="sxs-lookup"><span data-stu-id="e74cf-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e74cf-109">Under **SFTP** velger du **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="e74cf-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="e74cf-110">Gi målet et gjenkjennelig navn i feltet **Visningsnavn**.</span><span class="sxs-lookup"><span data-stu-id="e74cf-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e74cf-111">Angi et **brukernavn**, et **passord** og et **vertsnavn** og **eksportmappe** for SFTP-kontoen.</span><span class="sxs-lookup"><span data-stu-id="e74cf-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="e74cf-112">Velg **Bekreft** for å teste tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="e74cf-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="e74cf-113">Når verifiseringen er vellykket, velger du om du vil eksportere dataene **Komprimert** eller **Pakket ut**, og velger **feltskilletegnet** for de eksporterte filene.</span><span class="sxs-lookup"><span data-stu-id="e74cf-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="e74cf-114">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="e74cf-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e74cf-115">Velg **Neste** for å komme i gang med å konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="e74cf-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="e74cf-116">Konfigurer eksporten</span><span class="sxs-lookup"><span data-stu-id="e74cf-116">Configure the export</span></span>

1. <span data-ttu-id="e74cf-117">Velg enhetene du vil eksportere, for eksempel segmenter.</span><span class="sxs-lookup"><span data-stu-id="e74cf-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e74cf-118">Hver valgte enhet vil være opptil fem utdatafiler når de eksporteres.</span><span class="sxs-lookup"><span data-stu-id="e74cf-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="e74cf-119">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="e74cf-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e74cf-120">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="e74cf-120">Export the data</span></span>

<span data-ttu-id="e74cf-121">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e74cf-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e74cf-122">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e74cf-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e74cf-123">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="e74cf-123">Known limitations</span></span>

- <span data-ttu-id="e74cf-124">Kjøretiden for en eksport avhenger av systemytelsen.</span><span class="sxs-lookup"><span data-stu-id="e74cf-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="e74cf-125">Vi anbefaler to CPU-kjerner og 1 GB minne som minimal konfigurasjon av serveren.</span><span class="sxs-lookup"><span data-stu-id="e74cf-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="e74cf-126">Det kan ta tre timer å eksportere enheter med opptil 100 millioner kundeprofiler når du bruker den anbefalte minimumskonfigurasjonen av to CPU-kjerner og 1 GB minne.</span><span class="sxs-lookup"><span data-stu-id="e74cf-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e74cf-127">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="e74cf-127">Data privacy and compliance</span></span>

<span data-ttu-id="e74cf-128">Når du aktiverer Dynamics 365 Customer Insights for overføring av data via SFTP, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="e74cf-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e74cf-129">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at eksportmålet oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="e74cf-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e74cf-130">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e74cf-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e74cf-131">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="e74cf-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]