---
title: Opprette og behandle miljøer
description: Lær hvordan du registrerer deg for tjenesten og hvordan du administrerer miljøer.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/29/2022
ms.locfileid: "8492016"
---
# <a name="manage-environments"></a>Behandle miljøer

## <a name="switch-environments"></a>Bytt miljøer

Velg kontrollen **Miljø** øverst i høyre hjørne på siden for å endre miljøer.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Skjermbilde av kontrollen for å bytte miljø.":::

Administratorer kan [opprette](create-environment.md) og behandle miljøer.

## <a name="edit-an-existing-environment"></a>Redigere et eksisterende miljø

Du kan redigere noen av detaljene i eksisterende miljøer.

1.  Velg **Miljø**-velgeren i overskriften i appen.

2.  Velg **Rediger**-ikonet.

3. I **Rediger miljø**-boksen kan du oppdatere miljøinnstillingene.

Hvis du vil ha mer informasjon om miljøinnstillinger, kan du se [Opprette et nytt miljø](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Koble til Microsoft Dataverse
   
Trinnet **Microsoft Dataverse** lar deg koble til Customer Insights med Dataverse-miljøet. 

Oppgi ditt eget Microsoft Dataverse-miljø for å dele data (profiler og innsikt) med forretningsprogrammer basert på Dataverse, for eksempel Dynamics 365 Marketing eller modelldrevne apper i Power Apps.

For å bruke [standard prediksjonsmodeller](predictions-overview.md#out-of-box-models) konfigurerer du datadeling med Dataverse. Du kan også aktivere datainntak fra lokale datakilder og angi URL-adressen som Microsoft Dataverse-miljøet administrerer.

Aktivering av datadeling med Microsoft Dataverse ved å merke av for datadeling utløser en engangs full oppdatering av datakildene og alle andre prosesser.

> [!IMPORTANT]
> 1. Customer Insights og Dataverse må være i samme region for å aktivere datadeling.
> 1. Du må ha en global administrator-rolle i Dataverse-miljøet. Kontroller om dette [Dataverse-miljøet er tilknyttet](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) bestemte sikkerhetsgrupper, og kontroller at du er lagt til i disse sikkerhetsgruppene.
> 1. Ingen eksisterende Customer Insights-miljø er allerede tilknyttet Dataverse-miljøet. Lær hvordan du [fjerner en eksisterende tilkobling til et Dataverse-miljø ](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Konfigurasjonsalternativer for å aktivere datadeling med Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktivere datadeling med Dataverse fra din egen Azure Data Lake Storage (forhåndsversjon)

Hvis miljøet er konfigurert til å bruke Azure Data Lake Storage for å lagre Customer Insights-data, krever aktivering av datadeling med Microsoft Dataverse litt ekstra konfigurasjon.

1. Opprett to sikkerhetsgrupper i Azure-abonnementet – én **Leser**-sikkerhetsgruppe og én **Bidragsyter**-sikkerhetsgruppe, og angi Microsoft Dataverse-tjenesten som eier for begge sikkerhetsgruppene.
2. Administrer tilgangskontrollisten (ACL) i CustomerInsights-beholderen på lagringskontoen via disse sikkerhetsgruppene. Legg til Microsoft Dataverse-tjenesten og eventuelle Dataverse-baserte forretningsprogrammer som Dynamics 365 Marketing i  **Leser**-sikkerhetsgruppen med **skrivebeskyttede** tillatelser. Legg *bare* til Customers Insights-programmet i **Bidrag**-sikkerhetsgruppen for å gi **lese- og skrive**-tillatelser til å skrive profiler og innsikt.
   
#### <a name="prerequisites"></a>Krav

For å kunne kjøre PowerShell-skriptene må du importere følgende tre moduler: 

1. Installer den nyeste versjonen av [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. Velg Windows-tasten på tastaturet på PC-en, søk etter **Windows PowerShell**, og velg **Kjør som administrator**.
   1. I PowerShell-vinduet som åpnes, skriver du inn `Install-Module AzureAD`.
2. Importer tre moduler.
    1. I PowerShell-vinduet angir du `Install-Module -Name Az.Accounts` og følger trinnene. 
    1. Gjenta for `Install-Module -Name Az.Resources` og `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Konfigurasjonstrinn

1. Last ned de to PowerShell-skriptene du må kjøre fra teknikerens [GitHub-repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Du må ha *leieradmin*-tilgang for å kjøre dette PowerShell-skriptet. 
       - Dette PowerShell-skriptet oppretter to sikkerhetsgrupper på Azure-abonnementet. Ett for lesergruppe og et annet for bidragsytergruppe, og vil gjøre Microsoft Dataverse-tjenesten til eier for begge disse sikkerhetsgruppene.
       - Kjør dette PowerShell-skriptet i Windows PowerShell ved å angi Azure-abonnements-IDen som inneholder Azure Data Lake Storage. Åpne PowerShell-skriptet i et redigeringsprogram for å se gjennom tilleggsinformasjon og logikken som er implementert.
       - Lagre begge ID-verdiene for sikkerhetsgruppe som genereres av dette skriptet, fordi vi skal bruke dem i skriptet `ByolSetup.ps1`.
       
        > [!NOTE]
        > Oppretting av sikkerhetsgrupper kan deaktiveres for leieren. I det tilfellet kreves det en manuell konfigurasjon og Azure AD-administratoren må [aktivere oppretting av sikkerhetsgrupper](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Du må ha tillatelsene for *Eier av Storage Blob Data* på lagringskonto-/beholdernivå for å kjøre dette skriptet, ellers opprettes det et skript for deg. Rolletilordningen kan fjernes manuelt etter at skriptet er kjørt.
        - Dette PowerShell-skriptet legger til den nødvendige rollebaserte tilgangskontrollen (RBAC) for Microsoft Dataverse-tjenesten og eventuelle Dataverse-baserte forretningsprogrammer. Den oppdaterer også tilgangskontrollisten (ACL) i CustomerInsights-beholderen for sikkerhetsgruppene som opprettes med skriptet `CreateSecurityGroups.ps1`. Bidragsyteregruppen har også *RWX* tillatelse og lesergruppen har bare *r-x*-tillatelse.
        - Kjør dette PowerShell-skriptet i Windows PowerShell ved å angi Azure-abonnement-IDen som inneholder Azure Data Lake Storage, lagringskontonavnet, ressursgruppenavnet og id-verdier for leser og bidragsyter-sikkerhetsgruppe. Åpne PowerShell-skriptet i et redigeringsprogram for å se gjennom tilleggsinformasjon og logikken som er implementert.
        - Kopier utdatastrengen etter at skriptet er kjørt. Utdatastrengen ser slik ut: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Angi utdatastrengen som kopieres ovenfor, i **Tillatelsesidentifikator**-feltet i miljøkonfigurasjonstrinnet for Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurasjonsalternativer for å aktivere datadeling fra din egen Azure Data Lake Storage med Microsoft Dataverse.":::

Customer Insights støtter ikke følgende datadelingsscenarioer:
- Hvis du aktiverer datadeling med Dataverse, kan du ikke [opprette beregnede eller manglende verdier i en enhet](predictions.md).
- Hvis du aktiverer datadeling med Dataverse, kan du ikke vise valgfrie innebygde PowerBI-rapporter i Customer Insights-miljøet.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Fjern en eksisterende tilkobling til et Dataverse-miljø

Når du kobler til et Dataverse-miljø, vises feilmeldingen **Denne CDS-organisasjonen er allerede knyttet til en annen Customer Insights-forekomst**, betyr at Dataverse-miljøet allerede er brukt i et Customer Insights-miljø. Du kan fjerne den eksisterende tilkoblingen som en global administrator i Dataverse-miljøet. Det kan ta noen timer før endringene fylles ut.

1. Gå til [Power Apps](https://make.powerapps.com).
1. Velg miljøet fra miljøvelgeren.
1. Gå til **Løsninger**
1. Avinstaller eller slett løsningen kalt **Dynamics 365 Customer Insights-tillegg for kundekort (forhåndsvisning)**.

OR 

1. Åpne Dataverse-miljøet.
1. Gå til **Avanserte innstillinger** > **Løsninger**.
1. Avinstaller **CustomerInsightsCustomerCard**-løsningen.

## <a name="copy-the-environment-configuration"></a>Kopier miljøkonfigurasjonen

Som administrator kan du velge å kopiere konfigurasjonen fra et eksisterende miljø når du oppretter et nytt. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skjermbilde av innstillingsalternativene i miljøinnstillingene.":::

Det vises en liste over alle tilgjengelige miljøer i organisasjonen, der du kan kopiere data fra.

Følgende konfigurasjonsinnstillinger kopieres:

- Samlede/importerte datakilder
- Konfigurasjon av forening av data (tilordning, samsvar, sammenslåing)
- Segmenter
- Mål
- Relasjoner
- Aktiviteter
- Søk- og filterindeks
- Eksportmål
- Planlagt oppdatering
- Suppleringer
- Modelladministrasjon
- Rolletildelinger

## <a name="set-up-a-copied-environment"></a>Definere et kopiert miljø

Når du kopierer miljøkonfigurasjonen, kopieres *ikke* følgende data:

- Kundeprofiler.
- Legitimasjon for datakilde. Du må angi legitimasjonen for hver datakilde og oppdatere datakildene manuelt.
- Datakilder fra mappen Common Data Model og Dataverse-administrert datasjø. Du må opprette disse datakildene manuelt med samme navn som i kildemiljøet.
- Tilkoblingshemmeligheter som brukes til eksporter og tillegg. Du må godkjenne tilkoblingene på nytt og deretter reaktivere suppleringer og eksporter. 

Når du kopierer et miljø, vises en bekreftelsesmelding om at det nye miljøet er opprettet. Velg **Gå til datakilder** for å vise listen over datakilder.

Alle datakildene vil vise statusen **Legitimasjon kreves**. Rediger datakildene, og angi legitimasjonen for å oppdatere dem.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste over datakilder som ble kopiert og trenger godkjenning.":::

Etter at du har oppdatert datakildene, går du til **Data** > **Samle**. Her finner du innstillinger fra kildemiljøet. Rediger dem etter behov, eller velg **Kjør** for å starte prosessen med datasamling og opprette den enhetlige kundeenheten.

Når datasamlingen er fullført, kan du gå til **Mål** og **Segmenter** for å oppdatere dem også.

Før du reaktiverer eksporter og suppleringer, går du til **Admin** > **Tilkoblinger** for å godkjenne tilkoblingene på nytt i det nye miljøet.

## <a name="change-the-owner-of-an-environment"></a>Endre eieren av et miljø

Selv om flere brukere kan ha administratortillatelser i Customer Insights, er bare én bruker eieren av et miljø. Som standard er det administratoren som oppretter et miljø til å begynne med. Som administrator for et miljø kan du tilordne eierskap til en annen bruker med administratortillatelser.

1. Velg **Miljø**-velgeren i overskriften i appen.

1. Velg **Rediger**-ikonet.

1. Gå til trinnet **Grunnleggende informasjon** i boksen **Rediger miljø**.

1. Velg den nye eieren av miljøet i feltet **Endre eier av miljø**-feltet.  

1. Velg **Se gjennom og fullfør**, og **Oppdater** for å ta i bruk endringene. 

## <a name="claim-ownership-of-an-environment"></a>Kreve eierskap for et miljø

Hvis eieren av et miljø forlater organisasjonen eller brukerkontoen deres slettes, har ikke miljøet noen eier. En bruker med administratortillatelser kan kreve eierskap og bli ny eier. De kan fortsette å eie miljøet eller [endre eierskapet til en annen administrator](#change-the-owner-of-an-environment). 

Hvis du vil kreve eierskap , velger du **Ta eierskap**-knappen som vises øverst på hver side i Customer Insights når den opprinnelige eieren sluttet i organisasjonen.

## <a name="reset-an-existing-environment"></a>Tilbakestille et eksisterende miljø

Som eier av et miljø kan du tilbakestille et miljø til en tom tilstand hvis du vil slette alle konfigurasjoner og fjerne de innlagte dataene.

1.  Velg **Miljø**-velgeren i overskriften i appen. 

2.  Velg miljøet du vil tilbakestille, og velg ellipsen (**...**). 

3. Velg **Tilbakestill**-alternativet. 

4.  Bekreft slettingen ved å skrive inn miljønavnet og velge **Tilbakestill**.

## <a name="delete-an-existing-environment"></a>Slette et eksisterende miljø

Som eier av et miljø kan du slette et miljø du administrerer.

1.  Velg **Miljø**-velgeren i overskriften i appen.

2.  Velg miljøet du vil tilbakestille, og velg ellipsen (**...**). 

3. Velg **Slett**-alternativet. 

4.  Bekreft slettingen ved å angi miljønavnet og velge **Slett**.

> [!NOTE]
> Sletting av et miljø fjerner ikke tilknytningen til et Dataverse-miljø. Lær hvordan du [fjerner en eksisterende tilkobling til et Dataverse-miljø](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
