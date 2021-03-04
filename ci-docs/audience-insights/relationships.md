---
title: Relasjoner mellom enheter og enhetsbaner
description: Opprett og administrer relasjoner mellom enheter fra flere datakilder.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269893"
---
# <a name="relationships-between-entities"></a>Relasjoner mellom enheter

Relasjoner hjelper deg med å koble sammen enheter og generere et diagram over dataene når enhetene deler en felles identifikator (sekundærnøkkel) som kan refereres fra én enhet til en annen. Ved å bruke tilkoblede enheter kan du definere segmenter og mål basert på flere datakilder.

Det finnes to typer relasjoner: Systemrelasjoner som ikke kan redigeres, som opprettes automatisk, og egendefinerte relasjoner som opprettes og konfigureres av brukere.

I løpet av samsvars- og sammenslåingsprosessene opprettes systemrelasjoner i bakgrunnen basert på intelligent samsvar. Disse relasjonene hjelper deg med å relatere kundeprofiloppføringene med andre korresponderende enheters oppføringer. Følgende diagram illustrerer opprettelsen av tre systemrelasjoner når kundeenheten samsvarer med tilleggsenheter for å produsere den endelige kundeprofilenheten.

> [!div class="mx-imgBorder"]
> ![Relasjonsopprettelse](media/relationships-entities-merge.png "Relasjonsopprettelse")

- ***CustomerToContact*-relasjon** ble opprettet mellom kundeenheten og kontaktenheten. Kundeenheten får nøkkelfeltet **Contact_contactId** til å relatere til nøkkelfeltet til kontaktenheten **contactId**.
- ***CustomerToAccount*-relasjon** ble opprettet mellom kundeenheten og kontoenheten. Kundeenheten får nøkkelfeltet **Account_accountId** til å relatere til nøkkelfeltet til kontoenheten **accountId**.
- ***CustomerToWebAccount*-relasjon** ble opprettet mellom kundeenheten og webkontoenheten. Kundeenheten får nøkkelfeltet **WebAccount_webaccountId** til å relatere til nøkkelfeltet til webkontoenheten **webaccountId**.

## <a name="create-a-relationship"></a>Opprette en relasjon

Definer egendefinerte relasjoner på siden **Relasjoner**. Hver relasjon består av en kildeenhet (enheten som inneholder sekundærnøkkelen) og en målenhet (enheten som kildeenhetens sekundærnøkkel peker til).

1. I Målgruppeinnsikt går du til **Data** > **Relasjoner**.

2. Velg **Ny relasjon**.

3. Angi følgende informasjon i ruten **Legg til relasjon**:

   > [!div class="mx-imgBorder"]
   > ![Angi relasjonsdetaljer](media/relationships-add.png "Angi relasjonsdetaljer")

   - **Relasjonsnavn**: Navn som gjenspeiler formålet med relasjonen (for eksempel **AccountWebLogs**).
   - **Beskrivelse**: Beskrivelse av relasjonen.
   - **Kildeenhet**: Velg enheten som brukes som en kilde i relasjonen (for eksempel WebLog).
   - **Kardinalitet**: Velg kardinaliteten for kildeenhetsoppføringene. "Mange" betyr for eksempel at flere Weblog-oppføringer er relatert til én WebAccount.
   - **Kildenøkkelfelt**: Dette representerer sekundærnøkkelfeltet i kildeenheten. For eksempel har WebLog sekundærnøkkelfeltet **accountId** .
   - **Målenhet**: Velg enheten som brukes som et mål i relasjonen (for eksempel WebAccount).
   - **Målkardinalitet**: Velg kardinaliteten for målenhetsoppføringene. "Én" betyr for eksempel at flere Weblog-oppføringer er relatert til én WebAccount.
   - **Målprogramfelt**: Dette feltet representerer nøkkelfeltet for målenhet. For eksempel har WebAccount nøkkelfeltet **accountId** .

> [!NOTE]
> Bare mange-til-én- og én-til-én-relasjoner støttes. Mange-til-mange-relasjoner kan opprettes ved hjelp av to mange-til-én-relasjoner og en koblingsenhet (en enhet som brukes til å koble kildeenheten og målenheten).

## <a name="delete-a-relationship"></a>Slette en relasjon

1. I Målgruppeinnsikt går du til **Data** > **Relasjoner**.

2. Merk av for relasjonene du vil slette.

3. Velg **Slett** øverst i **Relasjoner** tabellen.

4. Bekreft slettingen.

## <a name="next-step"></a>Neste trinn

System- og egendefinerte relasjoner brukes til å opprette segmenter basert på flere datakilder som ikke lenger er i siloer. Du finner mer informasjon på [Segmenter](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]