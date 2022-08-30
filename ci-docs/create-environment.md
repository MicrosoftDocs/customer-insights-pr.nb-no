---
title: Opprett nytt miljø
description: Fremgangsmåte for å opprette miljøer i Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304256"
---
# <a name="create-a-new-environment"></a>Opprett nytt miljø

Når du har [kjøpt en abonnementslisens for Dynamics 365 Customer Insights](paid-license.md), mottar den globale administrator for Microsoft 365-leieren en e-post som inviterer dem til å opprette miljøet. Gå til [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) for å komme i gang. I dette scenarioet begynner du med [Trinn 1: Oppgi grunnleggende informasjon](#step-1-provide-basic-information).

Når det første miljøet er opprettet, kan den globale administratoren for Microsoft 365-leieren [legge til brukere fra organisasjonen som administratorer](permissions.md). Disse administratorene kan deretter administrere brukere og miljøer. Hvis organisasjonen kjøper mer enn én lisens for Customer Insights, [kontakter du kundestøtteteamet](https://go.microsoft.com/fwlink/?linkid=2079641) for å øke antallet tilgjengelige miljøer. Hvis du vil ha mer informasjon om kapasitet og kapasitet for tillegg, kan du se [lisensveiledningen for Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Når du kan opprette flere miljøer, går du til [Start prosessen for miljøoppretting](#start-the-environment-creation-process).

> [!TIP]
> Hvis du vil prøve tjenesten, kan du se [Konfigurere et prøvemiljø](trial-signup.md).

## <a name="prerequisites"></a>Forutsetning

[Administratortillatelser](permissions.md) i Customer Insights

## <a name="start-the-environment-creation-process"></a>Start prosessen for miljøoppretting

1. Åpne miljøvelgeren og velg **+ Ny**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Velg miljøvelgeren.":::

1. Følg den veiledede opplevelsen som er beskrevet i avsnittene nedenfor, for å gi deg all nødvendig informasjon for et nytt miljø.

## <a name="step-1-provide-basic-information"></a>Trinn 1: Oppgi grunnleggende informasjon

1. Velg om du vil opprette et miljø fra grunnen av eller kopiere data fra et annet miljø. [Kopiering av data fra et annet miljø](#copy-the-environment-configuration) krever ytterligere trinn.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialogboks for å opprette et nytt Customer Insights-miljø.":::

1. Angi følgende detaljer:

   - **Navn**: Navnet på dette miljøet. Dette feltet er allerede fylt ut hvis du har kopiert et eksisterende miljø, men du kan endre det.
   - **Velg virksomheten din**: Primær målgruppe for det nye miljøet: enkeltforbrukere (B2C) eller [forretningskontoer](work-with-business-accounts.md) (B2B). Hvis organisasjonen hovedsakelig gjør forretninger med enkeltpersoner, for eksempel en forhandler eller en kaffebar, velger du den enkeltforbrukere. Hvis hovedmålgruppen er andre selskaper, for eksempel en bilprodusent eller et papirfirma, velger du forretningskontoer.
   - **Type**: Miljøtype: produksjon eller sandkasse. Sandkassemiljøer tillater ikke oppdatering av planlagte data og er beregnet for forhåndsimplementering og testing. Sandkassemiljøer bruker samme målgruppe som produksjonsmiljøet som er valgt.
   - **Område**: Området der servicen er distribuert og driftet. Hvis du vil [bruke din egen Azure Data Lake Storage-konto](own-data-lake-storage.md) eller [koble til en eksisterende Microsoft Dataverse-organisasjon](customer-insights-dataverse.md), må Customer Insights-miljøet være i samme område.

1. Velg **Neste**.

## <a name="step-2-configure-data-storage"></a>Trinn 2: Konfigurere datalagring

1. Velg hvor du vil lagre Customer Insights-dataene:

   - **Customer Insights-lagring**: Datalagring administreres automatisk. Det er standardalternativet og med mindre det er spesifikke krav til å lagre data i din egen lagringskonto, anbefaler vi å bruke dette alternativet.
   - **Azure Data Lake Storage**: Din egen Azure Data Lake Storage-konto til lagring av dataene, slik at du har full kontroll over hvor dataene er lagret. Følg fremgangsmåten i [Bruk din egen Azure Data Lake Storage-konto](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Velg foretrukket alternativ for å lagre dataene.":::

1. Velg **Neste**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Trinn 3: Koble til Microsoft Dataverse

Hvis du har et Dataverse-miljø, kobler du til Customer Insights. Del data med Dataverse-miljø for å bruke dem med forretningsprogrammer basert på Dataverse, for eksempel Dynamics 365 Marketing eller modelldrevne apper i Power Apps.

1. Følg fremgangsmåten i [Arbeide med Customer Insights-data i Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="datadeling med Microsoft Dataverse automatisk aktivert for netto nye miljøer":::

1. Velg **Neste**.

## <a name="step-4-finalize-the-settings"></a>Trinn 4: Fullfør innstillingen

Se gjennom de angitte innstillingene. Når alt ser ut til å være ferdig, velger du **Opprett** for å konfigurere miljøet.

Hvis du vil endre noen av innstillingene senere, kan du se [Behandle miljøer](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbeide med det nye miljøet

Les gjennom følgende artikler for å hjelpe deg å komme i gang med å konfigurere Customer Insights:

- [Legg til flere brukere og tilordne tillatelser](permissions.md).
- [Innta datakildene](data-sources.md) og kjør dem gjennom [dataforeningsprosessen](data-unification.md) for å få [enhetlige kundeprofiler](customer-profiles.md).
- [Suppler de enhetlige kundeprofilene](enrichment-hub.md) eller [kjør prediktive modeller](predictions-overview.md).
- [Opprett segmenter](segments.md) for å gruppere kunder og [mål](measures.md) for å gjennomgå KPI-er.
- [Konfigurer tilkoblinger](connections.md) og [eksporter](export-destinations.md) for å behandle delsett av dataene i andre programmer.

## <a name="copy-the-environment-configuration"></a>Kopier miljøkonfigurasjonen

Hvis du som administrator velger å kopiere konfigurasjonen fra et eksisterende miljø, velger du fra listen over alle tilgjengelige miljøer i organisasjonen.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skjermbilde av innstillingsalternativene i miljøinnstillingene.":::

Følgende konfigurasjonsinnstillinger kopieres:

- Datakilder importert via Power Query
- Datasamlingskonfigurasjon
- Segments
- Mål
- Relasjoner
- Aktiviteter
- Søk- og filterindeks
- Eksporter
- Oppdater tidsplan
- Suppleringer
- Prediksjonsmodeller
- Rolletildelinger

### <a name="set-up-a-copied-environment"></a>Definere et kopiert miljø

Når du kopierer miljøkonfigurasjonen, vises en bekreftelsesmelding når det kopierte miljøet er opprettet. Utfør følgende trinn for å bekrefte legitimasjonen.

1. Velg **Gå til datakilder** for å vise listen over datakilder. Alle datakildene viser statusen **Legitimasjon kreves**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Liste over datakilder som ble kopiert og trenger godkjenning.":::

1. Rediger datakildene, og angi legitimasjonen for å oppdatere dem. Datakilder fra mappen Common Data Model og Dataverse må opprettes manuelt med samme navn som i kildemiljøet.

1. Etter at du har oppdatert datakildene, går du til **Data** > **Samle**. Her finner du innstillinger fra kildemiljøet. Rediger dem etter behov, eller velg **Samle** > **Samle kundeprofiler og avhengigheter** for å starte prosessen med datasamling og opprette den samlede kundeenheten.

   > [!TIP]
   > Når det gjelder forretningsforbindelser og kontakter, velger du **Samle forretningsforbindelser** > **Samle profiler og avhengigheter**.

1. Når datasamlingen er fullført, kan du gå til **Mål** og **Segmenter** for å oppdatere dem.

1. Gå til **Admin** > **Tilkoblinger** for å godkjenne tilkoblingene på nytt i det nye miljøet.

1. Gå til **Data** > **Supplering** og **Data** > **Eksporter** for å aktivere dem på nytt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
