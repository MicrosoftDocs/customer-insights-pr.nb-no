---
title: Trinnvis oppdatering for Power Query og Azure Data Lake-datakilder
description: Oppdater nye og oppdaterte data for store datakilder basert på Power Query- Azure-datasjøkilder.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207149"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Trinnvis oppdatering for Power Query og Azure Data Lake-datakilder

Trinnvis oppdatering for datakilder basert på Power Query eller Azure Data Lake gir følgende fordeler:

- **Raskere oppdateringer** – Bare data som er endret, blir oppdatert. Du kan for eksempel bare oppdatere de siste fem dagene i en historisk datasett.
- **Økt pålitelighet** – Med mindre oppdateringer trenger du ikke å opprettholde tilkoblinger til flyktige kildesystemer så lenge, noe som reduserer risikoen for tilkoblingsproblemer.
- **Reduksjon av ressursforbruk** – Oppdatering av bare et delsett av de totale dataene fører til mer effektiv bruk av dataressurser og reduserer miljøavtrykket.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Konfigurer trinnvis oppdatering for datakilder basert på Power Query

Customer Insights tillater trinnvis oppdatering for datakilder som importeres via Power Query som støtter trinnvis inntak. For eksempel Azure SQL-databaser med dato- og klokkeslettfelt, som angir når dataoppføringer sist ble oppdatert.

1. [Opprett en ny datakilde basert på Power Query](connect-power-query.md).

1. Velg en datakilde som støtter trinnvis oppdatering, for eksempel [Azure SQL-database](/power-query/connectors/azuresqldatabase).

1. Velg enhetene eller tabellene som skal inkluderes.

1. Fullfør transformeringstrinnene, og velg **Neste**.

1. I dialogboksen **Konfigurer trinnvis oppdatering** velger du **Konfigurer** for å åpne **Innstillinger for trinnvis oppdatering**. Hvis du velger **Hopp over**, vil datakilden oppdatere hele datasettet.
   > [!TIP]
   > Du kan også bruke trinnvis oppdatering senere ved å redigere en eksisterende datakilde.

1. I **Innstillinger for trinnvis oppdatering** konfigurerer du den trinnvise oppdateringen for alle enhetene som du valgte ved oppretting av datakilden.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurer innstillinger for trinnvis oppdatering.":::

1. Velg en enhet, og angi følgende detaljer:

   - **Angi primærnøkkelen**: Velg en primærnøkkel for enheten eller tabellen.
   - **Definer feltet Sist oppdatert**: Dette feltet viser bare attributter av typen dato eller klokkeslett. Velg et attributt som angir når oppføringene sist ble oppdatert. Den brukes til å identifisere oppføringene som faller innenfor tidsrammen for trinnvis oppdatering.
   - **Se etter oppdateringer hver**: Angi lengden på tidsrammen for trinnvis oppdatering.

1. Velg **Lagre** for å fullføre opprettingen av datakilden. Den første dataoppdateringen vil være en fullstendig oppdatering. Deretter utføres den trinnvise dataoppdateringen slik det er konfigurert i forrige trinn.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Konfigurer trinnvis oppdatering for Azure Data Lake-datakilder

Customer Insights tillater trinnvis oppdatering for datakilder som er koblet til Azure Data Lake Storage. Hvis du vil bruke trinnvis inntak og oppdatering for en enhet, konfigurerer du enheten når du legger til Azure Data Lake-datakilde eller senere når du redigerer datakilde. Mappen for enhetsdata må inneholde følgende mapper:

- **FullData**: Mappen med datafiler som inneholder innledende oppføringer
- **IncrementalData**: Mappe med dato-/klokkesletthierarkimapper i **åååå/mm/dd/tt**-format som inneholder de trinnvise oppdateringene. **hh** representerer UTC-tiden for oppdateringene og inneholder mappene **Upserts** og **Deletes**. **Upserts** inneholder datafiler med oppdateringer til eksisterende oppføringer eller nye oppføringer. **Deletes** inneholder datafiler med oppføringer som skal fjernes.

1. Når du legger til eller redigerer en datakilde, navigerer du til **Attributter**-ruten for enheten.

1. Gå gjennom attributtene. Kontroller at et opprettet eller sist oppdatert datoattributt er *konfigurert med et dateTime*-**dataformat** og en *Calendar.Date*-**semantisk type**. Rediger attributtet om nødvendig, og velg **Fullført**.

1. Rediger enheten fra **Velg enheter**-ruten. Avmerkingsboksen **Trinnvis inntak** er merket.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Konfigurer enheter i en datakilde for trinnvis oppdatering.":::

   1. Bla til rotmappen som inneholder .csv- eller .parquet-filene, for å få fullstendige data, trinnvise data-upserts og slettinger av trinnvise data.
   1. Angi utvidelsen for alle dataene og både trinnvise filer (\.csv eller \.parquet).
   1. For CSV-filer velger du kolonneskilletegnet og om du vil bruke første rad i filen som kolonneoverskrift.
   1. Velg **Lagre**.

1. Velg datotidsstempelattributtet for **Sist oppdatert**.

1. Hvis **primærnøkkelen** ikke er valgt, velger du primærnøkkelen. Primærnøkkelen er et attributt som er unikt for enheten. For at et attributt skal være en gyldig primærnøkkel, bør den ikke inneholde duplikate verdier, manglende verdier eller nullverdier. Datatypeattributtene streng, heltall og GUID støttes som primærnøkler.

1. Velg **Lukk** for å lagre lukke ruten.

1. Fortsett med å legge til eller redigere datakilden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
