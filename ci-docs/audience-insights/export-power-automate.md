---
title: Power Automate-kobling | Microsoft Docs
description: Opprett flyter i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406491"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="31c40-103">Power Automate-kobling (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="31c40-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="31c40-104">Utløs bestemte hendelser som skal skje automatisk når dataene endres og administrer mer komplekse flyter direkte i [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="31c40-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="31c40-105">Power Automate-utløsere</span><span class="sxs-lookup"><span data-stu-id="31c40-105">Power Automate triggers</span></span>

<span data-ttu-id="31c40-106">Du kan bruke en rekke utløsere som gjør det mulig for deg å opprette flyter for å automatisere repeterende oppgaver, for eksempel varslinger eller mer avanserte handlinger.</span><span class="sxs-lookup"><span data-stu-id="31c40-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="31c40-107">Utløs når en oppdatering av datakilde mislykkes.</span><span class="sxs-lookup"><span data-stu-id="31c40-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="31c40-108">Utløs når en oppdatering av datakilde er vellykket.</span><span class="sxs-lookup"><span data-stu-id="31c40-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="31c40-109">Utløs når en terskel blir overskredet i et segment.</span><span class="sxs-lookup"><span data-stu-id="31c40-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="31c40-110">Utløseren er begrenset til overgang over grensen.</span><span class="sxs-lookup"><span data-stu-id="31c40-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="31c40-111">Utløs når en terskel blir overskredet i et forretningsmål.</span><span class="sxs-lookup"><span data-stu-id="31c40-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="31c40-112">Utløseren er begrenset til overgang over grensen.</span><span class="sxs-lookup"><span data-stu-id="31c40-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="31c40-113">Utløses når en full oppdatering av (datakilder, segmenter, mål ...) er fullført.</span><span class="sxs-lookup"><span data-stu-id="31c40-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="31c40-114">Utløs når en oppdatering av samlingsprosessen (tilordning, samsvar, sammenslåing) er fullført.</span><span class="sxs-lookup"><span data-stu-id="31c40-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="31c40-115">[Konfigurere utløsere i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="31c40-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="31c40-116">Power Automate-handlinger</span><span class="sxs-lookup"><span data-stu-id="31c40-116">Power Automate actions</span></span>
<span data-ttu-id="31c40-117">Power Automate-koblingen gir andre handlinger enn de tilgjengelige utløserne.</span><span class="sxs-lookup"><span data-stu-id="31c40-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="31c40-118">Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="31c40-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="31c40-119">Opprette en Power Automate-flyt i målgruppeinnsikt</span><span class="sxs-lookup"><span data-stu-id="31c40-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="31c40-120">I Målgruppeinnsikt går du til **Administrasjon** > **System**.</span><span class="sxs-lookup"><span data-stu-id="31c40-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="31c40-121">På **System**-siden velger du kategorien **Status**.</span><span class="sxs-lookup"><span data-stu-id="31c40-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="31c40-122">I **Datakilder**-delen velger du **Flyter** og deretter **Opprett en flyt** fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="31c40-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="31c40-123">![Power Automate-koblingen som viser Opprett en flyt-handlingen](media/power-automate-connector-create-flow.png "Power Automate-koblingen viser Opprett en flyt-handling")</span><span class="sxs-lookup"><span data-stu-id="31c40-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="31c40-124">I Power Automate velger du en av de tilgjengelige utløserne for å opprette den foretrukne flyten.</span><span class="sxs-lookup"><span data-stu-id="31c40-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="31c40-125">Hvis du oppretter din første flyt, må du først godkjenne med Power Automate-koblingen.</span><span class="sxs-lookup"><span data-stu-id="31c40-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
