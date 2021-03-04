---
title: Enheter og datasett
description: Vise data på Enheter-siden.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269388"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="86d3e-103">Enheter i målgruppeinnsikt</span><span class="sxs-lookup"><span data-stu-id="86d3e-103">Entities in audience insights</span></span>

<span data-ttu-id="86d3e-104">Når du har [konfigurert datakildene](data-sources.md), går du til siden **Enheter** for å vurdere kvaliteten på de innhentede dataene.</span><span class="sxs-lookup"><span data-stu-id="86d3e-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="86d3e-105">Enheter anses som datasett.</span><span class="sxs-lookup"><span data-stu-id="86d3e-105">Entities are considered datasets.</span></span> <span data-ttu-id="86d3e-106">Flere funksjoner i Dynamics 365 Customer Insights er bygget rundt disse enhetene.</span><span class="sxs-lookup"><span data-stu-id="86d3e-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="86d3e-107">Når du ser gjennom dem, kan det hjelpe deg med å validere utdataene fra disse funksjonene.</span><span class="sxs-lookup"><span data-stu-id="86d3e-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="86d3e-108">Siden **Enheter** viser enheter og inneholder flere kolonner:</span><span class="sxs-lookup"><span data-stu-id="86d3e-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="86d3e-109">**Navn**: Navnet på dataenheten.</span><span class="sxs-lookup"><span data-stu-id="86d3e-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="86d3e-110">Hvis du ser et varselsymbol ved siden av et enhetsnavn, betyr det at dataene for enheten ikke ble lastet inn på riktig måte.</span><span class="sxs-lookup"><span data-stu-id="86d3e-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="86d3e-111">**Kilde**: Typen datakilde som hentet inn enheten</span><span class="sxs-lookup"><span data-stu-id="86d3e-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="86d3e-112">**Opprettet av**: Navnet på personen som opprettet enheten</span><span class="sxs-lookup"><span data-stu-id="86d3e-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="86d3e-113">**Opprettet**: Dato og klokkeslett for enhetsopprettingen</span><span class="sxs-lookup"><span data-stu-id="86d3e-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="86d3e-114">**Opprettet av**: Navnet på personen som oppdaterte enheten</span><span class="sxs-lookup"><span data-stu-id="86d3e-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="86d3e-115">**Sist oppdatert**: Dato og klokkeslett for den siste oppdateringen av enheten</span><span class="sxs-lookup"><span data-stu-id="86d3e-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="86d3e-116">**Siste oppdatering**: Dato og klokkeslett for den siste dataoppdateringen</span><span class="sxs-lookup"><span data-stu-id="86d3e-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="86d3e-117">Utforske dataene til en bestemt enhet</span><span class="sxs-lookup"><span data-stu-id="86d3e-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="86d3e-118">Velg en enhet for å utforske de forskjellige feltene og oppføringene som er inkludert i enheten.</span><span class="sxs-lookup"><span data-stu-id="86d3e-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="86d3e-119">![Velg en enhet](media/data-manager-entities-data.png "Velg en enhet")</span><span class="sxs-lookup"><span data-stu-id="86d3e-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="86d3e-120">Kategorien **Data** velges som standard og viser en tabell med detaljer om enkeltoppføringer for enheten.</span><span class="sxs-lookup"><span data-stu-id="86d3e-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="86d3e-121">![Tabellen Felt](media/data-manager-entities-fields.PNG "Tabellen Felt")</span><span class="sxs-lookup"><span data-stu-id="86d3e-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="86d3e-122">Kategorien **Felt** viser en tabell for å se gjennom detaljer for den valgte enheten, for eksempel feltnavn, datatyper og typer.</span><span class="sxs-lookup"><span data-stu-id="86d3e-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="86d3e-123">**Type**-kolonnen viser Common Data Model-tilknyttede typer, som enten er automatisk identifiserte av systemet eller [manuelt tilordnede](map-entities.md) av brukere.</span><span class="sxs-lookup"><span data-stu-id="86d3e-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="86d3e-124">Dette er semantiske typer som kan være forskjellige fra attributtenes datatyper – for eksempel har feltet *E-post* nedenfor datatypen *Tekst*, men (semantisk) Common Data Model-type kan være *E-post* eller *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="86d3e-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="86d3e-125">Begge tabellene viser bare et eksempel på enhetens data.</span><span class="sxs-lookup"><span data-stu-id="86d3e-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="86d3e-126">Hvis du vil vise hele datasettet, går du til siden **Datakilder**, velger en enhet, velger **Rediger** og deretter viser enhetens data med Power Query-redigeringsprogrammet som forklart i [Datakilder](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="86d3e-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="86d3e-127">Hvis du vil lære mer om data som hentes inn i enheten, gir kolonnen **Sammendrag** deg noen viktige egenskaper for dataene, for eksempel nuller, manglende verdier, unike verdier, antall og fordelinger, i henhold til hva som gjelder for dataene dine.</span><span class="sxs-lookup"><span data-stu-id="86d3e-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="86d3e-128">Velg diagramikonet for å vise sammendraget av dataene.</span><span class="sxs-lookup"><span data-stu-id="86d3e-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="86d3e-129">![Sammendragssymbol](media/data-manager-entities-summary.png "Tabell for datasammendrag")</span><span class="sxs-lookup"><span data-stu-id="86d3e-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="86d3e-130">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="86d3e-130">Next step</span></span>

<span data-ttu-id="86d3e-131">Se emnet [Samle](data-unification.md) for å lære hvordan du *tilordner*, *samsvarer* og *slår sammen* de innhentede dataene.</span><span class="sxs-lookup"><span data-stu-id="86d3e-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]