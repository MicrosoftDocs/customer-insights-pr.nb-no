---
title: Eksportere Customer Insights-data til Azure Blob Storage
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Blob Storage.
ms.date: 06/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b159f87276581f68e07bb73ffd257080eb3cb56422997b09a613bd7afa4e3980
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034740"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Eksporter segmentliste og andre data til Azure Blob Storage (forhåndsvisning)

Lagre Customer Insights-data i en Blob Storage, eller bruk den til å overføre dataene dine til andre programmer.

## <a name="set-up-the-connection-to-blob-storage"></a>Konfigurer tilkoblingen til Blob Storage

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Azure Blob Storage** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **Kontonavn**, **Kontonøkkel** og **Beholder** for Blob Storage-kontoen.
    - Hvis du vil finne ut mer om hvordan du finner navn på forretningsforbindelse og kontonøkkel for Blob Storage, kan du se [Behandle innstillinger for lagringskonto i Azure Portal](/azure/storage/common/storage-account-manage).
    - Hvis du vil lære hvordan du oppretter en beholder, kan du se [Opprette en beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Velg **Lagre** for å fullføre tilkoblingen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Hvis du har aktivert innstillingen for myk sletting for Azure Blob Storage-kontoen, vil eksporten mislykkes. Deaktiver myk sletting for å eksportere data til blober. Hvis du vil ha mer informasjon, kan du se [Aktiver myk sletting av blober](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Azure Blob Storage-delen i feltet **Tilkobling for eksport**. Hvis navnet på denne delen ikke vises, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Merk av i boksen ved siden av hver av enhetene du vil eksportere til dette stedet.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).     

Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

Eksporterte data lagres i Blob Storage-beholderen du konfigurerte. Følgende mappebaner opprettes automatisk i beholderen:

- For kildeenheter og enheter generert av systemet:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Model.json for de eksporterte enhetene er på %ExportDestinationName%-nivå.  
  - Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
