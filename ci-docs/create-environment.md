---
title: 'Veiledning: opprett et nytt miljø'
description: Fremgangsmåte for å opprette miljøer i Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 33c8910b7a4dd8723c0d62f2e28228cd2d8df4b7
ms.sourcegitcommit: 5716025eb4828425ca237377b02a892de8689f4a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2022
ms.locfileid: "9142831"
---
# <a name="how-to-create-a-new-environment"></a>Veiledning: opprett et nytt miljø

Når du har [kjøpt en abonnementslisens for Dynamics 365 Customer Insights](paid-license.md), mottar den globale administrator for Microsoft 365-leieren en e-post som inviterer dem til å opprette miljøet. Gå til [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) for å komme i gang. I dette scenarioet kan du gå direkte til [Trinn 1: Oppgi grunnleggende informasjon](#step-1-provide-basic-information).

Når det første miljøet er opprettet, kan den globale administrator for Microsoft 365-leieren [legge til brukere fra organisasjonen som administratorer](permissions.md). Fremover kan disse administratorene administrere brukere og miljøer. Hvis organisasjonen kjøper mer enn én lisens for Customer Insights, [kontakter du kundestøtteteamet](https://go.microsoft.com/fwlink/?linkid=2079641) for å øke antallet tilgjengelige miljøer. Hvis du vil ha mer informasjon om kapasitet og kapasitet for tillegg, kan du se [lisensveiledningen for Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Hvis du vil prøve tjenesten, kan du se [Konfigurere et prøvemiljø](trial-signup.md).

## <a name="prerequisites"></a>Forutsetning

Du må ha [administratortillatelser](permissions.md) i Customer Insights for å opprette eller administrere miljøer.

## <a name="start-the-environment-creation-process"></a>Start prosessen for miljøoppretting

1. Åpne miljøvelgeren og velg **+ Ny**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Velg miljøvelgeren.":::

1. Følg den veiledede opplevelsen som er beskrevet i avsnittene nedenfor, for å gi deg all nødvendig informasjon for et nytt miljø. Hvis du konfigurerte et miljø tidligere, kan du også [kopiere konfigurasjonen](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Trinn 1: Oppgi grunnleggende informasjon

I trinnet for **Grunnleggende informasjon** velger du om du vil opprette et miljø fra bunnen av eller [kopiere data fra et annet miljø](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialogboks for å opprette et nytt Customer Insights-miljø.":::

Angi følgende detaljer:

- **Navn**: Navnet på dette miljøet. Dette feltet er allerede fylt ut hvis du har kopiert et eksisterende miljø, men du kan endre det.
- **Velg forretningen**: Velg primærmålgruppe for det nye miljøet. Du kan arbeide med individuelle kunder (B-til-C) eller [forretningskontoer](work-with-business-accounts.md) (B-til-B). Hvis organisasjonen hovedsakelig gjør forretninger med enkeltpersoner, for eksempel en forhandler eller en kaffebar, velger du den enkeltforbrukere. Hvis hovedmålgruppen er andre selskaper, for eksempel en bilprodusent eller et papirfirma, velger du forretningskontoer.
- **Type**: Velg om du vil opprette et produksjons- eller sandkassemiljø. Sandkassemiljøer tillater ikke oppdatering av planlagte data og er beregnet for forhåndsimplementering og testing. Sandkassemiljøer bruker samme målgruppe som produksjonsmiljøet som er valgt.
- **Område**: Området som servicen er distribuert i, og driftet. Hvis du vil [bruke din egen Azure Data Lake Storage-konto](own-data-lake-storage.md) eller [koble til en eksisterende Microsoft Dataverse-organisasjon](customer-insights-dataverse.md), må Customer Insights-miljøet være i samme område.

## <a name="step-2-configure-data-storage"></a>Trinn 2: Konfigurere datalagring

Velg hvor du vil lagre dataene fra Customer Insights, i trinnet **Datalagring**.

Du kan velge mellom to alternativer:

- **Customer Insights-lagring**: Datalagring administreres av Customer Insights-teamet. Det er standardalternativet og med mindre det er spesifikke krav til å lagre data i din egen lagringskonto, anbefaler vi å bruke dette alternativet.
- **Azure Data Lake Storage**: Angi din egen Azure Data Lake Storage-konto for å lagre dataene slik at du har full kontroll over hvor dataene er lagret. Hvis du vil ha mer informasjon, kan du se [Bruk din egen Azure Data Lake Storage-konto](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Velg foretrukket alternativ for å lagre dataene.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Trinn 3: Koble til Microsoft Dataverse

Trinnet **Microsoft Dataverse** lar deg koble til Customer Insights med Dataverse-miljøet. Del data med Dataverse-miljø for å bruke dem med forretningsprogrammer basert på Dataverse, for eksempel Dynamics 365 Marketing eller modelldrevne apper i Power Apps.

La dette feltet stå tomt hvis du ikke har ditt eget Dataverse-miljø, så oppretter vi et for deg.

Hvis du vil ha mer informasjon, kan du se [Arbeid med Customer Insights-data i Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datadeling med Microsoft Dataverse automatisk aktivert for netto nye miljøer":::

### <a name="step-4-finalize-the-settings"></a>Trinn 4: Fullfør innstillingen

Gå gjennom alle de angitte innstillingene i trinnet **Se gjennom**. Når alt ser ut til å være ferdig, velger du **Opprett** for å konfigurere miljøet.

Du kan endre noen av innstillingene senere. Du finner mer informasjon under [Behandle miljøer](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbeide med det nye miljøet

Les gjennom følgende artikler for å hjelpe deg å komme i gang med å konfigurere Customer Insights:

- [Legg til flere brukere og tilordne tillatelser](permissions.md).
- [Innta datakildene](data-sources.md) og kjør dem gjennom [dataforeningsprosessen](data-unification.md) for å få [enhetlige kundeprofiler](customer-profiles.md).
- [Suppler de enhetlige kundeprofilene](enrichment-hub.md) eller [kjør prediktive modeller](predictions-overview.md).
- [Opprett segmenter](segments.md) for å gruppere kunder og [mål](measures.md) for å gjennomgå KPI-er.
- [Konfigurer tilkoblinger](connections.md) og [eksporter](export-destinations.md) for å behandle delsett av dataene i andre programmer.

## <a name="copy-the-environment-configuration"></a>Kopier miljøkonfigurasjonen

Som administrator kan du velge å kopiere konfigurasjonen fra et eksisterende miljø når du oppretter et nytt.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skjermbilde av innstillingsalternativene i miljøinnstillingene.":::

Det vises en liste over alle tilgjengelige miljøer i organisasjonen, der du kan kopiere data fra.

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

## <a name="set-up-a-copied-environment"></a>Definere et kopiert miljø

Når du kopierer miljøkonfigurasjonen, må du gå gjennom noen ekstra trinn for å bekrefte legitimasjon:

- Kundeprofiler. Først autentiserer og innhenter du datakildene dine og kjører dataforeningen for å opprette kundeprofilene på nytt.
- Legitimasjon for datakilde. Du må angi legitimasjonen for hver datakilde for å godkjenne og oppdatere datakildene manuelt.
- Datakilder fra mappen Common Data Model og Dataverse. Du må opprette datakildene manuelt med samme navn som i kildemiljøet.
- Tilkoblingshemmeligheter som brukes til eksporter og tillegg. Du må godkjenne tilkoblingene på nytt og deretter reaktivere suppleringer og eksporter.

Du ser en bekreftelsesmelding når det kopierte miljøet er opprettet. Velg **Gå til datakilder** for å vise listen over datakilder.

Alle datakildene vil vise statusen **Legitimasjon kreves**. Rediger datakildene, og angi legitimasjonen for å oppdatere dem.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste over datakilder som ble kopiert og trenger godkjenning.":::

Etter at du har oppdatert datakildene, går du til **Data** > **Samle**. Her finner du innstillinger fra kildemiljøet. Rediger dem etter behov, eller velg **Kjør** for å starte prosessen med datasamling og opprette den enhetlige kundeenheten.

Når datasamlingen er fullført, kan du gå til **Mål** og **Segmenter** for å oppdatere dem også.

Før du reaktiverer eksporter og suppleringer, går du til **Admin** > **Tilkoblinger** for å godkjenne tilkoblingene på nytt i det nye miljøet.

[!INCLUDE [footer-include](includes/footer-banner.md)]
