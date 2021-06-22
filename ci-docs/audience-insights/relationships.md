---
title: Relasjoner mellom enheter og enhetsbaner
description: Opprett og administrer relasjoner mellom enheter fra flere datakilder.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171176"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="6d753-103">Relasjoner mellom enheter</span><span class="sxs-lookup"><span data-stu-id="6d753-103">Relationships between entities</span></span>

<span data-ttu-id="6d753-104">Relasjoner kobler sammen enheter og definerer en graf for dataene når enheter deler en felles identifikator, en sekundærnøkkel.</span><span class="sxs-lookup"><span data-stu-id="6d753-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="6d753-105">Denne sekundærnøkkelen kan referere fra én enhet til en annen.</span><span class="sxs-lookup"><span data-stu-id="6d753-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="6d753-106">Tilkoblede enheter gjør at segmenter og mål kan defineres basert på flere datakilder.</span><span class="sxs-lookup"><span data-stu-id="6d753-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="6d753-107">Det finnes tre typer relasjoner:</span><span class="sxs-lookup"><span data-stu-id="6d753-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="6d753-108">systemrelasjoner som ikke kan redigeres, og som opprettes av systemet som en del av dataforeningsprosessen</span><span class="sxs-lookup"><span data-stu-id="6d753-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="6d753-109">arvede relasjoner som ikke kan redigeres, og som opprettes automatisk fra inntak av datakilder</span><span class="sxs-lookup"><span data-stu-id="6d753-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="6d753-110">egendefinerte relasjoner som kan redigeres, og som opprettes og konfigureres av brukere</span><span class="sxs-lookup"><span data-stu-id="6d753-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="6d753-111">Systemrelasjoner som ikke kan redigeres</span><span class="sxs-lookup"><span data-stu-id="6d753-111">Non-editable system relationships</span></span>

<span data-ttu-id="6d753-112">Under dataforening opprettes systemrelasjoner automatisk basert på intelligent samsvar.</span><span class="sxs-lookup"><span data-stu-id="6d753-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="6d753-113">Disse relasjonene hjelper deg å knytte kundeprofiloppføringene til tilsvarende oppføringer.</span><span class="sxs-lookup"><span data-stu-id="6d753-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="6d753-114">Diagrammet nedenfor illustrerer opprettelsen av tre systembaserte relasjoner.</span><span class="sxs-lookup"><span data-stu-id="6d753-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="6d753-115">Kundeenheten sammenlignes med andre enheter for å produsere den enhetlige *Kunde*-enheten.</span><span class="sxs-lookup"><span data-stu-id="6d753-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram med relasjonsbaner for kundeenheten med tre 1:N-relasjoner.":::

- <span data-ttu-id="6d753-117">\***CustomerToContact\*-relasjon** ble opprettet mellom *Kunde*-enheten og *Kontakt*-enheten.</span><span class="sxs-lookup"><span data-stu-id="6d753-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="6d753-118">*Kunde*-enheten får nøkkelfeltet **Contact_contactID** til å knyttes til nøkkelfeltet **contactID** for *Kontakt*-enheten.</span><span class="sxs-lookup"><span data-stu-id="6d753-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="6d753-119">\***CustomerToAccount\*-relasjon** ble opprettet mellom *Kunde*-enheten og *Konto*-enheten.</span><span class="sxs-lookup"><span data-stu-id="6d753-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="6d753-120">*Kunde*-enheten får nøkkelfeltet **Account_accountID** til å knyttes til nøkkelfeltet **accountID** for *Konto*-enheten.</span><span class="sxs-lookup"><span data-stu-id="6d753-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="6d753-121">\***CustomerToWebAccount\*-relasjon** ble opprettet mellom *Kunde*-enheten og *WebAccount*-enheten.</span><span class="sxs-lookup"><span data-stu-id="6d753-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="6d753-122">*Kunde*-enheten får nøkkelfeltet **WebAccount_webaccountID** til å knyttes til nøkkelfeltet **webaccountID** for *WebAccount*-enheten.</span><span class="sxs-lookup"><span data-stu-id="6d753-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="6d753-123">Arvede relasjoner som ikke kan redigeres</span><span class="sxs-lookup"><span data-stu-id="6d753-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="6d753-124">Under datainntaksprosessen kontrollerer systemet datakilder for eksisterende relasjoner.</span><span class="sxs-lookup"><span data-stu-id="6d753-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="6d753-125">Hvis ingen relasjoner finnes, oppretter systemet dem automatisk.</span><span class="sxs-lookup"><span data-stu-id="6d753-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="6d753-126">Disse relasjonene brukes også i nedstrømsprosesser.</span><span class="sxs-lookup"><span data-stu-id="6d753-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="6d753-127">Opprette en egendefinert relasjon</span><span class="sxs-lookup"><span data-stu-id="6d753-127">Create a custom relationship</span></span>

<span data-ttu-id="6d753-128">Relasjonen består av en *kildeenhet* som inneholder sekundærnøkkelen og en *målenhet* som kildeenhetens sekundærnøkkel peker mot.</span><span class="sxs-lookup"><span data-stu-id="6d753-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="6d753-129">I Målgruppeinnsikt går du til **Data** > **Relasjoner**.</span><span class="sxs-lookup"><span data-stu-id="6d753-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="6d753-130">Velg **Ny relasjon**.</span><span class="sxs-lookup"><span data-stu-id="6d753-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="6d753-131">Angi følgende informasjon i ruten **Ny relasjon**:</span><span class="sxs-lookup"><span data-stu-id="6d753-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Sideruten Ny relasjon med tomme inndatafelter.":::

   - <span data-ttu-id="6d753-133">**Relasjonsnavn**: Navn som gjenspeiler formålet med relasjonen.</span><span class="sxs-lookup"><span data-stu-id="6d753-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="6d753-134">Eksempel: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="6d753-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="6d753-135">**Beskrivelse**: Beskrivelse av relasjonen.</span><span class="sxs-lookup"><span data-stu-id="6d753-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="6d753-136">**Kildeenhet**: Enhet som brukes som en kilde i relasjonen.</span><span class="sxs-lookup"><span data-stu-id="6d753-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="6d753-137">Eksempel: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="6d753-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="6d753-138">**Målenhet**: Enhet som brukes som et mål i relasjonen.</span><span class="sxs-lookup"><span data-stu-id="6d753-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="6d753-139">Eksempel: Kunde.</span><span class="sxs-lookup"><span data-stu-id="6d753-139">Example: Customer.</span></span>
   - <span data-ttu-id="6d753-140">**Kildekardinalitet**: Angi kardinaliteten til kildeenheten.</span><span class="sxs-lookup"><span data-stu-id="6d753-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="6d753-141">Kardinalitet beskriver antall mulige elementer i et sett.</span><span class="sxs-lookup"><span data-stu-id="6d753-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="6d753-142">Den er alltid relatert til målkardinaliteten.</span><span class="sxs-lookup"><span data-stu-id="6d753-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="6d753-143">Du kan velge mellom **Én** og **Mange**.</span><span class="sxs-lookup"><span data-stu-id="6d753-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="6d753-144">Bare mange-til-én- og én-til-én-relasjoner støttes.</span><span class="sxs-lookup"><span data-stu-id="6d753-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="6d753-145">Mange-til-én: Flere kildeoppføringer kan knyttes til én måloppføring.</span><span class="sxs-lookup"><span data-stu-id="6d753-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="6d753-146">Eksempel: Flere kundestøttesaker fra én kunde.</span><span class="sxs-lookup"><span data-stu-id="6d753-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="6d753-147">Én-til-én: Én kildeoppføring er knyttet til én måloppføring.</span><span class="sxs-lookup"><span data-stu-id="6d753-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="6d753-148">Eksempel: Én fordels-ID for én kunde.</span><span class="sxs-lookup"><span data-stu-id="6d753-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="6d753-149">Mange-til-mange-relasjoner kan opprettes ved hjelp av to mange-til-én-relasjoner og en koblingsenhet, som kobler sammen kildeenheten og målenheten.</span><span class="sxs-lookup"><span data-stu-id="6d753-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="6d753-150">**Målkardinalitet**: Velg kardinaliteten for målenhetsoppføringene.</span><span class="sxs-lookup"><span data-stu-id="6d753-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="6d753-151">**Kildenøkkelfelt**: Sekundærnøkkelfeltet i kildeenheten.</span><span class="sxs-lookup"><span data-stu-id="6d753-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="6d753-152">Eksempel: SupportCase kan bruke CaseID som et sekundærnøkkelfelt.</span><span class="sxs-lookup"><span data-stu-id="6d753-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="6d753-153">**Målprogramfelt**: Nøkkelfeltet for målenheten.</span><span class="sxs-lookup"><span data-stu-id="6d753-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="6d753-154">Eksempel: Kunde kan bruke nøkkelfeltet **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="6d753-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="6d753-155">Velg **Lagre** for å opprette den egendefinerte relasjonen.</span><span class="sxs-lookup"><span data-stu-id="6d753-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="6d753-156">Vise relasjoner</span><span class="sxs-lookup"><span data-stu-id="6d753-156">View relationships</span></span>

<span data-ttu-id="6d753-157">Relasjoner-siden viser alle relasjonene som er opprettet.</span><span class="sxs-lookup"><span data-stu-id="6d753-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="6d753-158">Hver rad representerer en relasjon, som også omfatter detaljer om kildeenheten, målenheten og kardinaliteten.</span><span class="sxs-lookup"><span data-stu-id="6d753-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Liste over relasjoner og alternativer på handlingslinjen på Relasjoner-siden.":::

<span data-ttu-id="6d753-160">Denne siden har et sett med alternativer for eksisterende og nye relasjoner:</span><span class="sxs-lookup"><span data-stu-id="6d753-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="6d753-161">**Ny relasjon**: [Opprett en egendefinert relasjon](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="6d753-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="6d753-162">**Visualisering**: [Utforsk relasjonsvisualiseringen](#explore-the-relationship-visualizer) for å se et nettverksdiagram over eksisterende relasjoner og kardinaliteten deres.</span><span class="sxs-lookup"><span data-stu-id="6d753-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="6d753-163">**Filtrer etter**: Velg hvilken type relasjoner som skal vises i listen.</span><span class="sxs-lookup"><span data-stu-id="6d753-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="6d753-164">**Søk etter relasjoner**: Bruk et tekstbasert søk etter egenskaper i relasjoner.</span><span class="sxs-lookup"><span data-stu-id="6d753-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="6d753-165">Utforske relasjonsvisualiseringen</span><span class="sxs-lookup"><span data-stu-id="6d753-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="6d753-166">Relasjonsvisualiseringen viser et nettverksdiagram over eksisterende relasjoner mellom tilkoblede enheter og kardinaliteten deres.</span><span class="sxs-lookup"><span data-stu-id="6d753-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="6d753-167">Hvis du vil tilpasse visningen, kan du endre plasseringen til boksene ved å dra dem på lerretet.</span><span class="sxs-lookup"><span data-stu-id="6d753-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Skjermbilde av nettverksdiagrammet for relasjonsvisualisering med tilkoblinger mellom relaterte enheter.":::

<span data-ttu-id="6d753-169">Tilgjengelige alternativer:</span><span class="sxs-lookup"><span data-stu-id="6d753-169">Available options:</span></span> 
- <span data-ttu-id="6d753-170">**Eksporter som bilde**: Lagre gjeldende visning som en bildefil.</span><span class="sxs-lookup"><span data-stu-id="6d753-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="6d753-171">**Endre til vannrett/loddrett oppsett**: Endre justeringen av enhetene og relasjonene.</span><span class="sxs-lookup"><span data-stu-id="6d753-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="6d753-172">**Rediger**: Oppdater egenskaper for egendefinerte relasjoner i redigeringsruten, og lagre endringer.</span><span class="sxs-lookup"><span data-stu-id="6d753-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="6d753-173">Administrere eksisterende relasjoner</span><span class="sxs-lookup"><span data-stu-id="6d753-173">Manage existing relationships</span></span> 

<span data-ttu-id="6d753-174">Hver relasjon representeres av en rad på Relasjoner-siden.</span><span class="sxs-lookup"><span data-stu-id="6d753-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="6d753-175">Velg en relasjon, og velg ett av følgende alternativer:</span><span class="sxs-lookup"><span data-stu-id="6d753-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="6d753-176">**Rediger**: Oppdater egenskaper for egendefinerte relasjoner i redigeringsruten, og lagre endringer.</span><span class="sxs-lookup"><span data-stu-id="6d753-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="6d753-177">**Slett**: Slett egendefinerte relasjoner.</span><span class="sxs-lookup"><span data-stu-id="6d753-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="6d753-178">**Vis**: Vis systemopprettede og arvede relasjoner.</span><span class="sxs-lookup"><span data-stu-id="6d753-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="6d753-179">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="6d753-179">Next step</span></span>

<span data-ttu-id="6d753-180">Systemrelasjoner og egendefinerte relasjoner brukes til å [opprette segmenter](segments.md) basert på flere datakilder som ikke lenger er i siloer.</span><span class="sxs-lookup"><span data-stu-id="6d753-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
