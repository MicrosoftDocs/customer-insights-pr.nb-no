---
title: Datainntak i sanntid og begrensninger
description: Generell informasjon om sanntidsfunksjoner i målgruppeinnsikt.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270292"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="8e675-103">Datainntak i sanntid (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="8e675-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="8e675-104">Ved hjelp av den nær sanntidsfunksjonaliteten kan du se, i løpet av sekunder, de nyeste samhandlingene som kundene har gjort med dine produkter eller tjenester.</span><span class="sxs-lookup"><span data-stu-id="8e675-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="8e675-105">[Planlagte oppdateringer](system.md#schedule-tab) omfatter et stort antall oppføringer og flere komplekse operasjoner.</span><span class="sxs-lookup"><span data-stu-id="8e675-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="8e675-106">Først hentes data inn fra datakilden.</span><span class="sxs-lookup"><span data-stu-id="8e675-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="8e675-107">Deretter samles dataene og suppleres med tilleggsinformasjon.</span><span class="sxs-lookup"><span data-stu-id="8e675-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="8e675-108">Hver utførelse av denne prosessen kan ta minutter til timer.</span><span class="sxs-lookup"><span data-stu-id="8e675-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="8e675-109">Sanntidsfunksjonaliteten gir data øyeblikkelig for forbruk, helt til den påfølgende planlagte oppdateringen henter disse dataene fra datakilden.</span><span class="sxs-lookup"><span data-stu-id="8e675-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="8e675-110">Oppdateringer i sanntid har en utløpstid da de ikke lenger overstyrer verdien fra datakilden:</span><span class="sxs-lookup"><span data-stu-id="8e675-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="8e675-111">Profiloppdateringer vil beholdes i 4 timer</span><span class="sxs-lookup"><span data-stu-id="8e675-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="8e675-112">Det beholdes aktiviteter i 30 dager</span><span class="sxs-lookup"><span data-stu-id="8e675-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="8e675-113">Disse verdiene er API-kallparametere som du kan endre.</span><span class="sxs-lookup"><span data-stu-id="8e675-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="8e675-114">De skal sikre at kildedataene forblir sannhetskilden.</span><span class="sxs-lookup"><span data-stu-id="8e675-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="8e675-115">Hvis du vil at sanntidsoppdateringer skal være inkludert lengre, må du legge dem til i en datakilde slik at de blir hentet under den neste planlagte oppdateringen.</span><span class="sxs-lookup"><span data-stu-id="8e675-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="8e675-116">Sanntidsoppdatering av de enhetlige kundeprofilfeltene</span><span class="sxs-lookup"><span data-stu-id="8e675-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="8e675-117">Oppdaterte profiler vises i kundekortvisningen, eller en hvilken som helst annen visualisering, i løpet av noen få sekunder.</span><span class="sxs-lookup"><span data-stu-id="8e675-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="8e675-118">Siden sanntidsoperasjoner foregår etter at datasamlingen har skjedd, gjelder de bare for de enhetlige kundeprofilene.</span><span class="sxs-lookup"><span data-stu-id="8e675-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="8e675-119">Derfor oppdaterer ikke sanntidsprofilendringer mål, segmentmedlemskap eller suppleringer.</span><span class="sxs-lookup"><span data-stu-id="8e675-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="8e675-120">Begrensninger</span><span class="sxs-lookup"><span data-stu-id="8e675-120">Limitations</span></span>

- <span data-ttu-id="8e675-121">Kundeprofiler kan oppdateres, men ikke opprettes eller slettes.</span><span class="sxs-lookup"><span data-stu-id="8e675-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="8e675-122">Det er ikke mulig å eksportere sanntidsoppdateringer til eksterne systemer, for eksempel Power BI.</span><span class="sxs-lookup"><span data-stu-id="8e675-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="8e675-123">Sanntidsopprettelse av aktiviteter</span><span class="sxs-lookup"><span data-stu-id="8e675-123">Real-time creation of activities</span></span>

<span data-ttu-id="8e675-124">I sanntids-API-en kan du publisere en ny aktivitet fra kildesystemet (en individuell kildeoppføring) til en enhetlig kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="8e675-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="8e675-125">Den nye aktiviteten blir tilgjengelig som en ensartet aktivitet i den enhetlige kundeprofilens tidslinje i løpet av sekunder.</span><span class="sxs-lookup"><span data-stu-id="8e675-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="8e675-126">Du kan se tidslinjen i kundekortvisningen eller en annen tidslinjeintegrering du har konfigurert.</span><span class="sxs-lookup"><span data-stu-id="8e675-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="8e675-127">Aktivitetene er uforanderlige.</span><span class="sxs-lookup"><span data-stu-id="8e675-127">Activities are immutable.</span></span> <span data-ttu-id="8e675-128">De blir ikke endret etter at de er opprettet.</span><span class="sxs-lookup"><span data-stu-id="8e675-128">They don't change once created.</span></span>
> - <span data-ttu-id="8e675-129">For øyeblikket oppdateres ikke segmenter og mål basert på den nye aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="8e675-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="8e675-130">Aktiviteter som er lagt til bare via API-en i sanntid, er ikke en del av eksporter og vises ikke i PowerBI.</span><span class="sxs-lookup"><span data-stu-id="8e675-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="8e675-131">Du kan koble deg til sanntids-API-en på to måter:</span><span class="sxs-lookup"><span data-stu-id="8e675-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="8e675-132">[indirekte](#connect-via-the-dynamics-365-customer-insights-connector) ved hjelp av [Dynamics 365 Customer Insights-koblingen](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="8e675-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="8e675-133">[direkte](#connect-directly-to-the-real-time-api), med kode</span><span class="sxs-lookup"><span data-stu-id="8e675-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="8e675-134">Følgende forutsetninger gjelder for begge:</span><span class="sxs-lookup"><span data-stu-id="8e675-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="8e675-135">Et Customer Insights-miljø</span><span class="sxs-lookup"><span data-stu-id="8e675-135">A Customer Insights environment</span></span>
- <span data-ttu-id="8e675-136">Enhetlige kundeprofiler</span><span class="sxs-lookup"><span data-stu-id="8e675-136">Unified customer profiles</span></span>
- <span data-ttu-id="8e675-137">Aktiviteter konfigurert og kjørt</span><span class="sxs-lookup"><span data-stu-id="8e675-137">Activities configured and run</span></span>
- <span data-ttu-id="8e675-138">Bidragsyter eller administratortillatelser til å godkjenne kontoen</span><span class="sxs-lookup"><span data-stu-id="8e675-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="8e675-139">Koble til via Dynamics 365 Customer Insights-koblingen</span><span class="sxs-lookup"><span data-stu-id="8e675-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="8e675-140">Sanntids-API-en kan inkludere data fra en dedikert Power Platform-kobling, [Dynamics 365 Customer Insights-koblingen](https://docs.microsoft.com/connectors/customerinsights/), uten å måtte skrive og distribuere kode.</span><span class="sxs-lookup"><span data-stu-id="8e675-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="8e675-141">Koblingen kan utføre samme sanntidshandlinger som API-en.</span><span class="sxs-lookup"><span data-stu-id="8e675-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="8e675-142">Du trenger en gyldig lisens for Premium-koblinger.</span><span class="sxs-lookup"><span data-stu-id="8e675-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="8e675-143">Hvis du vil ha mer informasjon, kan du se [Vanlige spørsmål om om lisensiering for Power Apps og Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="8e675-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="8e675-144">Power Platform [Power Apps og/eller Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="8e675-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="8e675-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="8e675-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="8e675-146">Hvis du vil ha informasjon om hvordan du oppretter flyter, kan du se i [Power Automate-dokumentasjonen](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="8e675-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="8e675-147">Koble direkte til API i sanntid</span><span class="sxs-lookup"><span data-stu-id="8e675-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="8e675-148">Du kan bruke sanntidsfunksjonene ved å bygge din egen pipeline og direkte koble direkte til sanntids-API-en.</span><span class="sxs-lookup"><span data-stu-id="8e675-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="8e675-149">Du kan legge inn en aktivitet i formatet til kildesystemet eller i UnifiedActivity-formatet.</span><span class="sxs-lookup"><span data-stu-id="8e675-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="8e675-150">Få formatet ved å gjøre et API-kall til /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="8e675-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="8e675-151">Detaljer om denne API-en, inkludert parametere og svar, finner du i **EntityData**-delen i [Referanse for API-er i Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="8e675-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="8e675-152">Hvis du vil ha mer informasjon, kan du se [Arbeide med API-er i Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="8e675-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="8e675-153">Forstå sanntidsbruk med telemetri</span><span class="sxs-lookup"><span data-stu-id="8e675-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="8e675-154">Få en oversikt over volumet av forespørsler til sanntids-API-en og informasjon om problemer som systemet kan støte på.</span><span class="sxs-lookup"><span data-stu-id="8e675-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="8e675-155">Du får [tilgang til telemetrien i sanntid](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="8e675-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]