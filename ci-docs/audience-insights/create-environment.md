---
title: Opprette miljøer i Customer Insights
description: Fremgangsmåte for å opprette miljøer med et lisensiert abonnement for Dynamics 365 Customer Insights.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 914af46d2d82f3556d149f2836680c902f826d50
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673403"
---
# <a name="create-an-environment-in-audience-insights"></a>Opprette et miljø i målgruppeinnsikt

Denne artikkelen forklarer hvordan du oppretter et nytt miljø etter at organisasjonen har kjøpt et Dynamics 365 Customer Insights-abonnement. 

Organisasjoner kan opprette *to* miljøer for hver Customer Insights-lisens. Hvis organisasjonen kjøper mer enn én lisens, [kontakter du kundestøtteteamet](https://go.microsoft.com/fwlink/?linkid=2079641) for å øke antallet tilgjengelige miljøer. Hvis du vil ha mer informasjon om kapasitet og tilleggskapasitet, kan du laste ned [lisensieringsveiledningen for Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Hvis du vil prøve tjenesten, kan du se [Konfigurere et prøvemiljø](../trial-signup.md).

## <a name="create-a-new-environment"></a>Opprett nytt miljø

Når du har kjøpt en abonnementslisens for Customer Insights, mottar den globale administrator for Microsoft 365-leieren en e-post som inviterer dem til å opprette miljøet. Gå til [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) for å komme i gang. 

En veiledet opplevelse hjelper deg gjennom trinnene for å samle inn all nødvendig informasjon om et nytt miljø. Du må ha [administratortillatelser](permissions.md) i målgruppeinnsikt for å opprette eller administrere miljøer.

1. I målgruppeinnsikt åpner du miljøvelgeren og velger **+ Ny**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Velg miljøvelgeren.":::

1. Følg den veiledede opplevelsen som er beskrevet i avsnittene nedenfor.

### <a name="step-1-provide-environment-information"></a>Trinn 1: Gi miljøinformasjon

I trinnet for **Grunnleggende informasjon** velger du om du vil opprette et miljø fra bunnen av eller [kopiere data fra et annet miljø](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialogboks for å opprette et nytt Customer Insights-miljø.":::

Angi følgende detaljer:
   - **Navn**: Navnet på dette miljøet. Dette feltet er allerede fylt ut hvis du har kopiert et eksisterende miljø, men du kan endre det.
   - **Velg forretningen**: Velg primærmålgruppe for det nye miljøet. Du kan arbeide med individuelle kunder (B-til-C) eller [forretningskontoer](work-with-business-accounts.md) (B-til-B).
   - **Type**: Velg om du vil opprette et produksjons- eller sandkassemiljø. Sandkassemiljøer tillater ikke oppdatering av planlagte data og er beregnet for forhåndsimplementering og testing. Sandkassemiljøer bruker samme målgruppe som produksjonsmiljøet som er valgt.
   - **Område**: Området som servicen er distribuert i, og driftet.

### <a name="step-2-configure-data-storage"></a>Trinn 2: Konfigurere datalagring

Velg hvor du vil lagre dataene fra målgruppeinnsikt, i trinnet **Datalagring**.

Du har to alternativer: **Customer Insights-lagring** (en Azure Data Lake som administreres av Customer Insights-teamet) og **Azure Data Lake Storage** (din egen Azure Data Lake Storage). Som standard er det merket av for lagringsalternativet Customer Insights.

:::image type="content" source="media/data-storage-environment.png" alt-text="Velg Azure Data Lake Storage du vil lagre målgruppeinnsiktsdata i.":::

Ved å lagre data til Azure Data Lake Storage godtar du at data overføres til og lagres på riktig geografisk sted for Azure Storage-kontoen. Denne plasseringen kan være forskjellig fra der dataene er lagret i Dynamics 365 Customer Insights. Finn ut mer om [Microsofts Klareringssenter](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights støtter for øyeblikket følgende:
> - Registrerte enheter fra Power BI-dataflyter som er lagret i en Microsoft Dataverse-administrert Data Lake.  
> - Azure Data Lake Storage-kontoer fra samme Azure-område som du valgte da du opprettet miljøet.
> - Azure Data Lake Storage-forretningsforbindelser som har *hierarkisk navneområde* aktivert.

For Azure Data Lake Storage-alternativet kan du velge mellom et ressursbasert alternativ og et abonnementsbasert alternativ for godkjenning. Hvis du vil ha mer informasjon, kan du se [Koble til en Azure Data Lake Storage-konto ved å bruke en Azure-tjenestekontohaver](connect-service-principal.md). **Beholder**-navnet vil være `customerinsights` og kan ikke endres.

Når systemprosesser som datainntak er fullført, oppretter systemet tilsvarende mapper i lagringskontoen du angav. Datafiler og *model.json*-filer opprettes og legges til i mapper basert på prosessnavnet.

Hvis du oppretter flere miljøer med Customer Insights og velger å lagre utdataenhetene fra disse miljøene i lagringskontoen, oppretter Customer Insights separate mapper for hvert miljø med `ci_environmentID` i beholderen.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Trinn 3: Koble til Microsoft Dataverse
   
Trinnet **Microsoft Dataverse** lar deg koble til Customer Insights med Dataverse-miljøet.

For å bruke [standard prediksjonsmodeller](predictions-overview.md#out-of-box-models) konfigurerer du datadeling med Dataverse. Du kan også aktivere datainntak fra lokale datakilder og angi URL-adressen som Microsoft Dataverse-miljøet administrerer. Velg **Aktiver datadeling** for å dele Customer Insights-utdata med en Dataverse-administrert datasjø.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Konfigurasjonsalternativer for å aktivere datadeling med Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights støtter ikke følgende datadelingsscenarioer:
> - Hvis du lagrer alle dataene til din egen Azure Data Lake Storage, vil du ikke kunne aktivere datadeling med en Dataverse-administrert datasjø.
> - Hvis du aktiverer datadeling med Dataverse, kan du ikke [opprette beregnede eller manglende verdier i en enhet](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Trinn 4: Fullfør innstillingen

Gå gjennom alle de angitte innstillingene i trinnet **Se gjennom**. Når alt ser ut til å være ferdig, velger du **Opprett** for å konfigurere miljøet. 

Du kan også endre de fleste av innstillingene senere. Du finner mer informasjon under [Behandle miljøer](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbeide med det nye miljøet

Les gjennom følgende artikler for å hjelpe deg å komme i gang med å konfigurere Customer Insights: 

- [Legg til flere brukere og tilordne tillatelser](permissions.md).
- [Innta datakildene](data-sources.md) og kjør dem gjennom [dataforeningsprosessen](data-unification.md) for å få [enhetlige kundeprofiler](customer-profiles.md).
- [Suppler de enhetlige kundeprofilene](enrichment-hub.md) eller [kjør prediktive modeller](predictions-overview.md).
- [Opprett segmenter](segments.md) for å gruppere kunder og [mål](measures.md) for å gjennomgå KPI-er.
- [Konfigurer tilkoblinger](connections.md) og [eksporter](export-destinations.md) for å behandle delsett av dataene i andre programmer.
