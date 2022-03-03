---
title: DSR-forespørsler (Data Subject Rights) under GDPR | Microsoft Docs
description: Du kan svare på dataemneforespørsler for målgruppeinnsikt i Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350281"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>DSR-forespørsler (Data Subject Rights) under GDPR

EUs personvernforordning (GDPR) har vært gjeldende siden 25. mai 2018. Den gir personer betydelige rettigheter når det gjelder opplysningene deres. GDPR handler om å beskytte og ivareta personvernrettighetene til enkeltpersoner. Du kan lese mer om Microsofts engasjement for sikkerhet og overholdelse i [Microsoft Klareringssenter](https://www.microsoft.com/trust-center).

Vi går inn for å hjelpe kundene våre med å oppfylle GDPR-kravene. Den inkluderer retten til å slette og eksportere data som inneholder personlige opplysninger, for eksempel bruker-ID-er, telefonnumre og e-postadresser. Administratorer kan implementere brukerforespørsler om å slette eller eksportere personlige opplysninger.

## <a name="audience-insights"></a>Målgruppeinnsikt

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Svare på forespørsler om å slette GPDR-dataemner for målgruppeinnsikt i Dynamics 365 Customer Insights

"Retten til å fjerne" personlige data fra en organisasjons kundedata er en nøkkelbeskyttelse i EUs personvernforordning (GDPR). Fjerning av personlige data inkluderer fjerning av alle personlige data og systemgenererte logger, unntatt revisjonslogginformasjon.

#### <a name="manage-data-subject-delete-requests"></a>Behandle slettingsforespørsler for dataemner

Målgruppeinnsikt tilbyr følgende produktopplevelser for å slette personlige data for en bestemt kunde eller bruker:

- **Behandle sletteforespørsler for kundedata**: Kundedata i Customer Insights er innhentet fra opprinnelige datakilder som ikke er i Customer Insights. Alle GDPR-sletteforespørsler må utføres i den opprinnelige datakilden.
- **Behandle sletteforespørsler for Customer Insights-brukerdata**: Data for brukere opprettes av Customer Insights. Alle GDPR-sletteforespørsler må utføres i Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Administrer forespørsler for å slette kundedata

En Customer Insights-administrator kan følge fremgangsmåten nedenfor for å fjerne kundedata som ble slettet i datakilden:

1. Logg på Dynamics 365 Customer Insights.
2. I Målgruppeinnsikt går du til **Data** > **Datakilder**
3. For hver datakilde i listen som inneholder slettede kundedata:
   1. Velg (...) og deretter **Oppdater**.
   2. Kontroller statusen for datakilden under **Status**. Et merke betyr at oppdateringen var vellykket. En varseltrekant betyr at noe gikk galt. Hvis det vises en varseltrekant, kontakter du D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Behandle GDPR-sletteforespørsler for kundedata.](audience-insights/media/gdpr-data-sources.png "Behandle GDPR-sletteforespørsler for kundedata")

##### <a name="manage-delete-requests-for-user-data"></a>Behandle sletteforespørsler for brukerdata

En Customer Insights-administrator kan følge denne fremgangsmåten for å slette Customer Insights-brukerdata:

1. Logg på Dynamics 365 Customer Insights.
2. I Målgruppeinnsikt går du til **Administrasjon** > **Tillatelser**.
3. Merk av for brukeren du vil slette.
4. Velg **Fjern**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Svare på forespørsler om eksport av GDPR-dataemne

Som en del av vår forpliktelse til å samarbeide med deg om EUs personvernforordning (GDPR), har vi utviklet dokumentasjon som hjelper deg med å forberede deg. Denne dokumentasjonen beskriver fremgangsmåten du kan bruke i dag for å støtte GDPR-kompatibilitet når du bruker målgruppeinnsikt.

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

Hvis du vil fjerne samtykkedata om bestemte brukere, fjerner du dem i datakildene som er innlagt i samtykkebehandlingsmulighetene. Etter oppdateringen av datakilden slettes de fjernede dataene også i Samtykkesenter. Programmer som bruker samtykkeenheten, sletter også data som ble fjernet i kilden etter en [oppdatering](audience-insights/system.md#refresh-processes). Vi anbefaler at du oppdaterer datakilder raskt etter at du har svart på en dataemneforespørsel for å fjerne brukerens data fra alle andre prosesser og programmer.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]