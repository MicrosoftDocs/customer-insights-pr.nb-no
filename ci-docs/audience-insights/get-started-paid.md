---
title: Opprett og konfigurer en betalt lisens for Customer Insights
description: Fremgangsmåte for å få et lisensiert abonnement for Dynamics 365 Customer Insights og konfigurere det.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034464"
---
# <a name="get-started-with-a-paid-subscription"></a>Kom i gang med et betalt abonnementet

Denne artikkelen forklarer hvordan du oppretter et nytt miljø etter at organisasjonen har kjøpt et Dynamics 365 Customer Insights-abonnement. Hvis du vil kjøpe Customer Insights, vises kontaktalternativene våre på [Dynamics 365 Customer Insights-nettstedet](https://dynamics.microsoft.com/ai/customer-insights/). 

Hvis du vil prøve tjenesten og funksjonene, kan du se [Konfigurer et prøveversjonsmiljø](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Opprette et miljø i en eksisterende organisasjon

Når du har kjøpt en abonnementslisens for Customer Insights, mottar den globale administrator for Microsoft 365-leieren en e-post som inviterer dem til å opprette miljøet. Gå til [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) for å komme i gang. 

Customer Insights er ikke lisensiert per bruker, så den vises ikke i Lisenser-området. Hvis du leter etter lisensen i administrasjonssenteret for Microsoft 365, kan du gå til **Dine produkter**. 

> [!NOTE]
> Organisasjoner kan opprette *to* miljøer for hver Customer Insights-lisens. Hvis organisasjonen din kjøper flere enn én lisens, kan du [kontakte kundestøtteteamet](https://go.microsoft.com/fwlink/?linkid=2079641) for å øke antallet tilgjengelige miljøer. Hvis du vil ha mer informasjon om kapasitet og tilleggskapasitet, kan du laste ned [lisensieringsveiledningen for Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Slik oppretter du et miljø:

1. I dialogboksen **Opprett et miljø** velger du **Nytt miljø**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialogboks for å opprette et nytt Customer Insights-miljø.":::

   Vi anbefaler at du begynner å konfigurere et miljø fra grunnen av. Hvis du er administrator eller medlem av et prøveversjonsmiljø, kan du imidlertid [kopiere data fra et annet miljø](manage-environments.md#copy-the-environment-configuration) ved å velge **Kopier fra eksisterende miljø**. Det vises en liste over alle tilgjengelige miljøer i organisasjonen, der du kan kopiere data fra.

1. Angi følgende detaljer:
   - **Navn**: Navnet på dette miljøet. Dette feltet er allerede fylt ut hvis du har kopiert et eksisterende miljø, men du kan endre det.
   - **Område**: Området som servicen er distribuert i, og driftet.
   - **Type**: Velg om du vil opprette et produksjons- eller sandkassemiljø. Sandkassemiljøer tillater ikke oppdatering av planlagte data og er beregnet for forhåndsimplementering og testing.
   
1. Du kan eventuelt velge **Avanserte innstillinger**:

   - **Lagre alle data i**: Angir hvor du vil lagre utdataene som er generert av Customer Insights. Du har to alternativer: **Customer Insights-lagring** (et Azure Data Lake som administreres av Customer Insights-teamet) og **Azure Data Lake Storage** (din egen Azure Data Lake Storage). Som standard er det merket av for lagringsalternativet Customer Insights.

     > [!NOTE]
     > Når du lagrer data i Azure Data Lake Storage, godtar du at dataene overføres til og lagres i den riktige geografiske plasseringen for denne Azure Storage-kontoen, som kan variere fra der dataene lagres i Dynamics 365 Customer Insights. [Finn ut mer om Microsofts klareringssenter.](https://www.microsoft.com/trust-center)
     >
     > For øyeblikket lagres enheter fra Power BI-dataflyter i den administrerte Microsoft Dataverse-datasjøen. 
     > 
     > Vi støtter bare Azure Data Lake Storage-kontoer fra samme Azure-område du valgte da du opprettet miljøet. 
     > 
     > Vi støtter bare Azure Data Lake Storage-kontoer som har hierarkisk navneområde aktivert.


   - For Azure Data Lake Storage-alternativet kan du velge mellom et ressursbasert alternativ og et abonnementsbasert alternativ for godkjenning. Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md). **Beholder**-navnet kan ikke endres og er `customerinsights`.
   
   - Hvis du vil bruke [bruksklare modeller](predictions-overview.md#out-of-box-models), konfigurere datadeling med Microsoft Dataverse eller aktivere datainntak fra lokal datakilder, må du angi nettadressen til Microsoft Dataverse-miljøet under **Konfigurer datadeling med Microsoft Dataverse og aktiver flere funksjoner**. Velg **Aktiver datadeling** for å dele Customer Insights-utdata med en Microsoft Dataverse-administrert datasjø.

     > [!NOTE]
     > - Det er for øyeblikket ikke støtte for datadeling med Microsoft Dataverse-styrt datasjø når du lagrer alle dataene i din egen Azure Data Lake Storage.
     > - [Prediksjon av manglende verdier i en enhet](predictions.md) støttes for øyeblikket ikke når du aktiverer datadeling med Microsoft Dataverse-administrert Data Lake.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Konfigurasjonsalternativer for å aktivere datadeling med Microsoft Dataverse.":::

   Når systemprosesser som datainntak er fullført, opprettes tilsvarende mapper i lagringskontoen du angav. Datafiler og model.json-filer opprettes og legges til i mapper basert på prosessnavnet.

   Hvis du oppretter flere miljøer i Customer Insights og velger å lagre enhetene fra disse miljøene i lagringskontoen, blir det opprettet separate mapper for hvert miljø med ci_<environmentid> i beholderen.

1. Velg **Opprett** for å konfigurere miljøet. 

## <a name="configure-an-environment"></a>Konfigurer et miljø

Se gjennom følgende artikler for å hjelpe deg med å komme i gang med konfigureringen av Customer Insights. 

- [Legg til flere brukere og tilordne tillatelser](permissions.md).
- [Innta datakildene](data-sources.md) og kjør dem gjennom [dataforeningsprosessen](data-unification.md) for å få [enhetlige kundeprofiler](customer-profiles.md).
- [Suppler de enhetlige kundeprofilene](enrichment-hub.md) eller [kjør prediktive modeller](predictions-overview.md).
- Opprett [segmenter](segments.md) for å gruppere kunder og nøkkelindikatorer for [målgjennomgang](measures.md).
- Konfigurer [tilkoblinger](connections.md) og [eksporter](export-destinations.md) for å behandle delsett av dataene i andre programmer.
