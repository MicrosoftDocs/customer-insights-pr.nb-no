---
title: Eksportere Customer Insights-data til Azure Data Lake Storage Gen2
description: Lær hvordan du konfigurerer tilkoblingen til Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477191"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Kontakt for Azure Data Lake Storage Gen2 (forhåndsversjon)

Lagre Customer Insights-data i Azure Data Lake Storage Gen2, eller bruk den til å overføre dataene dine til andre programmer.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Konfigurer koblingen for Azure Data Lake Storage Gen2

1. I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.

1. Under **Azure Data Lake Storage Gen2** velger du **Oppsett**.

1. Gi målet et gjenkjennelig navn i feltet **Visningsnavn**.

1. Angi **kontonavn**, **kontonøkkel** og **beholder** for Azure Data Lake Storage Gen2.
    - Hvis du vil vite hvordan du oppretter en lagringskonto som skal brukes med Azure Data Lake Storage Gen2, kan du se [Opprett lagringskonto](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Hvis du vil finne ut mer om hvordan du finner kontonavnet og kontonøkkelen for lagringskontoen for Azure Data Lake Gen2, kan du se [Administrer innstillinger for lagringskonto i Azure Portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Velg **Neste**.

1. Merk av i boksen ved siden av hver av enhetene du vil eksportere til dette stedet.

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md#export-data-on-demand). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).
