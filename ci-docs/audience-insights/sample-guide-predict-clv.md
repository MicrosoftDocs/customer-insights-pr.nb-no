---
title: Eksempelveiledning for prediksjon om kundens levetidsverdi
description: Bruk denne eksempelveiledningen til å teste prediksjonsmodellen for kundens levetidsverdi.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129957"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="56f0b-103">Eksempelveiledning for prediksjon om kundens levetidsverdi (CLV)</span><span class="sxs-lookup"><span data-stu-id="56f0b-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="56f0b-104">Denne veiledningen går gjennom et komplett eksempel på prediksjon om kundens levetidsverdi (CLV) i Customer Insights ved hjelp av eksempeldata.</span><span class="sxs-lookup"><span data-stu-id="56f0b-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="56f0b-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="56f0b-105">Scenario</span></span>

<span data-ttu-id="56f0b-106">Contoso er et selskap som produserer kaffe og kaffemaskiner av høy kvalitet.</span><span class="sxs-lookup"><span data-stu-id="56f0b-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="56f0b-107">De selger produktene via nettstedet Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="56f0b-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="56f0b-108">Selskapet ønsker å forstå verdien (omsetningen) som kundene kan generere i løpet av de neste 12 månedene.</span><span class="sxs-lookup"><span data-stu-id="56f0b-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="56f0b-109">Hvis de vet den forventede verdien kundene kan generere i løpet av de neste 12 månedene, kan de styre markedsføringen mot kunder som genererer høy verdi.</span><span class="sxs-lookup"><span data-stu-id="56f0b-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56f0b-110">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="56f0b-110">Prerequisites</span></span>

- <span data-ttu-id="56f0b-111">Du må minst ha [bidragsytertillatelser](permissions.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="56f0b-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="56f0b-112">Vi anbefaler at du implementerer følgende trinn [i et nytt miljø](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="56f0b-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="56f0b-113">Oppgave 1 – hente inn data</span><span class="sxs-lookup"><span data-stu-id="56f0b-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="56f0b-114">Se gjennom artiklene [om datainntak](data-sources.md) og [import av datakilder ved hjelp av Power Query-koblinger](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="56f0b-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="56f0b-115">Følgende informasjon forutsetter at du kjenner til datainntakt generelt.</span><span class="sxs-lookup"><span data-stu-id="56f0b-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="56f0b-116">Hente inn kundedata fra eCommerce-plattform</span><span class="sxs-lookup"><span data-stu-id="56f0b-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="56f0b-117">Opprett en datakilde med navnet **eCommerce**, velg importalternativet, og velg koblingen **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="56f0b-118">Skriv inn nettadressen for eCommerce-kontakter [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="56f0b-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="56f0b-119">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="56f0b-120">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="56f0b-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="56f0b-121">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="56f0b-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="56f0b-122">**CreatedOn**: Dato/klokkeslett/sone</span><span class="sxs-lookup"><span data-stu-id="56f0b-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformer fødselsdato til dato.":::

1. <span data-ttu-id="56f0b-124">I Navn-feltet i den høyre ruten endrer du navnet på datakilden fra **Query** til **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="56f0b-125">**Lagre** datakilden.</span><span class="sxs-lookup"><span data-stu-id="56f0b-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="56f0b-126">Hente inn online kjøpsdata</span><span class="sxs-lookup"><span data-stu-id="56f0b-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="56f0b-127">Legge til et nyttdata sett i samme **eCommerce**-datakilde.</span><span class="sxs-lookup"><span data-stu-id="56f0b-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="56f0b-128">Velg koblingen **Tekst/CSV** på nytt.</span><span class="sxs-lookup"><span data-stu-id="56f0b-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="56f0b-129">Skriv inn URL-adressen for **Online kjøp**-dataene https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="56f0b-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="56f0b-130">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="56f0b-131">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="56f0b-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="56f0b-132">**PurchasedOn**: Dato/klokkeslett</span><span class="sxs-lookup"><span data-stu-id="56f0b-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="56f0b-133">**TotalPrice**: Valuta</span><span class="sxs-lookup"><span data-stu-id="56f0b-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="56f0b-134">I **Navn**-feltet i sideruten endrer du navnet på datakilden fra **Spørring** til **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="56f0b-135">**Lagre** datakilden.</span><span class="sxs-lookup"><span data-stu-id="56f0b-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="56f0b-136">Hente inn kundedata fra lojalitetsskjema</span><span class="sxs-lookup"><span data-stu-id="56f0b-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="56f0b-137">Opprett en datakilde med navnet **LoyaltyScheme**, velg importalternativet, og velg koblingen **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="56f0b-138">Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="56f0b-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="56f0b-139">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="56f0b-140">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="56f0b-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="56f0b-141">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="56f0b-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="56f0b-142">**RewardsPoints**: Heltall</span><span class="sxs-lookup"><span data-stu-id="56f0b-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="56f0b-143">**CreatedOn**: Dato/klokkeslett</span><span class="sxs-lookup"><span data-stu-id="56f0b-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="56f0b-144">I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="56f0b-145">**Lagre** datakilden.</span><span class="sxs-lookup"><span data-stu-id="56f0b-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="56f0b-146">Hente inn kundedata fra gjennomganger av nettsteder</span><span class="sxs-lookup"><span data-stu-id="56f0b-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="56f0b-147">Opprett en datakilde med navnet **Nettsted**, velg importalternativet, og velg koblingen **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="56f0b-148">Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="56f0b-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="56f0b-149">Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="56f0b-150">Oppdater datatypen for kolonnene som vises nedenfor:</span><span class="sxs-lookup"><span data-stu-id="56f0b-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="56f0b-151">**ReviewRating**: Desimaltall</span><span class="sxs-lookup"><span data-stu-id="56f0b-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="56f0b-152">**ReviewDate**: Dato</span><span class="sxs-lookup"><span data-stu-id="56f0b-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="56f0b-153">I Navn-feltet i ruten til høyre endrer du navnet til datakilden fra **Spørring** til **Omtaler**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="56f0b-154">**Lagre** datakilden.</span><span class="sxs-lookup"><span data-stu-id="56f0b-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="56f0b-155">Oppgave 2 – Dataforening</span><span class="sxs-lookup"><span data-stu-id="56f0b-155">Task 2 - Data unification</span></span>

<span data-ttu-id="56f0b-156">Etter å ha tatt inn dataene begynner vi nå dataforeningsprosessen for å opprette en enhetlig kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="56f0b-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="56f0b-157">Hvis du vil ha mer informasjon, kan du se [Dataforening](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="56f0b-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="56f0b-158">Tilordne</span><span class="sxs-lookup"><span data-stu-id="56f0b-158">Map</span></span>

1. <span data-ttu-id="56f0b-159">Etter at du har hentet inn dataene, tilordner du kontakter fra eCommerce og lojalitetsdata til vanlige datatyper.</span><span class="sxs-lookup"><span data-stu-id="56f0b-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="56f0b-160">Gå til **Data** > **Samle** > **Tilordne**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="56f0b-161">Velg enhetene som representerer kundeprofilen – **eCommerceContacts** og **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="56f0b-162">Velg deretter **Bruk**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-162">Then, select **Apply**.</span></span>

   ![Samle ecommerce- og lojalitetsdatakildene.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="56f0b-164">Velg **ContactId** som primærnøkkelen for **eCommerceContacts** og **LoyaltyID** som primærnøkkelen for **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Samle LoyaltyId som primærnøkkel.](media/unify-loyaltyid.png)

1. <span data-ttu-id="56f0b-166">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="56f0b-167">Treff</span><span class="sxs-lookup"><span data-stu-id="56f0b-167">Match</span></span>

1. <span data-ttu-id="56f0b-168">Gå til **Samsvar**-fanen, og velg **Angi rekkefølge**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="56f0b-169">I rullegardinlisten **Primær** velger du **eCommerceContacts : eCommerce** som primærkilden og inkluderer alle oppføringene.</span><span class="sxs-lookup"><span data-stu-id="56f0b-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="56f0b-170">I rullegardinlisten **Enhet 2** velger du **loyCustomers : LoyaltyScheme** og inkluderer alle oppføringer.</span><span class="sxs-lookup"><span data-stu-id="56f0b-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Samle treff for eCommerce og lojalitet.](media/unify-match-order.png)

1. <span data-ttu-id="56f0b-172">Velg **Legg til regel**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-172">Select **Add rule**</span></span>

1. <span data-ttu-id="56f0b-173">Legg til din første betingelse ved å bruke FullName.</span><span class="sxs-lookup"><span data-stu-id="56f0b-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="56f0b-174">For eCommerceContacts velger du **FullName** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="56f0b-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="56f0b-175">For loyCustomers velger du **FullName** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="56f0b-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="56f0b-176">Velg rullegardinlisten **Normaliser**, og velg **Type (telefon, navn, adresse ...)**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="56f0b-177">Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="56f0b-178">Angi navnet **FullName, Email** for den nye regelen.</span><span class="sxs-lookup"><span data-stu-id="56f0b-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="56f0b-179">Legg til en ny betingelse for e-postadresse ved å velge **Legg til betingelse**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="56f0b-180">For enheten eCommerceContacts velger du **EMail** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="56f0b-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="56f0b-181">For enheten loyCustomers velger du **EMail** i rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="56f0b-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="56f0b-182">La Normaliser være tomt.</span><span class="sxs-lookup"><span data-stu-id="56f0b-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="56f0b-183">Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Regel for å samle treff for navn og e-post.](media/unify-match-rule.png)

1. <span data-ttu-id="56f0b-185">Velg **Ferdig**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-185">Select **Done**.</span></span>

1. <span data-ttu-id="56f0b-186">Velg **Lagre** og **Kjør**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="56f0b-187">Flett</span><span class="sxs-lookup"><span data-stu-id="56f0b-187">Merge</span></span>

1. <span data-ttu-id="56f0b-188">Gå fil fanen **Slå sammen**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="56f0b-189">På **ContactId** for enheten **loyCustomers** endrer du visningsnavnet til **ContactIdLOYALTY** for å skille de fra de andre ID-ene som er hentet inn.</span><span class="sxs-lookup"><span data-stu-id="56f0b-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Endre navn på contactid fra loyalty id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="56f0b-191">Velg **Lagre** og **Kjør sammenslåings- og nedstrømsprosesser**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="56f0b-192">Oppgave 3 – konfigurere prediksjon om kundens levetidsverdi</span><span class="sxs-lookup"><span data-stu-id="56f0b-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="56f0b-193">Når de enhetlige kundeprofilene er på plass, kan vi nå kjøre prediksjonen om kundens levetidsverdi.</span><span class="sxs-lookup"><span data-stu-id="56f0b-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="56f0b-194">Hvis du vil se detaljerte trinn, kan du se [Prediksjon om kundens levetidsverdi (forhåndsversjon)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="56f0b-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="56f0b-195">Gå til **Intelligens**  > **Prediksjoner**, og velg **Modell for kundens levetidsverdi**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="56f0b-196">Gå gjennom informasjonen i sideruten, og velg **Start**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="56f0b-197">Gi modellen navnet **OOB eCommerce CLV Prediction** og utdataenheten **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="56f0b-198">Definer modellinnstillinger for CLV-modellen:</span><span class="sxs-lookup"><span data-stu-id="56f0b-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="56f0b-199">**Tidsperiode for prediksjon**: **12 måneder eller 1 år**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="56f0b-200">Denne innstillingen angir hvor langt inn i fremtiden kundens levetidsverdi skal forutsies.</span><span class="sxs-lookup"><span data-stu-id="56f0b-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="56f0b-201">**Aktive kunder**: Angi hva aktive kunder betyr for virksomheten din.</span><span class="sxs-lookup"><span data-stu-id="56f0b-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="56f0b-202">Angi den historiske tidsrammen en kunde må ha hatt minst én transaksjon i, for å kunne regnes som aktiv.</span><span class="sxs-lookup"><span data-stu-id="56f0b-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="56f0b-203">Modellen vil bare forutsi CLV for aktive kunder.</span><span class="sxs-lookup"><span data-stu-id="56f0b-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="56f0b-204">Velg mellom å la modellen beregne tidsperioden basert på historiske transaksjonsdata, eller angi en bestemt tidsramme.</span><span class="sxs-lookup"><span data-stu-id="56f0b-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="56f0b-205">I denne eksempelveiledningen skal vi **la modellen beregne kjøpsintervall**, som er standardalternativet.</span><span class="sxs-lookup"><span data-stu-id="56f0b-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="56f0b-206">**Kunder med høy verdi**: Definer kunder med høy verdi som en persentil av kundene som betaler mest.</span><span class="sxs-lookup"><span data-stu-id="56f0b-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="56f0b-207">Modellen bruker disse inndataene til å gi resultater som passer forretningsdefinisjonen din av kunder med høy verdi.</span><span class="sxs-lookup"><span data-stu-id="56f0b-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="56f0b-208">Du kan velge å la modellen definere kunder med høy verdi.</span><span class="sxs-lookup"><span data-stu-id="56f0b-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="56f0b-209">Den bruker en heuristisk regel som avleder persentilen.</span><span class="sxs-lookup"><span data-stu-id="56f0b-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="56f0b-210">Du kan også definere kunder med høy verdi som en persentil av fremtidige kunder som betaler mest.</span><span class="sxs-lookup"><span data-stu-id="56f0b-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="56f0b-211">I denne eksempelveiledningen definerer vi kunder med høy verdi manuelt som **de mest betalende 30 % av aktive kunder** og velger **Neste**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Innstillinger-trinnet i veiledningen for CLV-modellen.":::

1. <span data-ttu-id="56f0b-213">I trinnet **Obligatoriske data** velger du **Legg til data** for å oppgi transaksjonshistorikkdataene.</span><span class="sxs-lookup"><span data-stu-id="56f0b-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="56f0b-214">Legg til enheten **eCommercePurchases : eCommerce**, og tilordne attributtene som kreves av modellen:</span><span class="sxs-lookup"><span data-stu-id="56f0b-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="56f0b-215">Transaksjons-ID: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="56f0b-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="56f0b-216">Transaksjonsdato: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="56f0b-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="56f0b-217">Transaksjonsbeløp: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="56f0b-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="56f0b-218">Produkt-ID: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="56f0b-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="56f0b-219">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-219">Select **Next**.</span></span>

1. <span data-ttu-id="56f0b-220">Konfigurer relasjonen mellom enheten **eCommercePurchases : eCommerce** og **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="56f0b-221">Trinnet **Tilleggsdata (valgfritt)** lar deg legge til flere kundeaktivitetsdata.</span><span class="sxs-lookup"><span data-stu-id="56f0b-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="56f0b-222">Disse dataene kan gi større innsikt i kundesamhandlinger med virksomheten din, som kan bidra til CLV.</span><span class="sxs-lookup"><span data-stu-id="56f0b-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="56f0b-223">Hvis du legger til viktige kundesamhandlinger, for eksempel blogger, kundeservicelogger eller fordelsprogramhistorikk, kan du forbedre nøyaktigheten til prediksjoner.</span><span class="sxs-lookup"><span data-stu-id="56f0b-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="56f0b-224">Velg **Legg til data** for å ta med flere kundeaktivitetsdata.</span><span class="sxs-lookup"><span data-stu-id="56f0b-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="56f0b-225">Legg til enheten for kundeaktivitet og tilordne feltnavnene til de tilsvarende feltene som kreves av modellen:</span><span class="sxs-lookup"><span data-stu-id="56f0b-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="56f0b-226">Enhet for kundeaktivitet: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="56f0b-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="56f0b-227">Primærnøkkel: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="56f0b-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="56f0b-228">Tidsstempel: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="56f0b-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="56f0b-229">Hendelse (aktivitetsnavn): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="56f0b-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="56f0b-230">Detaljer (beløp eller verdi): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="56f0b-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="56f0b-231">Velg **Neste**, og konfigurer aktiviteten og relasjonen mellom transaksjonsdataene og kundedataene:</span><span class="sxs-lookup"><span data-stu-id="56f0b-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="56f0b-232">Aktivitetstype: Velg eksisterende</span><span class="sxs-lookup"><span data-stu-id="56f0b-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="56f0b-233">Aktivitetsetikett: Review</span><span class="sxs-lookup"><span data-stu-id="56f0b-233">Activity label: Review</span></span>
   - <span data-ttu-id="56f0b-234">Tilsvarende etikett: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="56f0b-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="56f0b-235">Kundeenhet: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="56f0b-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="56f0b-236">Relasjon: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="56f0b-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="56f0b-237">Velg **Neste** for å angi modellplanen.</span><span class="sxs-lookup"><span data-stu-id="56f0b-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="56f0b-238">Modellen må læres opp regelmessig for å lære nye mønstre når nye data tas inn.</span><span class="sxs-lookup"><span data-stu-id="56f0b-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="56f0b-239">I dette eksemplet velger du **Månedlig**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="56f0b-240">Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="56f0b-241">Oppgave 4 – gå gjennom modellresultater og forklaringer</span><span class="sxs-lookup"><span data-stu-id="56f0b-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="56f0b-242">La modellen fullføre opplæringen og beregne poengsum for dataene.</span><span class="sxs-lookup"><span data-stu-id="56f0b-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="56f0b-243">Du kan deretter se gjennom resultatene og forklaringene av CLV-modellen.</span><span class="sxs-lookup"><span data-stu-id="56f0b-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="56f0b-244">Hvis du vil ha mer informasjon, kan du se [Gå gjennom en prediksjonsstatus og resultater](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="56f0b-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="56f0b-245">Oppgave 5 – opprette et segment for kunder med høy verdi</span><span class="sxs-lookup"><span data-stu-id="56f0b-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="56f0b-246">Når du kjører modellen, opprettes en ny entitet som vises i **Data** > **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="56f0b-247">Du kan opprette et nytt kundesegment basert på enheten som ble opprettet av modellen.</span><span class="sxs-lookup"><span data-stu-id="56f0b-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="56f0b-248">Gå til **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="56f0b-249">Velg **Ny**, og velg **Opprett fra** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="56f0b-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Opprette et segment med modellutdataene.](media/segment-intelligence.png)

1. <span data-ttu-id="56f0b-251">Velg enheten **OOBeCommerceCLVPrediction**, og definer segmentet:</span><span class="sxs-lookup"><span data-stu-id="56f0b-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="56f0b-252">Felt: CLVScore</span><span class="sxs-lookup"><span data-stu-id="56f0b-252">Field: CLVScore</span></span>
  - <span data-ttu-id="56f0b-253">Operator: større enn</span><span class="sxs-lookup"><span data-stu-id="56f0b-253">Operator: greater than</span></span>
  - <span data-ttu-id="56f0b-254">Verdi: 1500</span><span class="sxs-lookup"><span data-stu-id="56f0b-254">Value: 1500</span></span>

1. <span data-ttu-id="56f0b-255">Velg **Se gjennom** og **Lagre** segmentet.</span><span class="sxs-lookup"><span data-stu-id="56f0b-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="56f0b-256">Du har nå et segment som identifiserer kunder som er anslått å generere mer enn USD 1500 i omsetning de neste 12 månedene.</span><span class="sxs-lookup"><span data-stu-id="56f0b-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="56f0b-257">Dette segmentet oppdateres dynamisk hvis mer data tas inn.</span><span class="sxs-lookup"><span data-stu-id="56f0b-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="56f0b-258">Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="56f0b-258">For more information, see [Create and manage segments](segments.md).</span></span>
