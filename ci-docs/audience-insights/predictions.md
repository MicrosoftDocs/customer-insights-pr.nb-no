---
title: Fullføre delvise data ved hjelp av prognoser
description: Bruk prognoser til å fylle ut ufullstendige kundedata.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6ce72486faa97e6f630a991044ca5e6d4714d0b8b8395a60fad12f3e3a49fa29
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032447"
---
# <a name="complete-your-partial-data-with-predictions"></a>Fyll ut de delvise dataene med prognoser

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Med prognoser er det mulig å enkelt opprette predisjonsverdier som kan forbedre forståelsen av en kunde. På siden **Intelligens** > **Prediksjoner** kan du velge **Mine prediksjoner** for å se prediksjoner som du har konfigurert i andre deler av målgruppeinnsikt, og du kan tilpasse dem ytterligere.

> [!NOTE]
> Du kan ikke bruke denne funksjonen hvis miljøet ditt bruker Azure Data Lake Gen 2-lagring.
>
> Prognosefunksjonen bruker automatiske gjennomsnitt for å evaluere data og foreta prognoser basert på disse dataene, og har derfor mulighet til å bruke dem som en profileringsmetode, slik termen defineres av EUs personvernforordning ("GDPR"). Kundens bruk av denne funksjonen til å behandle data kan være underlagt GDPR eller andre lover eller bestemmelser. Du er ansvarlig for å sikre at bruken av Dynamics 365 Customer Insights, inkludert prognoser, samsvarer med alle gjeldende lover og bestemmelser, inkludert lover som er relatert til personvern, personlige data, biometriske data, databeskyttelse og konfidensialitet for kommunikasjon.

## <a name="prerequisites"></a>Forutsetninger

Før organisasjonen kan bruke prognosefunksjonen, må du kontrollere at følgende forhåndskrav er oppfylt:

1. Organisasjonen har [konfigurert en forekomst i Microsoft Dataverse](/ai-builder/build-model#prerequisites), og den er i samme organisasjon som Customer Insights.

2. Ditt målgruppeinnsiktsmiljø er knyttet til Dataverse-forekomsten din.

Hvis du [oppretter et nytt miljø](get-started-paid.md), konfigurerer du det i dialogboksen **Opprett et miljø** og velger **Avansert**. Hvis du allerede har opprettet et miljø, går du til innstillingene og velger **Avansert**. Uansett går du til delen **Bruk prediksjoner** og angir URL-adressen til Dataverse-forekomsten som du vil knytte miljøet ditt til.

## <a name="create-a-prediction-in-the-customer-entity"></a>Opprette en prognose i kundeenheten

1. I Målgruppeinnsikt går du til **Data** > **Enheter**.

2. Velg enheten **Kunde**.

3. I enheten **Customer: CustomerInsights** velger du i fanen **Felt**.

4. Finn attributtnavnet du vil forutsi verdier for, og velg deretter ikonet **Oversikt** i kolonnen **Sammendrag**.
   > [!div class="mx-imgBorder"]
   > ![Oversikt-ikon.](media/intelligence-overviewicon.png "Oversikt-ikon")

5. Hvis det er mange manglende verdier for attributtet, velger du **Forutsi manglende verdier** for å fortsette med prognosen.
   > [!div class="mx-imgBorder"]
   > ![Oversiktsstatus med knappen for å forutsi manglende verdier.](media/intelligence-overviewpredictmissingvalues.png "Oversiktsstatus med knappen for å forutsi manglende verdier")

6. Angi et **Visningsnavn** og et **Navn på utdataenhet** for resultatet av prognosen.

7. En forhåndsvalgt liste over alternativer viser hvor du kan tilordne verdiene til en prognosekategori. I dette tilfellet vil de eneste kategorialternativene være 0 eller 1 fordi de tilordnes til den sanne/usanne eller binære typen av prognosen. I kolonnen Kategori tilordner du feltverdiene du vil klassifisere som "0" i den endelige prognosen, til "0", og elementene du vil klassifisere som "1" i den siste prognosen, til "1".
   > [!div class="mx-imgBorder"]
   > ![Eksempel på tilordnede feltverdier i kategorier.](media/intelligence-categorymapping.png "Eksempel på tilordnede feltverdier i kategorier")

8. Velg **Ferdig**, og prognosen blir behandlet. Behandlingen vil ta litt tid, avhengig av størrelsen på og kompleksiteten av data. Resultater er tilgjengelige i en ny enhet basert på **Navn på utdataenhet** til den opprettede prognosen.

## <a name="create-a-prediction-while-creating-a-segment"></a>Opprette en prognose når du oppretter et segment

Det er også mulig å forutsi manglende verdier for et bestemt attributt når et segment opprettes. Spesielt når du raskt oppretter et segment basert på enten den enhetlige kundeenheten eller kundemålenheten.

Som en del av denne flyten velger du et spesifikt attributt som du vil basere segmentet på, for eksempel Kundetilfredshet eller Kjøpsbeløp. Når segmentet er opprettet, vil systemet foreslå en metode for å forutse manglende verdier for dette attributtet.

1. I Målgruppeinnsikt går du til **Segmenter** og velger **Profiler**-flisen.

2. Velg et **Felt** du vil opprette et segment på, velg en **Operator**, og velg deretter **Gå gjennom**.

3. Angi et **Navn** og et **Visningsnavn** for segmentet.

4. Velg **Lagre**.

5. Hvis segmentet du opprettet, har ufullstendige data i kildefeltet, kan du velge å forutsi de manglende verdiene.
   > [!div class="mx-imgBorder"]
   > ![Prediksjon-knapp.](media/segments-predictoption.png "Prognose-knapp")

6. Angi et **Visningsnavn** og et **Navn på utdataenhet** for resultatet av prognosen.

7. Velg **Ferdig**. Prognosen genereres snart i en ny enhet med navnet du angav for **Navn på utdataenhet**.

## <a name="view-a-prediction"></a>Vise en prognose

1. I Målgruppeinnsikt går du til **Intelligens** > **Prediksjoner** > **Mine prediksjoner**.

2. Velg prognosen du vil gå gjennom.

3. Velg en ellipse i kolonnen **Handlinger**, og velg **Visning**.

4. Det vises en rekke datapunkter i visningen i prognosen.
   > [!div class="mx-imgBorder"]
   > ![Prediksjoner-side.](media/intelligence-predictionsviewpage.png "Prognoser-side")

   - **Forespeilede verdier** viser tilordningen du opprettet under fasen for Felt-verdi til Kategoritilordning. Dette er verdiene i datasettet som er tilordnet en bestemt kategori.
   -**Beste påvirkere** er faktorene i datasettet som mest sannsynlig vil påvirke prognosens konfidens til feltverdien som tilordnes en spesifikk kategori.
   - **Ytelse** angir hvordan prognoser gjør det. Klikk koblingen for å finne ut mer.
   - **Forhåndsvisning** viser eksempler på utdatasettet fra prognosen og sannsynligheten, eller vår konfidens, for den anslåtte verdien, der 0 er usikker og 1 er sikker.

## <a name="update-a-prediction"></a>Oppdatere en prognose

1. I Målgruppeinnsikt går du til **Intelligens** > **Prediksjoner** > **Mine prediksjoner**.

2. Velg hvilken prognose du vil oppdatere, og velg ikonet **Oppdater**.

3. Prognosen blir planlagt for behandling. Du kan se tiden den sist ble oppdatert, i kolonnen **Oppdatert** på siden **Prognoser**.

## <a name="edit-a-prediction"></a>Redigere en prognose

Når du har opprettet en prognose, kan du tilpasse modellen i AI Builder for å øke effektiviteten i modellen.  

1. I Målgruppeinnsikt går du til **Intelligens** > **Prediksjoner** > **Mine prediksjoner**.

2. Merk prognosen du vil redigere.

3. Velg en ellipse i kolonnen **Handlinger**, og velg **Visning**.

4. Velg **Tilpass i AI Builder**.

5. Oppdater modellen i AI Builder. [Lær mer om behandling av modeller i AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Neste kjøring av prognosen vil bruke den oppdaterte modellen du har opprettet.

> [!NOTE]
> Nye modeller som opprettes i AI Builder, vises ikke i målgruppeinsights hvis ikke modellen ble opprettet fra opplevelsene som er oppført ovenfor.

## <a name="remove-a-prediction"></a>Fjerne en prognose

1. I Målgruppeinnsikt går du til **Intelligens** > **Prediksjoner** > **Mine prediksjoner**.

2. Velg prognosen du vil slette.

3. Velg en ellipse i kolonnen **Handlinger**, og velg **Slett**.

4. Bekreft slettingen.

## <a name="troubleshooting"></a>Feilsøking

Hvis du ikke kan fullføre tilleggsprosessen for Dataverse på grunn av en feil, kan du prøve å fullføre prosessen manuelt. Det finnes to kjente problemer som kan oppstå i tilleggsprosessen:

- Kundekort-tillegget er ikke installert.
    1. Fullfør instruksjonene for å [installere og konfigurere løsningen](customer-card-add-in.md).

- Apptillatelser blir ikke innvilget.
    1. Gå til [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Velg **Miljøer**.
    1. Velg ellipsen ved siden av miljøet du vil legge til tillatelsen i, og velg **Innstillinger**.
    1. Utvid **Brukere + tillatelser**, og velg **Brukere**.
    1. Velg **+ Ny**, og velg **Bruker**.
    1. Velg **Programbruker** hvis det ikke allerede er valgt, og angi følgende informasjon:
        - **Brukernavn:** cihelp@microsoft.com
        - **Program-ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Fornavn:** Kunde
        - **Etternavn:** Innsikt
        - **Primær e-post:** cihelp@microsoft.com
    1. Velg **Lagre og lukk**.
    1. Velg brukeren du nettopp opprettet.
    1. Velg **Administrer roller** på den øverste menylinjen.
    1. Velg **Systemadministrator**, og velg deretter **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]