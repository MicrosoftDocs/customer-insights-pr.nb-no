---
title: Arbeide med API-er for Customer Insights
description: Bruk API-er og forstå begrensninger.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387352"
---
# <a name="work-with-customer-insights-apis"></a>Arbeide med API-er for Customer Insights

Dynamics 365 Customer Insights inneholder API-er for å bygge dine egne programmer basert på dataene dine i Customer Insights.

> [!IMPORTANT]
> Detaljer om disse API-ene vises i [Customer Insights-API-referansen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). De inneholder tilleggsinformasjon om operasjoner, parametere og svar.

Prøv API-ene for Customer Insights, opprett en Azure-appregistrering, og kom i gang med klientbiblioteker.

## <a name="get-started-trying-the-customer-insights-apis"></a>Kom i gang med å prøve API-ene for Customer Insights

Aktiver API-er for Customer Insights, og prøv dem ut. En Customer Insights-administrator må aktivere API-tilgang til Customer Insights. Når tilgang er aktivert, kan alle brukere bruke API med abonnementsnøkkelen.

1. [Logg på](https://home.ci.ai.dynamics.com) to Customer Insights. Hvis du ikke har et abonnement ennå, kan du [registrere deg for en prøveversjon av Customer Insights](https://aka.ms/tryci).

1. Gå til **Administrator** > **Sikkerhet**, og velg fanen **APIer**.

1. Hvis API-tilgang til miljøet ikke er konfigurert, velger du **Aktiver**.

   Når du aktiverer API-ene, opprettes en primær og en sekundær abonnementsnøkkel for forekomsten som blir brukt i API-forespørslene. For å generere nøklene på nytt velger du **Generer primær på nytt** eller **Generer sekundær på nytt** på fanen **APIer**.

1. Velg [**Utforsk API-ene våre**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) for å teste API-ene.

1. Søk etter og velg en API-operasjon, og velg **Prøv den**.

   :::image type="content" source="media/try-api.png" alt-text="Slik tester du API-ene.":::

1. Angi verdien i rullegardinmenyen **Autorisasjon** til **Implisitt**. Hodet `Authorization`legges til med et bærertoken. Abonnementsnøkkelen fylles ut automatisk.
  
1. Du kan eventuelt legge til alle nødvendige spørringsparametere.

1. Bla til bunnen av side ruten, og velg **Send**.

   HTTP-svaret visses nederst i navigasjonsruten.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Opprett en ny appregistrering i Azure Portal

Opprett en ny [appregistrering](/graph/auth-register-app-v2) for å bruke Customer Insights-APIer i et Azure-program ved hjelp av delegerte tillatelser.

1. Fullfør [Kom i gang-delen](#get-started-trying-the-customer-insights-apis).

1. Logg på [Azure Portal](https://portal.azure.com) med kontoen som har tilgang til Customer Insights -dataene.

1. Søk etter og velg **Appregistreringer**.

1. Velg **Ny registrering**, angi et programnavn, og velg kontotypen.

   Du kan også legge til en URL-adresse for omdirigering. http://localhost er tilstrekkelig for utvikling av et program på den lokale datamaskinen.

1. Velg **Registrer**.

1. I den nye appregistreringen går du til **API-tillatelser**.

1. Velg **Legg til en tillatelse**, og velg **Dynamics 365 AI for Customer Insights** i sideruten.

1. For **Tillatelsestype** velger du **Delegerte tillatelser**, og deretter velger du **user_impersonation**-tillatelsen.

1. Velg **Legg til tillatelser**.

1. Velg **Gi admin-tillatelse for ...** for å fullføre appregistreringen.

1. For tilgang til API-en uten at en bruker logger på, går du til [Server-til-server-programtillatelser](#server-to-server-application-permissions).

Du kan bruke program-/klient-ID-en for denne appregistreringen med [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) for å få et bærertoken for å sende forespørselen til API-en.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Hvis du vil ha informasjon om hvordan du bruker API-ene i klientbibliotekene, kan du se [Customer Insights-klientbiblioteker](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Server-til-server-programtillatelser

Opprett en appregistrering som ikke trenger brukersamhandling, og som kan kjøres på en server.

1. Gå til **API-tillatelser** i appregistreringen i Azure Portal.

1. Velg **Legg til en tillatelse**.

1. Velg fanen **API-ene organisasjonen** bruker, og velg deretter **Dynamics 365 AI for Customer Insights** fra listen.

1. For **Tillatelsestype** velger du **Programtillatelser**, og deretter velger du **CustomerInsights.Api.All**-tillatelsen.

1. Velg **Legg til tillatelser**.

1. Gå tilbake til **API-tillatelser** for appregistreringen.

1. Velg **Gi admin-tillatelse for ...** for å fullføre appregistreringen.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Legg til navnet på appregistreringen som en bruker i Customer Insights.

   1. Åpne Customer Insights, gå til **Administrator** > **Sikkerhet** og velg **Legg til brukere**.

   1. Søk etter navnet på appregistreringen, velg det fra søkeresultatene, og velg **Lagre**.

## <a name="sample-queries"></a>Eksempelspørringer

For en kort liste over OData-eksempelspørringer for å arbeide med API-ene se: [OData-spørringseksempler](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insights-klientbiblioteker

Kom i gang med å bruke klientbibliotekene som er tilgjengelige for API-ene i Customer Insights. Du finner all bibliotekkildekode og alle eksempelprogrammer på [Customer Insights GitHub-siden](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Bruk C#-klientbibliotekene fra NuGet.org. For øyeblikket målretter denne pakken seg mot rammeverkene netstandard2.0 og netcoreapp2.0. Hvis du vil ha mer informasjon om NuGet-pakken, kan [du se Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Legge til C#-klientbiblioteket i et C#-prosjekt

1. I Visual Studio åpner du **Pakkebehandling for NuGet** for prosjektet.

1. Søk etter **Microsoft.Dynamics.CustomerInsights.Api**.

1. Velg **Installer** for å legge til pakken i prosjektet.

   Du kan også kjøre denne kommandoen i **pakkebehandlingskonsollen for NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Bruke C#-klientbiblioteket

1. Bruk [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) for å få et `AccessToken` ved å bruke den eksisterende [Azure-appregistreringen](#create-a-new-app-registration-in-the-azure-portal).

1. Når godkjenningen og innhentingen av et token er vellykket, konstruerer du et nytt eller bruker en eksisterende `HttpClient` med **DefaultRequestHeaders-godkjenningen** angitt til **Bærer "tilgangstoken"** og **Ocp-Apim-Subscription-Key** satt til [**abonnementsnøkkel** fra Customer Insights-miljøet](#get-started-trying-the-customer-insights-apis).   

   Tilbakestill **Godkjenning**-hodet når det er nødvendig. For eksempel når tokenet utløper.

1. Send denne `HttpClient` til konstruksjonen av `CustomerInsights`-klienten.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Foreta kall til klienten for utvidelsesmetoder, for eksempel `GetAllInstancesAsync`. Hvis tilgang til den underliggende `Microsoft.Rest.HttpOperationResponse` foretrekkes, bruker du http-meldingsmetoder, for eksempel `GetAllInstancesWithHttpMessagesAsync`.

1. Svaret vil sannsynligvis være av typen `object` fordi metoden kan returnere flere typer (for eksempel `IList<InstanceInfo>` og `ApiErrorResult`). Du sjekker returtypen ved å bruke objektene i svartypene som er angitt på [API-detaljsiden](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for operasjonen.

   Hvis du trenger mer informasjon om forespørselen, kan du bruke **http-meldingsmetodene** til å få tilgang råsvarobjektet.

### <a name="nodejs-package"></a>NodeJS-pakke

Bruk NodeJS-klientbibliotekene som er tilgjengelige via NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python-pakke

Bruk Python-klientbibliotekene som er tilgjengelige via PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
