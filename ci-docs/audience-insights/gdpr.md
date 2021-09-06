---
title: DSR-forespørsler (Data Subject Rights) under GDPR | Microsoft Docs
description: Du kan svare på dataemneforespørsler for målgruppeinnsikt i Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 891794321f20954533ec0374b397eaf6b30445c2b0c95f601009912b3c3950a7
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034514"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>DSR-forespørsler (Data Subject Rights) under GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Svare på forespørsler om å slette GPDR-dataemner for målgruppeinnsikt i Dynamics 365 Customer Insights

"Retten til å fjerne" personlige data fra en organisasjons kundedata er en nøkkelbeskyttelse i EUs personvernforordning (GDPR). Fjerning av personlige data inkluderer fjerning av alle personlige data og systemgenererte logger, unntatt revisjonslogginformasjon.

### <a name="manage-data-subject-delete-requests"></a>Behandle slettingsforespørsler for dataemner

Målgruppeinnsikt tilbyr følgende produktopplevelser for å slette personlige data for en bestemt kunde eller bruker:

- **Behandle sletteforespørsler for kundedata**: Kundedata i Customer Insights er innhentet fra opprinnelige datakilder som ikke er i Customer Insights. Alle GDPR-sletteforespørsler må utføres i den opprinnelige datakilden.
- **Behandle sletteforespørsler for Customer Insights-brukerdata**: Data for brukere opprettes av Customer Insights. Alle GDPR-sletteforespørsler må utføres i Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Behandle sletteforespørsler for kundedata

En Customer Insights-administrator kan følge fremgangsmåten nedenfor for å fjerne kundedata som ble slettet i datakilden:

1. Logg på Dynamics 365 Customer Insights.
2. I Målgruppeinnsikt går du til **Data** > **Datakilder**
3. For hver datakilde i listen som inneholder slettede kundedata:
   1. Velg (...) og deretter **Oppdater**.
   2. Kontroller statusen for datakilden under **Status**. Et merke betyr at oppdateringen var vellykket. En varseltrekant betyr at noe gikk galt. Hvis det vises en varseltrekant, kontakter du D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Behandle GDPR-sletteforespørsler for kundedata.](media/gdpr-data-sources.png "Behandle GDPR-sletteforespørsler for kundedata")

#### <a name="manage-delete-requests-for-user-data"></a>Behandle sletteforespørsler for brukerdata

En Customer Insights-administrator kan følge denne fremgangsmåten for å slette Customer Insights-brukerdata:

1. Logg på Dynamics 365 Customer Insights.
2. I Målgruppeinnsikt går du til **Administrasjon** > **Tillatelser**.
3. Merk av for brukeren du vil slette.
4. Velg **Fjern**.

> [!div class="mx-imgBorder"]
> ![Behandle GPDR-sletteforespørsler for brukerdata.](media/gdpr-permissions.png "Håndtere GPDR-sletteforespørsler for brukerdata")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Svare på forespørsler om eksport av GDPR-dataemne

Som en del av vår forpliktelse til å samarbeide med deg om EUs personvernforordning (GDPR), har vi utviklet dokumentasjon som hjelper deg med å forberede deg. Denne dokumentasjonen beskriver fremgangsmåten du kan bruke i dag for å støtte GDPR-kompatibilitet når du bruker målgruppeinnsikt.

### <a name="manage-export-and-view-requests"></a>Behandle eksport- og visningsforespørsler

Med rettigheten for dataflyttbarhet kan dataemner be om en kopi av personlige data i et elektronisk format (et "strukturert, vanlig brukt, maskinlesbart og kompatibelt format") som kan overføres til en annen datakontroller.

#### <a name="export-customer-data-tenant-admin"></a>Eksportere kundedata (leieradministrasjon)

En leieradministrator kan følge disse trinnene for å eksportere data:

1. Send en e-post til D365CI@microsoft.com for å angi kundens e-postadresse i forespørselen. Customer Insights-teamet sender en e-post til den registrerte e-postadressen til leieradministratoren og ber om bekreftelse på å eksportere data.
2. Godta bekreftelsen om å eksportere dataene for den forespurte kunden.
3. Motta de eksporterte dataene via e-postadressen for leieradministratoren.

#### <a name="export-user-data-tenant-admin"></a>Eksportere brukerdata (leieradministrasjon)

1. Send en e-post til D365CI@microsoft.com for å angi brukerens e-postadresse i forespørselen. Customer Insights-teamet sender en e-post til den registrerte e-postadressen til leieradministratoren og ber om bekreftelse på å eksportere data.
2. Godta bekreftelsen om å eksportere dataene for den forespurte brukeren.
3. Motta de eksporterte dataene via e-postadressen for leieradministratoren.


[!INCLUDE[footer-include](../includes/footer-banner.md)]