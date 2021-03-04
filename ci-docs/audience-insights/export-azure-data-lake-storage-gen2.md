---
title: Eksportere Customer Insights-data til Azure Data Lake Storage Gen2
description: Lær hvordan du konfigurerer tilkoblingen til Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477191"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="1349b-103">Kontakt for Azure Data Lake Storage Gen2 (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="1349b-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="1349b-104">Lagre Customer Insights-data i Azure Data Lake Storage Gen2, eller bruk den til å overføre dataene dine til andre programmer.</span><span class="sxs-lookup"><span data-stu-id="1349b-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="1349b-105">Konfigurer koblingen for Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="1349b-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="1349b-106">I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="1349b-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1349b-107">Under **Azure Data Lake Storage Gen2** velger du **Oppsett**.</span><span class="sxs-lookup"><span data-stu-id="1349b-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="1349b-108">Gi målet et gjenkjennelig navn i feltet **Visningsnavn**.</span><span class="sxs-lookup"><span data-stu-id="1349b-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1349b-109">Angi **kontonavn**, **kontonøkkel** og **beholder** for Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="1349b-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="1349b-110">Hvis du vil vite hvordan du oppretter en lagringskonto som skal brukes med Azure Data Lake Storage Gen2, kan du se [Opprett lagringskonto](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="1349b-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="1349b-111">Hvis du vil finne ut mer om hvordan du finner kontonavnet og kontonøkkelen for lagringskontoen for Azure Data Lake Gen2, kan du se [Administrer innstillinger for lagringskonto i Azure Portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1349b-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="1349b-112">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="1349b-112">Select **Next**.</span></span>

1. <span data-ttu-id="1349b-113">Merk av i boksen ved siden av hver av enhetene du vil eksportere til dette stedet.</span><span class="sxs-lookup"><span data-stu-id="1349b-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="1349b-114">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="1349b-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1349b-115">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="1349b-115">Export the data</span></span>

<span data-ttu-id="1349b-116">Du kan [eksportere data etter behov](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1349b-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="1349b-117">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1349b-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
