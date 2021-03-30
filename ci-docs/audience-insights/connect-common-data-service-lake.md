---
title: Koble til enheter i den administrerte Common Data Service-sjøen
description: Importer data fra et Common Data Service-administrert datasjø.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596971"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Koble til data i en Common Data Service-administrert datasjø

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Denne artikkelen inneholder informasjon om hvordan eksisterende Dynamics 365-kunder raskt kan koble seg til sine analytiske enheter i den Common Data Service-administrerte datasjøen. Du må være administrator i Common Data Service-organisasjonen for å fortsette og vise listen over enheter som er tilgjengelige i den administrerte datasjøen.

## <a name="important-considerations"></a>Viktige hensyn

Data som lagres i onlinetjenester, for eksempel Azure Data Lake Storage, kan lagres på et annet sted enn der data behandles eller lagres i Dynamics 365 Customer Insights.Ved å importere eller koble til data som er lagret i en onlinetjeneste, godtar du at dataene kan overføres til og lagres med Dynamics 365 Customer Insights. [Finn ut mer på Microsoft Klareringssenter.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Koble til en Common Data Service-administrert sjø

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

2. Velg **Legg til datakilde**.

3. Velg **Koble til Common Data Service**, og velg deretter **Neste**.

4. Skriv inn et **navn** for datakilden, og klikk deretter **Neste**. Navneretningslinjer: 
   - Start med en bokstav.
   - Bruk bare bokstaver og tall. Spesialtegn og mellomrom er ikke tillatt.
   - Bruk mellom 3 og 64 tegn.

5. Angi **serveradressen** for Common Data Service-organisasjonen, og velg **Logg på**.

   > [!div class="mx-imgBorder"]
   > ![Dialogboks for å skrive inn Common Data Service-serveradresse](media/enter-CDS-org-details.png)

6. Velg enhetene du vil ta inn, fra den tilgjengelige listen.    

   > [!NOTE]
   > Hvis noen enheter allerede er valgt, kan de brukes av andre Dynamics 365-programmer (for eksempel Dynamics 365 Sales Insights eller Customer Service Insights). Du kan ikke endre valget. Disse enhetene vil være tilgjengelige når datakilden er opprettet.

   > [!div class="mx-imgBorder"]
   > ![Dialogboks som viser en liste over enheter i Common Data Service-organisasjonen](media/select-analytical-entities.png)

7. Lagre valget for å starte synkronisering av de valgte enhetene til den Common Data Service-administrerte sjøen. Du finner den nylig tillagte koblingen på **Datakilder**-siden. Det blir lagt i kø for oppdatering, og antallet enheter vises som 0 til alle enhetene er synkronisert.

Bare én datakilde av et miljø som kan bruke samme administrerte Common Data Service-sjø samtidig.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Redigere en datakilde for Common Data Service-administrert sjø

Du redigerer bare enhetsvalget etter opprettelsen av datakilden. For eksempel hvis flere enheter ble lagt til i Common Data Service, og du vil importere dem også.    
Hvis du vil koble til en annen Common Data Service, [oppretter du en ny datakilde](#connect-to-a-common-data-service-managed-lake).

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

2. Klikk ellipsen ved siden av datakilden du vil oppdatere.

3. Velg **Rediger**-alternativet fra listen.

4. Velg flere enheter fra den tilgjengelige listen med enheter, og velg **Lagre**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]