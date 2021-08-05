---
title: Koble Common Data Model-til en Azure Data Lake-konto
description: Arbeid med Common Data Model-data ved hjelp av Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 49bab0605197912cd4b81ff193b914599a092792
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554906"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Knytte til en Common Data Model-mappe ved å bruke en Azure Data Lake-konto

Denne artikkelen inneholder informasjon om hvordan du tar inn data fra en Common Data Model-mappe ved hjelp av en Azure Data Lake Storage Gen2-konto.

## <a name="important-considerations"></a>Viktige hensyn

- Data i Azure Data Lake må følge Common Data Model-standarden. Andre formater støttes ikke for øyeblikket.

- Datainntak støtter kun Azure Data Lake *Gen2*-lagringskontoer. Du kan ikke bruke Azure Data Lake Gen1-lagringskontoer til å ta inn data.

- Når du skal godkjenne med en Azure-tjenestekontohaver, må den være konfigurert i leieren. Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md).

- Azure Data Lake-forekomsten du vil koble til og ta inn data fra, må være i samme Azure-område som Dynamics 365 Customer Insights-miljøet. Tilkoblinger til en Common Data Model-mappe fra en Data Lake-forekomst i et annet Azure-område støttes ikke. Hvis du vil vite Azure-området i miljøet, går du til **Administrasjon** > **System** > **Om** i Målgruppeinnsikt.

- Data som er lagret i onlinetjenester, kan lagres på en annen plassering enn der data behandles eller lagres i Dynamics 365 Customer Insights.Ved å importere eller koble til data som er lagret i en onlinetjeneste, godtar du at dataene kan overføres til og lagres med Dynamics 365 Customer Insights. [Finn ut mer på Microsoft Klareringssenter.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Koble til en mappe i Common Data Model

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

1. Velg **Legg til datakilde**.

1. Velg **Koble til en mappe i Common Data Model**, angi et **navn** for datakilden, og velg **Neste**. Navneretningslinjer: 
   - Start med en bokstav.
   - Bruk bare bokstaver og tall. Spesialtegn og mellomrom er ikke tillatt.
   - Bruk mellom 3 og 64 tegn.

1. Du kan velge mellom å bruke et ressursbasert alternativ og et abonnementsbasert alternativ for godkjenning. Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md). Skriv inn informasjon om **beholderen**, og velg **Neste**.
   > [!div class="mx-imgBorder"]
   > ![Dialogboksen for å angi nye tilkoblingsdetaljer for Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Du må ha en av følgende roller i beholderen eller lagringskontoen nevnt ovenfor for å kunne koble til og opprette en datakilde:
   >  - Storage Blob-dataleser
   >  - Storage Blob-dataeier
   >  - Storage Blob-databidragsyter

1. I dialogboksen **Velg en mappe i Common Data Model** velger du model.json- eller manifest.json-filen du vil importere data fra, og velger deretter **Neste**.
   > [!NOTE]
   > En model.json- eller manifest.json-fil som er tilknyttet en annen datakilde i miljøet, vises ikke i listen.

1. Det vises en liste over tilgjengelige enheter i den valgte model.json- eller manifest.json-filen. Du kan se gjennom og velge fra listen over tilgjengelige enheter, og deretter velge **Lagre**. Alle de valgte enhetene tas inn fra den nye datakilden.
   > [!div class="mx-imgBorder"]
   > ![Dialogboks som viser en liste over enheter fra en model.json-fil.](media/review-entities.png)

8. Angi hvilke dataenheter du vil aktivere dataprofilering for, og velg **Lagre**. Dataprofilering aktiverer analyse og andre funksjoner. Du kan velge hele enheten, noe som velger alle attributter fra enheten, eller du kan velge bestemte valgte attributter. Som standard er ingen enheter aktivert for dataprofilering.
   > [!div class="mx-imgBorder"]
   > ![Dialogboks som viser dataprofilering.](media/dataprofiling-entities.png)

9. Når du har lagret valgene, åpnes siden **Datakilder**. Nå skal du se Common Data Model-mappen som en datakilde.

> [!NOTE]
> En model.json- eller manifest.json-fil kan bare tilknyttes én datakilde i samme miljø. Den samme model.json- eller manifest.json-filen kan imidlertid brukes for datakilder i flere miljøer.

## <a name="edit-a-common-data-model-folder-data-source"></a>Redigere en datakilde for Common Data Model-mappe

Du kan oppdatere tilgangsnøkkelen for lagringskontoen som inneholder Common Data Model-mappen. Du kan også endre model.json- eller manifest.json-filen. Hvis du vil koble til en annen beholder fra lagringskontoen, eller endre navnet på forretningsforbindelsen, må du [opprette en ny datakilde-tilkobling](#connect-to-a-common-data-model-folder).

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

2. Klikk ellipsen ved siden av datakilden du vil oppdatere.

3. Velg **Rediger**-alternativet fra listen.

4. Du kan eventuelt oppdatere **tilgangsnøkkelen** og velge **Neste**.

   ![Dialogboks for å redigere og oppdatere en tilgangstast for en eksisterende datakilde.](media/edit-access-key.png)

5. Du kan eventuelt oppdatere fra en kontonøkkeltilkobling til en ressursbasert eller abonnementsbasert tilkobling. Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md). Du kan ikke endre informasjon om en **beholder** når du oppdaterer tilkoblingen.
   > [!div class="mx-imgBorder"]

   > ![Dialogboksen for å angi tilkoblingsdetaljer for Azure Data Lake til en eksisterende lagringskonto.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Du må ha en av følgende roller i beholderen eller lagringskontoen nevnt ovenfor for å kunne koble til og opprette en datakilde:
   >  - Storage Blob-dataleser
   >  - Storage Blob-dataeier
   >  - Storage Blob-databidragsyter


6. Du kan eventuelt velge en annen model.json- eller manifest.json-fil med et annet sett enheter fra beholderen.

7. Alternativt kan du velge flere enheter å ta inn. Du kan også fjerne eventuelle enheter som allerede er valgt, hvis det ikke finnes avhengigheter.

   > [!IMPORTANT]
   > Hvis det finnes avhengigheter i den eksisterende model.json- eller manifest.json-filen og enhetene, vises en feilmelding og du kan ikke velge en annen model.json- eller manifest.json-fil. Fjern avhengighetene før du endrer model.json- eller manifest.json-filen, eller opprett en ny datakilde med model.json- eller manifest.json-filen som du vil bruke for å unngå å fjerne avhengighetene.

8. Du kan også velge flere attributter eller enheter du vil aktivere dataprofilering på eller deaktivere en som allerede er valgt.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]