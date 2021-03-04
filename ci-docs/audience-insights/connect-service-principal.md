---
title: Koble til en Azure Data Lake Storage Gen2-konto med en tjenestekontohaver
description: Bruk en Azure-tjenestekontohaver for målgruppeinnsikt for å koble deg til din egen Data Lake-forekomst når du legger den ved målgruppeinnsikt.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267734"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="40f5c-103">Koble til en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver for målgruppeinnsikt</span><span class="sxs-lookup"><span data-stu-id="40f5c-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="40f5c-104">Automatiske verktøy som bruker Azure-tjenester, bør alltid ha begrensede tillatelser.</span><span class="sxs-lookup"><span data-stu-id="40f5c-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="40f5c-105">I stedet for at programmer skal logges på som en bruker med full rettigheter, tilbyr Azure tjenestekontohavere.</span><span class="sxs-lookup"><span data-stu-id="40f5c-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="40f5c-106">Les videre for å lære hvordan du kobler til målgruppeinnsikt med en Azure Data Lake Storage Gen2-konto ved hjelp av en Azure-tjenestekontohaver i stedet for lagringskontonøkler.</span><span class="sxs-lookup"><span data-stu-id="40f5c-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="40f5c-107">Du kan bruke tjenestekontohaveren til å [legge til eller redigere en Common Data Model-mappe som en datakilde](connect-common-data-model.md) på en sikkwer måte eller [opprette et nytt eller oppdatere et eksisterende miljø](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="40f5c-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="40f5c-108">Lagringskontoen Azure Data Lake Gen2 som skal bruke Service Principal, må ha [hierarkisk navneområde (HNS) aktivert](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="40f5c-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="40f5c-109">Du trenger administratortillatelser for Azure-abonnementet for å opprette tjenestekontohaveren.</span><span class="sxs-lookup"><span data-stu-id="40f5c-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="40f5c-110">Opprette Azure-tjenestekontohaver for målgruppeinnsikt</span><span class="sxs-lookup"><span data-stu-id="40f5c-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="40f5c-111">Før du oppretter en ny tjenestekontohaver for målgruppeinnsikt, må du kontrollere om det allerede finnes en i organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="40f5c-112">Se etter en eksisterende tjenestekontohaver</span><span class="sxs-lookup"><span data-stu-id="40f5c-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="40f5c-113">Gå til [Azure-administratorportalen](https://portal.azure.com), og logg på organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="40f5c-114">Velg **Azure Active Directory** fra Azure-tjenestene.</span><span class="sxs-lookup"><span data-stu-id="40f5c-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="40f5c-115">Under **Administrer** velger du **Enterprise-programmer**.</span><span class="sxs-lookup"><span data-stu-id="40f5c-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="40f5c-116">Søk etter førsteparts program-ID-en for målgruppeinnsikt `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` eller navnet `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="40f5c-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="40f5c-117">Hvis du finner en samsvarende oppføring, betyr det at tjenestekontohaveren for målgruppeinnsikt finnes.</span><span class="sxs-lookup"><span data-stu-id="40f5c-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="40f5c-118">Du trenger ikke å opprette den på nytt.</span><span class="sxs-lookup"><span data-stu-id="40f5c-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skjermbilde som viser den eksisterende tjenestekontohaveren.":::
   
6. <span data-ttu-id="40f5c-120">Hvis ingen resultater returneres, oppretter du en ny tjenestekontohaver.</span><span class="sxs-lookup"><span data-stu-id="40f5c-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="40f5c-121">Opprett en ny tjenestekontohaver</span><span class="sxs-lookup"><span data-stu-id="40f5c-121">Create a new service principal</span></span>

1. <span data-ttu-id="40f5c-122">Installer den nyeste versjonen av **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="40f5c-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="40f5c-123">Hvis du vil ha mer informasjon, kan du se [Installere Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="40f5c-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="40f5c-124">På PC-en velger du Windows-tasten på tastaturet, og søker etter **Windows PowerShell** og **Kjør som administrator**.</span><span class="sxs-lookup"><span data-stu-id="40f5c-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="40f5c-125">I PowerShell-vinduet som åpnes, skriver du inn `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="40f5c-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="40f5c-126">Opprett tjenestekontohaveren for målgruppeinnsikt ved hjelp av Azure AD PowerShell-modulen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="40f5c-127">I PowerShell-vinduet skriver du inn `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="40f5c-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="40f5c-128">Erstatt "din leier-ID" med den faktiske ID-en for leieren din der du vil opprette tjenestekontohaveren.</span><span class="sxs-lookup"><span data-stu-id="40f5c-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="40f5c-129">Parameteren for miljønavnet `AzureEnvironmentName` er valgfri.</span><span class="sxs-lookup"><span data-stu-id="40f5c-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="40f5c-130">Angi `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="40f5c-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="40f5c-131">Denne kommandoen oppretter tjenestekontohaveren for målgruppeinnsikt i den valgte leieren.</span><span class="sxs-lookup"><span data-stu-id="40f5c-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="40f5c-132">Gi tillatelser til tjenestekontohaveren for tilgang til lagringskontoen</span><span class="sxs-lookup"><span data-stu-id="40f5c-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="40f5c-133">Gå til Azure-portalen for å gi tillatelser til tjenestekontohaveren for lagringskontoen du vil bruke i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="40f5c-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="40f5c-134">Gå til [Azure-administratorportalen](https://portal.azure.com), og logg på organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="40f5c-135">Åpne lagringskontoen du vil at tjenestekontohaveren for målgruppeinnsikt skal ha tilgang til.</span><span class="sxs-lookup"><span data-stu-id="40f5c-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="40f5c-136">Velg **Tilgangskontroll (IAM)** fra navigasjonsruten, og velg **Legg til** > **Legg til rolletilordning**.</span><span class="sxs-lookup"><span data-stu-id="40f5c-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skjermbilde som viser Azure Portal når en rolletildeling legges til.":::
   
1. <span data-ttu-id="40f5c-138">I ruten **Legg til rolletildeling** angir du følgende egenskaper:</span><span class="sxs-lookup"><span data-stu-id="40f5c-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="40f5c-139">Rolle: *Storage Blob-databidragsyter*</span><span class="sxs-lookup"><span data-stu-id="40f5c-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="40f5c-140">Tilordne tilgang til: *Bruker, gruppe eller tjenestekontohaver*</span><span class="sxs-lookup"><span data-stu-id="40f5c-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="40f5c-141">Velg: *Dynamics 365 AI for Customer Insights* ([tjenestekontohaveren du opprettet](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="40f5c-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="40f5c-142">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="40f5c-142">Select **Save**.</span></span>

<span data-ttu-id="40f5c-143">Det kan ta opptil 15 minutter å overføre endringene.</span><span class="sxs-lookup"><span data-stu-id="40f5c-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="40f5c-144">Skriv inn Azure-ressurs-ID-en eller Azure-abonnementsdetaljene i lagringskontovedlegget for målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="40f5c-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="40f5c-145">Legg ved en Azure Data Lake-lagringskonto i målgruppeinnsikt for å [lagre utdata](manage-environments.md) eller [bruke den som en datakilde](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="40f5c-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="40f5c-146">Hvis du velger Azure Data Lake-alternativet, kan du velge mellom en ressursbasert eller abonnementsbasert tilnærming.</span><span class="sxs-lookup"><span data-stu-id="40f5c-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="40f5c-147">Følg fremgangsmåten nedenfor for å gi den nødvendige informasjonen på den valgte tilnærmingen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="40f5c-148">Ressursbasert tilkobling til lagringskonto</span><span class="sxs-lookup"><span data-stu-id="40f5c-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="40f5c-149">Gå til [Azure-administrasjonsportalen](https://portal.azure.com), logg på abonnementet, og åpne lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="40f5c-150">Gå til **Innstillinger** > **Egenskaper** i navigasjonsruten.</span><span class="sxs-lookup"><span data-stu-id="40f5c-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="40f5c-151">Kopier ressurs-ID-verdien for lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopier ressurs-ID-en for lagringskontoen.":::

1. <span data-ttu-id="40f5c-153">I målgruppeinnsikt setter du inn ressurs-ID-en i ressursfeltet som vises i skjermbildet for tilkobling til lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Angi informasjon om ressurs-ID-en for lagringskontoen.":::   
   
1. <span data-ttu-id="40f5c-155">Fortsett med resten av trinnene i målgruppeinnsikt for å legge ved lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="40f5c-156">Abonnementsbasert tilkobling til lagringskonto</span><span class="sxs-lookup"><span data-stu-id="40f5c-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="40f5c-157">Gå til [Azure-administrasjonsportalen](https://portal.azure.com), logg på abonnementet, og åpne lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="40f5c-158">Gå til **Innstillinger** > **Egenskaper** i navigasjonsruten.</span><span class="sxs-lookup"><span data-stu-id="40f5c-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="40f5c-159">Gå gjennom **abonnementet**, **ressursgruppen** og **navnet** for lagringskontoen for å forsikre deg om at du velger de riktige verdiene i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="40f5c-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="40f5c-160">I målgruppeinnsikt velger du verdiene eller de tilsvarende feltene når du legger ved lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="40f5c-161">Fortsett med resten av trinnene i målgruppeinnsikt for å legge ved lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="40f5c-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]