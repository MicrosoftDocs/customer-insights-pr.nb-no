---
title: Kundeaktiviteter
description: Definer kundeaktiviteter, og vis dem på en tidslinje i kundeprofiler.
ms.date: 07/22/2022
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
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188151"
---
# <a name="customer-activities"></a>Kundeaktiviteter

Kundeaktiviteter er handlinger eller hendelser som utføres eller forårsakes av kunder. Eksempler kan være transaksjoner, samtalevarighet i en kundestøttesamtale, anmeldelser av nettsteder, kjøp eller returer. Disse aktivitetene finnes i en eller flere datakilder. Med Customer Insights kan du konsolidere kundeaktivitetene fra disse [datakildene](data-sources.md) og knytte dem til kundeprofiler. Disse aktivitetene vises kronologisk på en tidslinje i kundeprofilen. Inkluder tidslinjen i Dynamics 365-apper med [Kundekort-tilleggsprogrammet](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definere en aktivitet

En enhet må ha minst ett attributt av typen **Dato** for å kunne inkluderes på en kundetidslinje. Kontrollen **Legg til aktivitet** er deaktivert hvis det ikke finnes en slik enhet.

1. Gå til **Data** > **Aktiviteter**.

1. Velg **Legg til aktivitet** for å starte den veiledede opplevelsen.

1. I trinnet **Aktivitetsdata** angir du følgende informasjon:

   - **Aktivitetsnavn**: Navnet på aktiviteten.
   - **Aktivitetsenhet**: Enhet som inkluderer transaksjons- eller aktivitetsdata.
   - **Primærnøkkel**: Felt som unikt identifiserer en oppføring. Den skal ikke inneholde duplikat verdier, tomme verdier eller manglende verdier.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Konfigurer aktivitetsdataene med navn, enhet og hovednøkkel.":::

1. Velg **Neste**.

1. Velg **Legg til relasjon** i **Relasjon**-trinnet for å koble aktivitetsdataene til den tilsvarende kundeoppføringen. Dette trinnet visualiserer tilkoblingen mellom enheter.  

   - **Sekundærnøkkel fra enhet**: Felt i aktivitetsenheten som skal brukes til å opprette en relasjon til en annen enhet.
   - **Til enhetsnavn**: Tilsvarende kildekundeenhet som aktivitetsenheten skal være i relasjon med. Du kan bare relatere til kildekundeenheter som brukes i dataforeningsprosessen.
   - **Relasjonsnavn**: Navn som identifiserer relasjonen mellom enheter. Hvis det allerede finnes en relasjon mellom aktivitetsenheten og den valgte kildekundeenheten, er relasjonsnavnet skrivebeskyttet.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definer enhetsrelasjonen.":::

   > [!TIP]
   > I B-til-B-miljøer kan du velge mellom forretningsforbindelsesenheter og andre enheter. Hvis du velger en forretningsforbindelsesenhet, angis relasjonsbanen automatisk. For andre enheter må du definere relasjonsbanen over én eller flere mellomliggende enheter til du når en forretningsforbindelsesenhet.

1. Velg **Bruk** for å opprette relasjonen.

1. Velg **Neste**.

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

1. Velg **Neste** for å velge aktivitetstypen, eller velg **Fullfør og se gjennom** for å lagre aktiviteten med aktivitetstypen satt til **Annet**.

1. Velg aktivitetstypen i **Aktivitetstype**-trinnet, og velg eventuelt hvis du vil semantisk tilordne noen av aktivitetstypene for bruk i andre områder av Customer Insights. For øyeblikket støtter aktivitetstypene *Tilbakemelding*,*Lojalitet*, *SalesOrder*, *SalesOrderLine* og *Abonnement* semantikk etter at de har blitt enige om å tildele feltene. Hvis en aktivitetstype ikke er relevant for den nye aktiviteten, kan du velge *Annet* eller *Opprett ny* for en egendefinert type.

1. Velg **Neste**.

1. Bekreft valgene i trinnet **Se gjennom**. Gå tilbake til noen av de forrige trinnene, og oppdater informasjonen om nødvendig.

1. Velg **Lagre aktivitet** for å ta i bruk endringene, og velg **Fullført** for å gå tilbake til **Data** > **Aktiviteter**. Den opprettede aktiviteten vises.

1. Når du har opprettet alle aktivitetene, velger du **Kjør** for å behandle dem.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Behandle eksisterende aktiviteter

Gå til **Data** > **Aktiviteter** for å vise lagrede aktiviteter, kildeenheten, aktivitetstypen og om de er inkludert på kundetidslinjen. Du kan sortere listen over aktiviteter etter en hvilken som helst kolonne, eller du kan bruke søkefeltet til å finne aktiviteten du vil administrere.

Velg en aktivitet for å vise tilgjengelige handlinger.

- **Rediger** aktiviteten for å endre konfigurasjonen. Konfigurasjonen åpnes i gjennomgangstrinnet. Når du har endret konfigurasjonen, velger du **Lagre aktivitet** og deretter **Kjør** for å behandle endringene.
- **Gi nytt navn** til aktiviteten. Velg **Lagre** for å ta i bruk endringene.
- **Slett** aktiviteten. Hvis du vil slette flere aktiviteter samtidig, velger du aktivitetene og deretter **Slett**. Bekreft slettingen.

## <a name="view-activity-timelines-on-customer-profiles"></a>Vise aktivitetstidslinjer på kundeprofiler

1. Hvis du velger **Vis i tidslinje** i aktivitetskonfigurasjonen, går du til **Kunder** og velger en kundeprofil for å vise kundens aktiviteter i delen **Aktivitetstidslinje**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Vise konfigurerte aktiviteter i kundeprofiler.":::

1. Slik filtrerer du aktiviteter på aktivitetstidslinjen:

   - Velg et eller flere av aktivitetsikonene for å finjustere resultatene slik at de bare inkluderer de valgte typene.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrer aktiviteter etter type ved hjelp av ikonene.":::

   - Velg **Filter** for å åpne et filterpanel og konfigurere tidslinjefiltrene. Filtrer etter *ActivityType* og/eller *Dato*. Velg **Bruk**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Bruk filterpanelet til å konfigurere filterbetingelser.":::

1. Hvis du vil fjerne filtre, velger du **Fjern filtre** eller velger **Filter** og fjerner merket for filteret.

> [!NOTE]
> Aktivitetsfiltre fjernes når du forlater en kundeprofil. Du må bruke dem hver gang du åpner en kundeprofil.

[!INCLUDE [footer-include](includes/footer-banner.md)]
