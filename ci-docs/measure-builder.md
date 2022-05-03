---
title: Opprett nye mål med målverktøyet
description: Bygg mål fra bunnen av for å analysere nøkkeltallene for virksomheten.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 6370df0287362a5512a837cdb588f5d20ef03d3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647286"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Bruk måleverktøyet til å opprette mål fra bunnen av

Denne artikkelen forklarer hvordan du oppretter et nytt [mål](measures.md) fra bunnen av. Måleverktøyet lar deg definere beregninger ved hjelp av matteoperatorer, sammensettingsfunksjoner og filtre. Du kan bygge et mål med attributter fra enheter som er relatert til den enhetlige enheten *Kunde*.

Oppretting av mål i B2C- og B2B-miljøer fungerer på samme måte. Hvis du B2B-miljøet [bruker kontoer med hierarkier](relationships.md#set-up-account-hierarchies), kan du imidlertid velge å aggregere målet på tvers av relaterte underordnede forretningsforbindelser.

Du kan også raskt opprette et mål ved å velge fra et sett med vanlige og forhåndsdefinerte mål. Hvis du vil ha mer informasjon, kan du se [Bruk en mal til å bygge et mål](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

Du kan opprette mål på nivået for individuelle kunder (kundeattributt, kundemål) eller på forretnings-/organisasjonsnivå (forretningsmål). Kundeattributt og kundemål er to typer som gjør det mulig å spore ytelse per kunde. For eksempel totalkostnaden for hver kunde. Forretningsmål gjør det mulig å spore ytelse per virksomhet. For eksempel den totale omsetningen per firma.

- Kundeattributt: Genererer utdata som et nytt attributt, som blir lagret som en ny kolonne i den systemgenererte enheten *Customer_Measure*. Når du oppdaterer et kundeattributt, oppdateres alle de andre kundeattributtene i *Customer_Measure* samtidig. I tillegg vises kundeattributter på kundeprofilkortet. Når du har kjørt eller lagret, kan du ikke endre kundeattributtet til et kundemål.

- Kundemål: Genererer utdata som sin egen enhet, og du kan ikke endre det til et kundeattributt når de er kjørt eller lagret. Kundemål vises ikke på kundeprofilkortet.

- Forretningsmål: Genererer utdata som sin egen enhet og vises på startsiden i Customer Insights-miljøet.

1. Gå til **Mål**.

1. Velg **Ny** og deretter **Bygg din egen**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tom konfigurasjonsskjerm for et B2C-mål. " lightbox="media/measure-b2c.png":::

1. Hvis du vil spore ytelse på forretningsnivå, veksler du **Måltype** til **Forretningsnivå**. **Kundenivå** er valgt som standard. **Kundenivå** legger automatisk til attributtet *CustomerId* i Dimensjoner, mens **Forretningsnivå** automatisk fjerner det.

1. Velg aggregasjonsfunksjon fra rullegardinlisten **Velg funksjon** i konfigurasjonsområdet. Aggregasjonsfunksjonene omfatter:
   - **Sum**
   - **Gjennomsnitt**
   - **Antall**
   - **Antall unike**
   - **Max**
   - **Min**
   - **Første**: tar den første verdien i dataoppføringen
   - **Siste**: tar den siste verdien som ble lagt til i dataoppføringen
   - **ArgMax**: finner dataoppføringen som gir maksimumsverdien fra en målfunksjon
   - **ArgMin**: finner dataoppføringen som gir minimumsverdien fra en målfunksjon

1. Velg **Legg til attributt** for å velge dataene du vil opprette dette målet.

   1. Velg fanen **Attributtene**.
   1. Dataenhet: Velg enheten som inneholder attributtet du vil måle.
   1. Dataattributt: Velg attributtet du vil bruke i aggregasjonsfunksjonen, for å beregne målet. Du kan bare velge ett attributt om gangen.
   1. Du kan også velge et dataattributt fra et eksisterende mål ved å velge fanen **Mål**. Du kan også søke etter et enhets- eller målnavn.
   1. Velg **Legg til** for å legge til det valgte attributtet i målet.

1. Hvis du vil bygge mer komplekse tiltak, kan du legge til flere attributter eller bruke operatorer for målefunksjon.

1. Hvis du vil legge til filtre, velger du **Filter** i konfigurasjonsområdet. Bruk av filtre bruker bare oppføringene som samsvarer med filtrene, til å beregne målet.
  
   1. I delen **Legg til attributt** i **Filtre**-ruten velger du attributtet du vil bruke til å opprette filtre.
   1. Angi filteroperatorene for å definere filteret for hvert valgte attributt.
   1. Velg **Bruk** for å legge til filtrene i målet.

1. Velg **Dimensjon** for å velge flere felter som legges til som kolonner i målutdataenheten.

   1. Velg **Rediger dimensjoner** for å legge til dataattributter du vil gruppere målverdiene etter. For eksempel poststed eller kjønn.
   > [!TIP]
   > Hvis du valgte **Kundenivå** som **måltypen**, er attributtet *CustomerId* allerede lagt til. Hvis du fjerner attributtet, veksles **Måltype** til **Forretningsnivå**.
   1. Velg **Ferdig** for å legge til dimensjonene i målet.

1. Hvis det finnes verdier i dataene som du må erstatte med et heltall, velger du **Regler**. Konfigurer regelen, og pass på at du bare velger hele tall som erstatning. Du kan for eksempel erstatte *null* med *0*.

1. Hvis det finnes flere baner mellom dataenheten du tilordnet og *Kunde*-enheten, må du velge en av de identifiserte [enhetsrelasjonsbanene](relationships.md). Måleresultatene kan variere avhengig av den valgte banen.

   1. Velg **Relasjonsbane**, og velg enhetsbanen som skal brukes til å identifisere målet. Hvis det bare finnes én enkelt bane til *Kunde*-enheten, vises ikke denne kontrollen.
   1. Velg **Fullført** for å ta i bruk valget.

1. Hvis du vil legge til flere beregninger for målet, velger du **Ny beregning**. Du kan bare bruke enheter i den samme enhetsbanen for nye beregninger. Flere beregninger vises som nye kolonner i målutdataenheten.

1. Velg **...** i beregningen til **Duplikat**, **Gi nytt navn** eller **Fjern** en beregning fra et mål.

1. I området **Forhåndsvisning** vises dataskjemaet for målutdataenheten, inkludert filtre og dimensjoner. Forhåndsvisningen reagerer dynamisk på endringer i konfigurasjonen.

1. Velg **Rediger detaljer** ved siden av Mål uten tittel. Oppgi et navn for målet. Du kan eventuelt legge til [merker](work-with-tags-columns.md#manage-tags) i målet.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogboksen Rediger detaljer.":::

1. Velg **Kjør** for å beregne resultater for det konfigurerte målet. Velg **Lagre og lukk** hvis du vil beholde gjeldende konfigurasjon og kjøre tiltaket senere.

1. Gå til **Mål** for å vise det nylig opprettede målet i listen.

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

Du kan opprette mål på nivået for individuelle kontoer (kundemål) eller på nivået for alle kontoer (forretningsmål).

- Kundemål: Genererer utdata som sin egen enhet. Kundemål vises ikke på kundeprofilkortet.

- Forretningsmål: Genererer utdata som sin egen enhet og vises på startsiden i Customer Insights-miljøet.

1. Gå til **Mål**.

1. Velg **Ny**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tom konfigurasjonsskjerm for et B2B-mål. ":::

1. Velg aggregasjonsfunksjon fra rullegardinlisten **Velg funksjon** i konfigurasjonsområdet. Aggregasjonsfunksjonene omfatter:
   - **Sum**
   - **Gjennomsnitt**
   - **Antall**
   - **Antall unike**
   - **Max**
   - **Min**
   - **Første**: tar den første verdien i dataoppføringen
   - **Siste**: tar den siste verdien som ble lagt til i dataoppføringen

1. Velg **Legg til attributt** for å velge dataene du vil opprette dette målet.

   1. Velg fanen **Attributtene**.
   1. Dataenhet: Velg enheten som inneholder attributtet du vil måle.
   1. Dataattributt: Velg attributtet du vil bruke i aggregasjonsfunksjonen, for å beregne målet. Du kan bare velge ett attributt om gangen.
   1. Du kan også velge et dataattributt fra et eksisterende mål ved å velge fanen **Mål**. Du kan også søke etter et enhets- eller målnavn.
   1. Velg **Legg til** for å legge til det valgte attributtet i målet.

1. Hvis du vil bygge mer komplekse tiltak, kan du legge til flere attributter eller bruke operatorer for målefunksjon.

1. Hvis du vil legge til filtre, velger du **Filter** i konfigurasjonsområdet. Bruk av filtre bruker bare oppføringene som samsvarer med filtrene, til å beregne målet.
  
   1. I delen **Legg til attributt** i **Filtre**-ruten velger du attributtet du vil bruke til å opprette filtre.
   1. Angi filteroperatorene for å definere filteret for hvert valgte attributt.
   1. Velg **Bruk** for å legge til filtrene i målet.

1. Velg **Dimensjon** for å velge flere felter som legges til som kolonner i målutdataenheten.

   1. Velg **Rediger dimensjoner** for å legge til dataattributter du vil gruppere målverdiene etter. For eksempel poststed eller kjønn.
      > [!TIP]
      > Hvis du valgte **Kundenivå** som **måltypen**, er attributtet *CustomerId* allerede lagt til. Hvis du fjerner attributtet, byttes **Måltype** til **Forretningsnivå**.
   1. Velg **Ferdig** for å legge til dimensjonene i målet.

1. Hvis det finnes verdier i dataene som du må erstatte med et heltall, velger du **Regler**. Konfigurer regelen, og pass på at du bare velger hele tall som erstatning. Du kan for eksempel erstatte *null* med *0*.

1. Du kan bruke veksleknappen **Rull opp underordnede kontoer** hvis du [bruker forretningsforbindelser med hierarkier](relationships.md#set-up-account-hierarchies).
   - Hvis den er satt til **Av**, beregnes målet for hver forretningsforbindelse. Hver forretningsforbindelse får eget resultat.
   - Hvis den er satt til **På**, velger du **Rediger** for å velge kontohierarkiet i henhold til de innlagte hierarkiene. Målet gir bare ett resultat fordi det er aggregert med underordnede forretningsforbindelser.

1. Hvis det finnes flere baner mellom dataenheten du tilordnet og *Kunde*-enheten, må du velge en av de identifiserte [enhetsrelasjonsbanene](relationships.md). Måleresultatene kan variere avhengig av den valgte banen.

   1. Velg **Relasjonsbane**, og velg enhetsbanen som skal brukes til å identifisere målet. Hvis det bare finnes én enkelt bane til *Kunde*-enheten, vises ikke denne kontrollen.
   1. Velg **Fullført** for å ta i bruk valget.

1. Velg **...** i beregningen til **Duplikat**, **Gi nytt navn** eller **Fjern** en beregning fra et mål.

1. I området **Forhåndsvisning** vises dataskjemaet for målutdataenheten, inkludert filtre og dimensjoner. Forhåndsvisningen reagerer dynamisk på endringer i konfigurasjonen.

1. Velg **Rediger detaljer** ved siden av Mål uten tittel. Oppgi et navn for målet. Du kan eventuelt legge til [merker](work-with-tags-columns.md#manage-tags) i målet.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogboksen Rediger detaljer.":::

1. Velg **Kjør** for å beregne resultater for det konfigurerte målet. Velg **Lagre og lukk** hvis du vil beholde gjeldende konfigurasjon og kjøre tiltaket senere.

1. Gå til **Mål** for å vise det nylig opprettede målet i listen.
