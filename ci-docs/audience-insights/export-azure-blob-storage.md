---
title: Eksportere Customer Insights-data til Azure Blob Storage
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Blob Storage.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976193"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="8e1e0-103">Eksporter segmentliste og andre data til Azure Blob Storage (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="8e1e0-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="8e1e0-104">Lagre Customer Insights-data i en Blob Storage, eller bruk den til å overføre dataene dine til andre programmer.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="8e1e0-105">Konfigurer tilkoblingen til Blob Storage</span><span class="sxs-lookup"><span data-stu-id="8e1e0-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="8e1e0-106">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8e1e0-107">Velg **Legg til tilkobling**, og velg **Azure Blob Storage** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="8e1e0-108">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8e1e0-109">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8e1e0-110">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8e1e0-111">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-111">Choose who can use this connection.</span></span> <span data-ttu-id="8e1e0-112">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8e1e0-113">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8e1e0-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8e1e0-114">Angi **Kontonavn**, **Kontonøkkel** og **Beholder** for Blob Storage-kontoen.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="8e1e0-115">Hvis du vil finne ut mer om hvordan du finner navn på forretningsforbindelse og kontonøkkel for Blob Storage, kan du se [Behandle innstillinger for lagringskonto i Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="8e1e0-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="8e1e0-116">Hvis du vil lære hvordan du oppretter en beholder, kan du se [Opprette en beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="8e1e0-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="8e1e0-117">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="8e1e0-118">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="8e1e0-118">Configure an export</span></span>

<span data-ttu-id="8e1e0-119">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8e1e0-120">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8e1e0-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8e1e0-121">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8e1e0-122">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8e1e0-123">Velg en tilkobling fra Azure Blob Storage-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="8e1e0-124">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8e1e0-125">Merk av i boksen ved siden av hver av enhetene du vil eksportere til dette stedet.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="8e1e0-126">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-126">Select **Save**.</span></span>

<span data-ttu-id="8e1e0-127">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8e1e0-128">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8e1e0-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="8e1e0-129">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8e1e0-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="8e1e0-130">Eksporterte data lagres i Blob Storage-beholderen du konfigurerte.</span><span class="sxs-lookup"><span data-stu-id="8e1e0-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="8e1e0-131">Følgende mappebaner opprettes automatisk i beholderen:</span><span class="sxs-lookup"><span data-stu-id="8e1e0-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="8e1e0-132">For kildeenheter og enheter generert av systemet: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="8e1e0-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="8e1e0-133">Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="8e1e0-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="8e1e0-134">Model.json for de eksporterte enhetene er på %ExportDestinationName%-nivå</span><span class="sxs-lookup"><span data-stu-id="8e1e0-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="8e1e0-135">Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="8e1e0-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
