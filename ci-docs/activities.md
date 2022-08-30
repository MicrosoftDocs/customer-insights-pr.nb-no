---
title: Kunde- eller forretningskontaktaktiviteter
description: Definer kunde- eller forretningskontaktaktiviteter, og vis dem på en tidslinje i kundeprofiler.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
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
- customerInsights
ms.openlocfilehash: bbb8bc30d079273bc935181c628915bb3c02d982
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304117"
---
# <a name="customer-or-business-contact-activities"></a>Kunde- eller forretningskontaktaktiviteter

Kundeaktiviteter er handlinger eller hendelser som utføres av kunder eller forretningskontakter. Eksempler kan være transaksjoner, samtalevarighet i en kundestøttesamtale, anmeldelser av nettsteder, kjøp eller returer. Disse aktivitetene finnes i en eller flere datakilder. Med Customer Insights kan du konsolidere kundeaktivitetene fra disse [datakildene](data-sources.md) og knytte dem til kundeprofiler. Disse aktivitetene vises kronologisk på en tidslinje i kundeprofilen. Inkluder tidslinjen i Dynamics 365-apper med [Kundekort-tilleggsprogrammet](customer-card-add-in.md).

## <a name="define-a-customer-activity"></a>Definer en kundeaktivitet

En enhet må ha minst ett attributt av typen **Dato** for å kunne inkluderes på en kundetidslinje. Kontrollen **Legg til aktivitet** er deaktivert hvis det ikke finnes en slik enhet.

1. Gå til **Data** > **Aktiviteter**.

1. Velg **Legg til aktivitet** for å starte den veiledede opplevelsen.

1. I trinnet **Aktivitetsdata** angir du følgende informasjon:

   - **Aktivitetsnavn**: Velg et navn for aktiviteten.
   - **Aktivitetsenhet**: Velg en enhet som omfatter transaksjons- eller aktivitetsdata.
   - **Primærnøkkel**: Velg feltet som unikt identifiserer en oppføring. Den skal ikke inneholde duplikat verdier, tomme verdier eller manglende verdier.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Konfigurer aktivitetsdataene med navn, enhet og hovednøkkel.":::

1. Velg **Neste**.

1. Velg **Legg til relasjon** i **Relasjon**-trinnet for å koble aktivitetsdataene til den tilsvarende kundeoppføringen. Dette trinnet visualiserer tilkoblingen mellom enheter.  

   - **Sekundærnøkkel**: Sekundærnøkkelfelt i aktivitetsenheten som skal brukes til å opprette en relasjon til en annen enhet.
   - **Til enhetsnavn**: Tilsvarende kildekundeenhet som aktivitetsenheten skal være i relasjon med. Du kan bare relatere til kildekundeenheter som brukes i dataforeningsprosessen.
   - **Relasjonsnavn**: Hvis det allerede finnes en relasjon mellom denne aktivitetsenheten og den valgte kildekundeenheten, vil relasjonsnavnet være i skrivebeskyttet modus. Hvis det ikke finnes noen slik relasjon, opprettes det en ny relasjon med navnet du angir i denne boksen.

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

## <a name="manage-existing-customer-activities"></a>Behandle eksisterende kundeaktiviteter

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

> [!NOTE]
> Aktivitetsfiltre fjernes når du forlater en kundeprofil. Du må bruke dem hver gang du åpner en kundeprofil.

## <a name="define-a-contact-activity"></a>Definer en kontaktaktivitet

For forretningskontoer (B2B) bruker du en *ContactProfile*-enhet til å registrere kontaktaktiviteter. Du kan se på aktivitetstidslinjen for en forretningsforbindelse hvilken kontakt som var ansvarlig for hver aktivitet. De fleste trinnene følger konfigurasjonen for tilordning av kundeaktivitet.

   > [!NOTE]
   > Hvis du vil definere en aktivitet på kontaktnivå, må du opprette en *ContactProfile*-enhet, enten som en [samlet kontaktprofil](data-unification-contacts.md) eller via [semantisk tilordning](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Du må ha både **AccountID**- og **ContactID**-attributtene for hver oppføring for aktivitetsdataene.
  
1. Gå til **Data** > **Aktiviteter**.

1. Velg **Legg til aktivitet**.

1. Gi aktiviteten et navn, velg kildeaktivitetsenheten, og velg hovednøkkelen for aktivitetsenheten.

1. I trinnet **Relasjoner** oppretter du en indirekte relasjon mellom aktivitetskildedataene til forretningsforbindelser ved å bruke kontaktdataene som en mellomenhet. Hvis du vil ha mer informasjon, kan du se [direkte og indirekte relasjonsbaner](relationships.md#relationship-paths).
   - Eksempelrelasjon for en aktivitet kalt *Kjøp*:
      - **Aaktivitetsdata for kilde for kjøp** > **Kontakdata** på attributtet **ContactID**
      - **Kontaktdata** > **Data om forretningsforbindelse** på attributtet **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Eksempel på relasjonsoppsett.":::

1. Når du har satt opp Relasjoner, velger du **Neste** og fullfører konfigurasjonen av aktivitetstilordningen. Hvis du vil ha detaljerte trinn for oppretting av aktiviteter, kan du se [definer en kundeaktivitet](#define-a-customer-activity).

1. Kjør aktivitetstilordningene.

1. Aktivitetene på kontaktnivå vil nå være synlige på tidslinjen for kunden.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Endelig resultat etter konfigurasjon av kontaktaktiviteter":::

## <a name="contact-level-activity-timeline-filtering"></a>Tidslinjefiltrering av aktivitet på kontaktnivå

Når du har konfigurert en aktivitetstilordning på kontaktnivå og kjørt den, oppdateres tidslinjen for aktiviteten for kundene. Den inkluderer IDer eller navn, avhengig av *ContactProfile*-konfigurasjonen, for aktivitetene de handlet på. Du kan filtrere aktiviteter etter kontakter på tidslinjen for å se bestemte kontakter du er interessert i. I tillegg kan du vise alle aktiviteter som ikke er tilordnet til en bestemt kontakt, ved å velge **Aktiviteter som ikke er tilordnet til en kontakt**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Filtreringsalternativer som er tilgjengelige for aktiviteter på kontaktnivå.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
