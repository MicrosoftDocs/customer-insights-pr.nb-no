---
title: Opprett og rediger mål
description: Definere kunderelaterte tiltak for å analysere og gjenspeile ytelsen til bestemte forretningsområder.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406534"
---
# <a name="define-and-manage-measures"></a>Definere og administrere mål

**Mål** representerer viktige ytelsesindikatorer (KPI-er) som gjenspeiler ytelsen og tilstanden til bestemte forretningsområder. Målgruppeinnsikt gir en intuitiv opplevelse for bygging av ulike typer mål, ved hjelp av et spørringsverktøy som ikke krever at du skriver kode eller validerer målene manuelt. Du kan spore forretningsmålene på siden **Start**, se mål for bestemte kunder på **Kundekort** og bruke mål til å definere kundesegmenter på siden **Segmenter**.

## <a name="create-a-measure"></a>Opprette et mål

Denne delen veileder deg gjennom opprettingen av et mål fra bunnen av. Du kan bygge tiltak med data fra flere datakilder som er koblet sammen via kundeenheten. Enkelte [tjenestebegrensninger](service-limits.md) gjelder.

1. I Målgruppeinnsikt går du til **Mål**.

2. Velg **Nye mål**.

3. Velg målet **Type**:

   - **Kundeattributt**: Et enkelt felt per kunde som gjenspeiler en poengsum, en verdi eller en tilstand for kunden. Kundeattributter opprettes som attributter i en ny systemgenerert enhet som kalles **Kundemål**.

   - **Kundemål**: Innsikt i kundeatferd med nedbryting etter valgte dimensjoner. Det genereres en ny enhet for hvert mål, potensielt med flere oppføringer per kunde.

   - **Forretningsmål**: Sporer forretningsprestasjonen og tilstanden til virksomheten. Forretningstiltak kan ha to forskjellige resultater: et numerisk resultat som vises på siden **Start** eller en ny enhet som du finner på siden **Enheter**.

4. Angi et **Navn** og et valgfritt **Visningsnavn**, og velg **Neste**.

5. I delen **Enheter** velger du første enhet fra rullegardinlisten. Du bør nå bestemme om det skal brukes tilleggsenheter som en del av måldefinisjonen.

   > [!div class="mx-imgBorder"]
   > ![Måldefinisjon](media/measure-definition.png "Måldefinisjon")

   Hvis du vil legge til flere enheter, velger du **Legg til enhet**, og velg enhetene du vil bruke for målet.

   > [!NOTE]
   > Du kan bare velge enheter som har relasjoner til startenheten din. Hvis du vil ha mer informasjon om hvordan du definerer relasjoner, se [Relasjoner](relationships.md).

6. Du kan eventuelt konfigurere variabler. I delen **Variabler** velger du **Ny variabel**.

   Variabler er beregninger som gjøres for hver av de valgte oppføringene. Eksempel: Sammendrag av salgssted (POS) og onlinesalg for hver av kundenes oppføringer.

7. Gi variabelen et **Navn**.

8. I området **Uttrykk** velger du et felt å begynne beregningen med.

9. Skriv inn et uttrykk i området **Uttrykk** mens du velger flere felt som skal tas med i beregningen.

   > [!NOTE]
   > For øyeblikket støttes bare aritmetiske uttrykk. I tillegg støttes ikke variabelberegning for enheter fra forskjellige [enhetsbaner](relationships.md).

10. Velg **Ferdig**.

11. I delen **Måldefinisjon** definerer du hvordan de valgte enhetene og de beregnede variablene samles i en ny målenhet eller et nytt attributt.

12. Velg **Ny dimensjon**. Du kan tenke på en dimensjon som en *grupper etter*-funksjon. Utdataene for målenheten eller attributtet blir gruppert etter alle de definerte dimensjonene.

    > [!div class="mx-imgBorder"]
    > ![Velg samlesyklus](media/measures-businessreport-measure-definition2.png "Velg samlesyklus")

    Velg eller angi følgende informasjon som en del av dimensjonens definisjon:

    - **Enhet**: Hvis du angir en målenhet, må den inneholde minst ett attributt. Hvis du angir et målattributt, vil det bare inneholde ett attributt som standard. Dette valget handler om å velge enheten som inneholder det attributtet.
    - **Felt**: Velg det bestemte attributtet som skal inkluderes enten i målenheten eller i attributtet.
    - **Samling**: Velg om du vil samle data daglig, månedlig eller årlig. Det er et nødvendig valg bare hvis du har valgt et datotype-attributt.
    - **Som**: Definerer navnet på det nye feltet.
    - **Visningsnavn**: Definerer visningsnavnet for feltet.

    > [!NOTE]
    > Forretningsmålet blir lagret som en enhet med ett tall og vises på siden **Start** mindre du legger til flere dimensjoner i målet. Målet vil *ikke* vises på siden **Start** etter at du har lagt til flere dimensjoner.

13. Hvis du vil, kan du legge til aggregeringsfunksjoner. Alle aggregasjoner du oppretter, fører til en ny verdi i målenheten eller attributtet. Støttede aggregeringsfunksjoner er: **Min**, **Maks**, **Gjennomsnitt**, **Median**, **Sum**, **Antall unike**, **Første** (tar den første oppføringen for en dimensjonsverdi) og **Siste** (tar den siste oppføringen til en dimensjonsverdi).

14. Velg **Lagre** for å bruke endringene på målet.

## <a name="manage-your-measures"></a>Administrer målene dine

Etter at du har opprettet minst ett mål, vises en liste over mål på **Mål**-siden.

Du finner informasjon om måltypen, oppretteren, opprettelsesdato og -tidspunkt, dato og klokkeslett for siste redigering, status (om målet er aktivt, inaktivt eller mislykket), og dato og tidspunkt for siste oppdatering. Når du velger et mål fra listen, kan du se en forhåndsvisning av utdataene.

Hvis du vil oppdatere alle målene samtidig, velger du **Oppdater alle** uten å velge et bestemt mål.

> [!div class="mx-imgBorder"]
> ![Handlinger for å administrere enkeltmål](media/measure-actions.png "Handlinger for å administrere enkeltmål")

Alternativt kan du velge et mål fra listen og utføre én av følgende handlinger:

- Velg målnavnet for å vise detaljene.
- **Rediger** konfigurasjonen av målet.
- **Gi nytt navn** til målet.
- **Slett** målet.
- Velg ellipsen (...), og deretter **Oppdater** for å starte oppdateringsprosessen for målet.
- Velg ellipsen (...), og deretter **Last ned** for å hente en .CSV-fil for målet.

> [!TIP]
> Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser. De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies). Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben. Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.

## <a name="next-step"></a>Neste trinn

Du kan bruke eksisterende mål for å opprette ditt første kundesegment på siden **Segmenter**. Du finner mer informasjon på [Segmenter](segments.md).
