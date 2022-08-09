---
title: Eksporter Customer Insights-data til InMobi
description: Finn ut hvordan du konfigurerer og eksporterer til InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195900"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Eksporter Customer Insights-data til InMobi (forhåndsversjon)

Eksporter segmentlister eller andre data fra Customer Insights-forekomsten til [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Forutsetning

- En [InMobi-konto](https://www.inmobi.com/) og administratorlegitimasjon.
- Et navn og en kontonøkkel for [Azure Blob Storage-konto](/azure/storage/blobs/create-data-lake-storage-account). Du finner navnet og nøkkelen ved å se [Administrer lagringskontoinnstillinger i Azure Portal](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage-beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) å eksportere InMobi-data til.
- InMobi oppretter en direkte tilkobling til Blob Storage og konfigurerer en automatisk import av dataene til InMobi. Kontakt InMobi-representanten for å starte prosessen.

## <a name="known-limitations"></a>Kjente begrensninger

- For Azure Blob Storage velger du mellom [Standardytelse og Premium-ytelse](/azure/storage/blobs/storage-blob-performance-tiers). Hvis du velger Premium-ytelse, velger du [premiumblokkblobene som kontotype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Konfigurer tilkobling til Azure Blob Storage

[Konfigurer en tilkobling til Azure Blob Storage](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Konfigurere en eksport

[Konfigurere en eksport](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
