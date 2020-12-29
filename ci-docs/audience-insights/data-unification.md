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
# <a name="data-unification"></a><span data-ttu-id="c7a53-103">Datasamling</span><span class="sxs-lookup"><span data-stu-id="c7a53-103">Data unification</span></span>

<span data-ttu-id="c7a53-104">Når du har [konfigurert datakildene](data-sources.md), kan du samle dataene.</span><span class="sxs-lookup"><span data-stu-id="c7a53-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="c7a53-105">Datasamling består av tre trinn: **Tilordne**, **Samsvare** og **Slå sammen**.</span><span class="sxs-lookup"><span data-stu-id="c7a53-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="c7a53-106">Med datasamlingsprosessen kan du samle tidligere spredte datakilder til ett hoveddatasett som gir en ensartet visning av kundene.</span><span class="sxs-lookup"><span data-stu-id="c7a53-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="c7a53-107">Samlingsfasene er obligatoriske og utføres i følgende rekkefølge:</span><span class="sxs-lookup"><span data-stu-id="c7a53-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="c7a53-108">Tilordne</span><span class="sxs-lookup"><span data-stu-id="c7a53-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="c7a53-109">Samsvar</span><span class="sxs-lookup"><span data-stu-id="c7a53-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="c7a53-110">Slå sammen</span><span class="sxs-lookup"><span data-stu-id="c7a53-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="c7a53-111">Når du har fullført datasamlingen, kan du</span><span class="sxs-lookup"><span data-stu-id="c7a53-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="c7a53-112">[konfigurere relasjoner mellom enheter](relationships.md) hvis du vil opprette sofistikerte segmenter</span><span class="sxs-lookup"><span data-stu-id="c7a53-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="c7a53-113">[berike dataene](enrichment-hub.md) for å få et større utvalg av innsikt om kundene</span><span class="sxs-lookup"><span data-stu-id="c7a53-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="c7a53-114">[definere aktiviteter](activities.md) fra noen av attributtene som er hentet inn</span><span class="sxs-lookup"><span data-stu-id="c7a53-114">[define activities](activities.md) from some of the ingested attributes</span></span>
