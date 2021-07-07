---
title: Power Automate-kobling | Microsoft Docs
description: Opprett flyter i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305076"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="8a20d-103">Power Automate-kobling (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="8a20d-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="8a20d-104">Utløs bestemte hendelser som skal skje automatisk når dataene endres og administrer mer komplekse flyter direkte i [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="8a20d-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="8a20d-105">Power Automate-utløsere</span><span class="sxs-lookup"><span data-stu-id="8a20d-105">Power Automate triggers</span></span>

<span data-ttu-id="8a20d-106">Bruk utløsere til å opprette skyflyter og automatisere repeterende oppgaver, for eksempel varsler eller mer avanserte handlinger.</span><span class="sxs-lookup"><span data-stu-id="8a20d-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="8a20d-107">Utløs når en oppdatering av datakilde mislykkes.</span><span class="sxs-lookup"><span data-stu-id="8a20d-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="8a20d-108">Utløs når en oppdatering av datakilde er vellykket.</span><span class="sxs-lookup"><span data-stu-id="8a20d-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="8a20d-109">Utløs når en terskel blir overskredet i et segment.</span><span class="sxs-lookup"><span data-stu-id="8a20d-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="8a20d-110">Utløseren er begrenset til overgang over grensen.</span><span class="sxs-lookup"><span data-stu-id="8a20d-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="8a20d-111">Utløs når en terskel blir overskredet i et forretningsmål.</span><span class="sxs-lookup"><span data-stu-id="8a20d-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="8a20d-112">Bare forretningsmål uten en dimensjon støttes.</span><span class="sxs-lookup"><span data-stu-id="8a20d-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="8a20d-113">Utløseren er begrenset til overgang over grensen.</span><span class="sxs-lookup"><span data-stu-id="8a20d-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="8a20d-114">Utløses når en full oppdatering av (datakilder, segmenter, mål ...) er fullført.</span><span class="sxs-lookup"><span data-stu-id="8a20d-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="8a20d-115">Utløs når en oppdatering av samlingsprosessen (tilordning, samsvar, sammenslåing) er fullført.</span><span class="sxs-lookup"><span data-stu-id="8a20d-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="8a20d-116">Konfigurere utløsere i Power Automate.</span><span class="sxs-lookup"><span data-stu-id="8a20d-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="8a20d-117">Power Automate-handlinger</span><span class="sxs-lookup"><span data-stu-id="8a20d-117">Power Automate actions</span></span>

<span data-ttu-id="8a20d-118">Power Automate-koblingen gir andre handlinger enn de tilgjengelige utløserne.</span><span class="sxs-lookup"><span data-stu-id="8a20d-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="8a20d-119">Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="8a20d-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="8a20d-120">Opprett en Power Automate-flyt</span><span class="sxs-lookup"><span data-stu-id="8a20d-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="8a20d-121">I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="8a20d-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8a20d-122">Velg **Konfigurer** på **Power Automate**-flisen.</span><span class="sxs-lookup"><span data-stu-id="8a20d-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="8a20d-123">Customer Insights-koblingen (forhåndsversjon) i Power Automate åpnes.</span><span class="sxs-lookup"><span data-stu-id="8a20d-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="8a20d-124">**Logg på** Power Automate.</span><span class="sxs-lookup"><span data-stu-id="8a20d-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="8a20d-125">Velg en av de tilgjengelige utløserne, og legg til flere trinn i den nye flyten.</span><span class="sxs-lookup"><span data-stu-id="8a20d-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="8a20d-126">Hvis du vil ha mer informasjon, kan du se [Opprett en skyflyt i Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="8a20d-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="8a20d-127">Eksempler på hvordan du bruker flyter:</span><span class="sxs-lookup"><span data-stu-id="8a20d-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="8a20d-128">Publiser en melding på en Microsoft Teams-kanal hvis en datakildeoppdatering mislykkes.</span><span class="sxs-lookup"><span data-stu-id="8a20d-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="8a20d-129">Send en e-postmelding til dataeierne når en grense for et segment krysses.</span><span class="sxs-lookup"><span data-stu-id="8a20d-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
