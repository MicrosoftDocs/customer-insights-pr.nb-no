---
title: Eksporter data til Azure Data Lake Storage Gen2 (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen til Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: c2446fba425203d2910b82134b73543a73c7ecf8
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081484"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Eksporter data til Azure Data Lake Storage Gen2 (forhåndsversjon)

Lagre Customer Insights-data i en Data Lake Storage Gen2-konto, eller bruk den til å overføre dataene dine til andre programmer.

## <a name="known-limitations"></a>Kjente begrensninger

1. For Azure Data Lake Storage Gen2 kan du velge mellom [Standard-ytelse og Premium-ytelsesnivå](/azure/storage/blobs/create-data-lake-storage-account) når du oppretter en lagringskonto for Data Lake. Hvis du velger Premium-ytelse, velger du premiumblokkblobene som kontotype.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Konfigurere tilkoblingen til Azure Data Lake Storage Gen2

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Azure Data Lake Gen 2** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **kontonavn**, **kontonøkkel** og **beholder** for Azure Data Lake Storage Gen2.
    - Hvis du vil vite hvordan du oppretter en lagringskonto som skal brukes med Azure Data Lake Storage Gen2, kan du se [Opprett lagringskonto](/azure/storage/blobs/create-data-lake-storage-account). 
    - Hvis du vil finne ut mer om navn på forretningsforbindelse og kontonøkkel for Azure Data Lake Gen2, kan du se [Behandle innstillinger for lagringskonto i Azure Portal](/azure/storage/common/storage-account-manage).

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport** for å opprette en ny eksport.

1. Velg en tilkobling fra **Azure Data Lake**-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Merk av i boksen ved siden av hver av enhetene du vil eksportere til dette stedet.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).
Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).

Eksporterte data lagres i lagringsbeholderen du konfigurerte for Azure Data Lake Gen 2.

> [!TIP]
> Eksport av enheter som inneholder store mengder data, kan føre til flere CSV-filer i samme mappe for hver eksport. Oppdeling av eksporter skjer av ytelsesårsaker for å redusere tiden det tar før en eksport fullføres.

[!INCLUDE [footer-include](includes/footer-banner.md)]
