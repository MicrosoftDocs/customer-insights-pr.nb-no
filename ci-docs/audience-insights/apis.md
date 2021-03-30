---
title: Arbeide med APIer
description: Bruk API-er og forstå begrensninger.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710472"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="82d61-103">Arbeide med API-er for Customer Insights</span><span class="sxs-lookup"><span data-stu-id="82d61-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="82d61-104">Dynamics 365 Customer Insights inneholder API-er for å utvikle dine egne programmer basert på dataene dine i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="82d61-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82d61-105">Detaljer om disse API-ene vises i [Referanse for API-er i Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="82d61-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="82d61-106">De inneholder tilleggsinformasjon om operasjoner, parametere og svar.</span><span class="sxs-lookup"><span data-stu-id="82d61-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="82d61-107">Denne artikkelen veileder deg om hvordan du får tilgang til API-ene for Customer Insights, registrerer en Azure-app og hjelper deg med å komme i gang med de tilgjengelige klientbibliotekene.</span><span class="sxs-lookup"><span data-stu-id="82d61-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="82d61-108">Kom i gang med å prøve API-ene for Customer Insights</span><span class="sxs-lookup"><span data-stu-id="82d61-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="82d61-109">[Logg på](https://home.ci.ai.dynamics.com) to Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="82d61-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="82d61-110">Hvis du ikke har et abonnement ennå, kan du [registrere deg for en prøveversjon av Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="82d61-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="82d61-111">For å aktivere API-er i Customer Insights-miljøet går du til **Administrasjon** > **Tillatelser**.</span><span class="sxs-lookup"><span data-stu-id="82d61-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="82d61-112">Du må ha administratortillatelser for å gjøre dette.</span><span class="sxs-lookup"><span data-stu-id="82d61-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="82d61-113">Gå til fanen **API-er**, og velg **Aktiver**-knappen.</span><span class="sxs-lookup"><span data-stu-id="82d61-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="82d61-114">Når du aktiverer API-ene, opprettes en primær og en sekundær abonnementsnøkkel for forekomsten som blir brukt i API-forespørslene.</span><span class="sxs-lookup"><span data-stu-id="82d61-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="82d61-115">Du kan generere nøklene på nytt ved å merke av for **Generer primær på nytt** eller **Generer sekundær på nytt** på **Administrasjon** > **Tillatelser** > **API-er**.</span><span class="sxs-lookup"><span data-stu-id="82d61-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Aktivere API-er for Customer Insights":::

1. <span data-ttu-id="82d61-117">Velg **Utforsk API-ene våre** for å [teste API-ene](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="82d61-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="82d61-118">Velg en API-operasjon, og velg **Prøv den**.</span><span class="sxs-lookup"><span data-stu-id="82d61-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="82d61-119">I sideruten angir du verdien i på rullegardinmenyen **Autorisasjon** til **Implisitt**.</span><span class="sxs-lookup"><span data-stu-id="82d61-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="82d61-120">Overskriften `Authorization` får et bærertoken tilføyd.</span><span class="sxs-lookup"><span data-stu-id="82d61-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="82d61-121">Abonnementsnøkkelen fylles ut automatisk.</span><span class="sxs-lookup"><span data-stu-id="82d61-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="82d61-122">Du kan eventuelt legge til alle nødvendige spørringsparametere.</span><span class="sxs-lookup"><span data-stu-id="82d61-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="82d61-123">Bla til bunnen av side ruten, og velg **Send**.</span><span class="sxs-lookup"><span data-stu-id="82d61-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="82d61-124">HTTP-svaret vises snart nedenfor.</span><span class="sxs-lookup"><span data-stu-id="82d61-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Animert gif som viser hvordan du velger testing av API-ene.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="82d61-126">Opprett en ny appregistrering i Azure Portal</span><span class="sxs-lookup"><span data-stu-id="82d61-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="82d61-127">Disse trinnene hjelper deg med å komme i gang med å bruke API-ene for Customer Insights i et Azure-program ved hjelp av delegerte tillatelser.</span><span class="sxs-lookup"><span data-stu-id="82d61-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="82d61-128">Du må ha fullført [Komme i gang-delen](#get-started-trying-the-customer-insights-apis) først.</span><span class="sxs-lookup"><span data-stu-id="82d61-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="82d61-129">Logg på [Azure Portal](https://portal.azure.com) med kontoen som har tilgang til Customer Insights -dataene.</span><span class="sxs-lookup"><span data-stu-id="82d61-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="82d61-130">Til venstre velger du **Appregistreringer**.</span><span class="sxs-lookup"><span data-stu-id="82d61-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="82d61-131">Velg **Ny registrering**, angi et programnavn, og velg kontotypen.</span><span class="sxs-lookup"><span data-stu-id="82d61-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="82d61-132">Du kan også legge til en URL-adresse for omdirigering.</span><span class="sxs-lookup"><span data-stu-id="82d61-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="82d61-133">http://localhost er tilstrekkelig for utvikling av et program på den lokale datamaskinen.</span><span class="sxs-lookup"><span data-stu-id="82d61-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="82d61-134">I den nye appregistreringen går du til **API-tillatelser**.</span><span class="sxs-lookup"><span data-stu-id="82d61-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animert gif for å angi API-tillatelse i appregistrering.":::

1. <span data-ttu-id="82d61-136">Velg **Legg til en tillatelse**, og velg **Customer Insights** i sideruten.</span><span class="sxs-lookup"><span data-stu-id="82d61-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="82d61-137">For **Tillatelsestype** velger du **Delegerte tillatelser** og velger deretter tillatelsen **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="82d61-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="82d61-138">Velg **Legg til tillatelser**.</span><span class="sxs-lookup"><span data-stu-id="82d61-138">Select **Add permissions**.</span></span> <span data-ttu-id="82d61-139">Hvis du trenger tilgang til API-en uten at en bruker logger på, ser du gjennom [Server-til-server-programtillatelser](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="82d61-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="82d61-140">Velg **Gi admin-tillatelse for ...** for å fullføre appregistreringen.</span><span class="sxs-lookup"><span data-stu-id="82d61-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="82d61-141">Du kan bruke program-/klient-ID-en for denne appregistreringen med Microsoft Authentication Library (MSAL) for å få et bærertoken for å sende forespørselen til API-en.</span><span class="sxs-lookup"><span data-stu-id="82d61-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animert gif for å gi administratorsamtykke.":::

<span data-ttu-id="82d61-143">Hvis du vil ha mer informasjon om MSAL, kan du se [Oversikt over Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="82d61-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="82d61-144">Hvis du vil ha mer informasjon om appregistrering i Azure, kan du se [Den nye appregistreringsopplevelsen i Azure Portal](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="82d61-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="82d61-145">Hvis du vil ha informasjon om hvordan du bruker API-ene i klientbibliotekene, kan du se [Customer Insights-klilentbiblioteker](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="82d61-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="82d61-146">Server-til-server-programtillatelser</span><span class="sxs-lookup"><span data-stu-id="82d61-146">Server-to-server application permissions</span></span>

<span data-ttu-id="82d61-147">[Delen for appregistrering](#create-a-new-app-registration-in-the-azure-portal) beskriver hvordan du registrerer en app som krever at brukeren logger på for godkjenning.</span><span class="sxs-lookup"><span data-stu-id="82d61-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="82d61-148">Lær hvordan du oppretter en appregistrering som ikke trenger brukermedvirkning, og som kan kjøres på en server.</span><span class="sxs-lookup"><span data-stu-id="82d61-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="82d61-149">Gå til **API-tillatelser** i appregistreringen i Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="82d61-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="82d61-150">Velg **Legg til en tillatelse**, og velg **Customer Insights** i sideruten.</span><span class="sxs-lookup"><span data-stu-id="82d61-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="82d61-151">For **Tillatelsestype** velger du **Apptillatelser** og velger deretter tillatelsen **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="82d61-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="82d61-152">Velg **Legg til tillatelser**.</span><span class="sxs-lookup"><span data-stu-id="82d61-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="82d61-153">Du må legge til en tjenestekontohaver for at du skal kunne gi administratorsamtykke for denne apptillatelsen.</span><span class="sxs-lookup"><span data-stu-id="82d61-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="82d61-154">Installer Azure Active Directory (AD) PowerShell-modulen: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="82d61-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="82d61-155">Koble til AD-kontoen: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="82d61-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="82d61-156">Du finner leier-ID-en din under **Oversikt** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="82d61-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="82d61-157">Kjør følgende kommando for å legge til en Azure AD-tjenestekontohaver: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"`. AppId-parameteren gjelder for API-appen for Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="82d61-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Eksempel på tjenestekontohaver":::

1. <span data-ttu-id="82d61-159">Gå tilbake til **API-tillatelser** for appregistreringen.</span><span class="sxs-lookup"><span data-stu-id="82d61-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="82d61-160">Velg **Gi admin-tillatelse for ...** for å fullføre appregistreringen.</span><span class="sxs-lookup"><span data-stu-id="82d61-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animert gif for å gi administratorsamtykke.":::

1. <span data-ttu-id="82d61-162">For å fullføre må vi legge til navnet på appregistreringen som en bruker i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="82d61-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="82d61-163">Åpne Customer Insights, gå til **Administrasjon** > **Tillatelser**, og velg **Legg til bruker**.</span><span class="sxs-lookup"><span data-stu-id="82d61-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="82d61-164">Søk etter navnet på appregistreringen, velg det fra søkeresultatene, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="82d61-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="82d61-165">Customer Insights-klientbiblioteker</span><span class="sxs-lookup"><span data-stu-id="82d61-165">Customer Insights client libraries</span></span>

<span data-ttu-id="82d61-166">Denne delen hjelper deg med å komme i gang med å bruke klientbibliotekene som er tilgjengelige for API-ene i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="82d61-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="82d61-167">Du finner all bibliotekkildekode og alle eksempelprogrammer på [Customer Insights GitHub-siden](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="82d61-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="82d61-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="82d61-168">C# NuGet</span></span>

<span data-ttu-id="82d61-169">Lær hvordan du kommer i gang med C#-klientbibliotekene fra NuGet.org. Hvis du vil ha mer informasjon om NuGet-pakken, kan du se [Microsoft.Dynamics.CustomerInsights.API](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="82d61-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="82d61-170">For øyeblikket målretter denne pakken seg mot rammeverkene netstandard2.0 og netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="82d61-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="82d61-171">Legge til C#-klientbiblioteket i et C#-prosjekt</span><span class="sxs-lookup"><span data-stu-id="82d61-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="82d61-172">I Visual Studio åpner du **Pakkebehandling for NuGet** for prosjektet.</span><span class="sxs-lookup"><span data-stu-id="82d61-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="82d61-173">Søk etter **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="82d61-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="82d61-174">Velg **Installer** for å legge til pakken i prosjektet.</span><span class="sxs-lookup"><span data-stu-id="82d61-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="82d61-175">Du kan også kjøre denne kommandoen i **pakkebehandlingskonsollen for NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="82d61-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Legg til NuGet-pakken i Visual Studio-prosjektet":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="82d61-177">Bruke C#-klientbiblioteket</span><span class="sxs-lookup"><span data-stu-id="82d61-177">Use the C# client library</span></span>

1. <span data-ttu-id="82d61-178">Bruk [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) for å få et `AccessToken` ved å bruke den eksisterende [Azure-appregistreringen](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="82d61-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="82d61-179">Når du har godkjent og skaffet deg et token, kan du konstruere en ny eller bruke en eksisterende `HttpClient` med den ekstra **godkjenningen DefaultRequestHeaders** angitt til **Bærer <access token>** og **Ocp-Apim-Subscription-Key** angitt til [**abonnementsnøkkelen** fra Customer Insights-miljøet](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="82d61-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="82d61-180">Tilbakestill **Godkjenning**-hodet når det er nødvendig.</span><span class="sxs-lookup"><span data-stu-id="82d61-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="82d61-181">For eksempel når tokenet utløper.</span><span class="sxs-lookup"><span data-stu-id="82d61-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="82d61-182">Send denne `HttpClient` til konstruksjonen av `CustomerInsights`-klienten.</span><span class="sxs-lookup"><span data-stu-id="82d61-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Eksempel på httpclient":::

1. <span data-ttu-id="82d61-184">Foreta kall til klienten for utvidelsesmetoder, for eksempel `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="82d61-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="82d61-185">Hvis tilgang til den underliggende `Microsoft.Rest.HttpOperationResponse` foretrekkes, bruker du http-meldingsmetoder, for eksempel `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="82d61-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="82d61-186">Svaret vil sannsynligvis være av typen `object` fordi metoden kan returnere flere typer (for eksempel `IList<InstanceInfo>` og `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="82d61-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="82d61-187">Hvis du vil kontrollere returtypen, kan du endre objektene på en sikker måte til svartypene som er angitt på [siden API-detaljer](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for den operasjonen.</span><span class="sxs-lookup"><span data-stu-id="82d61-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="82d61-188">Hvis du trenger mer informasjon om forespørselen, kan du bruke **http-meldingsmetodene** til å få tilgang råsvarobjektet.</span><span class="sxs-lookup"><span data-stu-id="82d61-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="82d61-189">NodeJS-pakke</span><span class="sxs-lookup"><span data-stu-id="82d61-189">NodeJS package</span></span>

<span data-ttu-id="82d61-190">Bruk NodeJS-klientbibliotekene som er tilgjengelige via NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="82d61-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="82d61-191">Python-pakke</span><span class="sxs-lookup"><span data-stu-id="82d61-191">Python package</span></span>

<span data-ttu-id="82d61-192">Bruk Python-klientbibliotekene som er tilgjengelige via PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="82d61-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
