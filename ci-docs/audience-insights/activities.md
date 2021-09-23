---
title: Kundeaktiviteter
description: Definer kundeaktiviteter, og vis dem på en tidslinje i kundeprofiler.
ms.date: 09/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c5697df8a7d011c70384c8bc5e4773d7fcc25a62
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494423"
---
# <a name="customer-activities"></a>Kundeaktiviteter

Kombiner kundeaktiviteter fra [ulike datakilder](data-sources.md) i Dynamics 365 Customer Insights for å opprette en tidslinje som viser aktivitetene kronologisk. Inkluder tidslinjen i Dynamics 365-apper med løsningen for [kundekorttillegg](customer-card-add-in.md) eller i et Power BI-instrumentbord.

## <a name="define-an-activity"></a>Definere en aktivitet

Datakildene kan inneholde enheter med transaksjons- og aktivitetsdata fra flere datakilder. Identifiser disse enhetene, og velg aktivitetene du vil vise på kundens tidslinje. Velg enheten som inneholder målaktiviteten eller -aktivitetene.

> [!NOTE]
> En enhet må ha minst ett attributt av typen **Dato** som inkluderes på en kundetidslinje, og du kan ikke legge til enheter uten **Dato**-feltene. Kontrollen **Legg til aktivitet** er deaktivert hvis det ikke finnes en slik enhet.

1. I Målgruppeinnsikt går du til **Data** > **Aktiviteter**.

1. Velg **Legg til aktivitet** for å starte den veiledede opplevelsen for installasjonsprosessen for aktivitet.

1. Angi verdiene for følgende felt i **Aktivitetsdata**-trinnet:

   - **Aktivitetsnavn**: Velg et navn for aktiviteten.
   - **Enhet**: Velg en enhet som inkluderer transaksjons- eller aktivitetsdata.
   - **Primærnøkkel**: Velg feltet som unikt identifiserer en oppføring. Den skal ikke inneholde duplikat verdier, tomme verdier eller manglende verdier.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Konfigurer aktivitetsdataene med navn, enhet og hovednøkkel.":::

1. Velg **Neste** for å gå til neste trinn.

1. Konfigurer detaljene i **Relasjon**-trinnet til å koble aktivitetsdataene til den tilsvarende kunden. Dette trinnet visualiserer tilkoblingen mellom enheter.  

   - **Først**: Eksterne felt i aktivitetsenheten som skal brukes til å opprette en relasjon til en annen enhet.
   - **Sekund**: Tilsvarende kildekundeenhet som aktivitetsenheten skal være i relasjon med. Du kan bare relatere til kildekundeenheter som brukes i dataforeningsprosessen.
   - **Tredje**: Hvis det allerede finnes en relasjon mellom aktivitetsenheten og den valgte kildekundeenheten, vil relasjonsnavnet være i skrivebeskyttet modus. Hvis det ikke finnes noen slik relasjon, opprettes det en ny relasjon med navnet du angir i denne boksen.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definer enhetsrelasjonen.":::

1. Velg **Neste** for å gå til neste trinn. 

1. Velg aktivitetshendelsen og starttiden for aktiviteten i **Aktivitetsforening**-trinnet. 
   - **Obligatoriske felter**
      - **Hendelsesaktivitet**: Felt som er hendelsen for denne aktiviteten.
      - **Tidsstempel**: Felt som representerer starttidspunktet for aktiviteten.

   - **Valgfrie felt**
      - **Tilleggsdetaljer**: Felt med relevant informasjon for denne aktiviteten.
      - **Ikon**: Ikon som best representerer denne aktivitetstypen.
      - **Webadresse**: Felt som inneholder en URL-adresse med informasjon om denne aktiviteten. For eksempel transaksjonssystemet som er kilde for denne aktiviteten. Denne URL-adressen kan være et hvilket som helst felt fra datakilde, eller den kan konstrueres som et nytt felt ved hjelp av en Power Query-transformasjon. URL-dataene lagres i *Enhetlig aktivitet*-enheten, som kan brukes nedstrøms ved hjelp av [API-er](apis.md).

   - **Vis på tidslinje**
      - Velg om du vil vise denne aktiviteten i tidslinjevisningen for kundeprofilene dine. Velg **Ja** for å vise aktiviteten på tidslinjen, eller **Nei** for å skjule den.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Angi kundeaktivitetsdataene i en Enhetlig aktivitet-enhet.":::

1. Velg **Neste** for å gå til neste trinn. Du kan velge **Fullfør og se gjennom** for å lagre aktiviteten nå med aktivitetstypen satt til **Annet**. 

1. Velg aktivitetstypen i **Aktivitetstype**-trinnet, og velg eventuelt hvis du vil semantisk tilordne noen av aktivitetstypene for bruk i andre områder av Customer Insights. Aktivitetstypene *Tilbakemelding*, *Lojalitet*, *SalesOrder*, *SalesOrderLine* og *Abonnement* kan tilordnes semantisk etter at du har godtatt å tilordne feltene. Hvis en aktivitetstype ikke er relevant for den nye aktiviteten, kan du velge *Annet* eller *Opprett ny* for en egendefinert type.

1. Velg **Neste** for å gå til neste trinn. 

1. Bekreft valgene i trinnet **Se gjennom**. Gå tilbake til noen av de forrige trinnene, og oppdater informasjonen om nødvendig.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Se gjennom de angitte feltene for en aktivitet.":::
   
1. Velg **Lagre aktivitet** for å ta i bruk endringene, og velg **Fullført** for å gå tilbake til **Data** > **Aktiviteter**. Her ser du hvilke aktiviteter som skal vises på tidslinjen. 

1. På **Aktiviteter**-siden velger du **Kjør** for å behandle aktiviteten. 

> [!TIP]
> Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser. De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies). Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben. Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.


## <a name="manage-existing-activities"></a>Behandle eksisterende aktiviteter

I **Data** > **Aktiviteter** kan du vise alle lagrede aktiviteter og administrere dem. Hver aktivitet representeres av en rad som også inneholder detaljer om kilden, enheten og aktivitetstypen.

Handlingene nedenfor er tilgjengelige når du velger en aktivitet. 

- **Rediger**: Åpner aktivitetsoppsettet i gjennomgangstrinnet. Du kan endre hvilken som helst av eller alle gjeldende konfigurasjoner fra dette trinnet. Når du har endret konfigurasjonen, velger du **Lagre aktivitet** og deretter **Kjør** for å behandle endringene.

- **Gi nytt navn**: Åpner en dialogboks der du kan angi et annet navn for den valgte aktiviteten. Velg **Lagre** for å ta i bruk endringene.

- **Slett**: Åpner en dialogboks for å bekrefte slettingen av den valgte aktiviteten. Du kan også slette mer enn én aktivitet samtidig ved å velge aktivitetene og deretter velge sletteikonet. Velg **Slett** for å bekrefte slettingen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
