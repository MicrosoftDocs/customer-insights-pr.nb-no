---
title: Hente data via en Power Query-tilkobling (inneholder video)
description: Koblinger til datakilder basert på Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: aae49be4364676ecc7a307e60eeca13859f1662a
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934990"
---
# <a name="connect-to-a-power-query-data-source"></a>Koble til et Power Query-datakilde

Power Query tilbyr et bredt sett med koblinger for å hente data. De fleste av disse koblingene støttes av Dynamics 365 Customer Insights. 

Når du legger til datakilder basert på Power Query-koblinger, følger du trinnene som beskrives i denne delen. Avhengig av hvilken kontakt du bruker, er det imidlertid nødvendig med forskjellig informasjon. Hvis du vil vite mer, kan du se dokumentasjonen for individuelle koblinger i [Power Query-koblingsreferansen](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Opprette en ny datakilde

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

1. Velg **Legg til datakilde**.

1. Velg **Microsoft Power Query**, og velg deretter **Neste**.

1. Angi et **Navn** for datakilden, og velg deretter **Neste** for å opprette datakilden.

1. Velg én av de [tilgjengelige koblingene](#available-power-query-data-sources). I dette eksemplet velger vi **Tekst-/CSV**-koblingen.

1. Angi de nødvendige detaljene i **Tilkoblingsinnstillinger** for den valgte koblingen, og velg **Neste** for å vise en forhåndsvisning av dataene.

1. Velg **Transformere data**. I dette trinnet skal du legge til enheter i datakilden. Enheter er datasett. Hvis du har en database som inneholder flere datasett, er hvert datasett sin egen enhet.

1. Dialogboksen **Power Query – Rediger spørringer** lar deg se gjennom og finjustere dataene. Enhetene som systemene identifiserte i den valgte datakilden, vises i venstre rute.

   > [!div class="mx-imgBorder"]
   > ![Dialogboksen Rediger spørringer.](media/data-manager-configure-edit-queries.png "Dialogboksen Rediger spørringer")

1. Du kan også endre dataene dine. Velg en enhet som skal redigeres eller transformeres. Bruk alternativene i Power Query-vinduet til å bruke transformasjoner. Hver transformasjon blir ført opp under **Brukte trinn**. Power Query inneholder en rekke forhåndsbygde transformeringsalternativer. For mer informasjon, kan du se [Power Query-transformeringer](/power-query/power-query-what-is-power-query#transformations).

1. Du kan legge til flere enheter i datakilden ved å velge **Hent data** i dialogboksen **Rediger spørringer**.

   Vi anbefaler at du bruker følgende transformasjoner:

   - Hvis du heter data fra en CSV-fil, inneholder den første raden ofte overskrifter. Gå til **Transformer tabell**, og velg **Bruk overskrifter som første rad**.
   - Kontroller at datatypen er angitt riktig.

1. Velg **Lagre** nederst i Power Query-vinduet for å lagre transformeringene. Etter at du har lagret, finner du datakilden på **Data** > **Datakilder**.

1. På **Data kilder**-siden vil du legge merke til at den nye datakilden har **Oppdatering**-status.

## <a name="available-power-query-data-sources"></a>Tilgjengelige Power Query-datakilder

Se [Power Query-koblingsreferansen](/power-query/connectors/) for en liste over koblinger som du kan bruke til å importere data til Customer Insights. 

Kontakter med en hake i kolonnen **Customer Insights (dataflyter)** er tilgjengelige for oppretting av nye datakilder basert på Power Query. Se gjennom dokumentasjonen for en bestemt kobling for å finne ut mer om forhåndskravene, begrensningene og andre detaljer.

## <a name="edit-power-query-data-sources"></a>Redigere Power Query-datakilder

> [!NOTE]
> Det kan hende at det ikke er mulig å gjøre endringer i datakilder som for øyeblikket brukes i en av appenes prosesser (*segmentering*, *samsvar* eller *sammenslåing*, for eksempel). 
>
> Ved å bruke siden **Innstillinger** kan du spore fremdriften for hver av de aktive prosessene. Når en prosess er fullført, kan du gå tilbake til siden **Datakilder** og utføre endringene.

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

2. Velg den loddrette ellipsen ved siden av datakildene du vil endre, og velg **Rediger** fra rullegardinmenyen.

   > [!div class="mx-imgBorder"]
   > ![Rediger-alternativet.](media/edit-option-data-sources.png "Rediger-alternativet")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Ta i bruk endringene og transformasjonene i dialogboksen **Power Query – Rediger spørringer** slik det er beskrevet i delen [Opprett en ny datakilde](#create-a-new-data-source).

4. Velg **Lagre** i Power Query når du har fullført endringene, for å lagre endringene.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
