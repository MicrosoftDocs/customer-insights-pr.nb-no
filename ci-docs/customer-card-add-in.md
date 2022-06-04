---
title: Tillegg for kundekort for Dynamics 365-apper (inneholder video)
description: Vis kundeprofildata fra Customer Insights i Dynamics 365-apper med dette tillegget.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755648"
---
# <a name="customer-card-add-in-preview"></a>Tillegg for kundekort (forhåndsversjon)

Få en 360-graders visning av kundene direkte i Dynamics 365-apper. Når tillegget for kundekort er installert i en støttet Dynamics 365-app, kan du velge å vise kundeprofilfelt, innsikt og tidslinje for aktivitet. Tillegget henter data fra Customer Insights uten at det påvirker dataene i den tilkoblede Dynamics 365-appen.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Forutsetninger

- Tillegget fungerer bare med modelldrevne Dynamics 365-apper, for eksempel Sales eller Customer Service, versjon 9.0 og nyere.
- Hvis Dynamics 365-dataene skal tilordnes til Customer Insights-kundeprofilene, anbefaler vi at de [hentes fra Dynamics 365-appen ved hjelp av Microsoft Dataverse-koblingen](connect-power-query.md). Hvis du bruker en annen metode til å hente Dynamics 365-kontakter (eller forretningsforbindelser), må du kontrollere at feltet `contactid` (eller `accountid`) er angitt som [primærnøkkel for denne datakilden i tilordningstrinnet i dataforeningsprosessen](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Alle Dynamics 365-brukere av tillegget Kundekort må [legges til som brukere](permissions.md) i Customer Insights for å vise dataene.
- [Konfigurerte søke- og filterfunksjoner](search-filter-index.md) i Customer Insights kreves for at oppslag av data skal fungere.
- Hver tilleggskontroll er avhengig av bestemte data i Customer Insights. Noen data og kontroller er bare tilgjengelige i miljøer av bestemte typer. Konfigurasjonen av tillegget informerer deg hvis en kontroll ikke er tilgjengelig på grunn av den valgte miljøtypen. Finn ut mer om [miljøbrukstilfeller](work-with-business-accounts.md).
  - **Målkontroll**: Krever [konfigurerte målinger](measures.md) av typen kundeattributter.
  - **Intelligenskontroll**: Krever data generert ved hjelp av [prediksjoner eller egendefinerte modeller](predictions-overview.md).
  - **Kundedetaljer-kontroll**: Alle felt fra profilen er tilgjengelige i den enhetlige kundeprofilen.
  - **Suppleringskontroll**: Krever at aktive [suppleringer](enrichment-hub.md) brukes på kundeprofiler. Korttillegget støtter disse suppleringene: [Merker](enrichment-microsoft.md) fra Microsoft, [Interesser](enrichment-microsoft.md) fra Microsoft og [Office-engasjementsdata](enrichment-office.md) fra Microsoft.
  - **Kontakter**-kontroll: Krever definisjon av semantisk enhet av typekontakter.
  - **Tidslinjekontroll**: Krever [konfigurerte aktiviteter](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installere tillegget Kundekort

Kundekorttillegget er en løsning for Customer Engagement-apper i Dynamics 365. Gå til AppSource og søk etter **Dynamics-kundekort** for å installere løsningen. Velg [Tillegg for kundekort på AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) og velg **Hent det nå**.

Det kan hende at du må logge på med administratorlegitimasjonen for Dynamics 365-appen for å kunne installere løsningen. Det kan ta litt tid før løsningen installeres i miljøet ditt.

## <a name="configure-the-customer-card-add-in"></a>Konfigurere tillegget for kundekort

1. Som administrator kan du gå til delen **Innstillinger** i Dynamics 365 og velge **Løsninger**.

1. Velg **Visningsnavn**-koblingen for løsningen **Dynamics 365 Customer Insights-kundekorttillegg (forhåndsversjon)**.

   > [!div class="mx-imgBorder"]
   > ![Velg visningsnavn.](media/select-display-name.png "Velg visningsnavn.")

1. Velg **Logg på**, og angi legitimasjonen for administratorkontoen du bruker til å konfigurere Customer Insights.

   > [!NOTE]
   > Kontroller at popup-blokkeringen i nettleseren ikke blokkerer godkjenningsvinduet når du velger knappen **Logg på**.

1. Velg Customer Insights-miljøet du vil hente data fra.

1. Definer felttilordningen til oppføringer i Dynamics 365-appen. Avhengig av dataene i Customer Insights kan du velge å tilordne følgende alternativer:
   - Hvis du vil tilordne med en kontakt, velger du feltet i kundeenheten som samsvarer med ID-en til kontaktenheten.
   - Hvis du vil tilordne med en forretningsforbindelse, velger du feltet i kundeenheten som samsvarer med ID-en til forretningsforbindelsesenheten.

   > [!div class="mx-imgBorder"]
   > ![Kontakt-ID-felt.](media/contact-id-field.png "Kontakt-ID-felt.")

1. Velg **Lagre konfigurasjon** for å lagre innstillingene.

1. Deretter må du tilordne sikkerhetsroller i Dynamics 365 slik at brukere kan tilpasse og se kundekortet. I Dynamics 365 går du til **Innstillinger** > **Sikkerhet** > **Brukere**. Velg brukerne du vil redigere brukerroller for, og velg **Behandle roller**.

1. Tilordne rollen **Korttilpasser for Customer Insights** til brukere som skal tilpasse innholdet som vises på kortet for hele organisasjonen.

## <a name="add-customer-card-controls-to-forms"></a>Legge til Kundekort-kontroller i skjemaer

Avhengig av scenarioet kan du velge å legge til kontroller i enten **Kontakt**-skjemaet eller **Forretningsforbindelse**-skjemaet. Hvis Customer Insights-miljøet er for forretningskontoer, anbefaler vi å legge til kontrollene i Forretningsforbindelse-skjemaet. I det tilfellet erstatter du "kontakt" i trinnene nedenfor med "forretningsforbindelse".

1. Hvis du vil legge til kundekortkontrollene i kontaktskjemaet, går du til **Innstillinger** > **Tilpassinger** i Dynamics 365.

1. Velg **Tilpasse systemet**.

1. Bla til **Kontakt**-enheten, utvid den, og velg deretter **Skjemaer**.

1. Velg kontaktskjemaet du vil legge til kundekortkontrollene i.

    > [!div class="mx-imgBorder"]
    > ![Velg kontaktskjemaet.](media/contact-active-forms.png "Velg kontaktskjemaet.")

1. Hvis du vil legge til en kontroll, drar du et felt fra **Feltutforsker** i skjemaredigeringsprogrammet til stedet der du vil at kontrollen skal vises.

1. Velg feltet i skjemaet du nettopp la til, og velg deretter **Endre egenskaper**.

1. Gå til kategorien **Kontroller**, og velg **Legg til kontroll**. Velg en av de tilgjengelige egendefinerte kontrollene, og velg **Legg til**.

1. I dialogboksen **Feltegenskaper** fjerner du merket for **Vis etikett i skjemaet**.

1. Velg **Web**-alternativet for kontrollen. For suppleringskontrollen må du velge hvilken suppleringstype du vil skal vises, ved å konfigurere **enrichmentType**-feltet. Legg til en separat suppleringskontroll for hver suppleringstype.

1. Velg **Lagre** og **Publiser** for å publisere det oppdaterte kontaktskjemaet.

1. Gå til det publiserte kontaktskjemaet. Du vil se den nylig tillagte kontrollen. Det kan hende du må logge på første gang du bruker den.

1. Hvis du vil tilpasse det du vil vise på den egendefinerte kontrollen, velger du Rediger-knappen øverst i høyre hjørne.

## <a name="upgrade-customer-card-add-in"></a>Oppgrader tillegg for kundekort

Tillegget for kundekort oppgraderes ikke automatisk. Hvis du vil oppgradere til den nyeste versjonen, følger du denne fremgangsmåten i Dynamics 365-appen der tillegget er installert.

1. Gå til **Innstillinger** > **Tilpasning** i Dynamics 365-appen, og velg **Løsninger**.

1. Se etter **CustomerInsightsCustomerCard** i tabellen med tillegg, og velg raden.

1. Velg **Bruk løsningsoppgradering** på handlingslinjen.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Oppgrader løsningen i Tilpasning-området i Dynamics 365-appene.":::

1. Når du har startet oppgraderingsprosessen, vises en innlastingsindikator til oppgraderingen er fullført. Hvis det ikke finnes en nyere versjon, vises en feilmelding for oppgraderingen.

## <a name="troubleshooting"></a>Feilsøking

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kontroller fra tillegget for kundekort finner ikke data

**Problem:**

Selv med ID-felt som er riktig konfigurert, kan ikke kontrollene finne data for noen kunde.  

**Løsning.**

1. Kontroller at du har konfigurert Tillegg for kundekort i henhold til instruksjonene: [Konfigurere tillegget for kundekort](#configure-the-customer-card-add-in)

1. Se gjennom datainntakskonfigurasjonen. Rediger datakilde for Dynamics 365-systemet som inneholder GUID for kontakt-ID. Hvis GUID for kontakt-ID vises med store bokstaver i Power Query-redigeringsprogrammet, kan du prøve følgende trinn:
    1. Rediger datakilde for å åpne datakilde i Power Query-redigeringsprogrammet.
    1. Velg kontakt-ID-kolonnen.
    1. Velg **Transformer** på overskriftslinjen for å vise tilgjengelige handlinger.
    1. Velg **små bokstaver**. Kontroller om det nå er små bokstaver i GUIDene i tabellen.
    1. Lagre datakilden.
    1. Kjør datainntaks-, forenings- og nedstrømsprosesser for å overføre endringene til GUID.

Etter systemet har fullført hele oppdateringen, skal kontroller fra tillegget for kundekort vise de forventede dataene.

[!INCLUDE [footer-include](includes/footer-banner.md)]