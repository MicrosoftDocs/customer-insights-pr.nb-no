---
title: Ta inn data via en Power Query-kobling
description: Koblinger til datakilder basert på Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267783"
---
# <a name="connect-to-a-power-query-data-source"></a>Koble til et Power Query-datakilde

Power Query tilbyr et bredt sett med koblinger for å hente data. De fleste av disse koblingene støttes av Dynamics 365 Customer Insights. Når du legger til datakilder basert på Power Query-koblingene, følges generelt fremgangsmåtene som er beskrevet i neste del. Avhengig av hvilken kontakt du bruker, er det imidlertid nødvendig med forskjellig informasjon. Hvis du vil ha mer informasjon, kan du se dokumentasjonen for enkeltkoblinger i [Power Query-koblingsreferanse](https://docs.microsoft.com/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Opprette en ny datakilde

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

1. Velg **Legg til datakilde**.

1. Velg **Importer data**-metoden, og velg deretter **Neste**.

1. Angi et **Navn** for datakilden, og velg deretter **Neste** for å opprette datakilden. Navneretningslinjer: 
   - Start med en bokstav.
   - Bruk bare bokstaver og tall. Spesialtegn og mellomrom er ikke tillatt.
   - Bruk mellom 3 og 64 tegn.

1. Velg én av de [tilgjengelige koblingene](#available-power-query-data-sources). I dette eksemplet velger vi **Tekst/CSV**-koblingen.

1. Angi de nødvendige detaljene i **Tilkoblingsinnstillinger** for den valgte koblingen, og velg **Neste** for å vise en forhåndsvisning av dataene.

1. Velg **Transformere data**. I dette trinnet skal du legge til enheter i datakilden. Enheter er datasett. Hvis du har en database som inneholder flere datasett, er hvert datasett sin egen enhet.

1. Dialogboksen **Power Query – Rediger spørringer** lar deg se gjennom og finjustere dataene. Enhetene som systemene identifiserte i den valgte datakilden, vises i venstre rute.

   > [!div class="mx-imgBorder"]
   > ![Dialogboksen Rediger spørringer](media/data-manager-configure-edit-queries.png "Dialogboksen Rediger spørringer")

1. Du kan også endre dataene dine. Velg en enhet som skal redigeres eller transformeres. Bruk alternativene i Power Query-vinduet til å bruke transformasjoner. Hver transformasjon blir ført opp under **Brukte trinn**. Power Query inneholder en rekke forhåndsbygde transformeringsalternativer. For mer informasjon, kan du se [Power Query-transformeringer](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).

1. Du kan legge til flere enheter i datakilden ved å velge **Hent data** i dialogboksen **Rediger spørringer**.

   Disse transformasjonene anbefales på det sterkeste:

   - Hvis du heter data fra en CSV-fil, inneholder den første raden ofte overskrifter. Gå til **Transformer tabell**, og velg **Bruk overskrifter som første rad**.
   - Kontroller at datatypen er angitt riktig.

1. Velg **Lagre** nederst i Power Query-vinduet for å lagre transformeringene. Etter at du har lagret, finner du datakilden på **Data** > **Datakilder**.

1. På **Data kilder**-siden vil du legge merke til at den nye datakilden har **Oppdatering**-status.

## <a name="available-power-query-data-sources"></a>Tilgjengelige Power Query-datakilder

Se [Power Query-referansekobling](https://docs.microsoft.com/power-query/connectors/) for å få en oppdatert liste over koblinger som du kan velge for å importere data til Customer Insights. 

Kontakter med en hake i kolonnen **Customer Insights (dataflyter)** er tilgjengelige for oppretting av nye datakilder basert på Power Query. Se gjennom dokumentasjonen for en bestemt kobling for å finne ut mer om forhåndskravene, begrensningene og andre detaljer.

## <a name="edit-power-query-data-sources"></a>Redigere Power Query-datakilder

> [!NOTE]
> Det kan hende at det ikke er mulig å gjøre endringer i datakilder som for øyeblikket brukes i en av appenes prosesser (*segmentering*, *samsvar* eller *sammenslåing*, for eksempel). 
>
> Ved å bruke siden **Innstillinger** kan du spore fremdriften for hver av de aktive prosessene. Når en prosess er fullført, kan du gå tilbake til siden **Datakilder** og utføre endringene.

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

2. Merk den loddrette ellipsen ved siden av datakilden du vil endre, og velg **Rediger** fra rullegardinmenyen.

   > [!div class="mx-imgBorder"]
   > ![Rediger-alternativet](media/edit-option-data-sources.png "Rediger-alternativet")

3. Ta i bruk endringene og transformasjonene i dialogboksen **Power Query – Rediger spørringer** slik det er beskrevet i delen [Opprett en ny datakilde](#create-a-new-data-source).

4. Velg **Lagre** i Power Query når du har fullført endringene, for å lagre endringene.


[!INCLUDE[footer-include](../includes/footer-banner.md)]