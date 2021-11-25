---
title: Opprett og administrer mål
description: Definer mål som skal analyseres og gjenspeile selskapets ytelse.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f6be11bd97be71bc0c3a58eaee4d8ed45f535877
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732738"
---
# <a name="define-and-manage-measures"></a>Definere og administrere mål

Tiltak hjelper deg med å få bedre forståelse av kundeatferd og forretningsytelse. De ser på relevante verdier fra [enhetlige profiler](data-unification.md). En virksomhet vil for eksempel se *totalkostnaden per kunde* for å forstå en individuell kundes kjøpshistorikk eller måle *totalt salg av firmaet* for å forstå omsetningen på aggregert nivå i hele virksomheten.  

Tiltak opprettes ved hjelp av måleverktøyet, en dataspørringsplattform med forskjellige operatorer og enkle tilordningsalternativer. Den lar deg filtrere dataene, gruppere resultater, registrere [enhetsrelasjonsbaner](relationships.md) og forhåndsvise utdataene.

Bruk måleverktøyet til å planlegge forretningsaktiviteter ved å spørre etter kundedata og trekke ut innsikt. Hvis du for eksempel oppretter et mål for *totalkostnad per kunde* og *total avkastning per kunde*, blir det enklere å identifisere en gruppe kunder med høy avkastning, men likevel høy avkastning. Du kan [opprette et segment](segments.md) for å få de nest beste handlingene. 

## <a name="build-your-own-measure-from-scratch"></a>Bygg ditt eget mål fra bunnen av

Denne delen beskriver hvordan du oppretter et nytt mål fra bunnen av. Du kan bygge et mål med dataattributter fra dataenheter som har en relasjon konfigurert til å koble til enheten for enhetlig kundeprofil.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

1. I Målgruppeinnsikt går du til **Mål**.

1. Velg **Ny** og deretter **Bygg din egen**.

1. Velg **Rediger navn**, og angi et **navn** for målet. 

1. Velg aggregasjonsfunksjon fra rullegardinlisten **Velg funksjon** i konfigurasjonsområdet. Aggregasjonsfunksjonene omfatter: 
   - **Sum**
   - **Gjennomsnitt**
   - **Antall**
   - **Antall unike**
   - **Max**
   - **Min**
   - **Første**: tar den første verdien i dataoppføringen
   - **Siste**: tar den siste verdien som ble lagt til i dataoppføringen

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorer for måleberegninger.":::

1. Velg **Legg til attributt** for å velge dataene du vil opprette dette målet.
   
   1. Velg fanen **Attributtene**. 
   1. Dataenhet: Velg enheten som inneholder attributtet du vil måle. 
   1. Dataattributt: Velg attributtet du vil bruke i aggregasjonsfunksjonen, for å beregne målet. Du kan bare velge ett attributt om gangen.
   1. Du kan også velge et dataattributt fra et eksisterende mål ved å velge fanen **Mål**. Du kan også søke etter et enhets- eller målnavn. 
   1. Velg **Legg til** for å legge til det valgte attributtet i målet.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Velg et attributt som skal brukes i beregninger.":::

1. Hvis du vil bygge mer komplekse tiltak, kan du legge til flere attributter eller bruke operatorer for målefunksjon.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Opprett et komplekst mål med matteoperatorer.":::

1. Hvis du vil legge til filtre, velger du **Filter** i konfigurasjonsområdet. 
  
   1. I delen **Legg til attributt** i **Filtre**-ruten velger du attributtet du vil bruke til å opprette filtre.
   1. Angi filteroperatorene for å definere filteret for hvert valgte attributt.
   1. Velg **Bruk** for å legge til filtrene i målet.

1. Hvis du vil legge til dimensjoner, velger du **Dimensjon** i konfigurasjonsområdet. Dimensjoner vises som kolonner i målutdataenheten.
 
   1. Velg **Rediger dimensjoner** for å legge til dataattributter du vil gruppere målverdiene etter. For eksempel poststed eller kjønn. Som standard velges *CustomerID*-dimensjonen for å opprette *mål på kundenivå*. Du kan fjerne standarddimensjonen hvis du vil opprette *tiltak på forretningsnivå*.
   1. Velg **Ferdig** for å legge til dimensjonene i målet.

1. Hvis det finnes verdier i dataene som du må erstatte med et heltall, velger du **Regler**. Konfigurer regelen, og pass på at du bare velger hele tall som erstatning. Du kan for eksempel erstatte *null* med *0*.

1. Hvis det finnes flere baner mellom dataenheten du tilordnet og *Kunde*-enheten, må du velge en av de identifiserte [enhetsrelasjonsbanene](relationships.md). Måleresultatene kan variere avhengig av den valgte banen. 
   
   1. Velg **Relasjonsbane**, og velg enhetsbanen som skal brukes til å identifisere målet. Hvis det bare finnes én enkelt bane til *Kunde*-enheten, vises ikke denne kontrollen.
   1. Velg **Fullført** for å ta i bruk valget. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Velg enhetsbanen for målet.":::

1. Hvis du vil legge til flere beregninger for målet, velger du **Ny beregning**. Du kan bare bruke enheter i den samme enhetsbanen for nye beregninger. Flere beregninger vises som nye kolonner i målutdataenheten.

1. Velg **...** i beregningen til **Duplikat**, **Gi nytt navn** eller **Fjern** en beregning fra et mål.

1. I området **Forhåndsvisning** vises dataskjemaet for målutdataenheten, inkludert filtre og dimensjoner. Forhåndsvisningen reagerer dynamisk på endringer i konfigurasjonen.

1. Velg **Kjør** for å beregne resultater for det konfigurerte målet. Velg **Lagre og lukk** hvis du vil beholde gjeldende konfigurasjon og kjøre tiltaket senere.

1. Gå til **Mål** for å vise det nylig opprettede målet i listen.

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

1. I Målgruppeinnsikt går du til **Mål**.

1. Velg **Ny** og deretter **Bygg din egen**.

1. Velg **Rediger navn**, og angi et **navn** for målet. 

1. Velg aggregasjonsfunksjon fra rullegardinlisten **Velg funksjon** i konfigurasjonsområdet. Aggregasjonsfunksjonene omfatter: 
   - **Sum**
   - **Gjennomsnitt**
   - **Antall**
   - **Antall unike**
   - **Max**
   - **Min**
   - **Første**: tar den første verdien i dataoppføringen
   - **Siste**: tar den siste verdien som ble lagt til i dataoppføringen

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorer for måleberegninger.":::

1. Velg **Legg til attributt** for å velge dataene du vil opprette dette målet.
   
   1. Velg fanen **Attributtene**. 
   1. Dataenhet: Velg enheten som inneholder attributtet du vil måle. 
   1. Dataattributt: Velg attributtet du vil bruke i aggregasjonsfunksjonen, for å beregne målet. Du kan bare velge ett attributt om gangen.
   1. Du kan også velge et dataattributt fra et eksisterende mål ved å velge fanen **Mål**. Du kan også søke etter et enhets- eller målnavn. 
   1. Velg **Legg til** for å legge til det valgte attributtet i målet.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Velg et attributt som skal brukes i beregninger.":::

1. Hvis du vil bygge mer komplekse tiltak, kan du legge til flere attributter eller bruke operatorer for målefunksjon.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Opprett et komplekst mål med matteoperatorer.":::

1. Hvis du vil legge til filtre, velger du **Filter** i konfigurasjonsområdet. 
  
   1. I delen **Legg til attributt** i **Filtre**-ruten velger du attributtet du vil bruke til å opprette filtre.
   1. Angi filteroperatorene for å definere filteret for hvert valgte attributt.
   1. Velg **Bruk** for å legge til filtrene i målet.

1. Hvis du vil legge til dimensjoner, velger du **Dimensjon** i konfigurasjonsområdet. Dimensjoner vises som kolonner i målutdataenheten.
 
   1. Velg **Rediger dimensjoner** for å legge til dataattributter du vil gruppere målverdiene etter. For eksempel poststed eller kjønn. Som standard velges *CustomerID*-dimensjonen for å opprette *mål på kundenivå*. Du kan fjerne standarddimensjonen hvis du vil opprette *tiltak på forretningsnivå*.
   1. Velg **Ferdig** for å legge til dimensjonene i målet.

1. Hvis det finnes verdier i dataene som du må erstatte med et heltall, velger du **Regler**. Konfigurer regelen, og pass på at du bare velger hele tall som erstatning. Du kan for eksempel erstatte *null* med *0*.

1. Du kan bruke veksleknappen **Rull opp underordnede kontoer** hvis du [bruker forretningsforbindelser med hierarkier](relationships.md#set-up-account-hierarchies).
   - Hvis den er satt til **Av**, beregnes målet for hver forretningsforbindelse. Hver forretningsforbindelse får eget resultat.
   - Hvis den er satt til **På**, velger du **Rediger** for å velge kontohierarkiet i henhold til de innlagte hierarkiene. Målet gir bare ett resultat fordi det er aggregert med underordnede forretningsforbindelser.

1. Hvis det finnes flere baner mellom dataenheten du tilordnet og *Kunde*-enheten, må du velge en av de identifiserte [enhetsrelasjonsbanene](relationships.md). Måleresultatene kan variere avhengig av den valgte banen. 
   
   1. Velg **Relasjonsbane**, og velg enhetsbanen som skal brukes til å identifisere målet. Hvis det bare finnes én enkelt bane til *Kunde*-enheten, vises ikke denne kontrollen.
   1. Velg **Fullført** for å ta i bruk valget. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Velg enhetsbanen for målet.":::

1. Velg **...** i beregningen til **Duplikat**, **Gi nytt navn** eller **Fjern** en beregning fra et mål.

1. I området **Forhåndsvisning** vises dataskjemaet for målutdataenheten, inkludert filtre og dimensjoner. Forhåndsvisningen reagerer dynamisk på endringer i konfigurasjonen.

1. Velg **Kjør** for å beregne resultater for det konfigurerte målet. Velg **Lagre og lukk** hvis du vil beholde gjeldende konfigurasjon og kjøre tiltaket senere.

1. Gå til **Mål** for å vise det nylig opprettede målet i listen.

---

## <a name="use-a-template-to-build-a-measure"></a>Bruke en mal til å bygge et mål

Du kan bruke forhåndsdefinerte maler for vanlige mål for å opprette dem. Detaljerte beskrivelser av malene og en veiledet opplevelse hjelper deg med effektiv måloppretting. Maler bygger på tilordnede data fra *Enhetlig aktivitet*-enheten. Sørg derfor for at du har konfigurert [kundeaktiviteter](activities.md) før du oppretter et mål fra en mal.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

Du kan bruke forhåndsdefinerte maler for vanlige mål for å opprette dem. Detaljerte beskrivelser av malene og en veiledet opplevelse hjelper deg med effektiv måloppretting. Maler bygger på tilordnede data fra *Enhetlig aktivitet*-enheten. Sørg derfor for at du har konfigurert [kundeaktiviteter](activities.md) før du oppretter et mål fra en mal.

Tilgjengelige målmaler: 
- Gjennomsnittlig transaksjonsverdi (ATV)
- Total transaksjonsverdi
- Gjennomsnittlig daglig omsetning
- Gjennomsnittlig årlig omsetning
- Transaksjonstelling
- Opptjente fordelspoeng
- Innløste fordelspoeng
- Saldo for fordelspoeng
- Levetid for aktiv kunde
- Varighet for fordelsmedlemskap
- Tid siden forrige kjøp

Fremgangsmåten nedenfor beskriver hvordan du bygger et nytt mål ved hjelp av en mal.

1. I Målgruppeinnsikt går du til **Mål**.

1. Velg **Ny** og deretter **Velg en mal**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Skjermbilde av rullegardinmenyen når du oppretter et nytt mål med utheving på mal.":::

1. Finn malen du ønsker, og velg **Velg mal**.

1. Se gjennom de nødvendige dataene, og velg **Kom i gang** hvis du har alle dataene på plass.

1. Angi navnet på målet og utdataenheten i **Rediger navn**-ruten. 

1. Velg **Ferdig**.

1. I delen **Angi tidsperiode** definerer du tidsrammen for dataene som skal brukes. Velg om du vil at det nye målet skal dekke hele datasett, ved å velge **Alle tider**, eller om du vil at målet skal fokusere på en **Bestemt tidsperiode**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Skjermbilde som viser tidsperiodedelen når du konfigurerer et mål fra en mal.":::

1. I den neste delen velger du **Legg til data** for å velge aktivitetene og tilordne de tilsvarende dataene fra enheten *Enhetlig aktivitet*.

    1. Trinn 1 av 2: Under **Aktivitetstype** velger du typen enhet du vil bruke. For **Aktiviteter** velger du enhetene du vil tilordne.
    1. Trinn 2 av 2: Velg attributtet fra enheten *Enhetlig aktivitet* for komponenten som kreves av formelen. For gjennomsnittlig transaksjonsverdi er det for eksempel attributtet som representerer transaksjonsverdien. For **Aktivitetstidsstempel** velger du attributtet fra enheten Enhetlig aktivitet som representerer datoen og klokkeslettet for aktiviteten.
   
1. Når datatilordningen er vellykket, kan du se statusen **Fullført** og navnet på de tilordnede aktivitetene og attributtene.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Skjermbilde av en fullført målmalkonfigurasjon.":::

1. Du kan nå velge **Kjør** for å beregne resultatene av målet. Hvis du vil finjustere det senere, velger du **Lagre utkast**.

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

Denne funksjonen er bare tilgjengelig for tiltak som er opprettet i miljøer med individuelle kunder som primær målgruppe.

---

## <a name="manage-your-measures"></a>Administrer målene dine

Du finner mållisten på **Mål**-siden.

Du finner informasjon om måltypen, oppretteren, opprettingsdato, status og tilstand. Når du velger et mål fra listen, kan du forhåndsvise utdataene og laste ned en CSV-fil.

Hvis du vil oppdatere alle målene samtidig, velger du **Oppdater alle** uten å velge et bestemt mål.

> [!div class="mx-imgBorder"]
> ![Handlinger for å administrere enkeltmål.](media/measure-actions.png "Handlinger for å administrere enkeltmål.")

Velg et mål fra listen for følgende alternativer:

- Velg målnavnet for å vise detaljene.
- **Rediger** konfigurasjonen av målet.
- **Oppdater** målet basert på de nyeste dataene.
- **Gi nytt navn** til målet.
- **Slett** målet.
- **Aktiver** eller **Deaktiver**. Inaktive tiltak oppdateres ikke under en [planlagt oppdatering](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Neste trinn

Du kan bruke eksisterende målinger til å opprette [et kundesegment](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
