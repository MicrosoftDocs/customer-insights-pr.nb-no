---
title: Arbeide med APIer
description: Bruk API-er og forstå begrensninger.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689142"
---
# <a name="work-with-customer-insights-apis"></a>Arbeide med API-er for Customer Insights

Dynamics 365 Customer Insights inneholder API-er for å utvikle dine egne programmer basert på dataene dine i Customer Insights.

> [!IMPORTANT]
> Detaljer om disse API-ene vises i [Referanse for API-er i Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). De inneholder tilleggsinformasjon om operasjoner, parametere og svar.

Denne artikkelen veileder deg om hvordan du får tilgang til API-ene for Customer Insights, registrerer en Azure-app og hjelper deg med å komme i gang med de tilgjengelige klientbibliotekene.

## <a name="get-started-trying-the-customer-insights-apis"></a>Kom i gang med å prøve API-ene for Customer Insights

1. [Logg på](https://home.ci.ai.dynamics.com) to Customer Insights. Hvis du ikke har et abonnement ennå, kan du [registrere deg for en prøveversjon av Customer Insights](https://aka.ms/tryci).

1. For å aktivere API-er i Customer Insights-miljøet går du til **Administrasjon** > **Tillatelser**. Du må ha administratortillatelser for å gjøre dette.

1. Gå til fanen **API-er**, og velg **Aktiver**-knappen.    
   Når du aktiverer API-ene, opprettes en primær og en sekundær abonnementsnøkkel for forekomsten som blir brukt i API-forespørslene. Du kan generere nøklene på nytt ved å merke av for **Generer primær på nytt** eller **Generer sekundær på nytt** på **Administrasjon** > **Tillatelser** > **API-er**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Aktivere API-er for Customer Insights":::

1. Velg **Utforsk API-ene våre** for å teste API-ene.

1. Velg en API-operasjon, og velg **Prøv den**.

1. I sideruten angir du verdien i på rullegardinmenyen **Autorisasjon** til **Implisitt**. Overskriften `Authorization` får et bærertoken tilføyd. Abonnementsnøkkelen fylles ut automatisk.
  
1. Du kan eventuelt legge til alle nødvendige spørringsparametere.

1. Bla til bunnen av side ruten, og velg **Send**.

HTTP-svaret vises snart nedenfor.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Opprett en ny appregistrering i Azure Portal

Disse trinnene hjelper deg med å komme i gang med å bruke API-ene for Customer Insights i et Azure-program ved hjelp av delegerte tillatelser. Du må ha fullført [Komme i gang-delen](#get-started-trying-the-customer-insights-apis) først.

1. Logg på [Azure Portal](https://portal.azure.com) med kontoen som har tilgang til Customer Insights -dataene.

1. Til venstre velger du **Appregistreringer**.

1. Velg **Ny registrering**, angi et programnavn, og velg kontotypen.
   Du kan også legge til en URL-adresse for omdirigering. http://localhost er tilstrekkelig for utvikling av et program på den lokale datamaskinen.

1. I den nye appregistreringen går du til **API-tillatelser**.

1. Velg **Legg til en tillatelse**, og velg **Customer Insights** i sideruten.

1. For **Tillatelsestype** velger du **Delegerte tillatelser** og velger deretter tillatelsen **user_impersonation**.

1. Velg **Legg til tillatelser**. Hvis du trenger tilgang til API-en uten at en bruker logger på, ser du gjennom [Server-til-server-programtillatelser](#server-to-server-application-permissions).

1. Velg **Gi admin-tillatelse for ...** for å fullføre appregistreringen.

Du kan bruke program-/klient-ID-en for denne appregistreringen med Microsoft Authentication Library (MSAL) for å få et bærertoken for å sende forespørselen til API-en.

Hvis du vil ha mer informasjon om MSAL, kan du se [Oversikt over Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Hvis du vil ha mer informasjon om appregistrering i Azure, kan du se [Den nye appregistreringsopplevelsen i Azure Portal](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

Hvis du vil ha informasjon om hvordan du bruker API-ene i klientbibliotekene, kan du se [Customer Insights-klilentbiblioteker](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Server-til-server-programtillatelser

[Delen for appregistrering](#create-a-new-app-registration-in-the-azure-portal) beskriver hvordan du registrerer en app som krever at brukeren logger på for godkjenning. Lær hvordan du oppretter en appregistrering som ikke trenger brukermedvirkning, og som kan kjøres på en server.

1. Gå til **API-tillatelser** i appregistreringen i Azure Portal.

1. Velg **Legg til en tillatelse**, og velg **Customer Insights** i sideruten.

1. For **Tillatelsestype** velger du **Apptillatelser** og velger deretter tillatelsen **CustomerInsights.Api.All**.

1. Velg **Legg til tillatelser**.

1. Du må legge til en tjenestekontohaver for at du skal kunne gi administratorsamtykke for denne apptillatelsen.

   1. Installer Azure Active Directory (AD) PowerShell-modulen: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Koble til AD-kontoen: `Connect-AzureAD -TenantId <your tenant id>`. Du finner leier-ID-en din under **Oversikt** > **Azure Active Directory**.
   1. Kjør følgende kommando for å legge til en Azure AD-tjenestekontohaver: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"`. AppId-parameteren gjelder for API-appen for Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Eksempel på tjenestekontohaver":::

1. Gå tilbake til **API-tillatelser** for appregistreringen.

1. Velg **Gi admin-tillatelse for ...** for å fullføre appregistreringen.

1. For å fullføre må vi legge til navnet på appregistreringen som en bruker i Customer Insights.    
   Åpne Customer Insights, gå til **Administrasjon** > **Tillatelser**, og velg **Legg til bruker**.

1. Søk etter navnet på appregistreringen, velg det fra søkeresultatene, og velg **Lagre**.

## <a name="customer-insights-client-libraries"></a>Customer Insights-klientbiblioteker

Denne delen hjelper deg med å komme i gang med å bruke klientbibliotekene som er tilgjengelige for API-ene i Customer Insights.

### <a name="c-nuget"></a>C# NuGet

Lær hvordan du kommer i gang med C#-klientbibliotekene fra NuGet.org. Hvis du vil ha mer informasjon om NuGet-pakken, kan du se [Microsoft.Dynamics.CustomerInsights.API](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). For øyeblikket målretter denne pakken seg mot rammeverkene netstandard2.0 og netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Legge til C#-klientbiblioteket i et C#-prosjekt

1. I Visual Studio åpner du **Pakkebehandling for NuGet** for prosjektet.

1. Søk etter **Microsoft.Dynamics.CustomerInsights.Api**.

1. Velg **Installer** for å legge til pakken i prosjektet.
   Du kan også kjøre denne kommandoen i **pakkebehandlingskonsollen for NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Legg til NuGet-pakken i Visual Studio-prosjektet":::

#### <a name="use-the-c-client-library"></a>Bruke C#-klientbiblioteket

1. Bruk [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) for å få et `AccessToken` ved å bruke den eksisterende [Azure-appregistreringen](#create-a-new-app-registration-in-the-azure-portal).

1. Når du har godkjent og skaffet deg et token, kan du konstruere en ny eller bruke en eksisterende `HttpClient` med den ekstra **godkjenningen DefaultRequestHeaders** angitt til **Bærer <access token>** og **Ocp-Apim-Subscription-Key** angitt til [**abonnementsnøkkelen** fra Customer Insights-miljøet](#get-started-trying-the-customer-insights-apis).    
   Tilbakestill **Godkjenning**-hodet når det er nødvendig. For eksempel når tokenet utløper.

1. Send denne `HttpClient` til konstruksjonen av `CustomerInsights`-klienten.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Eksempel på httpclient":::

1. Foreta kall til klienten for utvidelsesmetoder, for eksempel `GetAllInstancesAsync`. Hvis tilgang til den underliggende `Microsoft.Rest.HttpOperationResponse` foretrekkes, bruker du http-meldingsmetoder, for eksempel `GetAllInstancesWithHttpMessagesAsync`.

1. Svaret vil sannsynligvis være av typen `object` fordi metoden kan returnere flere typer (for eksempel `IList<InstanceInfo>` og `ApiErrorResult`). Hvis du vil kontrollere returtypen, kan du endre objektene på en sikker måte til svartypene som er angitt på [siden API-detaljer](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for den operasjonen.    
   Hvis du trenger mer informasjon om forespørselen, kan du bruke **http-meldingsmetodene** til å få tilgang råsvarobjektet.
