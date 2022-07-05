---
title: Eksporter Customer Insights-data til InMobi
description: Finn ut hvordan du konfigurerer og eksporterer til InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056547"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Eksporter segmentliste og andre data til InMobi (forhåndsversjon)

Eksporter segmentlister eller andre data fra Customer Insights-forekomsten til [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Forutsetning

1. Du har en [InMobi-konto](https://www.inmobi.com/) og administratorlegitimasjon.
1. Du har en Azure Blob Storage-konto og den tilsvarende kontonøkkelen. Hvis du vil ha mer informasjon, kan du se [Administrer lagringskontoinnstillinger i Azure Portal](/azure/storage/common/storage-account-manage). Det er en beholder i lagringskontoen du kan eksportere inMobi-data til. Hvis du vil ha mer informasjon, kan du se [Opprett en beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi oppretter en direkte tilkobling til Blob Storage og konfigurerer en automatisk import av dataene til InMobi. Kontakt InMobi-representanten for å starte prosessen.

## <a name="known-limitations"></a>Kjente begrensninger

1. For Azure Blob Storage kan du velge mellom [Standardytelse og Premium-ytelse](/azure/storage/blobs/storage-blob-performance-tiers). Hvis du velger Premium-ytelse, velger du [premiumblokkblobene som kontotype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Konfigurer tilkoblingen til Azure Blob Storage og konfigurer en eksport

1. Følg instruksjonene for å [konfigurere en tilkobling til Azure Blob Storage](export-azure-blob-storage.md).
2. Følg instruksjonene for å [konfigurere en eksport](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
