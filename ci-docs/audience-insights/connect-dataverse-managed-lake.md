---
title: Koble til tabeller i Microsoft Dataverse
description: Importer data fra et Microsoft Dataverse-administrert datasjø.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033092"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Koble til data i en Microsoft Dataverse-administrert datasjø

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Denne artikkelen inneholder informasjon om hvordan Dataverse-brukere raskt kan koble seg til analytiske enheter i en administrert Dataverse-sjø. Du må være administrator i Dataverse-organisasjonen for å fortsette og vise listen over enheter som er tilgjengelige i den administrerte datasjøen.

## <a name="important-considerations"></a>Viktige hensyn

Data som lagres i onlinetjenester, for eksempel Azure Data Lake Storage, kan lagres på et annet sted enn der data behandles eller lagres i Dynamics 365 Customer Insights.Ved å importere eller koble til data som er lagret i en onlinetjeneste, godtar du at dataene kan overføres til og lagres med Dynamics 365 Customer Insights. [Finn ut mer på Microsoft Klareringssenter.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Koble til en Dataverse-administrert sjø

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

2. Velg **Legg til datakilde**.

3. Velg **Koble til administrert Microsoft Dataverse-sjø**, og velg **Neste**.

4. Skriv inn et **navn** for datakilden, og klikk deretter **Neste**. Navneretningslinjer: 
   - Start med en bokstav.
   - Bruk bare bokstaver og tall. Spesialtegn og mellomrom er ikke tillatt.
   - Bruk mellom 3 og 64 tegn.

5. Angi **serveradressen** til for Dataverse-organisasjonen, og velg **Logg på**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Skjermbilde i datainntakstrinn der en bruker kan angi nettadressen for Dataverse-miljøet.":::

6. Velg tabellene du vil innta som enheter i målgruppeinnsikt, fra den tilgjengelige listen.    

   > [!NOTE]
   > Hvis noen tabeller allerede er valgt, kan det hende de brukes av andre Dynamics 365-programmer (for eksempel Dynamics 365 Sales Insights eller Customer Service Insights). Du kan ikke endre valget. Disse tabellene vil være tilgjengelige som enheter når datakilden er opprettet.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogboks som viser en liste over enheter i Dataverse-miljøet.":::

7. Lagre det merkede området for å begynne å synkronisere de valgte tabellene fra Dataverse. Du finner den nylig tillagte koblingen på **Datakilder**-siden. Den legges i kø for oppdatering og viser enhetsantallet som 0 til alle de valgte tabellene er synkronisert.

Bare én datakilde av et miljø som kan bruke samme administrerte Dataverse-sjø samtidig.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Redigere en datakilde for Dataverse-administrert sjø

Du redigerer bare enhetsvalget etter opprettelsen av datakilden. For eksempel hvis flere enheter ble lagt til i Dataverse, og du vil importere dem også.    
Hvis du vil koble til en annen Dataverse-datasjø, må du [opprette en ny datakilde](#connect-to-a-dataverse-managed-lake).

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

2. Klikk ellipsen ved siden av datakilden du vil oppdatere.

3. Velg **Rediger**-alternativet fra listen.

4. Velg flere enheter fra den tilgjengelige listen med enheter, og velg **Lagre**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]