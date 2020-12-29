---
title: Datasamling
description: Lær hvordan du kan samle data som er tatt inn.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406499"
---
# <a name="data-unification"></a>Datasamling

Når du har [konfigurert datakildene](data-sources.md), kan du samle dataene. Datasamling består av tre trinn: **Tilordne**, **Samsvare** og **Slå sammen**.

Med datasamlingsprosessen kan du samle tidligere spredte datakilder til ett hoveddatasett som gir en ensartet visning av kundene. Samlingsfasene er obligatoriske og utføres i følgende rekkefølge:

1. [Tilordne](map-entities.md)
2. [Samsvar](match-entities.md)
3. [Slå sammen](merge-entities.md)

Når du har fullført datasamlingen, kan du

- [konfigurere relasjoner mellom enheter](relationships.md) hvis du vil opprette sofistikerte segmenter
- [berike dataene](enrichment-hub.md) for å få et større utvalg av innsikt om kundene
- [definere aktiviteter](activities.md) fra noen av attributtene som er hentet inn
