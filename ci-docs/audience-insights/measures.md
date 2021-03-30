---
title: Opprett og administrer mål
description: Definer mål som skal analyseres og gjenspeile selskapets ytelse.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654744"
---
# <a name="define-and-manage-measures"></a>Definere og administrere mål

Tiltak hjelper deg med å få bedre forståelse av kundeatferd og forretningsytelse ved å hente relevante verdier fra [enhetlige profiler](data-unification.md). En virksomhet vil for eksempel se *totalkostnaden per kunde* for å forstå den enkelte kundes kjøpshistorikk. Du kan også måle *det totale salget i selskapet* for å forstå omsetningen på aggregatnivå i hele selskapet.  

Tiltak opprettes ved hjelp av måleverktøyet, en dataspørringsplattform med forskjellige operatorer og enkle tilordningsalternativer. Den lar deg filtrere dataene, gruppere resultater, registrere [enhetsrelasjonsbaner](relationships.md) og forhåndsvise utdataene.

Bruk måleverktøyet til å planlegge forretningsaktiviteter ved å spørre etter kundedata og trekke ut innsikt. Hvis du for eksempel oppretter et mål for *totalkostnad per kunde* og *total avkastning per kunde*, blir det enklere å identifisere en gruppe kunder med høy avkastning, men likevel høy avkastning. Du kan [opprette et segment](segments.md) for å få de nest beste handlingene. 

## <a name="create-a-measure"></a>Opprette et mål

Denne delen beskriver hvordan du oppretter et nytt mål fra bunnen av. Du kan bygge et mål med dataattributter fra dataenheter som har en relasjon konfigurert til å koble til kundeenheten. 

1. I Målgruppeinnsikt går du til **Mål**.

1. Velg **Ny**.

1. Velg **Rediger navn**, og angi et **navn** for målet. 
   > [!NOTE]
   > Hvis den nye målkonfigurasjonen bare har to felter, for eksempel CustomerID og en beregning, blir utdataene lagt til som en ny kolonne i den systemgenererte enheten kalt Customer_Measure. Du kan også se målets verdi i den enhetlige kundeprofilen. Andre tiltak vil generere sine egne enheter.

1. Velg sammensettingsfunksjonen fra rullegardinlisten **Velg funksjon** i konfigurasjonsområdet. Aggregasjonsfunksjonene omfatter: 
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

1. Hvis det finnes flere baner mellom dataenheten du tilordnet og *Kunde*-enheten, må du velge en av de identifiserte [enhetsrelasjonsbanene](relationships.md). Måleresultatene kan variere avhengig av den valgte banen. 
   1. Velg **Datainnstillinger**, og velg enhetsbanen som skal brukes til å identifisere målet. Hvis det bare finnes én enkelt bane til *Kunde*-enheten, vises ikke denne kontrollen.
   1. Velg **Fullført** for å ta i bruk valget. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Velg enhetsbanen for målet.":::

1. Hvis du vil legge til flere beregninger for målet, velger du **Ny beregning**. Du kan bare bruke enheter i den samme enhetsbanen for nye beregninger. Flere beregninger vises som nye kolonner i målutdataenheten.

1. Velg **...** i beregningen til **Duplikat**, **Gi nytt navn** eller **Fjern** en beregning fra et mål.

1. I området **Forhåndsvisning** vises dataskjemaet for målutdataenheten, inkludert filtre og dimensjoner. Forhåndsvisningen reagerer dynamisk på endringer i konfigurasjonen.

1. Velg **Kjør** for å beregne resultater for det konfigurerte målet. Velg **Lagre og lukk** hvis du vil beholde gjeldende konfigurasjon og kjøre tiltaket senere.

1. Gå til **Mål** for å vise det nylig opprettede målet i listen.

## <a name="manage-your-measures"></a>Administrer målene dine

Etter at du har [opprettet et mål](#create-a-measure), vises en liste over mål på **Mål**-siden.

Du finner informasjon om måltypen, oppretteren, opprettingsdato, status og tilstand. Når du velger et mål fra listen, kan du forhåndsvise utdataene og laste ned en .CSV-fil.

Hvis du vil oppdatere alle målene samtidig, velger du **Oppdater alle** uten å velge et bestemt mål.

> [!div class="mx-imgBorder"]
> ![Handlinger for å administrere enkeltmål](media/measure-actions.png "Handlinger for å administrere enkeltmål")

Velg et mål fra listen for følgende alternativer:

- Velg målnavnet for å vise detaljene.
- **Rediger** konfigurasjonen av målet.
- **Oppdater** målet basert på de nyeste dataene.
- **Gi nytt navn** til målet.
- **Slett** målet.
- **Aktiver** eller **Deaktiver**. Inaktive tiltak oppdateres ikke under en [planlagt oppdatering](system.md#schedule-tab).

> [!TIP]
> Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser. De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies). Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben. Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.

## <a name="next-step"></a>Neste trinn

Du kan bruke eksisterende tiltak til å opprette [et kundesegment](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]