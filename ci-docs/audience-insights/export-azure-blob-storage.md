---
title: Eksportere Customer Insights-data til Azure Blob storage
description: Lær hvordan du konfigurerer tilkoblingen til Azure Blob Storage.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269204"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Kobling for Azure Blob Storage (forhåndsvisning)

Lagre Customer Insights-data i Azure Blob Storage, eller bruk dette til å overføre dataene dine til andre programmer.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigurere koblingen for Azure Blob Storage

1. I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.

1. Velg **Konfigurer** under **Azure Blob Storage**.

1. Angi **Kontonavn**, **Kontonøkkel** og **Beholder** for Azure Blob Storage-kontoen.
    - Hvis du vil vite mer om hvordan du finner navnet og nøkkelen til Azure Blob Storage-kontoen, kan du se [Administrere lagringskontoinnstillinger i Azure-portalen](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Hvis du vil lære hvordan du oppretter en beholder, kan du se [Opprette en beholder](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Gi målet et gjenkjennelig navn i feltet **Visningsnavn**.

1. Velg **Neste**.

1. Merk av i boksen ved siden av hver av enhetene du vil eksportere til dette stedet.

1. Velg **Lagre**.

Eksporterte data lagres i Azure Blob Storage-beholderen du har konfigurert. Følgende mappebaner opprettes automatisk i beholderen:

- For kildeenheter og enheter generert av systemet: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json for de eksporterte enhetene vil ligge på %ExportDestinationName%-nivået.
  - Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md#export-data-on-demand). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]