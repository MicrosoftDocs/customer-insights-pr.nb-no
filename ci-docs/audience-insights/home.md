---
title: Startside i målgruppeinnsikt
description: Kom i gang med å utforske appen på startsiden.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597247"
---
# <a name="create-a-new-environment"></a><span data-ttu-id="124cd-103">Opprett et nytt miljø</span><span class="sxs-lookup"><span data-stu-id="124cd-103">Create a new environment</span></span>

## <a name="create-a-trial-environment"></a><span data-ttu-id="124cd-104">Opprette et prøvemiljø</span><span class="sxs-lookup"><span data-stu-id="124cd-104">Create a trial environment</span></span>

<span data-ttu-id="124cd-105">Du kan registrere deg for en prøveversjon på [registreringssiden for prøveversjon](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span><span class="sxs-lookup"><span data-stu-id="124cd-105">You can sign up for a trial on the [trial sign up page](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span></span> 

> [!NOTE]
> <span data-ttu-id="124cd-106">Prøveversjoner utløper etter 30 dager.</span><span class="sxs-lookup"><span data-stu-id="124cd-106">Trials expire after 30 days.</span></span>

1. <span data-ttu-id="124cd-107">Velg alternativet for **Registrer deg for en gratis prøveversjon**, og velg **Registrer deg nå**.</span><span class="sxs-lookup"><span data-stu-id="124cd-107">Choose the **Sign up for a free trial** option and select **Sign up now**.</span></span>

1. <span data-ttu-id="124cd-108">Oppgi e-postadresse for jobb eller skole, og fortell oss mer om deg selv, og velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="124cd-108">Provide your work or school email address, tell us a more about yourself and select **Next**.</span></span>

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogen for å registrere deg for en prøveversjonsforekomst":::

1. <span data-ttu-id="124cd-110">Angi et **Navn** på det nye miljøet.</span><span class="sxs-lookup"><span data-stu-id="124cd-110">Provide a **Name** for your new environment.</span></span> 

1. <span data-ttu-id="124cd-111">Velg prøveversjonstype.</span><span class="sxs-lookup"><span data-stu-id="124cd-111">Select the trial type.</span></span>

1. <span data-ttu-id="124cd-112">Velg **Område** for miljøet ditt.</span><span class="sxs-lookup"><span data-stu-id="124cd-112">Choose the **Region** for your environment.</span></span>

1. <span data-ttu-id="124cd-113">Eksempel: For administratorer av en Dynamics 365-organisasjon: Velg **Avanserte innstillinger**, og angi URL-adressen til organisasjonen for å bruke prediksjonsfunksjoner som kundefrafall.</span><span class="sxs-lookup"><span data-stu-id="124cd-113">Optionally, for admins of a Dynamics 365 organization: Select **Advanced settings** and provide the URL of your organization to use prediction features like customer churn.</span></span>

1. <span data-ttu-id="124cd-114">Velg **Opprett**.</span><span class="sxs-lookup"><span data-stu-id="124cd-114">Select **Create**.</span></span> 

<span data-ttu-id="124cd-115">Når miljøet er opprettet, vil du se **Demo**-miljøet, som gjør det mulig å utforske appen med fiktive data.</span><span class="sxs-lookup"><span data-stu-id="124cd-115">After the environment was created, you'll see the **Demo** environment which lets you explore the app with fictitious data.</span></span> <span data-ttu-id="124cd-116">Du kan endre eksempeldataene, slik at de samsvarer med bransjen.</span><span class="sxs-lookup"><span data-stu-id="124cd-116">You can change the sample data to match your industry.</span></span> <span data-ttu-id="124cd-117">Velg **Innstillinger**-ikonet i hodet, og velg **Demoinnstillinger**.</span><span class="sxs-lookup"><span data-stu-id="124cd-117">Select the **Settings** icon in the header and select **Demo settings**.</span></span> <span data-ttu-id="124cd-118">Du kan også endre det visuelle temaet.</span><span class="sxs-lookup"><span data-stu-id="124cd-118">Additionally, you can change the visual theme.</span></span> 

<span data-ttu-id="124cd-119">Du [bytter til miljøet ](#switch-environments) du opprettet under registreringsprosessen, slik at du kan arbeide med dine egne data.</span><span class="sxs-lookup"><span data-stu-id="124cd-119">You [switch to the environment](#switch-environments) you created during the sign-up process to work with your own data.</span></span>

## <a name="create-a-new-production-or-sandbox-environment"></a><span data-ttu-id="124cd-120">Opprette et nytt produksjons- eller sandkassemiljø</span><span class="sxs-lookup"><span data-stu-id="124cd-120">Create a new production or sandbox environment</span></span>

<span data-ttu-id="124cd-121">I miljøet velger du **Miljøer**-velgeren i apphodet i miljøet, og velg **Ny**.</span><span class="sxs-lookup"><span data-stu-id="124cd-121">In your environment, select the **Environments** picker in the app header and select **New**.</span></span>

<span data-ttu-id="124cd-122">Følg fremgangsmåten som om du [oppretter et prøvemiljø](#create-a-trial-environment).</span><span class="sxs-lookup"><span data-stu-id="124cd-122">Follow the steps as if you [create a trial environment](#create-a-trial-environment).</span></span> <span data-ttu-id="124cd-123">Som standard lagres data i den Customer Insights-styrte datasjøen.</span><span class="sxs-lookup"><span data-stu-id="124cd-123">By default, data is stored in the Customer Insights managed data lake.</span></span> <span data-ttu-id="124cd-124">Du får et tilleggsalternativ når du velger **Avanserte innstillinger**, for lagring av data i din egen Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="124cd-124">You get an additional option when selecting **Advanced settings** to store your data in your own Azure Data Lake.</span></span> <span data-ttu-id="124cd-125">Angi kontonavn og kontonøkkel for å opprette en tilkobling til Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="124cd-125">Provide your account name and account key to establish a connection to your Azure Data Lake.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="124cd-126">Når du lagrer data i Azure Data Lake Storage, godtar du at dataene overføres til og lagres i den riktige geografiske plasseringen for denne Azure Storage-kontoen, som kan variere fra der dataene lagres i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="124cd-126">By saving data to your Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="124cd-127">Finn ut mer om Microsofts klareringssenter.</span><span class="sxs-lookup"><span data-stu-id="124cd-127">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a><span data-ttu-id="124cd-128">Utforske startsiden</span><span class="sxs-lookup"><span data-stu-id="124cd-128">Explore the home page</span></span>

<span data-ttu-id="124cd-129">Du kan [få målgruppeinnsikt fra Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) på følgende nettadresse: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="124cd-129">You can [access audience insights from Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) on the following URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span></span>
<span data-ttu-id="124cd-130">**Startsiden** viser en oversikt over segmenter, målinger og suppleringsdata (hvis konfigurert) etter fullføring av fasene [tilordningen](map-entities.md), [samsvare](match-entities.md) og [slå sammen](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="124cd-130">The **Home** page shows an overview of segments, measures, and enrichment data (if configured)after completing the [map](map-entities.md), [match](match-entities.md), and [merge](merge-entities.md) phases.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="124cd-131">![Innsikter på startside](media/home-page-insights.png "Innsikter på startside")</span><span class="sxs-lookup"><span data-stu-id="124cd-131">![Insights on Home page](media/home-page-insights.png "Insights on Home page")</span></span>

<span data-ttu-id="124cd-132">Under **Nylige segmenter** ser du grupper av kunder basert på demografiske, atferdsstyrte eller overførbare attributter som du har definert.</span><span class="sxs-lookup"><span data-stu-id="124cd-132">Under **Recent segments**, you see groups of customers based on demographic, behavioral, or transactional attributes that you've defined.</span></span> <span data-ttu-id="124cd-133">[Oppretting av segementer](segments.md) hjelper deg med å gruppere kundebasen din og målrette forretningsaktivitetene dine bedre.</span><span class="sxs-lookup"><span data-stu-id="124cd-133">[Creating segments](segments.md) helps you to group your customer base and better target your business activities.</span></span>

<span data-ttu-id="124cd-134">**Nylige mål** viser fliser med [viktige ytelsesindikatorer (KPI-er)](measures.md) du har definert.</span><span class="sxs-lookup"><span data-stu-id="124cd-134">**Recent measures** show tiles with [key performance indicators (KPIs)](measures.md) that you've defined.</span></span> <span data-ttu-id="124cd-135">Det kan for eksempel være gjennomsnittlig sannsynlighet for at en kunde frafaller, eller gjennomsnittlig Internett-bruk per kunde.</span><span class="sxs-lookup"><span data-stu-id="124cd-135">For example, average likelihood of a customer to churn or the average online spend per customer.</span></span>

<span data-ttu-id="124cd-136">Delen **Siste suppleringer** viser resultatene av de suppleringskjøringene som nylig ble utført.</span><span class="sxs-lookup"><span data-stu-id="124cd-136">The **Recent enrichments** section lists the results of the enrichment runs that completed recently.</span></span> <span data-ttu-id="124cd-137">[Suppleringer](enrichment-hub.md) legger til informasjon om kundebasen.</span><span class="sxs-lookup"><span data-stu-id="124cd-137">[Enrichments](enrichment-hub.md) add information about your customer base.</span></span> <span data-ttu-id="124cd-138">Hvis du for eksempel forstår interessene og merker de har affinitet for.</span><span class="sxs-lookup"><span data-stu-id="124cd-138">For example, by understanding the interests and brands that they have affinity for.</span></span>

## <a name="switch-environments"></a><span data-ttu-id="124cd-139">Bytt miljøer</span><span class="sxs-lookup"><span data-stu-id="124cd-139">Switch environments</span></span>

<span data-ttu-id="124cd-140">Velg kontrollen **Miljø** øverst i høyre hjørne på siden for å endre miljøer.</span><span class="sxs-lookup"><span data-stu-id="124cd-140">Select the **Environment** control in the upper-right corner of the page to change environments.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="124cd-141">![Bytt miljø](media/home-page-environment-switcher.png "Bytt miljø")</span><span class="sxs-lookup"><span data-stu-id="124cd-141">![Switch environment](media/home-page-environment-switcher.png "Switch environment")</span></span>

<span data-ttu-id="124cd-142">Administratorer kan opprette og administrere [flere miljøer](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="124cd-142">Administrators can create and manage [multiple environments](manage-environments.md).</span></span> <span data-ttu-id="124cd-143">Det kan være nyttig å vedlikeholde mer enn ett miljø hvis organisasjonen for eksempel opererer internasjonalt og du må skille data og innsikt på forskjellige måter.</span><span class="sxs-lookup"><span data-stu-id="124cd-143">Maintaining more than one environment may be useful if, for example, your organization operates internationally and you need to segregate data and insights in different ways.</span></span>

## <a name="next-step"></a><span data-ttu-id="124cd-144">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="124cd-144">Next step</span></span>

<span data-ttu-id="124cd-145">Hvis du vil se din egen innsikt på startsiden, må du først [legge til datakilder](data-sources.md) og [samle](data-unification.md) dataene for å bygge kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="124cd-145">To see your own insights on the home page, you'll first need to [add data sources](data-sources.md) and [unify](data-unification.md) your data to build customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]