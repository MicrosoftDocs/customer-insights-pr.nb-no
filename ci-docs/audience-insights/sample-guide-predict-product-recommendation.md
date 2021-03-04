---
title: Eksempelveiledning for prediksjon for produktanbefaling
description: Bruk denne eksempelveiledningen til å prøve ut den medfølgende prediksjonsmodellen for produktanbefaling.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270518"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="14c39-103">Eksempelveiledning for prediksjon for produktanbefaling (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="14c39-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="14c39-104">Vi tar deg gjennom et helhetlig eksempel på prediksjon av produktanbefaling ved å bruke eksempeldataene som vises nedenfor.</span><span class="sxs-lookup"><span data-stu-id="14c39-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="14c39-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="14c39-105">Scenario</span></span>

<span data-ttu-id="14c39-106">Contoso er et firma som produserer kaffe og kaffemaskiner av høy kvalitet, som de kan selge via nettstedet Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="14c39-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="14c39-107">Målet er å forstå hvilke produkter de bør anbefale til sine regelmessige kunder.</span><span class="sxs-lookup"><span data-stu-id="14c39-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="14c39-108">Hvis du vet hva det er mer **sannsynlig at kundene kjøper**, kan du hjelpe dem med å lagre markedsføringen ved å fokusere på bestemte elementer.</span><span class="sxs-lookup"><span data-stu-id="14c39-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="14c39-109">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="14c39-109">Prerequisites</span></span>

- <span data-ttu-id="14c39-110">Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="14c39-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="14c39-111">Vi anbefaler at du implementerer følgende trinn [i et nytt miljø](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="14c39-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="14c39-112">Oppgave 1 – hente inn data</span><span class="sxs-lookup"><span data-stu-id="14c39-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="14c39-113">Se gjennom artiklene [om datainntak](data-sources.md) og [importering av datakilder ved hjelp av Power Query-koblinger](connect-power-query.md) spesifikt.</span><span class="sxs-lookup"><span data-stu-id="14c39-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="14c39-114">Følgende informasjon forutsetter at du kjenner til datainntakt generelt.</span><span class="sxs-lookup"><span data-stu-id="14c39-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="14c39-115">Hente inn kundedata fra eCommerce-plattform</span><span class="sxs-lookup"><span data-stu-id="14c39-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="14c39-116">Opprett en datakilde med navnet **eCommerce**, velg importalternativet, og velg koblingen **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="14c39-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="14c39-117">Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="14c39-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="14c39-118">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="14c39-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="14c39-119">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="14c39-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="14c39-120">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="14c39-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="14c39-121">**CreatedOn**: Dato/klokkeslett/sone</span><span class="sxs-lookup"><span data-stu-id="14c39-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformer fødselsdato til dato.":::

5. <span data-ttu-id="14c39-123">I Navn-feltet i den høyre ruten endrer du navnet på datakilden fra **Query** til **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="14c39-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="14c39-124">**Lagre** datakilden.</span><span class="sxs-lookup"><span data-stu-id="14c39-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="14c39-125">Hente inn online kjøpsdata</span><span class="sxs-lookup"><span data-stu-id="14c39-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="14c39-126">Legge til et nyttdata sett i samme **eCommerce**-datakilde.</span><span class="sxs-lookup"><span data-stu-id="14c39-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="14c39-127">Velg koblingen **Tekst/CSV** på nytt.</span><span class="sxs-lookup"><span data-stu-id="14c39-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="14c39-128">Skriv inn URL-adressen for **Online kjøp**-dataene https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="14c39-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="14c39-129">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="14c39-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="14c39-130">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="14c39-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="14c39-131">**PurchasedOn**: Dato/klokkeslett</span><span class="sxs-lookup"><span data-stu-id="14c39-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="14c39-132">**TotalPrice**: Valuta</span><span class="sxs-lookup"><span data-stu-id="14c39-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="14c39-133">I **Navn**-feltet i sideruten endrer du navnet på datakilden fra **Spørring** til **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="14c39-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="14c39-134">Lagre datakilden.</span><span class="sxs-lookup"><span data-stu-id="14c39-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="14c39-135">Hente inn kundedata fra lojalitetsskjema</span><span class="sxs-lookup"><span data-stu-id="14c39-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="14c39-136">Opprett en datakilde med navnet **LoyaltyScheme**, velg importalternativet, og velg koblingen **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="14c39-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="14c39-137">Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="14c39-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="14c39-138">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="14c39-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="14c39-139">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="14c39-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="14c39-140">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="14c39-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="14c39-141">**RewardsPoints**: Heltall</span><span class="sxs-lookup"><span data-stu-id="14c39-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="14c39-142">**CreatedOn**: Dato/klokkeslett</span><span class="sxs-lookup"><span data-stu-id="14c39-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="14c39-143">I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="14c39-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="14c39-144">Lagre datakilden.</span><span class="sxs-lookup"><span data-stu-id="14c39-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="14c39-145">Oppgave 2 – Dataforening</span><span class="sxs-lookup"><span data-stu-id="14c39-145">Task 2 - Data unification</span></span>

<span data-ttu-id="14c39-146">Etter å ha hentet inn dataene, begynner vi nå med prosessen for å **tilordne, samsvare og slå sammen** for å opprette en enhetlig kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="14c39-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="14c39-147">Hvis du vil ha mer informasjon, kan du se [Dataforening](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="14c39-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="14c39-148">Tilordne</span><span class="sxs-lookup"><span data-stu-id="14c39-148">Map</span></span>

1. <span data-ttu-id="14c39-149">Etter at du har hentet inn dataene, tilordner du kontakter fra eCommerce og lojalitetsdata til vanlige datatyper.</span><span class="sxs-lookup"><span data-stu-id="14c39-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="14c39-150">Gå til **Data** > **Samle** > **Tilordne**.</span><span class="sxs-lookup"><span data-stu-id="14c39-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="14c39-151">Velg enhetene som representerer kundeprofilen – **eCommerceContacts** og **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="14c39-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![Samle ecommerce- og lojalitetsdatakildene.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="14c39-153">Velg **ContactId** som primærnøkkelen for **eCommerceContacts** og **LoyaltyID** som primærnøkkelen for **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="14c39-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Samle LoyaltyId som primærnøkkel.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="14c39-155">Treff</span><span class="sxs-lookup"><span data-stu-id="14c39-155">Match</span></span>

1. <span data-ttu-id="14c39-156">Gå til **Samsvar**-fanen, og velg **Angi rekkefølge**.</span><span class="sxs-lookup"><span data-stu-id="14c39-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="14c39-157">I rullegardinlisten **Primær** velger du **eCommerceContacts : eCommerce** som primærkilden og inkluderer alle oppføringene.</span><span class="sxs-lookup"><span data-stu-id="14c39-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="14c39-158">I rullegardinlisten **Enhet 2** velger du **loyCustomers : LoyaltyScheme** og inkluderer alle oppføringer.</span><span class="sxs-lookup"><span data-stu-id="14c39-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Samle treff for eCommerce og lojalitet.](media/unify-match-order.png)

4. <span data-ttu-id="14c39-160">Velg **Opprett en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="14c39-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="14c39-161">Legg til din første betingelse ved å bruke FullName.</span><span class="sxs-lookup"><span data-stu-id="14c39-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="14c39-162">For eCommerceContacts velger du **FullName** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="14c39-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="14c39-163">For loyCustomers velger du **FullName** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="14c39-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="14c39-164">Velg rullegardinlisten **Normaliser**, og velg **Type (telefon, navn, adresse ...)**.</span><span class="sxs-lookup"><span data-stu-id="14c39-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="14c39-165">Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.</span><span class="sxs-lookup"><span data-stu-id="14c39-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="14c39-166">Angi navnet **FullName, Email** for den nye regelen.</span><span class="sxs-lookup"><span data-stu-id="14c39-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="14c39-167">Legg til en ny betingelse for e-postadresse ved å velge **Legg til betingelse**.</span><span class="sxs-lookup"><span data-stu-id="14c39-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="14c39-168">For enheten eCommerceContacts velger du **EMail** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="14c39-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="14c39-169">For enheten loyCustomers velger du **EMail** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="14c39-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="14c39-170">La Normaliser være tomt.</span><span class="sxs-lookup"><span data-stu-id="14c39-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="14c39-171">Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.</span><span class="sxs-lookup"><span data-stu-id="14c39-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Regel for å samle treff for navn og e-post.](media/unify-match-rule.png)

7. <span data-ttu-id="14c39-173">Velg **Lagre** og **Kjør**.</span><span class="sxs-lookup"><span data-stu-id="14c39-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="14c39-174">Flett</span><span class="sxs-lookup"><span data-stu-id="14c39-174">Merge</span></span>

1. <span data-ttu-id="14c39-175">Gå fil fanen **Slå sammen**.</span><span class="sxs-lookup"><span data-stu-id="14c39-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="14c39-176">På **ContactId** for enheten **loyCustomers** endrer du visningsnavnet til **ContactIdLOYALTY** for å skille de fra de andre ID-ene som er hentet inn.</span><span class="sxs-lookup"><span data-stu-id="14c39-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Endre navn på contactid fra loyalty id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="14c39-178">Velg **Lagre** og **Kjør** for å starte sammenslåingsprosessen.</span><span class="sxs-lookup"><span data-stu-id="14c39-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="14c39-179">Oppgave 3 – Konfigurer prediksjon av produktanbefaling</span><span class="sxs-lookup"><span data-stu-id="14c39-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="14c39-180">Med de enhetlige kundeprofilene på plass kan vi nå kjøre prediksjonen for abonnementsfrafall.</span><span class="sxs-lookup"><span data-stu-id="14c39-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="14c39-181">Gå til **Intelligens** > **Prediksjon** og velg **Produktanbefaling**.</span><span class="sxs-lookup"><span data-stu-id="14c39-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="14c39-182">Velg **Komme i gang**.</span><span class="sxs-lookup"><span data-stu-id="14c39-182">Select **Get started**.</span></span>

1. <span data-ttu-id="14c39-183">Gi modellen navnet **Prediksjon for OOB-produktanbefalingsmodell** og utdataenheten **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="14c39-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="14c39-184">Definer tre betingelser for modellen:</span><span class="sxs-lookup"><span data-stu-id="14c39-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="14c39-185">**Antall produkter**: Angi **5** for denne verdien.</span><span class="sxs-lookup"><span data-stu-id="14c39-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="14c39-186">Denne innstillingen definerer hvor mange produkter du vil anbefale til kundene.</span><span class="sxs-lookup"><span data-stu-id="14c39-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="14c39-187">**Foreslå produkter som kunder nylig har kjøpt?**: Velg **Ja** for å angi at du vil inkludere produkter i anbefalingen som kundene har kjøpt tidligere.</span><span class="sxs-lookup"><span data-stu-id="14c39-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="14c39-188">**Tilbakeblikksvindu:** Velg minst **365 dager**.</span><span class="sxs-lookup"><span data-stu-id="14c39-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="14c39-189">Denne innstillingen definerer hvor langt modellen skal se bakover for å se på kundens aktivitet og bruke det som inndata i anbefalingene.</span><span class="sxs-lookup"><span data-stu-id="14c39-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modellinnstillinger for produktanbefalingsmodellen.":::

1. <span data-ttu-id="14c39-191">Velg **Obligatoriske data**, og velg **Legg til data** for kjøpshistorikken.</span><span class="sxs-lookup"><span data-stu-id="14c39-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="14c39-192">Legg til enheten **eCommercePurchases : eCommerce**, og tilordne feltene fra eCommerce til de tilsvarende feltene som kreves av modellen.</span><span class="sxs-lookup"><span data-stu-id="14c39-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="14c39-193">Slå sammen enheten **eCommercePurchases : eCommerce** med **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="14c39-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Slå sammen eCommerce-enheter.](media/model-purchase-join.png)

1. <span data-ttu-id="14c39-195">Velg **Neste** for å angi modellplanen.</span><span class="sxs-lookup"><span data-stu-id="14c39-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="14c39-196">Modellen må læres opp regelmessig for å lære nye mønstre når nye data er hentet inn.</span><span class="sxs-lookup"><span data-stu-id="14c39-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="14c39-197">I dette eksemplet velger du **Månedlig**.</span><span class="sxs-lookup"><span data-stu-id="14c39-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="14c39-198">Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**.</span><span class="sxs-lookup"><span data-stu-id="14c39-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="14c39-199">Oppgave 4 – Gå gjennom modellresultater og forklaringer</span><span class="sxs-lookup"><span data-stu-id="14c39-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="14c39-200">La modellen fullføre opplæringen og beregne poengsum for dataene.</span><span class="sxs-lookup"><span data-stu-id="14c39-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="14c39-201">Du kan nå se gjennom forklaringer av modellen for produktanbefaling.</span><span class="sxs-lookup"><span data-stu-id="14c39-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="14c39-202">Hvis du vil ha mer informasjon, kan du se [Gå gjennom en prediksjonsstatus og resultater](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="14c39-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="14c39-203">Oppgave 5 – Opprett et segment av mye kjøpte produkter</span><span class="sxs-lookup"><span data-stu-id="14c39-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="14c39-204">Når du kjører produksjonsmodellen, opprettes det en ny enhet som du kan se i **Data** > **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="14c39-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="14c39-205">Du kan opprette et nytt segment basert på enheten som er opprettet av modellen.</span><span class="sxs-lookup"><span data-stu-id="14c39-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="14c39-206">Gå til **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="14c39-206">Go to **Segments**.</span></span> <span data-ttu-id="14c39-207">Velg **Ny**, og velg **Opprett fra** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="14c39-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Opprette et segment med modellutdataene.](media/segment-intelligence.png)

1. <span data-ttu-id="14c39-209">Velg **OOBProductRecommendationModelPrediction**-endepunktet, og definer segmentet:</span><span class="sxs-lookup"><span data-stu-id="14c39-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="14c39-210">Felt: ProductID</span><span class="sxs-lookup"><span data-stu-id="14c39-210">Field: ProductID</span></span>
   - <span data-ttu-id="14c39-211">Operator: Verdi</span><span class="sxs-lookup"><span data-stu-id="14c39-211">Operator: Value</span></span>
   - <span data-ttu-id="14c39-212">Verdi: Velg de tre mest populære produkt-ID-ene</span><span class="sxs-lookup"><span data-stu-id="14c39-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Opprett et segment fra modellresultatene.":::

<span data-ttu-id="14c39-214">Du har nå et segment som oppdateres dynamisk, og denne identifiserer kundene som er mer villige til å kjøpe de tre mest anbefalte produktene</span><span class="sxs-lookup"><span data-stu-id="14c39-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="14c39-215">Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="14c39-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]