---
title: Koble til data i en Microsoft Dataverse-administrert datasjø
description: Importer data fra et Microsoft Dataverse-administrert datasjø.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 9ae0b964d8d39835715b7ddadc712e2338b855af
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081264"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Koble til data i en Microsoft Dataverse-administrert datasjø

Microsoft Dataverse-brukere kan raskt koble til analytiske enheter i en Microsoft Dataverse-administrert sjø.

> [!NOTE]
> Du må være administrator i Dataverse organisasjonen for å fortsette og vise listen over enheter som er tilgjengelig i den administrerte sjøen.

## <a name="important-considerations"></a>Viktige hensyn

1. Data som lagres i onlinetjenester, for eksempel Azure Data Lake Storage, kan lagres på et annet sted enn der data behandles eller lagres i Dynamics 365 Customer Insights. Ved å importere eller koble til data som er lagret i en onlinetjeneste, godtar du at dataene kan overføres til og lagres med Dynamics 365 Customer Insights. [Finn ut mer om Microsofts klareringssenter](https://www.microsoft.com/trust-center).
2. Bare Dataverse-enheter med [endringssporing](/power-platform/admin/enable-change-tracking-control-data-synchronization) aktivert, er synlige. Disse enhetene kan eksporteres til Dataverse-administrerte data lake og brukes i Customer Insights. Standard Dataverse-tabeller har endringssporing aktivert som standard. Du må aktivere endringssporing for egendefinerte tabeller. For å kontrollere om en Dataverse-tabell er aktivert for endringssporing, går du til [Power Apps](https://make.powerapps.com) > **Data** > **Tabeller**. Finn tabellen du er interessert i, og velg den. Gå til **Innstillinger** > **Avanserte alternativer**, og se gjennom innstillingen **Spor endringer**.

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

Bare én datakilde av et miljø som kan bruke samme administrerte Dataverse-sjø samtidig.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Redigere en datakilde for Dataverse-administrert sjø

Du redigerer bare enhetsvalget etter opprettelsen av datakilden. For eksempel hvis flere enheter ble lagt til i Dataverse, og du vil importere dem også.
Hvis du vil koble til en annen Dataverse-datasjø, må du [opprette en ny datakilde](#connect-to-a-dataverse-managed-lake).

1. Gå til **Data** > **Datakilder**.

1. Ved siden av datakilde du vil oppdatere, velger du **Rediger**.

1. Velg flere enheter fra den tilgjengelige listen med enheter, og velg **Lagre**.
