---
title: Kundeaktiviteter
description: Definer kundeaktiviteter, og vis dem på en tidslinje i kundeprofiler.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: 6c0a1bc5d9a42806b458142804199c733ff530ec
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755510"
---
# <a name="customer-activities"></a>Kundeaktiviteter

Kombiner kundeaktiviteter fra [forskjellige datakilder](data-sources.md) i Dynamics 365 Customer Insights. Opprett en tidslinje som viser aktivitetene kronologisk. Inkluder tidslinjen i Dynamics 365-apper med [Kundekort-tilleggsprogrammet](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definere en aktivitet

Datakildene kan inneholde enheter med transaksjons- og aktivitetsdata fra flere datakilder. Identifiser disse enhetene, og velg aktivitetene du vil vise på kundens tidslinje. Velg enheten som inneholder målaktiviteten eller -aktivitetene.

En enhet må ha minst ett attributt av typen **Dato** som inkluderes på en kundetidslinje, og du kan ikke legge til enheter uten **Dato**-feltene. Kontrollen **Legg til aktivitet** er deaktivert hvis det ikke finnes en slik enhet.

1. Gå til **Data** > **Aktiviteter**.

1. Velg **Legg til aktivitet** for å starte den veiledede opplevelsen for installasjonsprosessen for aktivitet.

1. Angi verdiene for følgende felt i **Aktivitetsdata**-trinnet:

   - **Aktivitetsnavn**: Velg et navn for aktiviteten.
   - **Enhet**: Velg en enhet som inkluderer transaksjons- eller aktivitetsdata.
   - **Primærnøkkel**: Velg feltet som unikt identifiserer en oppføring. Den skal ikke inneholde duplikat verdier, tomme verdier eller manglende verdier.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Konfigurer aktivitetsdataene med navn, enhet og hovednøkkel.":::

1. Velg **Neste** for å gå til neste trinn.

1. Konfigurer detaljene for å koble aktivitetsdataene til de tilsvarende kundeoppføringen i **Relasjoner**-trinnet. Dette trinnet visualiserer tilkoblingen mellom enheter.  

   - **Først**: Eksterne felt i aktivitetsenheten som skal brukes til å opprette en relasjon til en annen enhet.
   - **Sekund**: Tilsvarende kildekundeenhet som aktivitetsenheten skal være i relasjon med. Du kan bare relatere til kildekundeenheter som brukes i dataforeningsprosessen.
   - **Tredje**: Hvis det allerede finnes en relasjon mellom aktivitetsenheten og den valgte kildekundeenheten, vil relasjonsnavnet være i skrivebeskyttet modus. Hvis det ikke finnes noen slik relasjon, opprettes det en ny relasjon med navnet du angir i denne boksen.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definer enhetsrelasjonen.":::

   > [!TIP]
   > I B-til-B-miljøer kan du velge mellom forretningsforbindelsesenheter og andre enheter. Hvis du velger en forretningsforbindelsesenhet, angis relasjonsbanen automatisk. For andre enheter må du definere relasjonsbanen over én eller flere mellomliggende enheter til du når en forretningsforbindelsesenhet.

1. Velg **Neste** for å gå til neste trinn. 

1. Velg aktivitetshendelsen og starttiden for aktiviteten i **Aktivitetsforening**-trinnet. 
   - **Obligatoriske felter**
      - **Hendelsesaktivitet**: Felt som er hendelsen for denne aktiviteten.
      - **Tidsstempel**: Felt som representerer starttidspunktet for aktiviteten.

   - **Valgfrie felt**
      - **Tilleggsdetaljer**: Felt med relevant informasjon for denne aktiviteten.
      - **Ikon**: Ikon som best representerer denne aktivitetstypen.
      - **Webadresse**: Felt som inneholder en URL-adresse med informasjon om denne aktiviteten. For eksempel transaksjonssystemet som er kilde for denne aktiviteten. Denne nettadressen kan være et hvilket som helst felt fra datakilden, eller den kan konstrueres som et nytt felt ved hjelp av en Power Query-transformasjon. URL-dataene lagres i *Enhetlig aktivitet*-enheten, som kan brukes nedstrøms ved hjelp av [API-er](apis.md).

   - **Vis på tidslinje**
      - Velg om du vil vise denne aktiviteten i tidslinjevisningen for kundeprofilene dine. Velg **Ja** for å vise aktiviteten på tidslinjen, eller **Nei** for å skjule den.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Angi kundeaktivitetsdataene i en Enhetlig aktivitet-enhet.":::

1. Velg **Neste** for å gå til neste trinn. Du kan velge **Fullfør og se gjennom** for å lagre aktiviteten nå med aktivitetstypen satt til **Annet**. 

1. Velg aktivitetstypen i **Aktivitetstype**-trinnet, og velg eventuelt hvis du vil semantisk tilordne noen av aktivitetstypene for bruk i andre områder av Customer Insights. For øyeblikket støtter aktivitetstypene *Tilbakemelding*,*Lojalitet*, *SalesOrder*, *SalesOrderLine* og *Abonnement* semantikk etter at de har blitt enige om å tildele feltene. Hvis en aktivitetstype ikke er relevant for den nye aktiviteten, kan du velge *Annet* eller *Opprett ny* for en egendefinert type.

1. Velg **Neste** for å gå til neste trinn. 

1. Bekreft valgene i trinnet **Se gjennom**. Gå tilbake til noen av de forrige trinnene, og oppdater informasjonen om nødvendig.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Se gjennom de angitte feltene for en aktivitet.":::
   
1. Velg **Lagre aktivitet** for å ta i bruk endringene, og velg **Fullført** for å gå tilbake til **Data** > **Aktiviteter**. Her ser du hvilke aktiviteter som skal vises på tidslinjen. 

1. På **Aktiviteter**-siden velger du **Kjør** for å behandle aktiviteten. 

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Behandle eksisterende aktiviteter

I **Data** > **Aktiviteter** kan du vise alle lagrede aktiviteter og administrere dem. Hver aktivitet representeres av en rad som også inneholder detaljer om kilden, enheten og aktivitetstypen.

Handlingene nedenfor er tilgjengelige når du velger en aktivitet. 

- **Rediger**: Åpner aktivitetsoppsettet i gjennomgangstrinnet. Du kan endre hvilken som helst av eller alle gjeldende konfigurasjoner fra dette trinnet. Når du har endret konfigurasjonen, velger du **Lagre aktivitet** og deretter **Kjør** for å behandle endringene.

- **Gi nytt navn**: Åpner en dialogboks der du kan angi et annet navn for den valgte aktiviteten. Velg **Lagre** for å ta i bruk endringene.

- **Slett**: Åpner en dialogboks for å bekrefte slettingen av den valgte aktiviteten. Du kan også slette mer enn én aktivitet samtidig ved å velge aktivitetene og deretter velge sletteikonet. Velg **Slett** for å bekrefte slettingen.

## <a name="view-activity-timelines-on-customer-profiles"></a>Vise aktivitetstidslinjer på kundeprofiler

Når du har konfigurert kundeaktiviteter, velger du **Vis i tidslinje** i aktivitetskonfigurasjonen for å finne alle kundeaktivitetene i kundeprofilen.

Hvis du vil åpne tidslinjen for en kunde, går du til **Kunder** og velger kundeprofilen du vil vise.

Hvis en kunde har deltatt i en konfigurert aktivitet, finner du den i delen **Aktivitetstidslinje**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Vise konfigurerte aktiviteter i kundeprofiler.":::

Du kan filtrere aktiviteter på flere måter på tidslinjen for aktiviteter:

- Du kan velge ett eller mange av aktivitetsikonene for å finjustere resultatene slik at de bare inkluderer de valgte typene.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrer aktiviteter etter type ved hjelp av ikonene.":::

- Du kan velge **Filter** for å åpne et filterpanel for å konfigurere tidslinjefiltrene.

   1. Du kan filtrere etter *ActivityType* og *Dato*
   1. Velg **Bruk** for å bruke filtrene på tidslinjen for aktiviteten.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Bruk filterpanelet til å konfigurere filterbetingelser.":::

Hvis du vil fjerne filtre, velger du **x** ved siden av hvert filter som brukes på tidslinjen eller velger **Fjern filtre**.


> [!NOTE]
> Aktivitetsfiltre fjernes når du forlater en kundeprofil. Du må bruke dem hver gang du åpner dem i en kundeprofil.

[!INCLUDE [footer-include](includes/footer-banner.md)]