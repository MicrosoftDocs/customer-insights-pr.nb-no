---
title: Relasjoner mellom enheter og enhetsbaner
description: Opprett og administrer relasjoner mellom enheter fra flere datakilder.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269893"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="22109-103">Relasjoner mellom enheter</span><span class="sxs-lookup"><span data-stu-id="22109-103">Relationships between entities</span></span>

<span data-ttu-id="22109-104">Relasjoner hjelper deg med å koble sammen enheter og generere et diagram over dataene når enhetene deler en felles identifikator (sekundærnøkkel) som kan refereres fra én enhet til en annen.</span><span class="sxs-lookup"><span data-stu-id="22109-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="22109-105">Ved å bruke tilkoblede enheter kan du definere segmenter og mål basert på flere datakilder.</span><span class="sxs-lookup"><span data-stu-id="22109-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="22109-106">Det finnes to typer relasjoner:</span><span class="sxs-lookup"><span data-stu-id="22109-106">There are two types of relationships.</span></span> <span data-ttu-id="22109-107">Systemrelasjoner som ikke kan redigeres, som opprettes automatisk, og egendefinerte relasjoner som opprettes og konfigureres av brukere.</span><span class="sxs-lookup"><span data-stu-id="22109-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="22109-108">I løpet av samsvars- og sammenslåingsprosessene opprettes systemrelasjoner i bakgrunnen basert på intelligent samsvar.</span><span class="sxs-lookup"><span data-stu-id="22109-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="22109-109">Disse relasjonene hjelper deg med å relatere kundeprofiloppføringene med andre korresponderende enheters oppføringer.</span><span class="sxs-lookup"><span data-stu-id="22109-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="22109-110">Følgende diagram illustrerer opprettelsen av tre systemrelasjoner når kundeenheten samsvarer med tilleggsenheter for å produsere den endelige kundeprofilenheten.</span><span class="sxs-lookup"><span data-stu-id="22109-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="22109-111">![Relasjonsopprettelse](media/relationships-entities-merge.png "Relasjonsopprettelse")</span><span class="sxs-lookup"><span data-stu-id="22109-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="22109-112">\***CustomerToContact\*-relasjon** ble opprettet mellom kundeenheten og kontaktenheten.</span><span class="sxs-lookup"><span data-stu-id="22109-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="22109-113">Kundeenheten får nøkkelfeltet **Contact_contactId** til å relatere til nøkkelfeltet til kontaktenheten **contactId**.</span><span class="sxs-lookup"><span data-stu-id="22109-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="22109-114">\***CustomerToAccount\*-relasjon** ble opprettet mellom kundeenheten og kontoenheten.</span><span class="sxs-lookup"><span data-stu-id="22109-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="22109-115">Kundeenheten får nøkkelfeltet **Account_accountId** til å relatere til nøkkelfeltet til kontoenheten **accountId**.</span><span class="sxs-lookup"><span data-stu-id="22109-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="22109-116">\***CustomerToWebAccount\*-relasjon** ble opprettet mellom kundeenheten og webkontoenheten.</span><span class="sxs-lookup"><span data-stu-id="22109-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="22109-117">Kundeenheten får nøkkelfeltet **WebAccount_webaccountId** til å relatere til nøkkelfeltet til webkontoenheten **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="22109-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="22109-118">Opprette en relasjon</span><span class="sxs-lookup"><span data-stu-id="22109-118">Create a relationship</span></span>

<span data-ttu-id="22109-119">Definer egendefinerte relasjoner på siden **Relasjoner**.</span><span class="sxs-lookup"><span data-stu-id="22109-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="22109-120">Hver relasjon består av en kildeenhet (enheten som inneholder sekundærnøkkelen) og en målenhet (enheten som kildeenhetens sekundærnøkkel peker til).</span><span class="sxs-lookup"><span data-stu-id="22109-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="22109-121">I Målgruppeinnsikt går du til **Data** > **Relasjoner**.</span><span class="sxs-lookup"><span data-stu-id="22109-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="22109-122">Velg **Ny relasjon**.</span><span class="sxs-lookup"><span data-stu-id="22109-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="22109-123">Angi følgende informasjon i ruten **Legg til relasjon**:</span><span class="sxs-lookup"><span data-stu-id="22109-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="22109-124">![Angi relasjonsdetaljer](media/relationships-add.png "Angi relasjonsdetaljer")</span><span class="sxs-lookup"><span data-stu-id="22109-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="22109-125">**Relasjonsnavn**: Navn som gjenspeiler formålet med relasjonen (for eksempel **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="22109-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="22109-126">**Beskrivelse**: Beskrivelse av relasjonen.</span><span class="sxs-lookup"><span data-stu-id="22109-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="22109-127">**Kildeenhet**: Velg enheten som brukes som en kilde i relasjonen (for eksempel WebLog).</span><span class="sxs-lookup"><span data-stu-id="22109-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="22109-128">**Kardinalitet**: Velg kardinaliteten for kildeenhetsoppføringene.</span><span class="sxs-lookup"><span data-stu-id="22109-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="22109-129">"Mange" betyr for eksempel at flere Weblog-oppføringer er relatert til én WebAccount.</span><span class="sxs-lookup"><span data-stu-id="22109-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="22109-130">**Kildenøkkelfelt**: Dette representerer sekundærnøkkelfeltet i kildeenheten.</span><span class="sxs-lookup"><span data-stu-id="22109-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="22109-131">For eksempel har WebLog sekundærnøkkelfeltet **accountId** .</span><span class="sxs-lookup"><span data-stu-id="22109-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="22109-132">**Målenhet**: Velg enheten som brukes som et mål i relasjonen (for eksempel WebAccount).</span><span class="sxs-lookup"><span data-stu-id="22109-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="22109-133">**Målkardinalitet**: Velg kardinaliteten for målenhetsoppføringene.</span><span class="sxs-lookup"><span data-stu-id="22109-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="22109-134">"Én" betyr for eksempel at flere Weblog-oppføringer er relatert til én WebAccount.</span><span class="sxs-lookup"><span data-stu-id="22109-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="22109-135">**Målprogramfelt**: Dette feltet representerer nøkkelfeltet for målenhet.</span><span class="sxs-lookup"><span data-stu-id="22109-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="22109-136">For eksempel har WebAccount nøkkelfeltet **accountId** .</span><span class="sxs-lookup"><span data-stu-id="22109-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="22109-137">Bare mange-til-én- og én-til-én-relasjoner støttes.</span><span class="sxs-lookup"><span data-stu-id="22109-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="22109-138">Mange-til-mange-relasjoner kan opprettes ved hjelp av to mange-til-én-relasjoner og en koblingsenhet (en enhet som brukes til å koble kildeenheten og målenheten).</span><span class="sxs-lookup"><span data-stu-id="22109-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="22109-139">Slette en relasjon</span><span class="sxs-lookup"><span data-stu-id="22109-139">Delete a relationship</span></span>

1. <span data-ttu-id="22109-140">I Målgruppeinnsikt går du til **Data** > **Relasjoner**.</span><span class="sxs-lookup"><span data-stu-id="22109-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="22109-141">Merk av for relasjonene du vil slette.</span><span class="sxs-lookup"><span data-stu-id="22109-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="22109-142">Velg **Slett** øverst i **Relasjoner** tabellen.</span><span class="sxs-lookup"><span data-stu-id="22109-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="22109-143">Bekreft slettingen.</span><span class="sxs-lookup"><span data-stu-id="22109-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="22109-144">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="22109-144">Next step</span></span>

<span data-ttu-id="22109-145">System- og egendefinerte relasjoner brukes til å opprette segmenter basert på flere datakilder som ikke lenger er i siloer.</span><span class="sxs-lookup"><span data-stu-id="22109-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="22109-146">Du finner mer informasjon på [Segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="22109-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]