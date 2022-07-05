---
title: Oversikt over datasamling
description: Gå gjennom dataforeningsprosessen med dataene for å opprette ett datasett med enhetlige kundeprofiler.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 0dbc3b2c75365e94758a1b6330e8cb557e6bd768
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081289"
---
# <a name="data-unification-overview"></a>Oversikt over datasamling

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Når du har [konfigurert datakildene](data-sources.md), kan du samle dataene. Med datasamling kan du samle datakilder som en gang var spredt, til ett enkelt hoveddatasett som gir en enhetlig visning av dataene. For individuelle forbrukere (B-til-C) der dataene er sentrert rundt enkeltpersoner, gir samlingen en enhetlig visning av kundene. For forretningskontoer (B-til-B) der dataene er sentrert rundt kontoer, gir samlingen en enhetlig visning av kontoene.

Data kan forenes for én enkelt enhet eller flere enheter. Samlingen utføres i følgende rekkefølge:

1. [Kildefelter](map-entities.md) (tidligere kalt Tildeling): I kildefelttrinnet velger du enheter og felter som skal inkluderes i samlingsprosessen. Tildel felter til en felles semantisk type som beskriver formålet med feltet.

1. [Duplikatoppføringer](remove-duplicates.md) (tidligere del av Samsvar): I trinnet for duplikatoppføringer kan du eventuelt definere regler for å fjerne dupliserte kundeoppføringer fra hver enhet.

1. [Samsvarende betingelser](match-entities.md) (tidligere kalt Samsvar): I trinnet for samsvarende betingelser definerer du regler som samsvarer med kundeoppføringer mellom enheter. Når en kunde blir funnet i to eller flere enheter, opprettes en enkelt konsolidert oppføring med alle kolonner og data fra hver enhet.

1. [Enhetlige kundefelter](merge-entities.md) (tidligere kalt Slå sammen): I trinnet for enhetlige kundefelter bestemmer du hvilke kildefelter som skal inkluderes, utelates eller slås sammen til en enhetlig kundeprofil.  

1. [Se gjennom](review-unification.md) og opprett den enhetlige profilen.

Når du har fullført datasamlingen, kan du:

- [Konfigurer relasjoner mellom enheter](relationships.md) hvis du vil opprette sofistikerte segmenter.
- [Suppler dataene](enrichment-hub.md) for å få et større utvalg av innsikt om kundene.
- [Definer aktiviteter](activities.md) fra noen av attributtene som er hentet inn.
- [Bygg mål](measures.md) for å få bedre forståelse av kundeatferd og forretningsytelse.

[!INCLUDE [footer-include](includes/footer-banner.md)]
