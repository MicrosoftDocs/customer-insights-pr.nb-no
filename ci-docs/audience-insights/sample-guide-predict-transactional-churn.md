---
title: Eksempelveiledning for prognose på transaksjonelt frafall
description: Bruk denne eksempelveiledningen til å prøve ut den medfølgende prediksjonsmodellen for transaksjonelt frafall.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 81540ad2f490cf566f031233543b3cb6aa838033
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269802"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="43a69-103">Eksempelveiledning for prognose på transaksjonelt frafall (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="43a69-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="43a69-104">Vi tar deg gjennom et helhetlig eksempel på prediksjon av transaksjonelt frafall i Customer Insights ved å bruke dataene som vises nedenfor.</span><span class="sxs-lookup"><span data-stu-id="43a69-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="43a69-105">Ingen data som brukes i denne veiledningen, er reelle kundedata. De er en del av Contoso-datasettet som finnes i *demonstrasjonsmiljøet* i Customer Insights-abonnementet.</span><span class="sxs-lookup"><span data-stu-id="43a69-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="43a69-106">Scenario</span><span class="sxs-lookup"><span data-stu-id="43a69-106">Scenario</span></span>

<span data-ttu-id="43a69-107">Contoso er et firma som produserer kaffe og kaffemaskiner av høy kvalitet, som de kan selge via nettstedet Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="43a69-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="43a69-108">Målet er å vite hvilke kunder som vanligvis kjøper produktene deres regelmessig, og som vil slutte å være aktive kunder i løpet av de neste 60 dagene.</span><span class="sxs-lookup"><span data-stu-id="43a69-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="43a69-109">Det å vite hvilke av kundene som har **sannsynlighet for frafall**, kan hjelpe dem med å spare markedsføringsinnsats ved å fokusere på å beholde dem.</span><span class="sxs-lookup"><span data-stu-id="43a69-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="43a69-110">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="43a69-110">Prerequisites</span></span>

- <span data-ttu-id="43a69-111">Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="43a69-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="43a69-112">Vi anbefaler at du implementerer følgende trinn [i et nytt miljø](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="43a69-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="43a69-113">Oppgave 1 – hente inn data</span><span class="sxs-lookup"><span data-stu-id="43a69-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="43a69-114">Se gjennom artiklene [om datainntak](data-sources.md) og [importering av datakilder ved hjelp av Power Query-koblinger](connect-power-query.md) spesifikt.</span><span class="sxs-lookup"><span data-stu-id="43a69-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="43a69-115">Følgende informasjon forutsetter at du kjenner til datainntakt generelt.</span><span class="sxs-lookup"><span data-stu-id="43a69-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="43a69-116">Hente inn kundedata fra eCommerce-plattform</span><span class="sxs-lookup"><span data-stu-id="43a69-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="43a69-117">Opprett en datakilde med navnet **eCommerce**, velg importalternativet, og velg koblingen **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="43a69-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="43a69-118">Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="43a69-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="43a69-119">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="43a69-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="43a69-120">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="43a69-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="43a69-121">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="43a69-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="43a69-122">**CreatedOn**: Dato/klokkeslett/sone</span><span class="sxs-lookup"><span data-stu-id="43a69-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="43a69-123">![Transformer førdselsdato til dato](media/ecommerce-dob-date.PNG "Transformer fødselsdato til dato")</span><span class="sxs-lookup"><span data-stu-id="43a69-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="43a69-124">I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="43a69-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="43a69-125">Lagre datakilden.</span><span class="sxs-lookup"><span data-stu-id="43a69-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="43a69-126">Hente inn online kjøpsdata</span><span class="sxs-lookup"><span data-stu-id="43a69-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="43a69-127">Legge til et nyttdata sett i samme **eCommerce**-datakilde.</span><span class="sxs-lookup"><span data-stu-id="43a69-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="43a69-128">Velg koblingen **Tekst/CSV** på nytt.</span><span class="sxs-lookup"><span data-stu-id="43a69-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="43a69-129">Skriv inn URL-adressen for **Online kjøp**-dataene https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="43a69-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="43a69-130">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="43a69-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="43a69-131">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="43a69-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="43a69-132">**PurchasedOn**: Dato/klokkeslett</span><span class="sxs-lookup"><span data-stu-id="43a69-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="43a69-133">**TotalPrice**: Valuta</span><span class="sxs-lookup"><span data-stu-id="43a69-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="43a69-134">I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="43a69-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="43a69-135">Lagre datakilden.</span><span class="sxs-lookup"><span data-stu-id="43a69-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="43a69-136">Hente inn kundedata fra lojalitetsskjema</span><span class="sxs-lookup"><span data-stu-id="43a69-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="43a69-137">Opprett en datakilde med navnet **LoyaltyScheme**, velg importalternativet, og velg koblingen **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="43a69-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="43a69-138">Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="43a69-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="43a69-139">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="43a69-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="43a69-140">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="43a69-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="43a69-141">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="43a69-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="43a69-142">**RewardsPoints**: Heltall</span><span class="sxs-lookup"><span data-stu-id="43a69-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="43a69-143">**CreatedOn**: Dato/klokkeslett</span><span class="sxs-lookup"><span data-stu-id="43a69-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="43a69-144">I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="43a69-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="43a69-145">Lagre datakilden.</span><span class="sxs-lookup"><span data-stu-id="43a69-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="43a69-146">Oppgave 2 – Dataforening</span><span class="sxs-lookup"><span data-stu-id="43a69-146">Task 2 - Data unification</span></span>

<span data-ttu-id="43a69-147">Etter å ha hentet inn dataene, begynner vi nå med prosessen for å **tilordne, samsvare og slå sammen** for å opprette en enhetlig kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="43a69-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="43a69-148">Hvis du vil ha mer informasjon, kan du se [Dataforening](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="43a69-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="43a69-149">Tilordne</span><span class="sxs-lookup"><span data-stu-id="43a69-149">Map</span></span>

1. <span data-ttu-id="43a69-150">Etter at du har hentet inn dataene, tilordner du kontakter fra eCommerce og lojalitetsdata til vanlige datatyper.</span><span class="sxs-lookup"><span data-stu-id="43a69-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="43a69-151">Gå til **Data** > **Samle** > **Tilordne**.</span><span class="sxs-lookup"><span data-stu-id="43a69-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="43a69-152">Velg enhetene som representerer kundeprofilen – **eCommerceContacts** og **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="43a69-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Samle ecommerce- og lojalitetsdatakildene.":::

1. <span data-ttu-id="43a69-154">Velg **ContactId** som primærnøkkelen for **eCommerceContacts** og **LoyaltyID** som primærnøkkelen for **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="43a69-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Samle LoyaltyId som primærnøkkel.":::

### <a name="match"></a><span data-ttu-id="43a69-156">Treff</span><span class="sxs-lookup"><span data-stu-id="43a69-156">Match</span></span>

1. <span data-ttu-id="43a69-157">Gå til **Samsvar**-fanen, og velg **Angi rekkefølge**.</span><span class="sxs-lookup"><span data-stu-id="43a69-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="43a69-158">I rullegardinlisten **Primær** velger du **eCommerceContacts : eCommerce** som primærkilden og inkluderer alle oppføringene.</span><span class="sxs-lookup"><span data-stu-id="43a69-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="43a69-159">I rullegardinlisten **Enhet 2** velger du **loyCustomers : LoyaltyScheme** og inkluderer alle oppføringer.</span><span class="sxs-lookup"><span data-stu-id="43a69-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Samle treff for eCommerce og lojalitet.":::

1. <span data-ttu-id="43a69-161">Velg **Opprett en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="43a69-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="43a69-162">Legg til din første betingelse ved å bruke FullName.</span><span class="sxs-lookup"><span data-stu-id="43a69-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="43a69-163">For eCommerceContacts velger du **FullName** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="43a69-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="43a69-164">For loyCustomers velger du **FullName** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="43a69-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="43a69-165">Velg rullegardinlisten **Normaliser**, og velg **Type (telefon, navn, adresse ...)**.</span><span class="sxs-lookup"><span data-stu-id="43a69-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="43a69-166">Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.</span><span class="sxs-lookup"><span data-stu-id="43a69-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="43a69-167">Angi navnet **FullName, Email** for den nye regelen.</span><span class="sxs-lookup"><span data-stu-id="43a69-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="43a69-168">Legg til en ny betingelse for e-postadresse ved å velge **Legg til betingelse**.</span><span class="sxs-lookup"><span data-stu-id="43a69-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="43a69-169">For enheten eCommerceContacts velger du **EMail** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="43a69-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="43a69-170">For enheten loyCustomers velger du **EMail** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="43a69-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="43a69-171">La Normaliser være tomt.</span><span class="sxs-lookup"><span data-stu-id="43a69-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="43a69-172">Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.</span><span class="sxs-lookup"><span data-stu-id="43a69-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Regel for å samle treff for navn og e-post.":::

7. <span data-ttu-id="43a69-174">Velg **Lagre** og **Kjør**.</span><span class="sxs-lookup"><span data-stu-id="43a69-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="43a69-175">Flett</span><span class="sxs-lookup"><span data-stu-id="43a69-175">Merge</span></span>

1. <span data-ttu-id="43a69-176">Gå fil fanen **Slå sammen**.</span><span class="sxs-lookup"><span data-stu-id="43a69-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="43a69-177">På **ContactId** for enheten **loyCustomers** endrer du visningsnavnet til **ContactIdLOYALTY** for å skille de fra de andre ID-ene som er hentet inn.</span><span class="sxs-lookup"><span data-stu-id="43a69-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Endre navn på contactid fra loyalty id.":::

1. <span data-ttu-id="43a69-179">Velg **Lagre** og **Kjør** for å starte sammenslåingsprosessen.</span><span class="sxs-lookup"><span data-stu-id="43a69-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="43a69-180">Oppgave 3 – Konfigurere prognosen for transaksjonelt frafall</span><span class="sxs-lookup"><span data-stu-id="43a69-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="43a69-181">Med de enhetlige kundeprofilene på plass kan vi nå kjøre prediksjonen for abonnementsfrafall.</span><span class="sxs-lookup"><span data-stu-id="43a69-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="43a69-182">Hvis du vil ha detaljerte trinn, kan du se artikkelen om [prognose på abonnementsfrafall (forhåndsversjon)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="43a69-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="43a69-183">Gå til **Intelligens** > **Utforsk**, og velg å bruke **kundefrafallsmodellen**.</span><span class="sxs-lookup"><span data-stu-id="43a69-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="43a69-184">Velg **Transaksjonell**-alternativet, og velg **Kom i gang**.</span><span class="sxs-lookup"><span data-stu-id="43a69-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="43a69-185">Gi modellen navnet **Frafallsprognose for OOB eCommerce-transaksjon**, og gi utdataenheten navnet **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="43a69-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="43a69-186">Definer to betingelser for frafallsmodellen:</span><span class="sxs-lookup"><span data-stu-id="43a69-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="43a69-187">**Prediksjonsvindu**: **Minst 60** dager.</span><span class="sxs-lookup"><span data-stu-id="43a69-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="43a69-188">Denne innstillingen definerer hvor langt inn i fremtiden vi ønsker å forutse kundefrafall.</span><span class="sxs-lookup"><span data-stu-id="43a69-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="43a69-189">**Frafallsdefinisjon**: **Minst 60** dager.</span><span class="sxs-lookup"><span data-stu-id="43a69-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="43a69-190">Varigheten uten å kjøpe noe etter en kunde anses som frafalt.</span><span class="sxs-lookup"><span data-stu-id="43a69-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Velg modellbryterne Prediksjonsvindu og Frafallsdefinisjon.":::

1. <span data-ttu-id="43a69-192">Velg **Kjøpshistorikk (obligatorisk)**, og velg **Legg til data** for kjøpshistorikken.</span><span class="sxs-lookup"><span data-stu-id="43a69-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="43a69-193">Legg til enheten **eCommercePurchases : eCommerce**, og tilordne feltene fra eCommerce til de tilsvarende feltene som kreves av modellen.</span><span class="sxs-lookup"><span data-stu-id="43a69-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="43a69-194">Slå sammen enheten **eCommercePurchases : eCommerce** med **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="43a69-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Slå sammen eCommerce-enheter.":::

1. <span data-ttu-id="43a69-196">Velg **Neste** for å angi modellplanen.</span><span class="sxs-lookup"><span data-stu-id="43a69-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="43a69-197">Modellen må læres opp regelmessig for å lære nye mønstre når nye data er hentet inn.</span><span class="sxs-lookup"><span data-stu-id="43a69-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="43a69-198">I dette eksemplet velger du **Månedlig**.</span><span class="sxs-lookup"><span data-stu-id="43a69-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="43a69-199">Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**.</span><span class="sxs-lookup"><span data-stu-id="43a69-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="43a69-200">Oppgave 4 – Gå gjennom modellresultater og forklaringer</span><span class="sxs-lookup"><span data-stu-id="43a69-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="43a69-201">La modellen fullføre opplæringen og beregne poengsum for dataene.</span><span class="sxs-lookup"><span data-stu-id="43a69-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="43a69-202">Du kan nå se gjennom forklaringer av modellen for abonnementsfrafall.</span><span class="sxs-lookup"><span data-stu-id="43a69-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="43a69-203">Hvis du vil ha mer informasjon, kan du se [Gå gjennom en prediksjonsstatus og resultater](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="43a69-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="43a69-204">Oppgave 5 – Opprette et segment med kunder med høy risiko for frafall</span><span class="sxs-lookup"><span data-stu-id="43a69-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="43a69-205">Når du kjører produksjonsmodellen, opprettes det en ny enhet som du kan se i **Data** > **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="43a69-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="43a69-206">Du kan opprette et nytt segment basert på enheten som er opprettet av modellen.</span><span class="sxs-lookup"><span data-stu-id="43a69-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="43a69-207">Gå til **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="43a69-207">Go to **Segments**.</span></span> <span data-ttu-id="43a69-208">Velg **Ny**, og velg **Opprett fra** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="43a69-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Opprette et segment med modellutdataene.":::

1. <span data-ttu-id="43a69-210">Velg **OOBSubscriptionChurnPrediction**-endepunktet, og definer segmentet:</span><span class="sxs-lookup"><span data-stu-id="43a69-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="43a69-211">Felt: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="43a69-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="43a69-212">Operator: større enn</span><span class="sxs-lookup"><span data-stu-id="43a69-212">Operator: greater than</span></span>
   - <span data-ttu-id="43a69-213">Verdi: 0,6</span><span class="sxs-lookup"><span data-stu-id="43a69-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Konfigurer segement for abonnementsfrafall.":::

<span data-ttu-id="43a69-215">Du har nå et segment som er dynamisk oppdatert, og som identifiserer kunder med høy frafallsrisiko for denne abonnementsvirksomheten.</span><span class="sxs-lookup"><span data-stu-id="43a69-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="43a69-216">Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="43a69-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]