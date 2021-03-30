---
title: Kundeaktiviteter
description: Definer kundeaktiviteter og vis dem på kundetidslinjen.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596741"
---
# <a name="customer-activities"></a>Kundeaktiviteter

Kombiner kundeaktiviteter fra [forskjellige datakilder](data-sources.md) i Dynamics 365 Customer Insights for å opprette en kundetidslinje som viser aktivitetene i kronologisk rekkefølge. Du kan ta med tidslinjen i Customer Engagement-apper i Dynamics 365 via [kundekorttillegget](customer-card-add-in.md) eller på et Power BI-instrumentbord.

## <a name="define-an-activity"></a>Definere en aktivitet

Datakildene inneholder enheter med transaksjons- og aktivitetsdata fra flere datakilder. Identifiser disse enhetene, og velg aktivitetene du vil vise på kundens tidslinje. Velg enheten som inneholder målaktiviteten eller -aktivitetene.

1. I Målgruppeinnsikt går du til **Data** > **Aktiviteter**.

1. Velg **Legg til aktivitet**.

   > [!NOTE]
   > En enhet må ha minst ett attributt av typen **Dato** som inkluderes på en kundetidslinje, og du kan ikke legge til enheter uten **Dato**-feltene. Kontrollen **Legg til aktivitet** er deaktivert hvis det ikke finnes en slik enhet.

1. Angi verdiene for følgende felt, i ruten **Legg til aktivitet**:

   - **Enhet**: Velg en enhet som inkluderer transaksjons- eller aktivitetsdata.
   - **Primærnøkkel**: Velg feltet som unikt identifiserer en oppføring. Den skal ikke inneholde duplikat verdier, tomme verdier eller manglende verdier.
   - **Tidsstempel**: Velg feltet som representerer starttidspunktet for aktiviteten.
   - **Hendelse**: Velg feltet som er hendelsen for aktiviteten.
   - **Webadresse**: Velg feltet som representerer en URL-adresse som gir tilleggsinformasjon om denne aktiviteten. For eksempel transaksjonssystemet som er kilde for denne aktiviteten. Denne URL-adressen kan være et hvilket som helst felt fra datakilde, eller den kan konstrueres som et nytt felt ved hjelp av en Power Query-transformasjon. Disse URL-dataene blir lagret i Enhetlig aktivitet-enheten, som kan forbrukes nedstrøms med API-er.
   - **Detaljer**: Velg eventuelt feltet som er lagt til for ytterligere detaljer.
   - **Ikon**: Velg eventuelt ikonet som representerer denne aktiviteten.
   - **Aktivitetstype**: Definer aktivitetstypereferansen til Common Data Model som best beskriver den semantiske definisjonen av aktiviteten.

1. I delen **Konfigurer relasjon** konfigurerer du detaljer for å koble aktivitetsdataene til den tilsvarende kunden.

    - **Feltet Aktivitetsenhet**: Velg feltet i aktivitetsenheten som skal brukes til å opprette en relasjon til en annen enhet.
    - **Kundeenhet**: Velg den tilsvarende kildekundeenheten som aktivitetsenheten skal være i relasjon til. Du kan bare relatere til de kildekundeenhetene som brukes i datasamlingsprosessen.
    - **Feltet Kundeenhet**: Dette feltet viser primærnøkkelen for kildekundeenheten som er valgt i tilordningsprosessen. Dette hovednøkkelfeltet i kildekundeenheten brukes til å opprette en relasjon med aktivitetsenheten.
    - **Navn**: Hvis det allerede finnes en relasjon mellom denne aktivitetsenheten og den valgte kildekundeenheten, vil relasjonsnavnet være i skrivebeskyttet modus. Hvis det ikke finnes en slik relasjon, blir det opprettet en ny relasjon med navnet som er angitt her.
   
   > [!div class="mx-imgBorder"]
   > ![Definere enhetsrelasjonen](media/activities-entities-define.png "Definere enhetsrelasjonen")

1. Velg **Lagre** for å ta i bruk endringene.

1. På siden **Aktiviteter** velger du **Kjør**.

> [!TIP]
> Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser. De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies). Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben. Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.

## <a name="edit-an-activity"></a>Redigere en aktivitet

1. I Målgruppeinnsikt går du til **Data** > **Aktiviteter**.

2. Velg aktivitetsenheten du vil redigere, og velg **Rediger**. Du kan også holde pekeren over enhetsraden og velge **Rediger**-ikonet.

3. Klikk på **Rediger**-ikonet.

4. I ruten **Rediger aktivitet** oppdaterer du verdiene og velger **Lagre**.

5. På siden **Aktiviteter** velger du **Kjør**.

## <a name="delete-an-activity"></a>Slette en aktivitet

1. I Målgruppeinnsikt går du til **Data** > **Aktiviteter**.

2. Velg aktivitetsenheten du vil fjerne, og velg **Slett**. Du kan også holde pekeren over enhetsraden og velge **Slett**-ikonet. Du kan også velge at flere aktivitetsenheter skal slettes samtidig.
   > [!div class="mx-imgBorder"]
   > ![Redigere eller slette enhetsrelasjonen](media/activities-entities-edit-delete.png "Redigere eller slette enhetsrelasjonen")

3. Velg **Slett**-ikonet.

4. Bekreft slettingen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]