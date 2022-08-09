---
title: Eksporter data til Azure Data Lake Storage Gen2 (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen til Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196452"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Eksporter data til Azure Data Lake Storage Gen2 (forhåndsversjon)

Lagre Customer Insights-data i en Data Lake Storage Gen2-konto, eller bruk den til å overføre dataene dine til andre programmer.

## <a name="prerequisites"></a>Forutsetning

- En [lagringskonto som skal brukes med Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Du finner navnet og nøkkelen for lagringskontoen ved å se [Administrer lagringskontoinnstillinger i Azure Portal](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage-beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Kjente begrensninger

- For Azure Data Lake Storage Gen2 velger du mellom [Standardytelse og Premium-ytelse](/azure/storage/blobs/create-data-lake-storage-account). Hvis du velger Premium-ytelse, velger du [premiumblokkblobene som kontotype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Konfigurer tilkoblingen til Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Azure Data Lake Gen 2**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **kontonavn**, **kontonøkkel** og **beholder** for Azure Data Lake Storage Gen2.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Azure Data Lake-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Skriv inn mappenavnet for Azure Data Lake Storage Gen2-lagringen.

1. Merk av i boksen ved siden av hver av enhetene du vil eksportere til dette stedet.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Eksporterte data lagres i lagringsbeholderen du konfigurerte for Azure Data Lake Gen 2.

> [!TIP]
> Eksport av enheter som inneholder store mengder data, kan føre til flere CSV-filer i samme mappe for hver eksport. Oppdeling av eksporter skjer av ytelsesårsaker for å redusere tiden det tar før en eksport fullføres.

[!INCLUDE [footer-include](includes/footer-banner.md)]
