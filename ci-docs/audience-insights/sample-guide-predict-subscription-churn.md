---
title: Eksempelveiledning for prognose på abonnementsfrafall
description: Bruk denne eksempelveiledningen til å prøve ut den medfølgende prediksjonsmodellen for abonnementsfrafall.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269849"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="4b7ad-103">Eksempelveiledning for prognose på abonnementsfrafall (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="4b7ad-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="4b7ad-104">Vi tar deg gjennom et helhetlig eksempel på prediksjon av abonnementsfrafall ved å bruke eksempeldataene som vises nedenfor.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="4b7ad-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="4b7ad-105">Scenario</span></span>

<span data-ttu-id="4b7ad-106">Contoso er et firma som produserer kaffe og kaffemaskiner av høy kvalitet, som de kan selge via nettstedet Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="4b7ad-107">De har nylig startet et abonnementsselskap for kundene for å få kaffe på en jevn basis.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="4b7ad-108">Målet deres er å forstå hvilke kunder med abonnement som kanskje vil annullere abonnementet i løpet av de neste månedene.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="4b7ad-109">Det å vite hvilke av kundene som har **sannsynlighet for frafall**, kan hjelpe dem med å spare markedsføringsinnsats ved å fokusere på å beholde dem.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4b7ad-110">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="4b7ad-110">Prerequisites</span></span>

- <span data-ttu-id="4b7ad-111">Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="4b7ad-112">Vi anbefaler at du implementerer følgende trinn [i et nytt miljø](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="4b7ad-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="4b7ad-113">Oppgave 1 – hente inn data</span><span class="sxs-lookup"><span data-stu-id="4b7ad-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="4b7ad-114">Se gjennom artiklene [om datainntak](data-sources.md) og [importering av datakilder ved hjelp av Power Query-koblinger](connect-power-query.md) spesifikt.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="4b7ad-115">Følgende informasjon forutsetter at du kjenner til datainntakt generelt.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="4b7ad-116">Hente inn kundedata fra eCommerce-plattform</span><span class="sxs-lookup"><span data-stu-id="4b7ad-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="4b7ad-117">Opprett en datakilde med navnet **eCommerce**, velg importalternativet, og velg koblingen **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4b7ad-118">Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="4b7ad-119">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4b7ad-120">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="4b7ad-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="4b7ad-121">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="4b7ad-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="4b7ad-122">**CreatedOn**: Dato/klokkeslett/sone</span><span class="sxs-lookup"><span data-stu-id="4b7ad-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformer fødselsdato til dato.":::

1. <span data-ttu-id="4b7ad-124">I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="4b7ad-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="4b7ad-125">Lagre datakilden.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="4b7ad-126">Hente inn kundedata fra lojalitetsskjema</span><span class="sxs-lookup"><span data-stu-id="4b7ad-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="4b7ad-127">Opprett en datakilde med navnet **LoyaltyScheme**, velg importalternativet, og velg koblingen **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4b7ad-128">Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="4b7ad-129">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4b7ad-130">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="4b7ad-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="4b7ad-131">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="4b7ad-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="4b7ad-132">**RewardsPoints**: Heltall</span><span class="sxs-lookup"><span data-stu-id="4b7ad-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="4b7ad-133">**CreatedOn**: Dato/klokkeslett</span><span class="sxs-lookup"><span data-stu-id="4b7ad-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="4b7ad-134">I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="4b7ad-135">Lagre datakilden.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="4b7ad-136">Hente inn informasjon abonnement</span><span class="sxs-lookup"><span data-stu-id="4b7ad-136">Ingest subscription information</span></span>

1. <span data-ttu-id="4b7ad-137">Opprett en datakilde med navnet **SubscriptionHistory**, velg importalternativet, og velg koblingen **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4b7ad-138">Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="4b7ad-139">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4b7ad-140">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="4b7ad-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="4b7ad-141">**SubscriptioID**: Heltall</span><span class="sxs-lookup"><span data-stu-id="4b7ad-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="4b7ad-142">**SubscriptionAmount**: Valuta</span><span class="sxs-lookup"><span data-stu-id="4b7ad-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="4b7ad-143">**SubscriptionEndDate**: Dato/klokkeslett</span><span class="sxs-lookup"><span data-stu-id="4b7ad-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="4b7ad-144">**SubscriptionStartDate**: Dato/klokkeslett</span><span class="sxs-lookup"><span data-stu-id="4b7ad-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="4b7ad-145">**TransactionDate**: Dato/klokkeslett</span><span class="sxs-lookup"><span data-stu-id="4b7ad-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="4b7ad-146">**IsRecurring**: Sann/usann</span><span class="sxs-lookup"><span data-stu-id="4b7ad-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="4b7ad-147">**Is_auto_renew**: Sann/usann</span><span class="sxs-lookup"><span data-stu-id="4b7ad-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="4b7ad-148">**RecurringFrequencyInMonths**: Heltall</span><span class="sxs-lookup"><span data-stu-id="4b7ad-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="4b7ad-149">I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="4b7ad-150">Lagre datakilden.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="4b7ad-151">Hente inn kundedata fra gjennomganger av nettsteder</span><span class="sxs-lookup"><span data-stu-id="4b7ad-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="4b7ad-152">Opprett en datakilde med navnet **Nettsted**, velg importalternativet, og velg koblingen **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4b7ad-153">Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="4b7ad-154">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4b7ad-155">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="4b7ad-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="4b7ad-156">**ReviewRating**: Whole Heltall</span><span class="sxs-lookup"><span data-stu-id="4b7ad-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="4b7ad-157">**ReviewDate**: Dato</span><span class="sxs-lookup"><span data-stu-id="4b7ad-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="4b7ad-158">I Navn-feltet i den høyre ruten endrer du navnet på datakilden fra **Query** til **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="4b7ad-159">Oppgave 2 – Dataforening</span><span class="sxs-lookup"><span data-stu-id="4b7ad-159">Task 2 - Data unification</span></span>

<span data-ttu-id="4b7ad-160">Etter å ha hentet inn dataene, begynner vi nå med prosessen for å **tilordne, samsvare og slå sammen** for å opprette en enhetlig kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="4b7ad-161">Hvis du vil ha mer informasjon, kan du se [Dataforening](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="4b7ad-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="4b7ad-162">Tilordne</span><span class="sxs-lookup"><span data-stu-id="4b7ad-162">Map</span></span>

1. <span data-ttu-id="4b7ad-163">Etter at du har hentet inn dataene, tilordner du kontakter fra eCommerce og lojalitetsdata til vanlige datatyper.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="4b7ad-164">Gå til **Data** > **Samle** > **Tilordne**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="4b7ad-165">Velg enhetene som representerer kundeprofilen – **eCommerceContacts** og **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Samle ecommerce- og lojalitetsdatakildene.":::

1. <span data-ttu-id="4b7ad-167">Velg **ContactId** som primærnøkkelen for **eCommerceContacts** og **LoyaltyID** som primærnøkkelen for **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Samle LoyaltyId som primærnøkkel.":::

### <a name="match"></a><span data-ttu-id="4b7ad-169">Treff</span><span class="sxs-lookup"><span data-stu-id="4b7ad-169">Match</span></span>

1. <span data-ttu-id="4b7ad-170">Gå til **Samsvar**-fanen, og velg **Angi rekkefølge**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="4b7ad-171">I rullegardinlisten **Primær** velger du **eCommerceContacts : eCommerce** som primærkilden og inkluderer alle oppføringene.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="4b7ad-172">I rullegardinlisten **Enhet 2** velger du **loyCustomers : LoyaltyScheme** og inkluderer alle oppføringer.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Samle treff for eCommerce og lojalitet.":::

1. <span data-ttu-id="4b7ad-174">Velg **Opprett en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="4b7ad-175">Legg til din første betingelse ved å bruke FullName.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="4b7ad-176">For eCommerceContacts velger du **FullName** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="4b7ad-177">For loyCustomers velger du **FullName** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="4b7ad-178">Velg rullegardinlisten **Normaliser**, og velg **Type (telefon, navn, adresse ...)**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="4b7ad-179">Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="4b7ad-180">Angi navnet **FullName, Email** for den nye regelen.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="4b7ad-181">Legg til en ny betingelse for e-postadresse ved å velge **Legg til betingelse**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="4b7ad-182">For enheten eCommerceContacts velger du **EMail** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="4b7ad-183">For enheten loyCustomers velger du **EMail** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="4b7ad-184">La Normaliser være tomt.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="4b7ad-185">Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Regel for å samle treff for navn og e-post.":::

7. <span data-ttu-id="4b7ad-187">Velg **Lagre** og **Kjør**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="4b7ad-188">Flett</span><span class="sxs-lookup"><span data-stu-id="4b7ad-188">Merge</span></span>

1. <span data-ttu-id="4b7ad-189">Gå fil fanen **Slå sammen**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="4b7ad-190">På **ContactId** for enheten **loyCustomers** endrer du visningsnavnet til **ContactIdLOYALTY** for å skille de fra de andre ID-ene som er hentet inn.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Endre navn på contactid fra loyalty id.":::

1. <span data-ttu-id="4b7ad-192">Velg **Lagre** og **Kjør** for å starte sammenslåingsprosessen.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="4b7ad-193">Oppgave 3 – Konfigurere prognosen for abonnementsfrafall</span><span class="sxs-lookup"><span data-stu-id="4b7ad-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="4b7ad-194">Med de enhetlige kundeprofilene på plass kan vi nå kjøre prediksjonen for abonnementsfrafall.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="4b7ad-195">Hvis du vil ha detaljerte trinn, kan du se artikkelen om [prognose på abonnementsfrafall (forhåndsversjon)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="4b7ad-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="4b7ad-196">Gå til **Intelligens** > **Utforsk**, og velg å bruke **kundefrafallsmodellen**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="4b7ad-197">Velg **Abonnement**-alternativet, og velg **Kom i gang**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="4b7ad-198">Gi modellen navnet **Frafallsprognose for OOB-abonnement**, og gi utdataenheten navnet **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="4b7ad-199">Definer to betingelser for frafallsmodellen:</span><span class="sxs-lookup"><span data-stu-id="4b7ad-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="4b7ad-200">**Dager siden abonnementet ble avsluttet**: **Minst 60** dager.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="4b7ad-201">Hvis en kunde ikke fornyer abonnementet i denne perioden etter at abonnementet er avsluttet, anses de som frafalt.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="4b7ad-202">**Frafallsdefinisjon**: **Minst 93** dager.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="4b7ad-203">Hvor lenge modellen forutsier hvilke kunder som kanskje frafaller.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="4b7ad-204">Jo lenger inn i fremtiden som du ser, jo mindre nøayktig blir resultatet.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Velg modellbryterne Prediksjonsvindu og Frafallsdefinisjon.":::

1. <span data-ttu-id="4b7ad-206">Velg **Legg til obligatoriske data**, og velg **Legg til data** for abonnementshistorikken.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="4b7ad-207">Legg til enheten **Subscription : SubscriptionHistory**, og tilordne feltene fra eCommerce til de tilsvarende feltene som kreves av modellen.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="4b7ad-208">Slå sammen enheten **Subscription : SubscriptionHistory** med **eCommerceContacts : eCommerce**, og gi relasjonen navnet **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Slå sammen eCommerce-enheter.":::

1. <span data-ttu-id="4b7ad-210">Under Kundeaktiviteter legger du til enheten **webReviews : Website** og tilordner feltene fra webReviews til de tilsvarende feltene som kreves av modellen.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="4b7ad-211">Primærnøkkel: ReviewId</span><span class="sxs-lookup"><span data-stu-id="4b7ad-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="4b7ad-212">Tidsstempel: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="4b7ad-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="4b7ad-213">Hendelse: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="4b7ad-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="4b7ad-214">Konfigurere en aktivitet for gjennomganger av nettsteder.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="4b7ad-215">Velg aktiviteten **Gjennomgang**, og slå sammen enheten **webReviews : Website** med **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="4b7ad-216">Velg **Neste** for å angi modellplanen.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="4b7ad-217">Modellen må læres opp regelmessig for å lære nye mønstre når nye data er hentet inn.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="4b7ad-218">I dette eksemplet velger du **Månedlig**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="4b7ad-219">Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="4b7ad-220">Oppgave 4 – Gå gjennom modellresultater og forklaringer</span><span class="sxs-lookup"><span data-stu-id="4b7ad-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="4b7ad-221">La modellen fullføre opplæringen og beregne poengsum for dataene.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="4b7ad-222">Du kan nå se gjennom forklaringer av modellen for abonnementsfrafall.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="4b7ad-223">Hvis du vil ha mer informasjon, kan du se [Gå gjennom en prediksjonsstatus og resultater](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="4b7ad-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="4b7ad-224">Oppgave 5 – Opprette et segment med kunder med høy risiko for frafall</span><span class="sxs-lookup"><span data-stu-id="4b7ad-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="4b7ad-225">Når du kjører produksjonsmodellen, opprettes det en ny enhet som du kan se i **Data** > **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="4b7ad-226">Du kan opprette et nytt segment basert på enheten som er opprettet av modellen.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="4b7ad-227">Gå til **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-227">Go to **Segments**.</span></span> <span data-ttu-id="4b7ad-228">Velg **Ny**, og velg **Opprett fra** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Opprette et segment med modellutdataene.":::

1. <span data-ttu-id="4b7ad-230">Velg **OOBSubscriptionChurnPrediction**-endepunktet, og definer segmentet:</span><span class="sxs-lookup"><span data-stu-id="4b7ad-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="4b7ad-231">Felt: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="4b7ad-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="4b7ad-232">Operator: større enn</span><span class="sxs-lookup"><span data-stu-id="4b7ad-232">Operator: greater than</span></span>
   - <span data-ttu-id="4b7ad-233">Verdi: 0,6</span><span class="sxs-lookup"><span data-stu-id="4b7ad-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Konfigurer segement for abonnementsfrafall.":::

<span data-ttu-id="4b7ad-235">Du har nå et segment som er dynamisk oppdatert, og som identifiserer kunder med høy frafallsrisiko for denne abonnementsvirksomheten.</span><span class="sxs-lookup"><span data-stu-id="4b7ad-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="4b7ad-236">Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="4b7ad-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]