---
title: Startside i målgruppeinnsikt
description: Kom i gang med å utforske appen på startsiden.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477053"
---
# <a name="create-a-new-environment"></a>Opprett et nytt miljø

## <a name="create-a-trial-environment"></a>Opprette et prøvemiljø

Du kan registrere deg for en prøveversjon på [registreringssiden for prøveversjon](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Prøveversjoner utløper etter 30 dager.

1. Velg alternativet for **Registrer deg for en gratis prøveversjon**, og velg **Registrer deg nå**.

1. Oppgi e-postadresse for jobb eller skole, og fortell oss mer om deg selv, og velg **Neste**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogen for å registrere deg for en prøveversjonsforekomst":::

1. Angi et **Navn** på det nye miljøet. 

1. Velg prøveversjonstype.

1. Velg **Område** for miljøet ditt.

1. Eksempel: For administratorer av en Dynamics 365-organisasjon: Velg **Avanserte innstillinger**, og angi URL-adressen til organisasjonen for å bruke prediksjonsfunksjoner som kundefrafall.

1. Velg **Opprett**. 

Når miljøet er opprettet, vil du se **Demo**-miljøet, som gjør det mulig å utforske appen med fiktive data. Du kan endre eksempeldataene, slik at de samsvarer med bransjen. Velg **Innstillinger**-ikonet i hodet, og velg **Demoinnstillinger**. Du kan også endre det visuelle temaet. 

Du [bytter til miljøet ](#switch-environments) du opprettet under registreringsprosessen, slik at du kan arbeide med dine egne data.

## <a name="create-a-new-production-or-sandbox-environment"></a>Opprette et nytt produksjons- eller sandkassemiljø

I miljøet velger du **Miljøer**-velgeren i apphodet i miljøet, og velg **Ny**.

Følg fremgangsmåten som om du [oppretter et prøvemiljø](#create-a-trial-environment). Som standard lagres data i den Customer Insights-styrte datasjøen. Du får et tilleggsalternativ når du velger **Avanserte innstillinger**, for lagring av data i din egen Azure Data Lake. Angi kontonavn og kontonøkkel for å opprette en tilkobling til Azure Data Lake. 

> [!IMPORTANT]
> Når du lagrer data i Azure Data Lake Storage, godtar du at dataene overføres til og lagres i den riktige geografiske plasseringen for denne Azure Storage-kontoen, som kan variere fra der dataene lagres i Dynamics 365 Customer Insights. [Finn ut mer om Microsofts klareringssenter.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Utforske startsiden

Du kan [få målgruppeinnsikt fra Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) på følgende nettadresse: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Startsiden** viser en oversikt over segmenter, målinger og suppleringsdata (hvis konfigurert) etter fullføring av fasene [tilordningen](map-entities.md), [samsvare](match-entities.md) og [slå sammen](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Innsikter på startside](media/home-page-insights.png "Innsikter på startside")

Under **Nylige segmenter** ser du grupper av kunder basert på demografiske, atferdsstyrte eller overførbare attributter som du har definert. [Oppretting av segementer](segments.md) hjelper deg med å gruppere kundebasen din og målrette forretningsaktivitetene dine bedre.

**Nylige mål** viser fliser med [viktige ytelsesindikatorer (KPI-er)](measures.md) du har definert. Det kan for eksempel være gjennomsnittlig sannsynlighet for at en kunde frafaller, eller gjennomsnittlig Internett-bruk per kunde.

Delen **Siste suppleringer** viser resultatene av de suppleringskjøringene som nylig ble utført. [Suppleringer](enrichment-hub.md) legger til informasjon om kundebasen. Hvis du for eksempel forstår interessene og merker de har affinitet for.

## <a name="switch-environments"></a>Bytt miljøer

Velg kontrollen **Miljø** øverst i høyre hjørne på siden for å endre miljøer.

> [!div class="mx-imgBorder"] 
> ![Bytt miljø](media/home-page-environment-switcher.png "Bytt miljø")

Administratorer kan opprette og administrere [flere miljøer](manage-environments.md). Det kan være nyttig å vedlikeholde mer enn ett miljø hvis organisasjonen for eksempel opererer internasjonalt og du må skille data og innsikt på forskjellige måter.

## <a name="next-step"></a>Neste trinn

Hvis du vil se din egen innsikt på startsiden, må du først [legge til datakilder](data-sources.md) og [samle](data-unification.md) dataene for å bygge kundeprofiler.


[!INCLUDE[footer-include](../includes/footer-banner.md)]