---
title: Opprette en enhetlig visning av kundene
description: Gå gjennom datasamlingsprosessen med dataene for å opprette ett hoveddatasett med forretningsforbindelses- eller kundeprofiler.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304439"
---
# <a name="data-unification-overview"></a>Oversikt over datasamling

Når du har [konfigurert datakildene](data-sources.md), kan du samle dataene. Med datasamling kan du samle datakilder som en gang var spredt, til ett enkelt hoveddatasett som gir en enhetlig visning av dataene.

For individuelle forbrukere (B-til-C) der dataene er sentrert rundt enkeltpersoner, gir samlingen en enhetlig visning av kundene. For forretningskontoer (B-til-B) der dataene er sentrert rundt kontoer, gir samlingen en enhetlig visning av kontoene. [Kontaktsamling (forhåndsversjon)](data-unification-contacts.md) gjør at kontakter for disse forretningsforbindelsene kan samles separat og knyttes til forretningsforbindelsene.

Data kan forenes for én enkelt enhet eller flere enheter.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

Samlingsprosessen tilordner kundedata fra datakildene, fjerner duplikater, samsvarer dataene på tvers av enheter og oppretter en samlet profil. Samlingen utføres i følgende rekkefølge:

1. [Kildefelter](map-entities.md) (tidligere kalt Tildeling): I kildefelttrinnet velger du enheter og felter som skal inkluderes i samlingsprosessen. Tildel felter til en felles semantisk type som beskriver formålet med feltet.

1. [Duplikatoppføringer](remove-duplicates.md) (tidligere del av Samsvar): I trinnet for duplikatoppføringer kan du eventuelt definere regler for å fjerne dupliserte kundeoppføringer fra hver enhet.

1. [Samsvarende betingelser](match-entities.md) (tidligere kalt Samsvar): I trinnet for samsvarende betingelser definerer du regler som samsvarer med kundeoppføringer mellom enheter. Når en kunde blir funnet i to eller flere enheter, opprettes en enkelt konsolidert oppføring med alle kolonner og data fra hver enhet.

1. [Enhetlige kundefelter](merge-entities.md) (tidligere kalt Slå sammen): I trinnet for enhetlige kundefelter bestemmer du hvilke kildefelter som skal inkluderes, utelates eller slås sammen til en enhetlig kundeprofil.  

1. [Se gjennom](review-unification.md) og opprett den enhetlige profilen.

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

Samlingsprosessen tilordner forretningsforbindelsesdata fra datakildene, fjerner duplikater, samsvarer dataene på tvers av enheter og oppretter en samlet profil. Samlingen utføres i følgende rekkefølge:

1. [Kildefelter](map-entities.md) (tidligere kalt Tildeling): I kildefelttrinnet velger du enheter og felter som skal inkluderes i prosessen for samling av forretningsforbindelser. Tildel felter til en felles semantisk type som beskriver formålet med feltet.

1. [Duplikatoppføringer](remove-duplicates.md) (tidligere del av Samsvar): I trinnet for duplikatoppføringer kan du eventuelt definere regler for å fjerne dupliserte forretningsforbindelsesoppføringer fra hver enhet.

1. [Samsvarende betingelser](match-entities.md) (tidligere kalt Samsvar): I trinnet for samsvarende betingelser definerer du regler som samsvarer med forretningsforbindelsesoppføringer mellom enheter. Når en forretningsforbindelse blir funnet i to eller flere enheter, opprettes en enkelt konsolidert oppføring med alle kolonner og data fra hver enhet.

1. [Enhetlige kundefelter](merge-entities.md) (tidligere kalt Slå sammen): I trinnet for enhetlige kundefelter bestemmer du hvilke kildefelter som skal inkluderes, utelates eller slås sammen til en enhetlig kundeprofil.  

1. [Se gjennom](review-unification.md) og opprett den enhetlige profilen.

Når forretningsforbindelsene er samlet, kan du eventuelt [samle kontakter (forhåndsversjon)](data-unification-contacts.md) for disse forretningsforbindelsene og koble de samlede kontaktene til de samlede forretningsforbindelsene.

---

Når du har fullført datasamlingen, kan du eventuelt gjøre følgende:

- [Konfigurer relasjoner mellom enheter](relationships.md) hvis du vil opprette sofistikerte segmenter.
- [Suppler dataene](enrichment-hub.md) for å få et større utvalg av innsikt om kundene.
- [Definer aktiviteter](activities.md) fra noen av attributtene som er hentet inn.
- [Bygg mål](measures.md) for å få bedre forståelse av kundeatferd og forretningsytelse.

[!INCLUDE [footer-include](includes/footer-banner.md)]
