---
title: Supplere kundeprofiler med data fra Microsoft Office 365
description: Bruk proprietære data fra Microsoft Office for å forbedre kundeprofilene med engasjementsdata.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 938a9de83fd8f5ff0c9ae815d626cdfa35228aba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228486"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Supplere kundeprofiler med engasjementsdata (forhåndsversjon)

Bruk data fra Microsoft Office 365 til å forbedre kundekontoprofilene dine med innsikt i engasjementer gjennom Office 365-apper. Engasjementsdataene består av e-post og møteaktivitet, som samles på kontonivå. For eksempel antall e-poster fra en forretningsforbindelse eller antall møter med forretningsforbindelsen. Ingen data om enkeltbrukere blir gjort tilgjengelig. 

Denne suppleringen er tilgjengelig i følgende regioner: Storbritannia, Europa og Nord-Amerika.

## <a name="prerequisites"></a>Krav

Følgende forutsetninger må være oppfylt for at du skal konfigurere suppleringen:

- Du må ha en aktiv Office 365-skylisens.
- Du har [enhetlige kundeprofiler](customer-profiles.md) basert [på forretningsforbindelser](work-with-business-accounts.md).
- Customer Insights-miljøet må ha en [Microsoft Dataverse vedlagt organisasjon](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Du har [administrator](permissions.md#administrator)-tillatelser.
- Du har, eller kan få, samtykke fra Office 365 leierdministratoren til å bruke Office 365 data til å gi **innsikt for organisasjonen** i Dynamics 365-programmer.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. I Målgruppeinnsikt går du til **Data** > **Supplering**.

1. Gå til Kategorien **Oppdag**, og velg **Suppler dataene mine** på flisen **Kontoengasjement**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Kontoengasjement-flis.":::
   
1. Velg **Neste** i **Oversikt**-trinnet, og angi e-postadresser fra organisasjonen som Office-data skal samles for. Bare data fra de oppførte e-postadressene blir behandlet for relevant kommunikasjon. En god fremgangsmåte er å bruke e-postgrupper, for eksempel *Salgsteam, USA*, som enkelt administreres i Office 365. Antall e-postadresser i gruppene løses og vises. Det totale antallet e-postadresser må være minst 2 og kan ikke overskride 2 500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-postadresser for forretningsforbindelsesgasjement.":::

1. Gå gjennom samtykkeerklæringen, merk av for **Jeg godtar** og velg **Neste**.

1. Velg kundedatasettet og deretter **Neste**.

1. Tilordne feltet for e-postadresse for kontakt, og velg **Neste**.

1. Gå gjennom suppleringskonfigurasjonen, gi suppleringen et navn, og velg **Lagre supplering** for å lagre suppleringen.

## <a name="office-365-tenant-administrator-consent"></a>Office 365-leieradministrator-samtykke

Det kreves samtykke fraen Office 365-leieradministrator for å aktivere suppleringen. Det sendes en e-postmelding til Office 365 leieradministratorene når suppleringen lagres. Den ber dem om å gå gjennom og samtykke til å la Dynamics 365-programmer bruke bedriftens Office 365 data til å **gi innsikt for organisasjonen**. Office 365 leieradministratoren kan også samtykke direkte i Office 365 administratorkonsollen ved å velge **Innsikt for organisasjonen**.

## <a name="running-the-enrichment-for-the-first-time"></a>Kjøre suppleringen for første gang

Når suppleringen startes for første gang, etter at Office 365 leieradministratoren har gitt samtykke, begynner datanedlastingen fra Office 365. Denne prosessen tar litt tid. Første suppleringskjøring vil etter planen skje med en forsinkelse på seks timer. Du kan se antall dager dataene dekker, på oversiktssiden for forretningsforbindelsesengasjementet etter at suppleringen er fullført. Med et stort datavolum kan du kjøre suppleringen på nytt etter noen dager. Det sikrer at dataene er fullført for hele tidsvinduet, som er ett år.

Start prosessen ved å velge **Kjør** på konfigurasjonssiden for kontoengasjement. I tillegg kan du la systemet kjøre suppleringen automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab). Som standard kjører suppleringen én gang i uken.

Avhengig av størrelsen på Office-dataene kan det ta flere timer før en suppleringskjøring fullføres.

Når du kjører en supplering, behandler Microsoft dataene innenfor Office 365 samsvarsgrensen for å opprette aggregert innsikt, som deretter legges til i Customer Insights-miljøet. Ingen data på individuelt nivå (for eksempel brødteksten i en e-post eller kalenderinvitasjon) blir tilgjengelig for brukere av Customer Insights. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultater av supplering

Når du har kjørt suppleringsprosessen, går du til **Mine suppleringer** for å se gjennom suppleringsresultatene. Du finner totalt antall supplerte kunder og en oversikt over suppleringsresultatene. Det inkluderer antall behandlede e-poster og møter, antall dager data er aggregert for, og mer.

Du finner også et diagram med antall supplerte kunder over tid, og en forhåndsvisning av de supplerte enhetene.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Forhåndsvisning av resultater etter kjøring av suppleringsprosessen.":::

Alle data samles opp til forretningsforbindelsesnivå. Systemet beregner en engasjementspoengsum, som er fra 0 til 100, for hver forretningsforbindelse. Engasjementspoengsummen gir et sammensatt mål for forretningsforbindelsesengasjementet på tvers av e-poster og møter i forhold til de andre forretningsforbindelsene. Følgende liste inneholder samlede data som suppleringen av forretningsforbindelsen gir:



| Data                                                                              | Kolonnenavn                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Engasjementspoengsum                                                                  |  EngagementScore                         |
| Antall e-postmeldinger til konto                                                       |  NoOfEmails_ToAccount                    |
| Antall e-postmeldinger fra konto                                                     |  NoOfEmails_FromAccount                  | 
| Antall møter som er startet av forretningsforbindelsen                                           |  NoOfMeetings_FromAccount                | 
| Antall møter som er startet av organisasjonen                                 |  NoOfMeetings_ToAccount                  | 
| Antall personer fra organisasjonen i møter med forretningsforbindelse                  |  NoOfContactsInvolved_Meetings           | 
| Antall personer fra organisasjonen i e-postdiskusjoner med forretningsforbindelse       |  NoOfContactsInvolved_Emails             | 
| Antall personer fra forretningsforbindelse i møter med organisasjonen                  |  NoOfAccountContactsInvolved_Meetings    | 
| Antall personer fra forretningsforbindelse i e-postdiskusjoner med organisasjonen       |  NoOfAccountContactsInvolved_Emails      | 
| Startdato for engasjement (første e-post eller møte i dataene)                        |  EngagementStartDate                     | 
| Dager siden siste e-post                                                             |  DaysSinceLastEmail                      | 
| Dager siden siste møte                                                           |  DaysSinceLastMeeting                    | 
| Gjennomsnittlig varighet for møter                                                      |  AverageDuration_Of_Meetings             | 
| Gjennomsnittlig varighet for e-postsvar fra forretningsforbindelse                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Startdato for samling                                                            |  AggregationStartDate                    | 
| Aggregeringsnivå (år, måned eller uke)                                          |  AggregationLevel                        | 


Se gjennom de supplerte dataene ved å velge **Se mer** i forhåndsvisningsdelen. De åpnes i *Office*-enheten. Du kan også finne enheten oppført i **Supplering**-gruppen i **Data** > **Enheter**. Du finner også *Office_UserEntity*, som inneholder Active Directory-IDene for e-postadressene som ble valgt under suppleringskonfigurasjonen 

## <a name="see-enrichment-data-on-the-customer-card"></a>Vise supplerte data på kundekortet

Forretningsforbindelsesengasjement kan også vises på individuelle kundekort. Gå til **Kunder**, og velg en kundeprofil. På kundekortet finner du forretningsforbindelsens engasjementspoengsum, totalt antall e-poster og totalt antall møter samlet i løpet av det siste året. Du finner også diagrammer som viser e-post- og møtehistorikken.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kundekort med supplerte data.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Opprette segmenter og tiltak basert på de supplerte dataene

De supplerte dataene kan brukes til å opprette segmenter og målinger som beskrevet nedenfor. Et segment som for eksempel inneholder alle kunder som har en verdi som er over 60 *dager siden forrige e-post* og *dager siden forrige møte*. Dette segmentet inneholder foreldede forretningsforbindelser som du kan prøve å reaktivere. 

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
