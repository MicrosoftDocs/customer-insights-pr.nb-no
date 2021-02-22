---
title: Trinnvis oppdatering for Power Query-baserte datakilder
description: Oppdatere nye og oppdaterte data for store datakilder basert på Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406526"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Trinnvis oppdatering for datakilder som er baserte på Power Query

Trinnvis oppdatering for datakilder gir følgende fordeler:

- **Raskere oppdateringer** – Bare data som er endret, blir oppdatert. Du kan for eksempel bare oppdatere de siste fem dagene i en historisk datasett.
- **Økt pålitelighet** – Med mindre oppdateringer trenger du ikke å opprettholde tilkoblinger til flyktige kildesystemer så lenge, noe som reduserer risikoen for tilkoblingsproblemer.
- **Reduksjon av ressursforbruk** – Oppdatering av bare et delsett av de totale dataene fører til mer effektiv bruk av dataressurser og reduserer miljøavtrykket.

## <a name="configure-incremental-refresh"></a>Konfigurer trinnvis oppdatering

Målgruppeinnsikt tillater trinnvis oppdatering for datakilder importert via Power Query som støtter trinnvis inkludering. For eksempel Azure SQL-databaser med dato- og klokkeslettfelt, som angir når dataoppføringer sist ble oppdatert.

1. [Opprett en ny datakilde basert på Power Query ](connect-power-query.md).

1. Skriv inn et navn på datakilden.

1. Velg en datakilde som støtter trinnvis oppdatering, for eksempel Azure SQL-database.

1. Velg enhetene eller tabellene som skal inkluderes.

1. Fullfør transformeringstrinnene, og velg **Neste**.

1. I dialogboksen **Konfigurer trinnvis oppdatering** velger du **Konfigurer** for å åpne **Innstillinger for trinnvis oppdatering**. Hvis du velger **Hopp over**, vil datakilden oppdatere hele datasettet.
   > [!TIP]
   > Du kan også bruke trinnvis oppdatering senere ved å redigere en eksisterende datakilde.

1. I **Innstillinger for trinnvis oppdatering** konfigurerer du den trinnvise oppdateringen for alle enhetene som du valgte ved oppretting av datakilden.

   > [!div class="mx-imgBorder"]
   > ![Konfigurere enheter i en datakilde for trinnvis oppdatering](media/incremental-refresh-settings.png "Konfigurere enheter i en datakilde for trinnvis oppdatering")

1. Velg en enhet, og angi følgende detaljer:

   - **Angi primærnøkkelen**: Velg en primærnøkkel for enheten eller tabellen.
   - **Definer feltet Sist oppdatert**: Dette feltet viser bare attributter av typen dato eller klokkeslett. Velg et attributt som angir når oppføringene sist ble oppdatert. Den brukes til å identifisere oppføringene som faller innenfor tidsrammen for trinnvis oppdatering.
   - **Se etter oppdateringer hver**: Angi lengden på tidsrammen for trinnvis oppdatering.

1. Velg **Lagre** for å fullføre opprettingen av datakilden. Den første dataoppdateringen vil være en fullstendig oppdatering. Deretter utføres den trinnvise dataoppdateringen slik det er konfigurert i forrige trinn.