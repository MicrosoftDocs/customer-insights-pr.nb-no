---
title: Opprett en samlet kontaktprofil (forhåndsversjon)
description: Gå gjennom datasamlingsprosessen for å opprette ett hoveddatasett med kontakter.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305050"
---
# <a name="create-a-unified-contact-profile-preview"></a>Opprett en samlet kontaktprofil (forhåndsversjon)

Når [forretningsforbindelsene er samlet](map-entities.md), kan du eventuelt samle kontaktene for disse forretningsforbindelsene og koble de samlede kontaktene til de samlede forretningsforbindelsene. Kontaktsamlingsprosessen tilordner kontaktdata fra flere datakilder, fjerner duplikater, samsvarer dataene på tvers av enheter, konfigurerer semantisk tilordning, oppretter relasjoner mellom kontakter og forretningsforbindelser, og oppretter deretter en samlet kontaktprofil.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

De første trinnene er identiske med trinnene for å samle forretningsforbindelser.

## <a name="prerequisites"></a>Forutsetning

Forretningsforbindelses- og kontaktoppføringer må ha en unik nøkkel (kalt en sekundærnøkkel) som kobler dem sammen. Dette kan for eksempel være en forretningsforbindelses-ID i forretningsforbindelsesoppføringen og kontaktoppføringen som knytter forretningsforbindelsen og kontakten sammen.

## <a name="preview-limitations"></a>Begrensninger i forhåndsversjonen

- Kontakter uten en kobling til en forretningsforbindelse forkastes.
- Hvis en forretningsforbindelse blir deduplisert, identifiseres en vinneroppføring basert på fletteinnstillingene. Taperoppføringer velges ikke og blir derfor forkastet. Kontakter som er knyttet til oppføringene som tapte, forkastes.
- En forretningsforbindelse kan ha flere kontakter, men en kontakt er koblet til én forretningsforbindelse.
- Kontaktattributtene som er tilordnet i trinnet for semantisk tilordning, er de eneste attributtene som kan vises på kundekortet. 17 attributter er imidlertid tilgjengelige.

## <a name="select-source-fields"></a>Velg kildefelter

1. Velg **Kom i gang** under **Samle kontakter (forhåndsversjon)**.

1. [Velg enhetene og feltene](map-entities.md) for kontaktdatakildene, inkludert primærnøklene og attributtypene.

1. Velg **Neste**.

## <a name="remove-duplicate-records"></a>Fjern dupliserte oppføringer

1. Du kan eventuelt [definere dedupliseringsregler](remove-duplicates.md) for de valgte enhetene.

1. Velg **Neste**.

## <a name="match-conditions"></a>Samsvar betingelser

1. [Definer samsvarsrekkefølgen og -reglene](match-entities.md) for samsvar på tvers av enheter.

1. Velg **Neste**.

## <a name="unify-contact-fields"></a>Samle kontaktfelter

1. [Kombinere og utelate kontaktfelter](merge-entities.md).

1. Velg **Neste**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definer semantiske felter for samlede kontakter

Dette trinnet i samlingsprosessen tilordner de enhetlige kontaktfeltene til semantiske typer. I B2B vises forretningsforbindelser på kundekortene. Når du velger kortet, vises alle kontaktene som er knyttet til forretningsforbindelsen. Feltene du tilordner i dette trinnet, er feltene som kommer til å vises på kortene.

1. Velg den semantiske typen som tilordnes til hvert samlede felt. Velg **Ingen** hvis en semantisk type ikke er tilgjengelig.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Skjermbilde av siden Semantiske felter for å definere semantiske typer." lightbox="media/semantic_mapping.png":::

1. Når du har tilordnet alle samlede felter, velger du **Neste**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Angi relasjonen mellom kontakter og forretningsforbindelser

Dette trinnet i samlingsprosessen kobler kontaktdataene til de tilsvarende forretningsforbindelsesdataene.

1. Angi følgende informasjon for hver enhet:

   - **Sekundærnøkkel fra kontaktenhet**: Velg attributtet som kobler kontaktenheten til forretningsforbindelsen.
   - **Til forretningsforbindelsesenhet**: Velg forretningsforbindelsesenheten som er knyttet til kontakten.

   :::image type="content" source="media/contact_relationship.png" alt-text="Skjermbilde av Relasjon-siden for å koble sammen kontakt- og forretningsforbindelsesenhetene.":::

1. Velg **Neste**.

## <a name="review-contact-unification"></a>Se gjennom kontaktsamling

Se gjennom oversikten over endringene, opprett den samlede profilen, og se gjennom resultatene.

### <a name="review-and-create-contact-profiles"></a>Se gjennom og opprett kontoprofiler

Dette siste trinnet i samlingsprosessen viser et sammendrag av trinnene i prosessen og gir mulighet til å gjøre endringer før du oppretter kontaktprofilen.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Skjermbilde av Se gjennom og opprett kontaktprofiler.":::

1. Velg **Rediger** i en av kontaktsamlingstrinnene for å se gjennom og gjøre endringer.

1. Hvis du er fornøyd med valgene dine, velger du **Opprett kontaktprofiler**. **Samle**-siden vises mens den enhetlige kontaktprofilen opprettes.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Skjermbilde av Samle kontakter-siden med fliser som viser I kø eller Oppdaterer.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Det tar litt tid å fullføre samlingsalgoritmen, og du kan ikke endre konfigurasjonen før den er fullført.

### <a name="view-the-results-of-contact-unification"></a>Vis resultatene for kontaktsamling

Etter samlingen er fullført, viser siden **Data** > **Samle** antall samlede kontaktprofiler. Resultatene av hvert trinn i samlingsprosessen vises på hver flis. **Kildefelter** viser for eksempel antall tildelte attributter (felter) og **Duplikatoppføringer** viser antall duplikatoppføringer som ble funnet.

:::image type="content" source="media/unified_contacts.png" alt-text="Skjermbilde av siden for datasamling etter at kontaktene er samlet.":::

> [!TIP]
> Flisen **Samsvarende betingelser** vises bare hvis flere enheter er valgt.

Vi anbefaler at du ser gjennom resultatene, spesielt kvaliteten på [samsvarsreglene](data-unification-update.md#manage-match-rules) dine og finjusterer dem om nødvendig.

Når det er nødvendig, [kan du gjøre endringer i innstillingene for kontaktsamling](data-unification-update.md) og kjøre den samlede profilen på nytt.

### <a name="verify-output-entities-from-data-unification"></a>Kontroller utdataenheter fra datasamling

Gå til **Data** > **Enheter** for å kontrollere utdataenhetene.

Enheten for samlet kontaktprofil, kalt *ContactProfile*, vises i delen **Semantiske enheter**. Første vellykkede samlingskjøring oppretter den samlede *ContactProfile*-enheten. Alle påfølgende kjøringer utvider enheten.

*ContactsCustomer*-enheten (forhåndsversjon) opprettes og vises i **Profiler**-delen. Denne enheten inneholder kontaktdataene uten koblingene til forretningsforbindelsene. Denne enheten brukes som inndata i semantisk tilordning og relasjonstrinn for kontaktsamling.

Dedupliserings- og sammenslåingsenheter opprettes og vises i **System**-delen. En deduplisert enhet kalt **Deduplication_DataSource_Entity** opprettes for hver av kildeenhetene. Enheten **ContactsConflationMatchPairs** inneholder informasjon om samsvar på tvers av enheter.

En utdataenhet for deduplisering inneholder følgende informasjon:
- ID-er/nøkler
  - Primærnøkkel- og Alternativ ID-felter. Alternativ ID-felt består av alle de alternative ID-ene som er identifisert for en oppføring.
  - Feltet Deduplication_GroupId viser gruppen eller klyngen som identifiseres i en enhet, som grupperer alle lignende oppføringer basert på de angitte dedupliseringsfeltene. Det brukes til systembehandlingsformål. Hvis det ikke er angitt noen regler for manuell deduplisering og systemdefinerte dedupliseringsregler gjelder, kan det hende du ikke finner dette feltet i utdataenheten for deduplisering.
  - Deduplication_WinnerId: Dette feltet inneholder vinner-ID-en fra de identifiserte gruppene eller klyngene. Hvis Deduplication_WinnerId er den samme som primærnøkkelverdien for en oppføring, betyr det at oppføringen er vinneroppføringen.
- Felter brukes til å definere dedupliseringsreglene.
- Feltene Regel og Poengsum for å angi hvilke av dedupliseringsreglene som ble brukt, og poengsummen som ble returnert av den samsvarende algoritmen.

## <a name="next-step"></a>Neste trinn

Konfigurer [aktiviteter](activities.md), [supplering](enrichment-hub.md) eller [relasjoner](relationships.md) for å få mer informasjon om kontaktene.
