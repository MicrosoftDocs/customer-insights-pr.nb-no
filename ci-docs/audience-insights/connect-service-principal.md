---
title: Koble til en Azure Data Lake Storage Gen2-konto med en tjenestekontohaver
description: Bruk en Azure-tjenestekontohaver for målgruppeinnsikt for å koble deg til din egen Data Lake-forekomst når du legger den ved målgruppeinnsikt.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644100"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="b34c4-103">Koble til en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver for målgruppeinnsikt</span><span class="sxs-lookup"><span data-stu-id="b34c4-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="b34c4-104">Automatiske verktøy som bruker Azure-tjenester, bør alltid ha begrensede tillatelser.</span><span class="sxs-lookup"><span data-stu-id="b34c4-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="b34c4-105">I stedet for at programmer skal logges på som en bruker med full rettigheter, tilbyr Azure tjenestekontohavere.</span><span class="sxs-lookup"><span data-stu-id="b34c4-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="b34c4-106">Les videre for å lære hvordan du kobler til målgruppeinnsikt med en Azure Data Lake Storage Gen2-konto ved hjelp av en Azure-tjenestekontohaver i stedet for lagringskontonøkler.</span><span class="sxs-lookup"><span data-stu-id="b34c4-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="b34c4-107">Du kan bruke tjenestekontohaveren til å [legge til eller redigere en Common Data Model-mappe som en datakilde](connect-common-data-model.md) på en sikkwer måte eller [opprette et nytt eller oppdatere et eksisterende miljø](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="b34c4-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="b34c4-108">Du trenger administratortillatelser for Azure-abonnementet for å opprette tjenestekontohaveren.</span><span class="sxs-lookup"><span data-stu-id="b34c4-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="b34c4-109">Opprette Azure-tjenestekontohaver for målgruppeinnsikt</span><span class="sxs-lookup"><span data-stu-id="b34c4-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="b34c4-110">Før du oppretter en ny tjenestekontohaver for målgruppeinnsikt, må du kontrollere om det allerede finnes en i organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="b34c4-111">Se etter en eksisterende tjenestekontohaver</span><span class="sxs-lookup"><span data-stu-id="b34c4-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="b34c4-112">Gå til [Azure-administratorportalen](https://portal.azure.com), og logg på organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="b34c4-113">Velg **Azure Active Directory** fra Azure-tjenestene.</span><span class="sxs-lookup"><span data-stu-id="b34c4-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="b34c4-114">Under **Administrer** velger du **Enterprise-programmer**.</span><span class="sxs-lookup"><span data-stu-id="b34c4-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="b34c4-115">Søk etter førsteparts program-ID-en for målgruppeinnsikt `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` eller navnet `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="b34c4-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="b34c4-116">Hvis du finner en samsvarende oppføring, betyr det at tjenestekontohaveren for målgruppeinnsikt finnes.</span><span class="sxs-lookup"><span data-stu-id="b34c4-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="b34c4-117">Du trenger ikke å opprette den på nytt.</span><span class="sxs-lookup"><span data-stu-id="b34c4-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skjermbilde som viser den eksisterende tjenestekontohaveren.":::
   
6. <span data-ttu-id="b34c4-119">Hvis ingen resultater returneres, oppretter du en ny tjenestekontohaver.</span><span class="sxs-lookup"><span data-stu-id="b34c4-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="b34c4-120">Opprett en ny tjenestekontohaver</span><span class="sxs-lookup"><span data-stu-id="b34c4-120">Create a new service principal</span></span>

1. <span data-ttu-id="b34c4-121">Installer den nyeste versjonen av **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="b34c4-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="b34c4-122">Hvis du vil ha mer informasjon, kan du se [Installere Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="b34c4-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="b34c4-123">På PC-en velger du Windows-tasten på tastaturet, og søker etter **Windows PowerShell** og **Kjør som administrator**.</span><span class="sxs-lookup"><span data-stu-id="b34c4-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="b34c4-124">I PowerShell-vinduet som åpnes, skriver du inn `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="b34c4-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="b34c4-125">Opprett tjenestekontohaveren for målgruppeinnsikt ved hjelp av Azure AD PowerShell-modulen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="b34c4-126">I PowerShell-vinduet skriver du inn `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="b34c4-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="b34c4-127">Erstatt "din leier-ID" med den faktiske ID-en for leieren din der du vil opprette tjenestekontohaveren.</span><span class="sxs-lookup"><span data-stu-id="b34c4-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="b34c4-128">Parameteren for miljønavnet `AzureEnvironmentName` er valgfri.</span><span class="sxs-lookup"><span data-stu-id="b34c4-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="b34c4-129">Angi `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="b34c4-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="b34c4-130">Denne kommandoen oppretter tjenestekontohaveren for målgruppeinnsikt i den valgte leieren.</span><span class="sxs-lookup"><span data-stu-id="b34c4-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="b34c4-131">Gi tillatelser til tjenestekontohaveren for tilgang til lagringskontoen</span><span class="sxs-lookup"><span data-stu-id="b34c4-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="b34c4-132">Gå til Azure-portalen for å gi tillatelser til tjenestekontohaveren for lagringskontoen du vil bruke i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="b34c4-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="b34c4-133">Gå til [Azure-administratorportalen](https://portal.azure.com), og logg på organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="b34c4-134">Åpne lagringskontoen du vil at tjenestekontohaveren for målgruppeinnsikt skal ha tilgang til.</span><span class="sxs-lookup"><span data-stu-id="b34c4-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="b34c4-135">Velg **Tilgangskontroll (IAM)** fra navigasjonsruten, og velg **Legg til** > **Legg til rolletilordning**.</span><span class="sxs-lookup"><span data-stu-id="b34c4-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skjermbilde som viser Azure Portal når en rolletildeling legges til.":::
   
1. <span data-ttu-id="b34c4-137">I ruten **Legg til rolletildeling** angir du følgende egenskaper:</span><span class="sxs-lookup"><span data-stu-id="b34c4-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="b34c4-138">Rolle: *Storage Blob-databidragsyter*</span><span class="sxs-lookup"><span data-stu-id="b34c4-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="b34c4-139">Tilordne tilgang til: *Bruker, gruppe eller tjenestekontohaver*</span><span class="sxs-lookup"><span data-stu-id="b34c4-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="b34c4-140">Velg: *Dynamics 365 AI for Customer Insights* ([tjenestekontohaveren du opprettet](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="b34c4-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="b34c4-141">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="b34c4-141">Select **Save**.</span></span>

<span data-ttu-id="b34c4-142">Det kan ta opptil 15 minutter å overføre endringene.</span><span class="sxs-lookup"><span data-stu-id="b34c4-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="b34c4-143">Skriv inn Azure-ressurs-ID-en eller Azure-abonnementsdetaljene i lagringskontovedlegget for målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="b34c4-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="b34c4-144">Legg ved en Azure Data Lake-lagringskonto i målgruppeinnsikt for å [lagre utdata](manage-environments.md) eller [bruke den som en datakilde](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="b34c4-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="b34c4-145">Hvis du velger Azure Data Lake-alternativet, kan du velge mellom en ressursbasert eller abonnementsbasert tilnærming.</span><span class="sxs-lookup"><span data-stu-id="b34c4-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="b34c4-146">Følg fremgangsmåten nedenfor for å gi den nødvendige informasjonen på den valgte tilnærmingen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="b34c4-147">Ressursbasert tilkobling til lagringskonto</span><span class="sxs-lookup"><span data-stu-id="b34c4-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="b34c4-148">Gå til [Azure-administrasjonsportalen](https://portal.azure.com), logg på abonnementet, og åpne lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="b34c4-149">Gå til **Innstillinger** > **Egenskaper** i navigasjonsruten.</span><span class="sxs-lookup"><span data-stu-id="b34c4-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="b34c4-150">Kopier ressurs-ID-verdien for lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopier ressurs-ID-en for lagringskontoen.":::

1. <span data-ttu-id="b34c4-152">I målgruppeinnsikt setter du inn ressurs-ID-en i ressursfeltet som vises i skjermbildet for tilkobling til lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Angi informasjon om ressurs-ID-en for lagringskontoen.":::   
   
1. <span data-ttu-id="b34c4-154">Fortsett med resten av trinnene i målgruppeinnsikt for å legge ved lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="b34c4-155">Abonnementsbasert tilkobling til lagringskonto</span><span class="sxs-lookup"><span data-stu-id="b34c4-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="b34c4-156">Gå til [Azure-administrasjonsportalen](https://portal.azure.com), logg på abonnementet, og åpne lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="b34c4-157">Gå til **Innstillinger** > **Egenskaper** i navigasjonsruten.</span><span class="sxs-lookup"><span data-stu-id="b34c4-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="b34c4-158">Gå gjennom **abonnementet**, **ressursgruppen** og **navnet** for lagringskontoen for å forsikre deg om at du velger de riktige verdiene i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="b34c4-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="b34c4-159">I målgruppeinnsikt velger du verdiene eller de tilsvarende feltene når du legger ved lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Angi informasjon om ressurs-ID-en for lagringskontoen.":::
   
1. <span data-ttu-id="b34c4-161">Fortsett med resten av trinnene i målgruppeinnsikt for å legge ved lagringskontoen.</span><span class="sxs-lookup"><span data-stu-id="b34c4-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
