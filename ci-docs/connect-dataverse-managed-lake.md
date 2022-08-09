---
title: Koble til data i en Microsoft Dataverse-administrert datasjø
description: Importer data fra et Microsoft Dataverse-administrert datasjø.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206965"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Koble til data i en Microsoft Dataverse-administrert datasjø

Microsoft Dataverse-brukere kan raskt koble til analytiske enheter i en Microsoft Dataverse-administrert sjø. Bare én datakilde av et miljø som kan bruke samme administrerte Dataverse-sjø samtidig.

> [!NOTE]
> Du må være administrator i Dataverse organisasjonen for å fortsette og vise listen over enheter som er tilgjengelig i den administrerte sjøen.

## <a name="prerequisites"></a>Forutsetning

- Data som lagres i onlinetjenester, for eksempel Azure Data Lake Storage, kan lagres på et annet sted enn der data behandles eller lagres i Dynamics 365 Customer Insights. Ved å importere eller koble til data som er lagret i en onlinetjeneste, godtar du at dataene kan overføres til og lagres med Dynamics 365 Customer Insights. [Finn ut mer om Microsofts klareringssenter](https://www.microsoft.com/trust-center).

- Bare Dataverse-enheter med [endringssporing](/power-platform/admin/enable-change-tracking-control-data-synchronization) aktivert, er synlige. Disse enhetene kan eksporteres til Dataverse-administrerte data lake og brukes i Customer Insights. Standard Dataverse-tabeller har endringssporing aktivert som standard. Du må aktivere endringssporing for egendefinerte tabeller. For å kontrollere om en Dataverse-tabell er aktivert for endringssporing, går du til [Power Apps](https://make.powerapps.com) > **Data** > **Tabeller**. Finn tabellen du er interessert i, og velg den. Gå til **Innstillinger** > **Avanserte alternativer**, og se gjennom innstillingen **Spor endringer**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Koble til en Dataverse-administrert sjø

1. Gå til **Data** > **Datakilder**.

1. Velg **Legg til datakilde**.

1. Velg **Microsoft Dataverse**.

1. Angi et **Navn** for datakilden og en valgfri **beskrivelse**.

1. Angi **serveradressen** til for Dataverse-organisasjonen, og velg **Logg på**.

1. Velg tabellene du vil legge inn som enheter, i Customer Insights fra den tilgjengelige listen.

   > [!NOTE]
   > Hvis noen tabeller allerede er valgt, kan det hende de brukes av andre Dynamics 365-programmer (for eksempel Dynamics 365 Sales Insights eller Customer Service Insights). Du kan ikke endre valget. Disse tabellene vil være tilgjengelige som enheter når datakilden er opprettet.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogboks som viser en liste over enheter i Dataverse-miljøet.":::

1. Lagre det merkede området for å begynne å synkronisere de valgte tabellene fra Dataverse. Du finner den nylig tillagte koblingen på **Datakilder**-siden. Den legges i kø for oppdatering og viser enhetsantallet som 0 til alle de valgte tabellene er synkronisert.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan ta tid å laste inn data. Etter en vellykket oppdatering kan de innhentede dataene gjennomgås fra [**Enheter**](entities.md)-siden.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Redigere en datakilde for Dataverse-administrert sjø

Du redigerer bare enhetsvalget etter opprettelsen av datakilden. For eksempel hvis flere enheter ble lagt til i Dataverse, og du vil importere dem også.
Hvis du vil koble til en annen Dataverse-datasjø, må du [opprette en ny datakilde](#connect-to-a-dataverse-managed-lake).

1. Gå til **Data** > **Datakilder**.

1. Ved siden av datakilde du vil oppdatere, velger du **Rediger**.

1. Velg flere enheter fra den tilgjengelige listen med enheter.

1. Klikk på **Lagre** for å ta i bruk endringene, og gå tilbake til siden **Datakilder**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
