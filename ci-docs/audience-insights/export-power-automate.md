---
title: Power Automate-kobling | Microsoft Docs
description: Opprett flyter i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597937"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="2edff-103">Power Automate-kobling (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="2edff-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="2edff-104">Utløs bestemte hendelser som skal skje automatisk når dataene endres og administrer mer komplekse flyter direkte i [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="2edff-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="2edff-105">Power Automate-utløsere</span><span class="sxs-lookup"><span data-stu-id="2edff-105">Power Automate triggers</span></span>

<span data-ttu-id="2edff-106">Bruk utløsere til å opprette skyflyter og automatisere repeterende oppgaver, for eksempel varsler eller mer avanserte handlinger.</span><span class="sxs-lookup"><span data-stu-id="2edff-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="2edff-107">Utløs når en oppdatering av datakilde mislykkes.</span><span class="sxs-lookup"><span data-stu-id="2edff-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="2edff-108">Utløs når en oppdatering av datakilde er vellykket.</span><span class="sxs-lookup"><span data-stu-id="2edff-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="2edff-109">Utløs når en terskel blir overskredet i et segment.</span><span class="sxs-lookup"><span data-stu-id="2edff-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="2edff-110">Utløseren er begrenset til overgang over grensen.</span><span class="sxs-lookup"><span data-stu-id="2edff-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="2edff-111">Utløs når en terskel blir overskredet i et forretningsmål.</span><span class="sxs-lookup"><span data-stu-id="2edff-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="2edff-112">Utløseren er begrenset til overgang over grensen.</span><span class="sxs-lookup"><span data-stu-id="2edff-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="2edff-113">Utløses når en full oppdatering av (datakilder, segmenter, mål ...) er fullført.</span><span class="sxs-lookup"><span data-stu-id="2edff-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="2edff-114">Utløs når en oppdatering av samlingsprosessen (tilordning, samsvar, sammenslåing) er fullført.</span><span class="sxs-lookup"><span data-stu-id="2edff-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="2edff-115">[Konfigurere utløsere i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="2edff-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="2edff-116">Power Automate-handlinger</span><span class="sxs-lookup"><span data-stu-id="2edff-116">Power Automate actions</span></span>
<span data-ttu-id="2edff-117">Power Automate-koblingen gir andre handlinger enn de tilgjengelige utløserne.</span><span class="sxs-lookup"><span data-stu-id="2edff-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="2edff-118">Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="2edff-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="2edff-119">Opprett en Power Automate-flyt</span><span class="sxs-lookup"><span data-stu-id="2edff-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="2edff-120">I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="2edff-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2edff-121">Velg **Konfigurer** på **Power Automate**-flisen.</span><span class="sxs-lookup"><span data-stu-id="2edff-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="2edff-122">Customer Insights-koblingen (forhåndsversjon) i Power Automate åpnes.</span><span class="sxs-lookup"><span data-stu-id="2edff-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="2edff-123">**Logg på** Power Automate.</span><span class="sxs-lookup"><span data-stu-id="2edff-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="2edff-124">Velg en av de tilgjengelige utløserne, og legg til flere trinn i den nye flyten.</span><span class="sxs-lookup"><span data-stu-id="2edff-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="2edff-125">Hvis du vil ha mer informasjon, kan du se [Opprett en skyflyt i Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="2edff-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="2edff-126">Eksempler på hvordan du bruker flyter:</span><span class="sxs-lookup"><span data-stu-id="2edff-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="2edff-127">Publiser en melding på en Microsoft Teams-kanal hvis en datakildeoppdatering mislykkes.</span><span class="sxs-lookup"><span data-stu-id="2edff-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="2edff-128">Send en e-postmelding til dataeierne når en grense for et segment krysses.</span><span class="sxs-lookup"><span data-stu-id="2edff-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]