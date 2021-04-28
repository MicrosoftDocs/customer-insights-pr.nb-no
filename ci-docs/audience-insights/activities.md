---
title: Kundeaktiviteter
description: Definer kundeaktiviteter og vis dem på kundetidslinjen.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866419"
---
# <a name="customer-activities"></a><span data-ttu-id="26e07-103">Kundeaktiviteter</span><span class="sxs-lookup"><span data-stu-id="26e07-103">Customer activities</span></span>

<span data-ttu-id="26e07-104">Kombiner kundeaktiviteter fra [ulike datakilder](data-sources.md) i Dynamics 365 Customer Insights for å opprette en tidslinje som viser aktivitetene kronologisk.</span><span class="sxs-lookup"><span data-stu-id="26e07-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="26e07-105">Inkluder tidslinjen i Dynamics 365-apper med løsningen for [kundekorttillegg](customer-card-add-in.md) eller i et Power BI-instrumentbord.</span><span class="sxs-lookup"><span data-stu-id="26e07-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="26e07-106">Definere en aktivitet</span><span class="sxs-lookup"><span data-stu-id="26e07-106">Define an activity</span></span>

<span data-ttu-id="26e07-107">Datakildene kan inneholde enheter med transaksjons- og aktivitetsdata fra flere datakilder.</span><span class="sxs-lookup"><span data-stu-id="26e07-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="26e07-108">Identifiser disse enhetene, og velg aktivitetene du vil vise på kundens tidslinje.</span><span class="sxs-lookup"><span data-stu-id="26e07-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="26e07-109">Velg enheten som inneholder målaktiviteten eller -aktivitetene.</span><span class="sxs-lookup"><span data-stu-id="26e07-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="26e07-110">En enhet må ha minst ett attributt av typen **Dato** som inkluderes på en kundetidslinje, og du kan ikke legge til enheter uten **Dato**-feltene.</span><span class="sxs-lookup"><span data-stu-id="26e07-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="26e07-111">Kontrollen **Legg til aktivitet** er deaktivert hvis det ikke finnes en slik enhet.</span><span class="sxs-lookup"><span data-stu-id="26e07-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="26e07-112">I Målgruppeinnsikt går du til **Data** > **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="26e07-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="26e07-113">Velg **Legg til aktivitet** for å starte den veiledede opplevelsen for installasjonsprosessen for aktivitet.</span><span class="sxs-lookup"><span data-stu-id="26e07-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="26e07-114">Angi verdiene for følgende felt i **Aktivitetsdata**-trinnet:</span><span class="sxs-lookup"><span data-stu-id="26e07-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="26e07-115">**Aktivitetsnavn**: Velg et navn for aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="26e07-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="26e07-116">**Enhet**: Velg en enhet som inkluderer transaksjons- eller aktivitetsdata.</span><span class="sxs-lookup"><span data-stu-id="26e07-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="26e07-117">**Primærnøkkel**: Velg feltet som unikt identifiserer en oppføring.</span><span class="sxs-lookup"><span data-stu-id="26e07-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="26e07-118">Den skal ikke inneholde duplikat verdier, tomme verdier eller manglende verdier.</span><span class="sxs-lookup"><span data-stu-id="26e07-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Konfigurer aktivitetsdataene med navn, enhet og hovednøkkel.":::

1. <span data-ttu-id="26e07-120">Velg **Neste** for å gå til neste trinn.</span><span class="sxs-lookup"><span data-stu-id="26e07-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="26e07-121">Konfigurer detaljene i **Relasjon**-trinnet til å koble aktivitetsdataene til den tilsvarende kunden.</span><span class="sxs-lookup"><span data-stu-id="26e07-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="26e07-122">Dette trinnet visualiserer tilkoblingen mellom enheter.</span><span class="sxs-lookup"><span data-stu-id="26e07-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="26e07-123">**Først**: Eksterne felt i aktivitetsenheten som skal brukes til å opprette en relasjon til en annen enhet.</span><span class="sxs-lookup"><span data-stu-id="26e07-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="26e07-124">**Sekund**: Tilsvarende kildekundeenhet som aktivitetsenheten skal være i relasjon med.</span><span class="sxs-lookup"><span data-stu-id="26e07-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="26e07-125">Du kan bare relatere til kildekundeenheter som brukes i dataforeningsprosessen.</span><span class="sxs-lookup"><span data-stu-id="26e07-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="26e07-126">**Tredje**: Hvis det allerede finnes en relasjon mellom aktivitetsenheten og den valgte kildekundeenheten, vil relasjonsnavnet være i skrivebeskyttet modus.</span><span class="sxs-lookup"><span data-stu-id="26e07-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="26e07-127">Hvis det ikke finnes noen slik relasjon, opprettes det en ny relasjon med navnet du angir i denne boksen.</span><span class="sxs-lookup"><span data-stu-id="26e07-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definer enhetsrelasjonen.":::

1. <span data-ttu-id="26e07-129">Velg **Neste** for å gå til neste trinn.</span><span class="sxs-lookup"><span data-stu-id="26e07-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="26e07-130">Velg aktivitetshendelsen og starttiden for aktiviteten i **Aktivitetsforening**-trinnet.</span><span class="sxs-lookup"><span data-stu-id="26e07-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="26e07-131">**Obligatoriske felter**</span><span class="sxs-lookup"><span data-stu-id="26e07-131">**Required fields**</span></span>
      1. <span data-ttu-id="26e07-132">**Hendelsesaktivitet**: Felt som er hendelsen for denne aktiviteten</span><span class="sxs-lookup"><span data-stu-id="26e07-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="26e07-133">**Tidsstempel**: Felt som representerer starttidspunktet for aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="26e07-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="26e07-134">**Valgfrie felt**</span><span class="sxs-lookup"><span data-stu-id="26e07-134">**Optional fields**</span></span>
      1. <span data-ttu-id="26e07-135">**Tilleggsdetaljer**: Felt med relevant informasjon for denne aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="26e07-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="26e07-136">**Ikon**: Ikon som best representerer denne aktivitetstypen.</span><span class="sxs-lookup"><span data-stu-id="26e07-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="26e07-137">**Webadresse**: Felt som inneholder en URL-adresse med informasjon om denne aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="26e07-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="26e07-138">For eksempel transaksjonssystemet som er kilde for denne aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="26e07-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="26e07-139">Denne URL-adressen kan være et hvilket som helst felt fra datakilde, eller den kan konstrueres som et nytt felt ved hjelp av en Power Query-transformasjon.</span><span class="sxs-lookup"><span data-stu-id="26e07-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="26e07-140">URL-dataene lagres i *Enhetlig aktivitet*-enheten, som kan brukes nedstrøms ved hjelp av [API-er](apis.md).</span><span class="sxs-lookup"><span data-stu-id="26e07-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Angi kundeaktivitetsdataene i en Enhetlig aktivitet-enhet.":::

1. <span data-ttu-id="26e07-142">Velg **Neste** for å gå til neste trinn.</span><span class="sxs-lookup"><span data-stu-id="26e07-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="26e07-143">Du kan velge **Fullfør og se gjennom** for å lagre aktiviteten nå med aktivitetstypen satt til **Annet**.</span><span class="sxs-lookup"><span data-stu-id="26e07-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="26e07-144">Velg aktivitetstypen i **Aktivitetstype**-trinnet, og velg eventuelt hvis du vil semantisk tilordne noen av aktivitetstypene for bruk i andre områder av Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="26e07-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="26e07-145">Aktivitetstypene *Abonnement* & *SalesOrderLine* kan tilordnes semantisk etter at du har godtatt å tilordne feltene.</span><span class="sxs-lookup"><span data-stu-id="26e07-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="26e07-146">Hvis en aktivitetstype ikke er relevant for den nye aktiviteten, kan du velge *Annet* eller *Opprett ny* for en egendefinert type.</span><span class="sxs-lookup"><span data-stu-id="26e07-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="26e07-147">Velg **Neste** for å gå til neste trinn.</span><span class="sxs-lookup"><span data-stu-id="26e07-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="26e07-148">Bekreft valgene i trinnet **Se gjennom**.</span><span class="sxs-lookup"><span data-stu-id="26e07-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="26e07-149">Du går tilbake til noen av de forrige trinnene, og oppdaterer informasjonen om nødvendig.</span><span class="sxs-lookup"><span data-stu-id="26e07-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Se gjennom de angitte feltene for en aktivitet.":::
   
1. <span data-ttu-id="26e07-151">Velg **Lagre aktivitet** for å ta i bruk endringene, og velg **Fullført** for å gå tilbake til **Data** > **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="26e07-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="26e07-152">Her ser du hvilke aktiviteter som skal vises på tidslinjen.</span><span class="sxs-lookup"><span data-stu-id="26e07-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="26e07-153">På **Aktiviteter**-siden velger du **Kjør** for å behandle aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="26e07-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="26e07-154">Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser.</span><span class="sxs-lookup"><span data-stu-id="26e07-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="26e07-155">De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="26e07-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="26e07-156">Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben.</span><span class="sxs-lookup"><span data-stu-id="26e07-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="26e07-157">Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.</span><span class="sxs-lookup"><span data-stu-id="26e07-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="26e07-158">Behandle eksisterende aktiviteter</span><span class="sxs-lookup"><span data-stu-id="26e07-158">Manage existing activities</span></span>

<span data-ttu-id="26e07-159">I **Data** > **Aktiviteter** kan du vise alle lagrede aktiviteter og administrere dem.</span><span class="sxs-lookup"><span data-stu-id="26e07-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="26e07-160">Hver aktivitet representeres av en rad som også inneholder detaljer om kilden, enheten og aktivitetstypen.</span><span class="sxs-lookup"><span data-stu-id="26e07-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="26e07-161">Handlingene nedenfor er tilgjengelige når du velger en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="26e07-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="26e07-162">**Rediger**: Åpner aktivitetsoppsettet i gjennomgangstrinnet.</span><span class="sxs-lookup"><span data-stu-id="26e07-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="26e07-163">Du kan endre hvilken som helst av eller alle gjeldende konfigurasjoner fra dette trinnet.</span><span class="sxs-lookup"><span data-stu-id="26e07-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="26e07-164">Når du har endret konfigurasjonen, velger du **Lagre aktivitet** og deretter **Kjør** for å behandle endringene.</span><span class="sxs-lookup"><span data-stu-id="26e07-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="26e07-165">**Gi nytt navn**: Åpner en dialogboks der du kan angi et annet navn for den valgte aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="26e07-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="26e07-166">Velg **Lagre** for å ta i bruk endringene.</span><span class="sxs-lookup"><span data-stu-id="26e07-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="26e07-167">**Slett**: Åpner en dialogboks for å bekrefte slettingen av den valgte aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="26e07-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="26e07-168">Du kan også slette mer enn én aktivitet samtidig ved å velge aktivitetene og deretter velge sletteikonet.</span><span class="sxs-lookup"><span data-stu-id="26e07-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="26e07-169">Velg **Slett** for å bekrefte slettingen.</span><span class="sxs-lookup"><span data-stu-id="26e07-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
