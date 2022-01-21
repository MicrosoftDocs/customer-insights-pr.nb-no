---
title: Opprette en enhetlig visning av kundene
description: Gå gjennom dataforeningsprosessen med dataene for å opprette ett hoveddatasett med kundeprofiler.
ms.date: 10/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-unify
ms.openlocfilehash: c5422c9b60c21923caf4d9dc9baeec575cba093f
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977471"
---
# <a name="data-unification-overview"></a>Oversikt over datasamling

Når du har [konfigurert datakildene](data-sources.md), kan du samle dataene. Datasamling består av tre trinn: **Tilordne**, **Samsvare** og **Slå sammen**.

Med datasamlingsprosessen kan du samle tidligere spredte datakilder til ett hoveddatasett som gir en ensartet visning av kundene. Samlingsfasene er obligatoriske og utføres i følgende rekkefølge:

1. [Tilordne](map-entities.md)
2. [Samsvar](match-entities.md)
3. [Slå sammen](merge-entities.md)

Når du har fullført datasamlingen, kan du

- [konfigurere relasjoner mellom enheter](relationships.md) hvis du vil opprette sofistikerte segmenter
- [berike dataene](enrichment-hub.md) for å få et større utvalg av innsikt om kundene
- [definere aktiviteter](activities.md) fra noen av attributtene som er hentet inn


[!INCLUDE[footer-include](../includes/footer-banner.md)]