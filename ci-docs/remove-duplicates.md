---
title: Fjern duplikater før du samler data
description: Det andre trinnet i samlingsprosessen er å velge hvilken oppføring som skal beholdes når duplikater blir funnet.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a838fbdabdb3bfffc6d3835a3f0e97306a43964a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139441"
---
# <a name="remove-duplicates-before-unifying-data"></a>Fjern duplikater før du samler data

Med dette trinnet i samlingen kan du eventuelt definere regler for håndtering av duplikatoppføringer i en enhet. *Deduplisering* identifiserer duplikatoppføringer og slår dem sammen til én oppføring. Kildeoppføringer kobles til den flettede oppføringen med alternative ID-er. Hvis regler ikke konfigureres, brukes systemdefinerte regler.

## <a name="include-enriched-entities-preview"></a>Inkludere supplerte enheter (forhåndsversjon)

Hvis du supplerte enheter på datakildenivå for å forbedre foreningsresultatene, velger du dem. Hvis du vil ha mer informasjon, kan du se [Supplering for datakilder](data-sources-enrichment.md).

1. Velg **Bruk supplerte enheter** øverst på siden på siden **Duplikatoppføringer**.

1. Velg én eller flere supplerte enheter på siden **Bruk supplerte enheter**.

1. Velg **Ferdig**.

## <a name="define-deduplication-rules"></a>Definer dedupliseringsregler

1. Velg en enhet på siden **Duplikatoppføringer**, og velg **Legg til regel** for å definere dedupliseringsreglene.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Skjermbilde av sidene duplikatoppføringer med Vis mer uthevet":::

   1. Angi følgende informasjon i ruten **Legg til regel**:
      - **Velg felt**: Velg fra listen over tilgjengelige felter fra enheten du vil søke etter duplikater for. Velg felter som sannsynligvis er unike for hver enkelt kunde. For eksempel en e-postadresse eller en kombinasjon av navn, poststed og telefonnummer.
      - **Normaliser**: Velg blant følgende normaliseringsalternativer for de valgte attributtene.
        - **Tall**: Konverterer andre tallsystemer, for eksempel romertall, til arabiske tall. *VIII* blir *8*.
        - **Symboler**: Fjerner alle symboler og spesialtegn. *Head&Shoulder* blir *HeadShoulder*.
        - **Tekst til små bokstaver: Konverterer alle tegn til små bokstaver**. *BARE STORE BOKSTAVER og Store forbokstaver* blir *bare store bokstaver og store forbokstaver*.
        - **Type (telefon, navn, adresse, organisasjon)**: standardiserer navn, titler, telefonnumre, adresser osv.
        - **Unicode til ASCII**: Konverterer Unicode-notasjon til ASCII-tegn. */u00B2* blir *2*.
        - **Mellomrom**: Fjerner alle mellomrom. *Hello   World* blir *HelloWorld*.
      - **Presisjon:** Angir presisjonsnivået som skal brukes for denne betingelsen.
        - **Grunnleggende**: Velg mellom *Lav (30 %)*, *Middels (60 %)*, *Høy (80 %)* og *Nøyaktig (100 %)*. Velg **Eksakt** for å samsvare bare med oppføringer som samsvarer med 100 prosent.
        - **Egendefinert:** Angi en prosentandel som oppføringer må samsvare med. Systemet samsvarer bare oppføringer som passerer denne terskelen.
      - **Navn**: Navn for regelen.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Skjermbilde av ruten Legg til regel for fjerning av duplikater.":::

   1. Du kan eventuelt velge **Legg til** > **Legg til betingelse** for å legge til flere betingelser i regelen. Betingelser er koblet til en logisk OG-operator og kjøres derfor bare hvis alle betingelser er oppfylt.

   1. **Legg til** > **Legg til unntak** for å [legge til unntak i regelen](match-entities.md#add-exceptions-to-a-rule). Unntak brukes til å løse sjeldne tilfeller av falske positive og falske negativer.

   1. Velg **Ferdig** for å opprette regelen.

1. Du kan eventuelt [legge til flere regler](#define-deduplication-rules).

1. Velg en enhet og deretter **Rediger fletteinnstillinger**.

1. I ruten **Fletteinnstillinger**:
   1. Velg et av tre alternativer for å bestemme hvilken oppføring som skal beholdes hvis det blir funnet et duplikat:
      - **Mest fylte**: Identifiserer oppføringen med de mest utfylte attributtfeltene som vinneroppføringen. Dette er standardalternativet for sammenslåing.
      - **Nyeste**: Identifiserer vinneroppføringen, basert på den nyeste oppføringen. Krever en dato eller et numerisk felt for å definere den nyeste.
      - **Minst nylig**: Identifiserer vinneroppføringen, basert på den minst nye oppføringen. Krever en dato eller et numerisk felt for å definere den nyeste.
      
      Ved uavgjort er vinneroppføringen den med MAX(PK) eller den største primærnøkkelverdien.
      
   1. Hvis du eventuelt vil definere fletteinnstillinger for individuelle attributter for en enhet, velger du **Avansert** nederst i ruten. Du kan for eksempel velge å beholde den nyeste e-postadressen OG den mest fullstendige adressen fra forskjellige oppføringer. Utvid enheten for å vise alle attributtene, og definer hvilket alternativ som skal brukes for enkeltattributter. Hvis du velger et besøksbasert alternativ, må du også angi et dato-/klokkeslettfelt som definerer ventetiden.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Ruten Avanserte fletteinnstillinger som viser den nyeste e-posten og den mest fullstendige adressen":::

   1. Velg **Ferdig** for å ta i bruk fletteinnstillingene.

1. Når du har definert dedupliseringsreglene og fletteinnstillingene, velger du **Neste**.
  
> [!div class="nextstepaction"]
> [Neste trinn for én enhet: Samle felter](merge-entities.md)

> [!div class="nextstepaction"]
> [Neste trinn for flere enheter: Samsvarende betingelser](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Dedupliseringsutdata som en enhet

Dedupliseringsprosessen oppretter en ny deduplisert enhet for hver av kildeenhetene. Disse enhetene kan finnes sammen med **ConflationMatchPairs:CustomerInsights** i **System**-delen på **Enheter**-siden med navnet **Deduplication_DataSource_Entity**.

En utdataenhet for deduplisering inneholder følgende informasjon:

- ID-er/nøkler
  - Primærnøkkel- og Alternativ ID-felter. Alternativ ID-felt består av alle de alternative ID-ene som er identifisert for en oppføring.
  - Feltet Deduplication_GroupId viser gruppen eller klyngen som identifiseres i en enhet, som grupperer alle lignende oppføringer basert på de angitte dedupliseringsfeltene. Det brukes til systembehandlingsformål. Hvis det ikke er angitt noen regler for manuell deduplisering og systemdefinerte dedupliseringsregler gjelder, kan det hende du ikke finner dette feltet i utdataenheten for deduplisering.
  - Deduplication_WinnerId: Dette feltet inneholder vinner-ID-en fra de identifiserte gruppene eller klyngene. Hvis Deduplication_WinnerId er den samme som primærnøkkelverdien for en oppføring, betyr det at oppføringen er vinneroppføringen.
- Felter brukes til å definere dedupliseringsreglene.
- Feltene Regel og Poengsum for å angi hvilke av dedupliseringsreglene som ble brukt, og poengsummen som ble returnert av den samsvarende algoritmen.

[!INCLUDE[footer-include](includes/footer-banner.md)]
