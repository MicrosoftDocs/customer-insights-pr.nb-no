---
title: Planlegg systemoppdatering
description: Planlegg klokkeslettet når systemet skal oppdateres
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246345"
---
# <a name="schedule-system-refresh"></a>Planlegg systemoppdatering

Planlegg automatisk oppdatering av alle [datakildene som er hentet inn](data-sources.md). Automatisk oppdatering bidrar til å sikre at oppdateringer fra datakildene gjenspeiles i de enhetlige kundeprofilene.

> [!NOTE]
> Power Query-datakilder som administreres av deg, oppdateres etter egne tidsplaner. Hvis du vil planlegge oppdatering av disse Power Query-datakilder som administreres av deg, konfigurerer du oppdateringsinnstillinger for bestemte datakilde fra **Datakilder**-siden.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Oppdateringsinnstillinger for Power Platform-dataflyt.":::

## <a name="set-system-refresh-schedule"></a>Angi systemoppdateringsplanlegging

1. Gå til **Administrator** > **System**, og velg fanen **Planlegg**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Fanen Planlegg oppdatering fra System-siden.":::

1. Standardtilstanden for den planlagte oppdateringen er **Av**. Hvis du vil aktivere planlagte oppdateringer, endrer du vekslingsknappen øverst på skjermen til **På**.

1. Velg mellom **Ukentlig** (standard) og **Daglig** for oppdateringer. Hvis du planlegger ukentlige oppdateringer, velger du én eller flere dager du vil kjøre oppdateringen på.

1. Angi **Tidssone**, og bruk deretter rullegardinlisten **Tidspunkt** til å angi tiden for oppdatering. Hvis du vil planlegge flere repetisjoner på én enkelt dag, velger du **Legg til et annet tidspunkt**.

1. Velg **Lagre** for å ta i bruk endringene.

[!INCLUDE [footer-include](includes/footer-banner.md)]
