---
title: DSR-forespørsler (Data Subject Rights) under GDPR | Microsoft Docs
description: Du kan svare på dataemneforespørsler for målgruppeinnsikt i Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732692"
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


## <a name="engagement-insights-preview"></a>Engasjementsinnsikt (forhåndsversjon)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Slette og eksportere hendelsesdata som inneholder identifiserbar informasjon om sluttbrukeren

Avsnittene nedenfor beskriver hvordan du sletter og eksporterer hendelsesdata som kan inneholde personlige opplysninger.

Slette eller eksportere data:

1. Merk hendelsesegenskaper som inneholder data med personlig informasjon.
2. Slett eller eksporter data tilknyttet bestemte verdier (for eksempel en bestemt bruker-ID).

#### <a name="tag-and-update-event-properties"></a>Merk og oppdater hendelsesegenskaper

Personlige opplysninger merkes på et hendelsesegenskapsnivå. Først merker du egenskapene som vurderes for sletting eller eksport.

Følg denne fremgangsmåten for å merke en hendelsesegenskap som inneholder personlige opplysninger:

1. Åpne arbeidsområdet som inneholder hendelsen.

1. Gå til **Data** > **Hendelser** for å vise listen over hendelser i det valgte arbeidsområdet.
  
1. Velg hendelsen du vil merke.

1. Velg **Rediger egenskaper** for å åpne ruten med alle egenskapene for den valgte hendelsen.
     
1. Velg **...** og velg deretter **Rediger** for å gå til dialogboksen **Oppdater egenskap**.

   ![Rediger hendelse.](engagement-insights/media/edit-event.png "Rediger hendelse")

1. Velg **...** øverst i høyre hjørne i vinduet **Oppdater egenskap**, og velg deretter boksen **Inneholder EUII**. Velg **Oppdater** for å lagre endringene.

   ![Lagre endringene.](engagement-insights/media/update-property.png "Lagre endringene")

   > [!NOTE]
   > Hver gang hendelsesskjemaet endres eller du oppretter en ny hendelse, anbefales det at du evaluerer de tilknyttede hendelsesegenskapene og -koden eller opphever merkingen som viser at de inneholder personlige opplysninger, om nødvendig.

#### <a name="delete-or-export-tagged-event-data"></a>Slett eller eksporter merkede hendelsesdata

Hvis alle hendelsesegenskapene er merket på riktig måte som beskrevet i forrige trinn, kan en miljøadministrator utstede en sletteforespørsel mot de merkede hendelsesdataene.

Administrere forespørsler om sletting eller eksport av EUII

1. Gå til **Administrator** > **Miljø** > **Innstillinger**.

1. Velg **Administrer EUII** i delen **Administrer identifiserbar informasjon for sluttbruker (EUII)**.

##### <a name="deletion"></a>Sletting

For sletting kan du angi en liste over kommadelte bruker-ID-er i delen **Slett identifiserbar informasjon for sluttbruker (EUII)**. Disse ID-ene sammenlignes deretter med alle merkede hendelsesegenskaper for alle prosjekter i det gjeldende miljøet via nøyaktig strengavstemming. 

Hvis en egenskapsverdi svarer til en av de angitte ID-ene, slettes den tilknyttede hendelsen permanent. Siden denne handlingen ikke kan angres, må du bekrefte slettingen etter at du har valgt **Slett**.

##### <a name="export"></a>Export

Eksportprosessen er identisk med slettingsprosessen når det gjelder å definere egenskapsverdier for hendelser i delen **Eksporter identifiserbar informasjon for sluttbruker (EUII)**. I tillegg må du oppgi en **URL-adresse for Azure-bloblagring** for å angi eksportmålet. URL-adressen til Azure Blob må inneholde en [Signatur for delt tilgang (SAS)](/azure/storage/common/storage-sas-overview).

Når du har valgt **Eksporter**, eksporteres alle hendelser for gjeldende team som inneholder samsvarende merkede egenskaper, i CSV-format til eksportmålet.

### <a name="good-practices"></a>Anbefalte fremgangsmåter

* Prøv å unngå å sende hendelser som inneholder personlige opplysninger.
* Hvis du må sende hendelser som inneholder EUII-data, begrenser du antall hendelser og hendelsesegenskaper som inneholder EUII-data. Ideelt sett bør du begrense deg selv til én slik hendelse.
* Sørg for at så få personer som mulig har tilgang til de sendte personopplysningene.
* For hendelser som inneholder personlige opplysninger, må du sørge for at du angir én egenskap til å sende ut en unik ID som enkelt kan kobles til en bestemt bruker (for eksempel en bruker-ID). Dette gjør det enklere å skille data og eksportere eller slette riktige data.
* Bare merk én egenskap per hendelse som inneholder personlige opplysninger. Ideelt sett en som bare inneholder en unik identifikator.
* Ikke merk egenskaper som inneholder detaljerte verdier (for eksempel en hel forespørselstekst). Engasjementsinnsiktfunksjonalitet bruker nøyaktig strengsamsvar for å avgjøre hvilke hendelser som skal slettes eller eksporteres.

[!INCLUDE[footer-include](includes/footer-banner.md)]