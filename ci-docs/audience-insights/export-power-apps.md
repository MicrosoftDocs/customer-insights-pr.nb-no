---
title: Power Apps-kobling
description: Koble til med Power Apps og Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598167"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="4f048-103">Microsoft Power Apps-kobling (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="4f048-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="4f048-104">Samle inn enhetlige kundeprofiler i de tilpassede appene med Power Apps.</span><span class="sxs-lookup"><span data-stu-id="4f048-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="4f048-105">Koble sammen Power Apps og Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4f048-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="4f048-106">Customer Insights er én av mange [tilgjengelige kilder for data i Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="4f048-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="4f048-107">Se i Power Apps-dokumentasjonen for å lære hvordan du [legger til en datatilkobling til en app](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="4f048-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="4f048-108">Vi anbefaler at du også ser gjennom [hvordan Power Apps bruker delegering til å håndtere store datasett i lerretsapper](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="4f048-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="4f048-109">Tilgjengelige enheter</span><span class="sxs-lookup"><span data-stu-id="4f048-109">Available entities</span></span>

<span data-ttu-id="4f048-110">Etter at du har lagt til Customer Insights som en datatilkobling, kan du velge følgende enheter i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="4f048-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="4f048-111">Kunde: for å bruke data fra den [enhetlige kundeprofilen](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4f048-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="4f048-112">UnifiedActivity: for å vise den [enhetlige tidslinjen](activities.md) på appen.</span><span class="sxs-lookup"><span data-stu-id="4f048-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="4f048-113">Begrensninger</span><span class="sxs-lookup"><span data-stu-id="4f048-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="4f048-114">Enheter som kan hentes</span><span class="sxs-lookup"><span data-stu-id="4f048-114">Retrievable entities</span></span>

<span data-ttu-id="4f048-115">Du kan bare hente enhetene **Kunde**, **UnifiedActivity** og **Segmenter** via Power Apps-koblingen.</span><span class="sxs-lookup"><span data-stu-id="4f048-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="4f048-116">Andre enheter vises fordi den underliggende koblingen støtter dem gjennom utløsere i Power Automate.</span><span class="sxs-lookup"><span data-stu-id="4f048-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="4f048-117">Delegering</span><span class="sxs-lookup"><span data-stu-id="4f048-117">Delegation</span></span>

<span data-ttu-id="4f048-118">Delegering fungerer for kundeenhet og UnifiedActivity-enhet.</span><span class="sxs-lookup"><span data-stu-id="4f048-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="4f048-119">Delegering for **Kunde**-enhet: Hvis du vil bruke delegering for enheten, må feltene indekseres i [Søk- og filterindeks](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="4f048-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="4f048-120">Delegering for **UnifiedActivity**: Delegering for denne enheten fungerer bare for feltene **ActivityId** og **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="4f048-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="4f048-121">Hvis du vil ha mer informasjon om delegering, se [Power Apps-funksjoner og operasjoner som kan delegeres](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="4f048-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="4f048-122">Eksempel på Galleri-kontroll</span><span class="sxs-lookup"><span data-stu-id="4f048-122">Example gallery control</span></span>

<span data-ttu-id="4f048-123">Du legger for eksempel til kundeprofiler i en [gallerikontroll](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="4f048-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="4f048-124">Legg til en **Galleri**-kontroll i en app du skal bygge.</span><span class="sxs-lookup"><span data-stu-id="4f048-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f048-125">![Legge til et gallerielement](media/connector-powerapps9.png "Legge til et gallerielement")</span><span class="sxs-lookup"><span data-stu-id="4f048-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="4f048-126">Velg **Kunde** som datakilde for varer.</span><span class="sxs-lookup"><span data-stu-id="4f048-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4f048-127">![Velg en datakilde](media/choose-datasource-powerapps.png "Velg en datakilde")</span><span class="sxs-lookup"><span data-stu-id="4f048-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="4f048-128">Du kan endre datapanelet til høyre for å velge hvilket felt kundeenheten skal vise i galleriet.</span><span class="sxs-lookup"><span data-stu-id="4f048-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="4f048-129">Hvis du vil vise et felt fra den valgte kunden i galleriet, fyller du ut tekstegenskapen for en etikett:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="4f048-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="4f048-130">Eksempel: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="4f048-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="4f048-131">Hvis du vil vise den enhetlige tidslinjen for en kunde, legger du til et gallerielement og legger til elementegenskapen: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="4f048-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="4f048-132">Eksempel: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="4f048-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]