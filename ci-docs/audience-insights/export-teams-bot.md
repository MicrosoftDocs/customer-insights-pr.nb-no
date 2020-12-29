---
title: Robot for Microsoft Teams
description: Slå opp enhetlige kundeprofiler i Microsoft Teams ved hjelp av en robot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406524"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="7df61-103">Teams-robot for Dynamics 365 Customer Insights (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="7df61-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="7df61-104">Koble til Microsoft Teams for å la en robot slå opp enhetlige kundeprofiler i Teams-kanaler.</span><span class="sxs-lookup"><span data-stu-id="7df61-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7df61-105">![Teams-robot som viser en kundeoppføring](media/teams-bot.png "Teams-robot som viser en kundeoppføring")</span><span class="sxs-lookup"><span data-stu-id="7df61-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7df61-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="7df61-106">Prerequisites</span></span>

<span data-ttu-id="7df61-107">Når du skal konfigurere roboten, må følgende forhåndskrav være oppfylt:</span><span class="sxs-lookup"><span data-stu-id="7df61-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7df61-108">Det er minst én [datakilde lagt til](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="7df61-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="7df61-109">[Samlingsprosessen](data-unification.md) er fullført.</span><span class="sxs-lookup"><span data-stu-id="7df61-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="7df61-110">Felt er lagt til i [søke- og filterindeksen](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="7df61-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="7df61-111">Customer Insights og Teams er i samme organisasjon.</span><span class="sxs-lookup"><span data-stu-id="7df61-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="7df61-112">Konfigurere roboten</span><span class="sxs-lookup"><span data-stu-id="7df61-112">Configure the bot</span></span>

1. <span data-ttu-id="7df61-113">I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="7df61-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="7df61-114">Velg **Konfigurer** på Microsoft Teams-flisen.</span><span class="sxs-lookup"><span data-stu-id="7df61-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="7df61-115">Du blir omdirigert til **Apper**-området i Teams.</span><span class="sxs-lookup"><span data-stu-id="7df61-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="7df61-116">Du kan også åpne Teams og velge **Apper** nederst i venstre hjørne eller [hente det fra AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) direkte.</span><span class="sxs-lookup"><span data-stu-id="7df61-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="7df61-117">Søk etter **Customer Insights** og velg appen.</span><span class="sxs-lookup"><span data-stu-id="7df61-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="7df61-118">Velg **Legg til**.</span><span class="sxs-lookup"><span data-stu-id="7df61-118">Select **Add**.</span></span>
1. <span data-ttu-id="7df61-119">Etter at du har logget på Customer Insights i Teams, vil du se en velkomstmelding og kan komme i gang.</span><span class="sxs-lookup"><span data-stu-id="7df61-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="7df61-120">Ting du kan gjøre med roboten</span><span class="sxs-lookup"><span data-stu-id="7df61-120">Things you can do with the bot</span></span>

<span data-ttu-id="7df61-121">Roboten har oppslagsfunksjoner for enhetlige kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="7df61-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="7df61-122">Skriv inn **søk** etterfulgt av et navn, en e-postadresse eller et annet felt i den enhetlige kundeprofilen som legges til i søke- og filterindeksen.</span><span class="sxs-lookup"><span data-stu-id="7df61-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="7df61-123">Du får et kort med opptil 15 felt fra den resulterende kundeprofilen.</span><span class="sxs-lookup"><span data-stu-id="7df61-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="7df61-124">Flere treff returnerer en liste over resultater der du kan velge en profil.</span><span class="sxs-lookup"><span data-stu-id="7df61-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="7df61-125">Du kan legge til søkeord i doble anførselstegn for å finne et nøyaktig treff.</span><span class="sxs-lookup"><span data-stu-id="7df61-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="7df61-126">Hvis organisasjonen din vedlikeholder flere Customer Insights-miljøer i den samme organisasjonen, kan du angi **switchinstance** for å velge hvilket miljø du vil koble den til.</span><span class="sxs-lookup"><span data-stu-id="7df61-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="7df61-127">Angi **hjelp** for å vise en liste over tilgjengelige kommandoer for roboten.</span><span class="sxs-lookup"><span data-stu-id="7df61-127">Enter **help** to see a list of available commands for the bot.</span></span>  
