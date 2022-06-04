---
title: Trinnvis oppdatering for Power Query-baserte datakilder
description: Oppdater nye og oppdaterte data for store datakilder basert på Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647186"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Trinnvis oppdatering for datakilder basert på Power Query

Denne artikkelen beskriver hvordan du konfigurerer trinnvis oppdatering for datakilder basert på Power Query.

Trinnvis oppdatering for datakilder gir følgende fordeler:

- **Raskere oppdateringer** – Bare data som er endret, blir oppdatert. Du kan for eksempel bare oppdatere de siste fem dagene i en historisk datasett.
- **Økt pålitelighet** – Med mindre oppdateringer trenger du ikke å opprettholde tilkoblinger til flyktige kildesystemer så lenge, noe som reduserer risikoen for tilkoblingsproblemer.
- **Reduksjon av ressursforbruk** – Oppdatering av bare et delsett av de totale dataene fører til mer effektiv bruk av dataressurser og reduserer miljøavtrykket.

## <a name="configure-incremental-refresh"></a>Konfigurere trinnvis oppdatering

Customer Insights tillater trinnvis oppdatering for datakilder som importeres via Power Query som støtter trinnvis inntak. For eksempel Azure SQL-databaser med dato- og klokkeslettfelt, som angir når dataoppføringer sist ble oppdatert.

1. [Opprett en ny datakilde basert på Power Query](connect-power-query.md).

1. Skriv inn et **navn** på datakilden.

1. Velg en datakilde som støtter trinnvis oppdatering, for eksempel [Azure SQL-database](/power-query/connectors/azuresqldatabase).

1. Velg enhetene eller tabellene som skal inkluderes.

1. Fullfør transformeringstrinnene, og velg **Neste**.

1. I dialogboksen **Konfigurer trinnvis oppdatering** velger du **Konfigurer** for å åpne **Innstillinger for trinnvis oppdatering**. Hvis du velger **Hopp over**, vil datakilden oppdatere hele datasettet.
   > [!TIP]
   > Du kan også bruke trinnvis oppdatering senere ved å redigere en eksisterende datakilde.

1. I **Innstillinger for trinnvis oppdatering** konfigurerer du den trinnvise oppdateringen for alle enhetene som du valgte ved oppretting av datakilden.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurer enheter i en datakilde for trinnvis oppdatering.":::

1. Velg en enhet, og angi følgende detaljer:

   - **Angi primærnøkkelen**: Velg en primærnøkkel for enheten eller tabellen.
   - **Definer feltet Sist oppdatert**: Dette feltet viser bare attributter av typen dato eller klokkeslett. Velg et attributt som angir når oppføringene sist ble oppdatert. Den brukes til å identifisere oppføringene som faller innenfor tidsrammen for trinnvis oppdatering.
   - **Se etter oppdateringer hver**: Angi lengden på tidsrammen for trinnvis oppdatering.

1. Velg **Lagre** for å fullføre opprettingen av datakilden. Den første dataoppdateringen vil være en fullstendig oppdatering. Deretter utføres den trinnvise dataoppdateringen slik det er konfigurert i forrige trinn.


[!INCLUDE [footer-include](includes/footer-banner.md)]