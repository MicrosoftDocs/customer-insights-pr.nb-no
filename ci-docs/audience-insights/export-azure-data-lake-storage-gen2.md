---
title: Eksportere Customer Insights-data til Azure Data Lake Storage Gen2
description: Lær hvordan du konfigurerer tilkoblingen til Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760063"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="8f405-103">Konfigurer tilkoblingen til Azure Data Lake Storage Gen2 (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="8f405-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="8f405-104">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="8f405-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8f405-105">Velg **Legg til tilkobling**, og velg **Azure Data Lake Gen 2** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8f405-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="8f405-106">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="8f405-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8f405-107">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8f405-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8f405-108">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8f405-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8f405-109">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8f405-109">Choose who can use this connection.</span></span> <span data-ttu-id="8f405-110">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="8f405-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8f405-111">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8f405-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8f405-112">Angi **kontonavn**, **kontonøkkel** og **beholder** for Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="8f405-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="8f405-113">Hvis du vil vite hvordan du oppretter en lagringskonto som skal brukes med Azure Data Lake Storage Gen2, kan du se [Opprett lagringskonto](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="8f405-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="8f405-114">Hvis du vil finne ut mer om navn på forretningsforbindelse og kontonøkkel for Azure Data Lake Gen2, kan du se [Behandle innstillinger for lagringskonto i Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="8f405-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="8f405-115">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="8f405-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="8f405-116">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="8f405-116">Configure an export</span></span>

<span data-ttu-id="8f405-117">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="8f405-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8f405-118">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8f405-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8f405-119">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="8f405-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8f405-120">Velg **Legg til eksport** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="8f405-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="8f405-121">Velg en tilkobling fra **Azure Data Lake**-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="8f405-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="8f405-122">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="8f405-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8f405-123">Merk av i boksen ved siden av hver av enhetene du vil eksportere til dette stedet.</span><span class="sxs-lookup"><span data-stu-id="8f405-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="8f405-124">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="8f405-124">Select **Save**.</span></span>

<span data-ttu-id="8f405-125">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="8f405-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8f405-126">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8f405-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8f405-127">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8f405-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="8f405-128">Eksporterte data lagres i lagringsbeholderen du konfigurerte for Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="8f405-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
