---
title: Eksportere Customer Insights-data til SFTP-verter
description: Lær hvordan du konfigurerer tilkoblingen til en SFTP-vert.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643515"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="45f2b-103">Kobling for SFTP (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="45f2b-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="45f2b-104">Bruk kundedata i tredjepartsprogrammer ved å eksportere dem til en SFTP-vert (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="45f2b-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="45f2b-105">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="45f2b-105">Prerequisites</span></span>

- <span data-ttu-id="45f2b-106">Tilgjengelighet av en SFTP-vert og tilhørende legitimasjoner.</span><span class="sxs-lookup"><span data-stu-id="45f2b-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="45f2b-107">Koble til SFTP</span><span class="sxs-lookup"><span data-stu-id="45f2b-107">Connect to SFTP</span></span>

1. <span data-ttu-id="45f2b-108">Gå til **Admin** > **Eksporter mål**.</span><span class="sxs-lookup"><span data-stu-id="45f2b-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="45f2b-109">Under **SFTP** velger du **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="45f2b-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="45f2b-110">Gi målet et gjenkjennelig navn i feltet **Visningsnavn**.</span><span class="sxs-lookup"><span data-stu-id="45f2b-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="45f2b-111">Angi et **brukernavn**, et **passord** og et **vertsnavn** for SFTP-kontoen.</span><span class="sxs-lookup"><span data-stu-id="45f2b-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="45f2b-112">Eksempel: Hvis rotmappen til SFTP-serveren er /root/folder, og du ønsker at dataene skal eksporteres til /root/folder/ci_export_destination_folder, må verten være sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="45f2b-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="45f2b-113">Velg **Bekreft** for å teste tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="45f2b-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="45f2b-114">Når bekreftelsen er vellykket, velger du om du vil eksportere dataene **zippet** eller **utpakket**, og deretter velger du **feltskilletegnet** for de eksporterte filene.</span><span class="sxs-lookup"><span data-stu-id="45f2b-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="45f2b-115">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="45f2b-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="45f2b-116">Velg **Neste** for å komme i gang med å konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="45f2b-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="45f2b-117">Konfigurere tilkoblingen</span><span class="sxs-lookup"><span data-stu-id="45f2b-117">Configure the connection</span></span>

1. <span data-ttu-id="45f2b-118">Velg **kundeattributtene** du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="45f2b-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="45f2b-119">Du kan eksportere ett eller flere attributter.</span><span class="sxs-lookup"><span data-stu-id="45f2b-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="45f2b-120">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="45f2b-120">Select **Next**.</span></span>

1. <span data-ttu-id="45f2b-121">Velg segmentene du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="45f2b-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="45f2b-122">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="45f2b-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="45f2b-123">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="45f2b-123">Export the data</span></span>

<span data-ttu-id="45f2b-124">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="45f2b-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="45f2b-125">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="45f2b-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="45f2b-126">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="45f2b-126">Data privacy and compliance</span></span>

<span data-ttu-id="45f2b-127">Når du aktiverer Dynamics 365 Customer Insights for overføring av data via SFTP, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="45f2b-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="45f2b-128">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at eksportmålet oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="45f2b-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="45f2b-129">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="45f2b-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="45f2b-130">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="45f2b-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
