---
title: Samsvar betingelser for dataforening
description: Samsvar enheter for å opprette enhetlige kundeprofiler.
recommendations: false
ms.date: 10/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721533"
---
# <a name="match-conditions-for-data-unification"></a>Samsvar betingelser for dataforening

Dette trinnet i samlingen definerer samsvarsrekkefølgen og reglene for samsvar på tvers av enheter. Dette trinnet krever minst to enheter.

> [!NOTE]
> Når du har opprettet samsvarsbetingelsene og valgt **Neste**, kan du ikke fjerne en valgt enhet eller et valgt attributt. Velg **Tilbake** hvis nødvendig for å se gjennom de valgte enhetene og attributtene før du fortsetter.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Inkludere supplerte enheter (forhåndsversjon)

Hvis du supplerte enheter på datakildenivå for å forbedre foreningsresultatene, velger du dem. Hvis du vil ha mer informasjon, kan du se [Supplering for datakilder](data-sources-enrichment.md). Hvis du valgte supplerte enheter på siden **Duplikatoppføringer**, trenger du ikke å velge dem på nytt.

1. Velg **Bruk supplerte enheter** øverst på siden på siden **Samsvarende betingelser**.

1. Velg én eller flere supplerte enheter på siden **Bruk supplerte enheter**.

1. Velg **Ferdig**.

## <a name="specify-the-match-order"></a>Angi samsvarsrekkefølgen

Hvert samsvar forener to eller flere enheter i én konsolidert enhet. Samtidig beholdes de unike kundeoppføringene. Samsvarsrekkefølgen angir rekkefølgen systemet prøver å samsvare oppføringene i.

> [!IMPORTANT]
> Den første enheten kalles hovedenheten, som fungerer som grunnlaget for de samlede profilene. Flere enheter som er valgt, blir lagt til denne enheten.
>
> Viktige hensyn:
>
> - Velg enheten med de mest fullstendige og pålitelige profildataene om kundene som hovedenhet.
> - Velg enheten som har flere attributter til felles med andre enheter (for eksempel navn, telefonnummer eller e-postadresse) som primær enhet.

1. Bruk pilene flytt opp og pil ned på siden **Samsvarende betingelser** til å flytte enhetene i ønsket rekkefølge, eller flytt og slipp dem. Velg for eksempel **eCommerceCustomers** som hovedenhet og **loyCustomers** som den andre enheten.

1. For å inkludere alle oppføringer i enheten som en unik kunde uavhengig av om et treff blir funnet, velger du **Inkluder alle oppføringer**. Alle oppføringer i denne enheten som ikke samsvarer med oppføringer i noen annen enhet, inkluderes i den enhetlige profilen. Oppføringer som ikke har treff, kalles enkeltdatabaser.
  
Primærenheten *Contacts:eCommerce* samsvares med neste enhet *CustomerLoyalty:Loyalty*. Datasettet som er et resultat av det første samsvarstrinnet, samsvares med enheten nedenfor hvis du har flere enn to enheter.

:::image type="content" source="media/m3_match.png" alt-text="Skjermbilde av den valgte samsvarsrekkefølgen for enhetene." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definer regler for samsvarspar

Samsvarsregler angir logikken som et bestemt enhetspar skal samsvares etter. En regel består av en eller flere betingelser.

Advarselen ved siden av et enhetsnavn betyr at ingen samsvarsregel er definert for et samsvarspar.

1. Velg **Legg til regel** for et enhetspar for å definere samsvarsregler.

1. Konfigurer betingelsene for regelen i ruten **Legg til regel**.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Skjermbilde av ruten Legg til regel.":::

   - **Velg Enhet/felt (første rad)**: Velg en enhet og et attributt som sannsynligvis er unik for en kunde. For eksempel et telefonnummer eller en e-postadresse. Unngå samsvar etter attributter av aktivitetstypen. En kjøps-ID samsvarer for eksempel sannsynligvis ikke med andre oppføringstyper.

   - **Velg Enhet/Felt (andre rad)**: Velg et attributt som er relatert til attributtet til enheten som er angitt i den første raden.

   - **Normaliser**: Velg blant følgende normaliseringsalternativer for de valgte attributtene.
     - **Tall**: Konverterer andre tallsystemer, for eksempel romertall, til arabiske tall. *VIII* blir *8*.
     - **Symboler**: Fjerner alle symboler og spesialtegn. *Head&Shoulder* blir *HeadShoulder*.
     - **Tekst til små bokstaver**: Konverterer alle tegn til små bokstaver. *BARE STORE BOKSTAVER og Store forbokstaver* blir *bare store bokstaver og store forbokstaver*.
     - **Type (telefon, navn, adresse, organisasjon)**: standardiserer navn, titler, telefonnumre, adresser og organisasjoner.
     - **Unicode til ASCII**: Konverterer Unicode-notasjon til ASCII-tegn. */u00B2* blir *2*.
     - **Mellomrom**: Fjerner alle mellomrom. *Hello   World* blir *HelloWorld*.

   - **Presisjon:** Angir presisjonsnivået som skal brukes for denne betingelsen.
     - **Grunnleggende**: Velg mellom *Lav (30 %)*, *Middels (60 %)*, *Høy (80 %)* og *Nøyaktig (100 %)*. Velg **Eksakt** for å samsvare bare med oppføringer som samsvarer med 100 prosent.
     - **Egendefinert:** Angi en prosentandel som oppføringer må samsvare med. Systemet samsvarer bare oppføringer som passerer denne terskelen.

   - **Navn**: Navn for regelen.

1. Hvis du bare vil samsvare enheter hvis attributter oppfyller flere betingelser, velger du **Legg til** > **Legg til betingelse** for å legge til flere betingelser i en samsvarsregel. Betingelser er koblet til en logisk OG-operator og kjøres derfor bare hvis alle betingelser er oppfylt.

1. Vurder eventuelt avanserte alternativer, for eksempel [unntak](#add-exceptions-to-a-rule) eller [egendefinerte samsvarsbetingelser](#specify-custom-match-conditions).

1. Velg **Ferdig** for å fullføre regelen.

1. Du kan eventuelt [legge til flere regler](#add-rules-to-a-match-pair).

1. Klikk **Neste**.

> [!div class="nextstepaction"]
> [Neste trinn: Samle felter](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Legg til regler i et samsvarspar

Samsvarsregler representerer sett med betingelser. Hvis du vil samsvare enheter etter betingelser basert på flere attributter, kan du legge til flere regler.

1. Velg **Legg til regel** for enheten du vil legge til regler for.

1. Følg fremgangsmåten i [Definer regler for samsvarspar](#define-rules-for-match-pairs).

> [!NOTE]
> Rekkefølgen av regler er viktig. Den samsvarende algoritmen prøver å samsvare med en gitt kundeoppføring på grunnlag av den første regelen, og fortsetter bare til den andre regelen hvis ingen treff ble identifisert med den første regelen.

## <a name="advanced-options"></a>Avanserte alternativer

### <a name="add-exceptions-to-a-rule"></a>Legge til unntak i en regel

I de fleste tilfeller samsvarer enheten med kundeemner til unike kundeprofiler med konsoliderte data. For å håndtere sjeldne tilfeller av falske positive og falske negativer definerer du unntak for en samsvarsregel. Unntak brukes etter behandling av samsvarsreglene og unngår samsvar for alle oppføringer, som oppfyller unntaksvilkårene.

Hvis for eksempel samsvarsregelen kombinerer etternavn, poststed og fødselsdato, vil systemet identifisere tvillinger med samme etternavn som bor i samme by som har samme profil. Du kan angi et unntak som ikke samsvarer med profilene hvis fornavn i enhetene du kombinerer, ikke er de samme.

1. Velg **Legg til** > **Legg til unntak** i **Rediger regel**-ruten.

1. Angi unntaksvilkårene.

1. Velg **Ferdig** for å lagre regelen.

### <a name="specify-custom-match-conditions"></a>Angi egendefinerte samsvarsbetingelser

Angi betingelser som overstyrer standard samsvarslogikk. Fire alternativer er tilgjengelige:

|Alternativ  |Bekrivelse |Eksempel  |
|---------|---------|---------|
|Samsvar alltid     | Definerer verdier for primærnøklene som alltid samsvarer.         |  Samsvar alltid raden med primærnøkkelen *12345* med raden med primærnøkkelen *54321*.       |
|Samsvar aldri     | Definerer verdier for primærnøklene som aldri samsvarer.        | Samsvar aldri raden med primærnøkkelen *12345* med raden med primærnøkkelen *54321*.        |
|Utelat            | Definerer verdier som systemet alltid skal ignorere i samsvarsfasen. |  Ignorer verdiene *11111* og *Ukjent* under samsvar.        |
|Aliastilordning    | Definere verdier som systemet skal anse som samme verdi.         | Anse *Joe* lik som *Joseph*.        |

1. Velg **Egendefinert**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Egendefinert-knappen":::

1. Velg **Egendefinert type** og velg **Last ned mal**. Gi malen nytt navn uten å bruke mellomrom. Bruk en egen mal for hvert samsvarsalternativ.

1. Åpne den nedlastede malfilen, og fyll ut detaljene. Malen inneholder felt for å angi enheten og primærnøkkelverdiene for enheten som skal brukes i det egendefinerte samsvaret. Det skilles mellom små og store bokstaver i enhetsnavn. Hvis du for eksempel vil at primærnøkkelen *12345* fra *Salg*-enheten alltid skal samsvare med primærnøkkelen *34567* fra *Kontakt*-enheten, fyller du ut malen:
   - Entity1: Salg
   - Entity1Key: 12345
   - Entity2: Kontakt
   - Entity2Key: 34567

   Den samme malfilen kan angi egendefinerte samsvarsoppføringer fra flere enheter.

   > [!NOTE]
   > Hvis du vil angi egendefinert samsvar for deduplisering for en enhet, angir du samme enhet som både Enhet1 og Enhet2 og angir de forskjellige primærnøkkelverdiene. Du må definere minst én dedupliseringsregel for enheten for å kunne bruke egendefinert samsvar.

1. Når du har lagt til alle overstyringene, lagrer du malfilen.

1. Gå til **Data** > **Datakilder**, og hent inn malfilene som nye enheter.

1. Når du har lastet opp filene, velger du alternativet **Egendefinert** på nytt. Velg de nødvendige enhetene på rullegardinmenyen, og velg **Fullført**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Skjermbilde av dialogen for å velge overstyringer for et egendefinert samsvarsscenario.":::

1. Bruk av det egendefinerte samsvaret avhenger av samsvarsalternativet du vil bruke.

   - Gå til neste trinn for **Samsvar alltid** eller **Samsvar aldri**.
   - For **Utelatelse** eller **Aliastildeling** velger du **Rediger** for en eksisterende samsvarsregel eller oppretter en ny regel. Velg alternativet **Egendefinert utelatelse** eller **Aliastildeling** i rullegardinlisten Normaliseringer, og velg **Fullført**.

1. Velg **Fullført** i **Egendefinert**-ruten for å bruke konfigurasjonen for tilpasset samsvar.

   Hver malfil som tas inn, er sin egen datakilde. Hvis det oppdages oppføringer som krever spesiell samsvarsbehandling, oppdaterer du den aktuelle datakilden. Oppdateringen brukes i løpet av neste samlingsprosess. Du kan for eksempel identifisere tvillinger med nesten like navn som bor på samme adresse som hadde blitt slått sammen som én person. Oppdater datakilden å identifisere tvillingene som separate, unike oppføringer.

> [!div class="nextstepaction"]
> [Neste trinn: Samle felter](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
