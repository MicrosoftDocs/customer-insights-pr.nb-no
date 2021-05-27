---
title: Eksportere Customer Insights-data til Azure Synapse Analytics
description: Lær hvordan du konfigurerer tilkoblingen til Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977389"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="9f03e-103">Eksporter data til Azure Synapse Analytics (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="9f03e-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="9f03e-104">Azure Synapse er en analysetjeneste som akselererer tid til innsikt på tvers av datalagre og store datasystemer.</span><span class="sxs-lookup"><span data-stu-id="9f03e-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="9f03e-105">Du kan ta inn og bruke Customer Insights-dataene i [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="9f03e-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9f03e-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="9f03e-106">Prerequisites</span></span>

<span data-ttu-id="9f03e-107">Følgende forhåndskrav må oppfylles for å konfigurere tilkoblingen fra Customer Insights til Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="9f03e-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="9f03e-108">Pass på at du angir alle **rolletilordninger** slik det er beskrevet.</span><span class="sxs-lookup"><span data-stu-id="9f03e-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="9f03e-109">Forhåndskrav i Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9f03e-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="9f03e-110">Du har en **Administrator**-brukerrolle i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="9f03e-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="9f03e-111">Finn ut mer om [angivelse av brukertillatelser i målgruppeinnsikt](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="9f03e-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="9f03e-112">I Azure:</span><span class="sxs-lookup"><span data-stu-id="9f03e-112">In Azure:</span></span> 

- <span data-ttu-id="9f03e-113">Et aktivt Azure-abonnement.</span><span class="sxs-lookup"><span data-stu-id="9f03e-113">An active Azure subscription.</span></span>

- <span data-ttu-id="9f03e-114">Hvis du bruker en ny Azure Data Lake Storage Gen2-konto, må *tjenestesjefen for målgruppeinnsikt* ha tillatelsene **Storage Blob-databidragsyter**.</span><span class="sxs-lookup"><span data-stu-id="9f03e-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="9f03e-115">Finn ut mer om hvordan du [kobler til en Azure Data Lake Storage Gen2-konto med Azure-hovedkontohaver for målgruppeinnsikt](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="9f03e-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="9f03e-116">Data Lake Storage Gen2 **må ha** [hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace) aktivert.</span><span class="sxs-lookup"><span data-stu-id="9f03e-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="9f03e-117">I ressursgruppen der Azure Synapse-arbeidsområdet er plassert, må *tjenestekontohaveren* og *brukeren for målgruppeinnsikt* tilordnes minst **lesetillatelser**.</span><span class="sxs-lookup"><span data-stu-id="9f03e-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="9f03e-118">Hvis du vil ha mer informasjon, kan du se [Tilordne Azure-roller ved hjelp av Azure Portal](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="9f03e-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="9f03e-119">*Brukeren* må ha tillatelsene **Storage Blob-databidragsyter** på Azure Data Lake Storage Gen2-kontoen der dataene er plassert og koblet til Azure Synapse-arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="9f03e-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="9f03e-120">Finn ut mer om hvordan du [bruker Azure Portal til å tilordne en Azure-rolle for tilgang til blob- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [tillatelsene for Storage Blob-databidragsyter](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="9f03e-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="9f03e-121">*[Azure Synapse-arbeidsområdeadministrert identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* må ha tillatelsene **Storage Blob-databidragsyter** på Azure Data Lake Storage Gen2-kontoen der dataene er plassert og koblet til Azure Synapse-arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="9f03e-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="9f03e-122">Finn ut mer om hvordan du [bruker Azure Portal til å tilordne en Azure-rolle for tilgang til blob- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [tillatelsene for Storage Blob-databidragsyter](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="9f03e-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="9f03e-123">I Azure Synapse-arbeidsområdet må *tjenestekontohaveren for målgruppeinnsikt* ha rollen **Synapse-administrator** tilordnet.</span><span class="sxs-lookup"><span data-stu-id="9f03e-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="9f03e-124">Hvis du vil ha mer informasjon, kan du se [Slik konfigurerer du tilgangskontroll for Synapse-arbeidsområdet](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="9f03e-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="9f03e-125">Konfigurer tilkoblingen og eksporter til Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="9f03e-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="9f03e-126">Konfigurer en tilkobling</span><span class="sxs-lookup"><span data-stu-id="9f03e-126">Configure a connection</span></span>

1. <span data-ttu-id="9f03e-127">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="9f03e-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9f03e-128">Velg **Legg til tilkobling**, og velg **Azure Synapse Analytics** eller velg **Konfigurer** op flisen **Azure Synapse Analytics** til å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="9f03e-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="9f03e-129">Gi tilkoblingen et gjenkjennelig navn i Visningsnavn-feltet.</span><span class="sxs-lookup"><span data-stu-id="9f03e-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="9f03e-130">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="9f03e-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="9f03e-131">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="9f03e-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9f03e-132">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="9f03e-132">Choose who can use this connection.</span></span> <span data-ttu-id="9f03e-133">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="9f03e-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9f03e-134">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9f03e-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9f03e-135">Velg eller søk etter abonnementet du vil bruke Customer Insights-dataene i.</span><span class="sxs-lookup"><span data-stu-id="9f03e-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="9f03e-136">Så snart et abonnement er valgt, kan du også velge **Arbeidsområde**, **Lagringskonto** og **Beholder**.</span><span class="sxs-lookup"><span data-stu-id="9f03e-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="9f03e-137">Velg **Lagre** for å lagre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="9f03e-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="9f03e-138">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="9f03e-138">Configure an export</span></span>

<span data-ttu-id="9f03e-139">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="9f03e-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9f03e-140">Hvis du vil ha mer informasjon, kan du se [tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9f03e-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9f03e-141">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="9f03e-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9f03e-142">Velg **Legg til eksport** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="9f03e-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="9f03e-143">Velg en tilkobling fra **Azure Synapse Analytics**-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="9f03e-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="9f03e-144">Hvis du ikke ser dette inndelingsnavnet, er ingen [tilkoblinger](connections.md) av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="9f03e-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="9f03e-145">Angi et gjenkjennelig **visningsnavn** for eksporten og et **databasenavn**.</span><span class="sxs-lookup"><span data-stu-id="9f03e-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="9f03e-146">Velg hvilke enheter du vil eksportere til Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="9f03e-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="9f03e-147">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="9f03e-147">Select **Save**.</span></span>

<span data-ttu-id="9f03e-148">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="9f03e-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9f03e-149">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9f03e-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9f03e-150">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9f03e-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="9f03e-151">Oppdater en eksport</span><span class="sxs-lookup"><span data-stu-id="9f03e-151">Update an export</span></span>

1. <span data-ttu-id="9f03e-152">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="9f03e-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9f03e-153">Velg **Rediger** på eksporten du vil oppdatere.</span><span class="sxs-lookup"><span data-stu-id="9f03e-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="9f03e-154">**Legg til** eller **Fjern** enheter fra utvalget.</span><span class="sxs-lookup"><span data-stu-id="9f03e-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="9f03e-155">Hvis enheter fjernes fra utvalget, slettes de ikke fra Synapse Analytics-databasen.</span><span class="sxs-lookup"><span data-stu-id="9f03e-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="9f03e-156">Fremtidige data oppdateres imidlertid ikke for de fjernede enhetene i databasen.</span><span class="sxs-lookup"><span data-stu-id="9f03e-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="9f03e-157">**Endring av databasenavnet** oppretter en ny Synapse Analytics-database.</span><span class="sxs-lookup"><span data-stu-id="9f03e-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="9f03e-158">Databasen med navnet som ble konfigurert før, vil ikke motta oppdateringer i fremtidige oppdateringer.</span><span class="sxs-lookup"><span data-stu-id="9f03e-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
