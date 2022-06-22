---
title: Supplere kundeprofiler med data fra Microsoft Office 365
description: Bruk proprietære data fra Microsoft Office for å forbedre kundeprofilene med engasjementsdata.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954145"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Supplere kundeprofiler med engasjementsdata (forhåndsversjon)

Bruk data fra Microsoft Office 365 til å forbedre kundekontoprofilene dine med innsikt i engasjementer gjennom Office 365-apper. Engasjementsdataene består av e-post og møteaktivitet, som samles på kontonivå. For eksempel antall e-poster fra en forretningsforbindelse eller antall møter med forretningsforbindelsen. Ingen data om enkeltbrukere blir gjort tilgjengelig.

## <a name="supported-countries-or-regions"></a>Støttede land eller områder

Vi støtter for øyeblikket følgende områder: Storbritannia, Europa, Nord-Amerika.

## <a name="prerequisites"></a>Forutsetning

- En aktiv Office 365-skylisens.
- [Enhetlige kundeprofiler](customer-profiles.md) basert på [forretningskontoer](work-with-business-accounts.md).
- En [Microsoft Dataverse-organisasjon tilknyttet](create-environment.md#step-3-connect-to-microsoft-dataverse) i Customer Insights-miljøet.
- [Administratorrettigheter](permissions.md#admin).
- Samtykke fra Office 365-leieradministratoren til å bruke Office 365-data til å gi **innsikt for organisasjonen** i Dynamics 365-programmer.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på flisen **Kontoengasjement**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Kontoengasjement-flis.":::

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Angi e-postadresser fra organisasjonen som Office-data skal samles for. Bare data fra de oppførte e-postadressene blir behandlet for relevant kommunikasjon. En god fremgangsmåte er å bruke e-postgrupper, for eksempel *Salgsteam, USA*, som du kan administrere i Office 365. Antall e-postadresser i gruppene løses og vises. Det totale antallet e-postadresser må være minst 2 og kan ikke overskride 2 500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-postadresser for forretningsforbindelsesgasjement.":::

1. Gå gjennom og gi samtykke for [samtykke for Office 365-leieradministratoren](#office-365-tenant-administrator-consent) ved å velge **Jeg samtykker**.

1. Velg **Neste**.

1. Velg **kontaktdatasettet** og velg profilen du vil supplere. Velg **Neste**.

1. Tilordne feltet for e-postadresse for kontakt, og velg **Neste**.

1. Angi et **Navn** for suppleringen og **Utdataenheten**.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

1. Velg **Lukk** for å gå tilbake til siden **Suppleringer**.

### <a name="office-365-tenant-administrator-consent"></a>Office 365-leieradministrator-samtykke

Det kreves samtykke fraen Office 365-leieradministrator for å aktivere suppleringen. Det sendes en e-postmelding til Office 365 leieradministratorene når suppleringen lagres. Den ber dem om å gå gjennom og samtykke til å la Dynamics 365-programmer bruke bedriftens Office 365 data til å **gi innsikt for organisasjonen**. Office 365 leieradministratoren kan også samtykke direkte i Office 365 administratorkonsollen ved å velge **Innsikt for organisasjonen**.

## <a name="running-the-enrichment-for-the-first-time"></a>Kjøre suppleringen for første gang

Når suppleringen startes for første gang, etter at Office 365 leieradministratoren har gitt samtykke, begynner datanedlastingen fra Office 365. Denne prosessen tar litt tid. Første suppleringskjøring vil etter planen skje med en forsinkelse på seks timer. Du kan se antall dager dataene dekker, på oversiktssiden for forretningsforbindelsesengasjementet etter at suppleringen er fullført. Med et stort datavolum kan du kjøre suppleringen på nytt etter noen dager. Det sikrer at dataene er fullført for hele tidsvinduet, som er ett år.

Avhengig av størrelsen på Office-dataene kan det ta flere timer før en suppleringskjøring fullføres.

Når du kjører en supplering, behandler Microsoft dataene innenfor Office 365 samsvarsgrensen for å opprette aggregert innsikt, som deretter legges til i Customer Insights-miljøet. Ingen data på individuelt nivå (for eksempel brødteksten i en e-post eller kalenderinvitasjon) blir tilgjengelig for brukere av Customer Insights.

Velg **Kjør** for å starte suppleringsprosessen.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultater av supplering

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Dette er *Office*-enheten. *Office_UserEntity* inneholder Active Directory-ID-ene for e-postadressene som ble valgt under suppleringskonfigurasjonen.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Vise supplerte data på kundekortet

Forretningsforbindelsesengasjement kan også vises på individuelle kundekort. Gå til **Kunder**, og velg en kundeprofil. På kundekortet finner du forretningsforbindelsens engasjementspoengsum, totalt antall e-poster og totalt antall møter samlet i løpet av det siste året. Du finner også diagrammer som viser e-post- og møtehistorikken.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kundekort med supplerte data.":::

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Et segment som for eksempel inneholder alle kunder som har en verdi som er over 60 *dager siden forrige e-post* og *dager siden forrige møte*. Dette segmentet inneholder foreldede forretningsforbindelser som du kan prøve å reaktivere.

[!INCLUDE [footer-include](includes/footer-banner.md)]
