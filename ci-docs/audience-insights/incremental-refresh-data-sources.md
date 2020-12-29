---
title: Trinnvis oppdatering for Power Query-baserte datakilder
description: Oppdatere nye og oppdaterte data for store datakilder basert på Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406526"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="3a6b8-103">Trinnvis oppdatering for datakilder som er baserte på Power Query</span><span class="sxs-lookup"><span data-stu-id="3a6b8-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="3a6b8-104">Trinnvis oppdatering for datakilder gir følgende fordeler:</span><span class="sxs-lookup"><span data-stu-id="3a6b8-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="3a6b8-105">**Raskere oppdateringer** – Bare data som er endret, blir oppdatert.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="3a6b8-106">Du kan for eksempel bare oppdatere de siste fem dagene i en historisk datasett.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="3a6b8-107">**Økt pålitelighet** – Med mindre oppdateringer trenger du ikke å opprettholde tilkoblinger til flyktige kildesystemer så lenge, noe som reduserer risikoen for tilkoblingsproblemer.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="3a6b8-108">**Reduksjon av ressursforbruk** – Oppdatering av bare et delsett av de totale dataene fører til mer effektiv bruk av dataressurser og reduserer miljøavtrykket.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="3a6b8-109">Konfigurer trinnvis oppdatering</span><span class="sxs-lookup"><span data-stu-id="3a6b8-109">Configure incremental refresh</span></span>

<span data-ttu-id="3a6b8-110">Målgruppeinnsikt tillater trinnvis oppdatering for datakilder importert via Power Query som støtter trinnvis inkludering.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="3a6b8-111">For eksempel Azure SQL-databaser med dato- og klokkeslettfelt, som angir når dataoppføringer sist ble oppdatert.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="3a6b8-112">[Opprett en ny datakilde basert på Power Query ](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="3a6b8-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="3a6b8-113">Skriv inn et navn på datakilden.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="3a6b8-114">Velg en datakilde som støtter trinnvis oppdatering, for eksempel Azure SQL-database.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="3a6b8-115">Velg enhetene eller tabellene som skal inkluderes.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="3a6b8-116">Fullfør transformeringstrinnene, og velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="3a6b8-117">I dialogboksen **Konfigurer trinnvis oppdatering** velger du **Konfigurer** for å åpne **Innstillinger for trinnvis oppdatering**.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="3a6b8-118">Hvis du velger **Hopp over**, vil datakilden oppdatere hele datasettet.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="3a6b8-119">Du kan også bruke trinnvis oppdatering senere ved å redigere en eksisterende datakilde.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="3a6b8-120">I **Innstillinger for trinnvis oppdatering** konfigurerer du den trinnvise oppdateringen for alle enhetene som du valgte ved oppretting av datakilden.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a6b8-121">![Konfigurere enheter i en datakilde for trinnvis oppdatering](media/incremental-refresh-settings.png "Konfigurere enheter i en datakilde for trinnvis oppdatering")</span><span class="sxs-lookup"><span data-stu-id="3a6b8-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="3a6b8-122">Velg en enhet, og angi følgende detaljer:</span><span class="sxs-lookup"><span data-stu-id="3a6b8-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="3a6b8-123">**Angi primærnøkkelen**: Velg en primærnøkkel for enheten eller tabellen.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="3a6b8-124">**Definer feltet Sist oppdatert**: Dette feltet viser bare attributter av typen dato eller klokkeslett.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="3a6b8-125">Velg et attributt som angir når oppføringene sist ble oppdatert.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="3a6b8-126">Den brukes til å identifisere oppføringene som faller innenfor tidsrammen for trinnvis oppdatering.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="3a6b8-127">**Se etter oppdateringer hver**: Angi lengden på tidsrammen for trinnvis oppdatering.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="3a6b8-128">Velg **Lagre** for å fullføre opprettingen av datakilden.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="3a6b8-129">Den første dataoppdateringen vil være en fullstendig oppdatering.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="3a6b8-130">Deretter utføres den trinnvise dataoppdateringen slik det er konfigurert i forrige trinn.</span><span class="sxs-lookup"><span data-stu-id="3a6b8-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
