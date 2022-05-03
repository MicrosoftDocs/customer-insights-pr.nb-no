---
title: DSR-forespørsler (Data Subject Rights) under GDPR | Microsoft Docs
description: Svare på dataemneforespørsler for Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 5b39452d7a4612242739e8000e57217954c71289
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641528"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>DSR-forespørsler (Data Subject Rights) under GDPR

EUs personvernforordning (GDPR) har vært gjeldende siden 25. mai 2018. Den gir personer betydelige rettigheter når det gjelder opplysningene deres. GDPR handler om å beskytte og ivareta personvernrettighetene til enkeltpersoner. Du kan lese mer om Microsofts engasjement for sikkerhet og overholdelse i [Microsoft Klareringssenter](https://www.microsoft.com/trust-center).

Vi går inn for å hjelpe kundene våre med å oppfylle GDPR-kravene. Den inkluderer retten til å slette og eksportere data som inneholder personlige opplysninger, for eksempel bruker-ID-er, telefonnumre og e-postadresser. Administratorer kan implementere brukerforespørsler om å slette eller eksportere personlige opplysninger.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Svar på sletteforespørsler for GDPR-dataemner for Dynamics 365 Customer Insights

"Retten til å fjerne" personlige data fra en organisasjons kundedata er en nøkkelbeskyttelse i EUs personvernforordning (GDPR). Fjerning av personlige data inkluderer fjerning av alle personlige data og systemgenererte logger, unntatt revisjonslogginformasjon.

#### <a name="manage-data-subject-delete-requests"></a>Behandle slettingsforespørsler for dataemner

Customer Insights tilbyr følgende produkterfaringer for å slette personlige data for en bestemt kunde eller Customer Insights-bruker:

- **Behandle sletteforespørsler for kundedata**: Kundedata i Customer Insights er innhentet fra opprinnelige datakilder som ikke er i Customer Insights. Alle GDPR-sletteforespørsler må utføres i den opprinnelige datakilden.
- **Behandle sletteforespørsler for Customer Insights-brukerdata**: Data for brukere opprettes av Customer Insights. Alle GDPR-sletteforespørsler må utføres i Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Administrer forespørsler for å slette kundedata

En Customer Insights-administrator kan følge fremgangsmåten nedenfor for å fjerne kundedata som ble slettet i datakilden:

1. Logg på Dynamics 365 Customer Insights.
2. Gå til **Data** > **Datakilder**
3. For hver datakilde i listen som inneholder slettede kundedata:
   1. Velg (...) og deretter **Oppdater**.
   2. Kontroller statusen for datakilden under **Status**. Et merke betyr at oppdateringen var vellykket. En varseltrekant betyr at noe gikk galt. Hvis det vises en varseltrekant, kontakter du D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Behandle GDPR-sletteforespørsler for kundedata.](media/gdpr-data-sources.png "Behandle GDPR-sletteforespørsler for kundedata")

##### <a name="manage-delete-requests-for-user-data"></a>Behandle sletteforespørsler for brukerdata

En Customer Insights-administrator kan følge denne fremgangsmåten for å slette Customer Insights-brukerdata:

1. Logg på Dynamics 365 Customer Insights.
2. Gå til **Administrator** > **Tillatelser**.
3. Merk av for brukeren du vil slette.
4. Velg **Fjern**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Svare på forespørsler om eksport av GDPR-dataemne

Som en del av vår forpliktelse til å samarbeide med deg om EUs personvernforordning (GDPR), har vi utviklet dokumentasjon som hjelper deg med å svare på forespørsler fra dataemner.

#### <a name="manage-export-and-view-requests"></a>Behandle eksport- og visningsforespørsler

Med rettigheten for dataflyttbarhet kan dataemner be om en kopi av personlige data i et elektronisk format (et "strukturert, vanlig brukt, maskinlesbart og kompatibelt format") som kan overføres til en annen datakontroller.

##### <a name="export-customer-data-tenant-admin"></a>Eksportere kundedata (leieradministrasjon)

En leieradministrator kan følge disse trinnene for å eksportere data:

1. Send en e-post til D365CI@microsoft.com for å angi kundens e-postadresse i forespørselen. Customer Insights-teamet sender en e-post til den registrerte e-postadressen til leieradministratoren og ber om bekreftelse på å eksportere data.
2. Godta bekreftelsen om å eksportere dataene for den forespurte kunden.
3. Motta de eksporterte dataene via e-postadressen for leieradministratoren.

##### <a name="export-user-data-tenant-admin"></a>Eksportere brukerdata (leieradministrasjon)

1. Send en e-post til D365CI@microsoft.com for å angi brukerens e-postadresse i forespørselen. Customer Insights-teamet sender en e-post til den registrerte e-postadressen til leieradministratoren og ber om bekreftelse på å eksportere data.
2. Godta bekreftelsen om å eksportere dataene for den forespurte brukeren.
3. Motta de eksporterte dataene via e-postadressen for leieradministratoren.

## <a name="consent-management-preview"></a>Samtykkeadministrasjon (forhåndsversjon)

Funksjonen for samtykkeadministrasjon samler ikke inn brukerdata direkte. Den importerer og behandler bare samtykkedata som leveres av brukere i andre programmer.

Hvis du vil fjerne samtykkedata om bestemte brukere, fjerner du dem i datakildene som er innlagt i samtykkebehandlingsmulighetene. Etter oppdateringen av datakilden slettes de fjernede dataene også i Samtykkesenter. Programmer som bruker samtykkeenheten, sletter også data som ble fjernet i kilden etter en [oppdatering](system.md#refresh-processes). Vi anbefaler at du oppdaterer datakilder raskt etter at du har svart på en dataemneforespørsel for å fjerne brukerens data fra alle andre prosesser og programmer.

[!INCLUDE [footer-include](includes/footer-banner.md)]