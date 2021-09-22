---
title: Traktrapporter
description: Slik bruker du traktrapporter til å forstå hvordan målgrupper tar avgjørelser.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7c6b7b7285556f8a531ce9e29f0d1de162562be6fb43dd826a65fd9e00d87b30
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032267"
---
# <a name="create-and-manage-funnel-reports"></a>Opprette og administrere traktrapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En traktrapport samler inn informasjon om trinnene som inntreffer i løpet av en kundereise via nettstedet ditt eller mobilappen. Den hjelper deg med å forstå hvordan en målgruppe går gjennom en prosess og identifiserer frafallspunkter. Du kan for eksempel bruke en traktrapport til å identifisere baner kundene følger før de foretar et kjøp. En traktrapport inneholder data som informerer avgjørelser og identifiserer områder for optimalisering og prosessforbedringer.

## <a name="create-a-funnel-report"></a>Opprett en traktrapport

Hvis du vil opprette traktrapporten, angir du trinnene du vil inkludere, og aktiviteten for hvert trinn. En aktivitet er en [hendelse](glossary.md) som representerer brukeratferd. Traktrapporten viser antall brukere som fullførte hvert definerte trinn. 

1. Gå til **Trakter** og velg **+Ny trakt** for å starte en traktrapport.

1. Velg **+Legg til trinn** under **Trinn** i **Redigeringsprogram for trakt**. 

1. Angi et navn i **Trinntittel**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Ny traktrapport.":::

1. Velg en **aktivitet**. En aktivitet registrerer når en bruker viser en side (**visningsaktivitet**) eller samhandler med innhold (**handlingsaktivitet**).

1. Bruk **Trinnvilkår** til å angi aktivitetens dimensjon. [Dimensjoner](dimensions.md) er attributter som kan beskrive, filtrere eller gruppere data.

1. Du kan eventuelt konfigurere trakttrinn med flere betingelser. Velg **Legg til betingelse** for å angi flere dimensjoner i et trinn. Tilleggsvilkår må bruke samme aktivitetstype. Du kan velge om flere betingelser er koblet sammen med en OG- eller ELLER-operator.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Redigeringsprogram for trakt der trinnkonfigurasjonen med trinn med flere betingelser vises.":::

1. Velg **Legg til trinn** til du har fullført alle trinnene du vil ha med i rapporten.

1. Velg **Lagre**, gi rapporten et navn, og velg **Lagre** på nytt. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Eksempel: Traktrapport om Fourth Coffee-firma

Følgende scenario viser en måte å bruke en traktrapport på. En analytiker i selskapet Fourth Coffee ønsker å forstå hvilken innvirkning en nylig kampanje har på abonnementspriser. Analytikeren oppretter en traktrapport for å identifisere kundeaktivitet. Den starter når kunder kommer til startsiden for firmaet til de bruker tilbudskoden for abonnementet. Analytikeren oppretter en traktrapport med følgende trinn:

Trinn 1: Kunder som kommer til startsiden   
Trinn 2: Kunder som foretar et kjøp   
Trinn 3: Kunder som bruker tilbudskoden til å få rabatt på et abonnement   
Trinn 4: Registrering av abonnement   

:::image type="content" source="media/funnel-report-example.png" alt-text="eksempel på traktrapport.":::
  
I denne trakten kan du se antall brukere som brukte tilbudskoden etter et engangskjøp for registrering for abonnementsprogrammet.

### <a name="configure-advanced-settings"></a>Konfigurer avanserte innstillinger 

Traktrapporter lar deg angi en grense for hvor lang tid det tar å fullføre en trakt. Du kan for eksempel sette tiden for å fullføre trakten til fire dager. Denne innstillingen teller bare vellykkede abonnementsregistreringer som ble foretatt innen fire dager etter at en bruker besøkte startsiden.

1. Gå til **Trakter** for å åpne **Traktbiblioteket**.

1. Velg et navn for å åpne rapporten. 

1. Velg **Avanserte innstillinger** i **Traktredigering**-ruten. 

1. Sett Begrens fullføringstid for trakt til **På**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Traktredigering der det vises avanserte innstillinger og alternativer for å begrense tiden til å fullføre en trakt.":::

1. Velg når trakten må være fullført, i rullegardinlisten **Sett grense til**.

1. Velg **Lagre** for å ta i bruk endringene.


## <a name="cross-channel-funnel-reports"></a>Traktrapporter på tvers av flere kanaler 

Engasjementsinnsikt kan også samle inn atferdsdata fra kunder i mobilappen din. Når du har instrumentert mobilappen med Engasjementsinnsikt [Android SDK](get-started-android.md) eller [iOS SDK](get-started-ios.md), kan du opprette traktrapporter på tvers av kanaler. 

### <a name="create-a-cross-channel-funnel-report"></a>Opprette en traktrapport på tvers av flere kanal 

1. Følg fremgangsmåten for å [opprette en traktrapport](#create-a-funnel-report).    

1. Hvis du vil spore hvordan kundene samhandler med varemerket ditt på tvers av både nettstedet ditt og mobilappen din, eller flere nettsteder, kan du bruke arbeidsområdeveksleren til å opprette trakttrinn med data fra andre arbeidsområder. I **Traktredigering**, under **Trinn**, velger du hvilket arbeidsområde dataene for trakttrinnet skal komme fra.

## <a name="manage-funnel-reports"></a>Administrer traktrapporter

Du kan gå gjennom traktrapporter for å analysere data, spore ytelse og samle inn innsikt.

> [!NOTE]
> - Traktrapporter for engasjementsinnsikt støtter for øyeblikket scenarioer der alle brukerne i trakten er anonyme eller alle brukere er godkjent. 
> - Historiske data i traktrapporter er tilgjengelige for de siste 30 dagene.

### <a name="view-funnel-reports"></a>Vis traktrapporter

1. Gå til **Trakter** for å åpne **Traktbiblioteket**.
1. Velg et navn for å åpne rapporten.    

### <a name="see-the-data-collected-for-a-report"></a>Se dataene som er samlet inn for en rapport   

Slik der du informasjon om en fase

- Pek på et trinn i rapporten.

:::image type="content" source="media/funnel-step-data.png" alt-text="traktdata.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Endre datointervallet for traktrapporten

1. Gå til **Trakter** for å åpne **Traktbiblioteket**.

1. Velg et navn for å åpne rapporten.

1. Åpne **tidsintervallet**, og velg en ny tidsperiode fra listen eller **Fast datointervall** for å angi et datointervall.

## <a name="edit-or-delete-funnel-reports"></a>Rediger eller slett traktrapporter

Du kan endre navnet på en traktrapport, slette den eller endre trinnene i rapporten.

### <a name="rename-or-delete-a-funnel-report"></a>Gi nytt navn til eller slett en traktrapport

1. Gå til **Trakter** for å åpne **Traktbiblioteket**. 

1. Velg **Mer** ved siden av rapporten du vil endre, og velg **Rediger navn** eller **Slett**.

### <a name="edit-a-funnel-step"></a>Rediger et trakttrinn  

1. Gå til **Trakter** for å åpne **Traktbiblioteket**. 

1. Velg et navn for å åpne rapporten.

1. Velg trinnet du vil redigere.

1. Velg **Rediger**.

1. Oppdater informasjonen du vil endre, i **Redigeringsprogram for trakt**.  

1. Velg **Lagre**.

### <a name="reorder-a-funnel-step"></a>Endre rekkefølgen på et trakttrinn

1. Gå til **Trakter** for å åpne **Traktbiblioteket**. 

1. Velg et navn for å åpne rapporten.

1. Velg trinnet du vil endre rekkefølgen på.

1. Velg **Flytt** og deretter **Opp**, **Ned**, **Til toppen** eller **Til bunnen** for å flytte trinnet.

### <a name="delete-a-funnel-step"></a>Slett et trakttrinn

1. Gå til **Trakter** for å åpne **Traktbiblioteket**. 

1. Velg et navn for å åpne rapporten.

1. Velg trinnet du vil fjerne, og velg **Slett**.

