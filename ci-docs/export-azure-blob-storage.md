---
title: Eksporter data til en Azure Blob Storage (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Blob Storage.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195716"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Eksporter data til en Azure Blob Storage (forhåndsversjon)

Lagre Customer Insights-data i en Blob Storage, eller bruk den til å overføre dataene dine til andre programmer.

## <a name="prerequisites"></a>Forutsetning

- Et navn og en kontonøkkel for [Azure Blob Storage-konto](/azure/storage/blobs/create-data-lake-storage-account). Du finner navnet og nøkkelen ved å se [Administrer lagringskontoinnstillinger i Azure Portal](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage-beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Kjente begrensninger

- For Azure Blob Storage velger du mellom [Standardytelse og Premium-ytelse](/azure/storage/blobs/storage-blob-performance-tiers). Hvis du velger Premium-ytelse, velger du [premiumblokkblobene som kontotype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Konfigurer tilkobling til Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Azure Blob Storage**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **Kontonavn**, **Kontonøkkel** og **Beholder** for Blob Storage-kontoen.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

For å kunne konfigurere denne eksporten må du ha [tillatelse](export-destinations.md#set-up-a-new-export) til denne tilkoblingstypen.

> [!IMPORTANT]
> Hvis du har aktivert [innstillingen for myk sletting](/azure/storage/blobs/soft-delete-blob-enable) for Azure Blob Storage-kontoen, vil eksporten mislykkes. Deaktiver myk sletting for å eksportere data til blober.

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Azure Blob Storage-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Skriv inn mappenavnet for Blob Storage.

1. Merk av i boksen ved siden av hver av enhetene du vil eksportere til dette stedet.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Eksporterte data lagres i Blob Storage-beholderen du konfigurerte. Følgende mappebaner opprettes automatisk i beholderen:

- For kildeenheter og enheter generert av systemet:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Eksport av enheter som inneholder store mengder data, kan føre til flere CSV-filer i samme mappe for hver eksport. Oppdeling av eksporter skjer av ytelsesårsaker for å redusere tiden det tar før en eksport fullføres.

- Filen model.json for de eksporterte enhetene er på *%ExportDestinationName%*-nivået.  
  
  Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
