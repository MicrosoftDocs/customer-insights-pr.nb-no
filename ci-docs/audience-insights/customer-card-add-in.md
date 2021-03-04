---
title: Installere og konfigurere Kundekort-tillegget
description: Installere og konfigurere tillegg for kundekort for Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268056"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="0e2ea-103">Tillegg for kundekort (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="0e2ea-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0e2ea-104">Få en 360-graders visning av kundene direkte i Dynamics 365-apper.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="0e2ea-105">Vis demografi, innsikt og timeplan for aktiviteter med kundekorttillegget.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0e2ea-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="0e2ea-106">Prerequisites</span></span>

- <span data-ttu-id="0e2ea-107">Dynamics 365-appen (for eksempel Salgssenter eller Kundeservicehub) versjon 9.0 og nyere med Enhetlig grensesnitt aktivert.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="0e2ea-108">Kundeprofiler [hentet fra Dynamics 365-appen ved hjelp av Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0e2ea-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="0e2ea-109">Brukere av Kundekort-tillegget må [legges til som brukere](permissions.md) i målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="0e2ea-110">[Konfigurerte søke- og filterfunksjoner](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="0e2ea-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="0e2ea-111">Demografisk kontroll: Demografiske felter (for eksempel alder eller kjønn) er tilgjengelige i den enhetlige kundeprofilen.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="0e2ea-112">Suppleringskontroll: Krever at aktive [suppleringer](enrichment-hub.md) er brukt på kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="0e2ea-113">Intelligenskontroll: Krever data generert ved hjelp av Azure Machine Learning ([prediksjoner](predictions.md) eller [egendefinerte modeller](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="0e2ea-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="0e2ea-114">Målkontroll: Krever [konfigurerte mål](measures.md).</span><span class="sxs-lookup"><span data-stu-id="0e2ea-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="0e2ea-115">Tidslinjekontroll: Krever [konfigurerte aktiviteter](activities.md).</span><span class="sxs-lookup"><span data-stu-id="0e2ea-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="0e2ea-116">Installere tillegget Kundekort</span><span class="sxs-lookup"><span data-stu-id="0e2ea-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="0e2ea-117">Kundekorttillegget er en løsning for Customer Engagement-apper i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="0e2ea-118">Gå til AppSource og søk etter **Dynamics-kundekort** for å installere løsningen.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="0e2ea-119">Velg [Tillegg for kundekort på AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) og velg **Hent det nå**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="0e2ea-120">Det kan hende at du må logge på med administratorlegitimasjonen for Dynamics 365-appen for å kunne installere løsningen.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="0e2ea-121">Det kan ta litt tid før løsningen installeres i miljøet ditt.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="0e2ea-122">Konfigurere tillegget for kundekort</span><span class="sxs-lookup"><span data-stu-id="0e2ea-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="0e2ea-123">Som administrator kan du gå til delen **Innstillinger** i Dynamics 365 og velge **Løsninger**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="0e2ea-124">Velg **Visningsnavn**-koblingen for løsningen **Dynamics 365 Customer Insights-kundekorttillegg (forhåndsversjon)**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0e2ea-125">![Velg visningsnavn](media/select-display-name.png "Velg visningsnavn")</span><span class="sxs-lookup"><span data-stu-id="0e2ea-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="0e2ea-126">Velg **Logg på**, og angi legitimasjonen for administratorkontoen du bruker til å konfigurere Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0e2ea-127">Kontroller at popup-blokkeringen i nettleseren ikke blokkerer godkjenningsvinduet når du velger knappen **Logg på**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="0e2ea-128">Velg miljøet du vil hente data fra.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="0e2ea-129">Definerer hvilke felt som skal tilknyttes oppføringer i Dynamics 365-appen.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="0e2ea-130">Hvis du vil tilordne med en kontakt, velger du feltet i kundeenheten som samsvarer med ID-en til kontaktenheten.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="0e2ea-131">Hvis du vil tilordne med en forretningsforbindelse, velger du feltet i kundeenheten som samsvarer med ID-en til forretningsforbindelsesenheten.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0e2ea-132">![Kontakt-ID-felt](media/contact-id-field.png "Kontakt-ID-felt")</span><span class="sxs-lookup"><span data-stu-id="0e2ea-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="0e2ea-133">Velg **Lagre konfigurasjon** for å lagre innstillingene.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="0e2ea-134">Deretter må du tilordne sikkerhetsroller i Dynamics 365 slik at brukere kan tilpasse og se kundekortet.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="0e2ea-135">I Dynamics 365 går du til **Innstillinger** > **Sikkerhet** > **Brukere**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="0e2ea-136">Velg brukerne du vil redigere brukerroller for, og velg **Behandle roller**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="0e2ea-137">Tilordne rollen **Korttilpasser for Customer Insights** til brukere som skal tilpasse innholdet som vises på kortet for hele organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="0e2ea-138">Legge til Kundekort-kontroller i skjemaer</span><span class="sxs-lookup"><span data-stu-id="0e2ea-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="0e2ea-139">Hvis du vil legge til kundekortkontrollene i kontaktskjemaet, går du til **Innstillinger** > **Tilpassinger** i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="0e2ea-140">Velg **Tilpasse systemet**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="0e2ea-141">Bla til **Kontakt**-enheten, utvid den, og velg deretter **Skjemaer**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="0e2ea-142">Velg kontaktskjemaet du vil legge til kundekortkontrollene i.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0e2ea-143">![Velg kontaktskjemaet](media/contact-active-forms.png "Velg kontaktskjemaet")</span><span class="sxs-lookup"><span data-stu-id="0e2ea-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="0e2ea-144">Hvis du vil legge til en kontroll, drar du et felt fra **Feltutforsker** i skjemaredigeringsprogrammet til stedet der du vil at kontrollen skal vises.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="0e2ea-145">Velg feltet i skjemaet du nettopp la til, og velg deretter **Endre egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="0e2ea-146">Gå til kategorien **Kontroller**, og velg **Legg til kontroll**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="0e2ea-147">Velg en av de tilgjengelige egendefinerte kontrollene, og velg **Legg til**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="0e2ea-148">I dialogboksen **Feltegenskaper** fjerner du merket for **Vis etikett i skjemaet**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="0e2ea-149">Velg **Web**-alternativet for kontrollen.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="0e2ea-150">For suppleringskontrollen må du velge hvilken suppleringstype du vil skal vises, ved å konfigurere **enrichmentType**-feltet.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="0e2ea-151">Legg til en separat suppleringskontroll for hver suppleringstype.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="0e2ea-152">Velg **Lagre** og **Publiser** for å publisere det oppdaterte kontaktskjemaet.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="0e2ea-153">Gå til det publiserte kontaktskjemaet.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-153">Go to the published contact form.</span></span> <span data-ttu-id="0e2ea-154">Du vil se den nylig tillagte kontrollen.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-154">You'll see the newly added control.</span></span> <span data-ttu-id="0e2ea-155">Det kan hende du må logge på første gang du bruker den.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="0e2ea-156">Hvis du vil tilpasse det du vil vise på den egendefinerte kontrollen, velger du Rediger-knappen øverst i høyre hjørne.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="0e2ea-157">Oppgrader tillegg for kundekort</span><span class="sxs-lookup"><span data-stu-id="0e2ea-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="0e2ea-158">Tillegget for kundekort oppgraderes ikke automatisk.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="0e2ea-159">Hvis du vil oppgradere til den nyeste versjonen, følger du denne fremgangsmåten i Dynamics 365-appen der tillegget er installert.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="0e2ea-160">Gå til **Innstillinger** > **Tilpasning** i Dynamics 365-appen, og velg **Løsninger**.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="0e2ea-161">Se etter **CustomerInsightsCustomerCard** i tabellen med tillegg, og velg raden.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="0e2ea-162">Velg **Bruk løsningsoppgradering** på handlingslinjen.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Oppgrader løsningen i Tilpasning-området i Dynamics 365-appene":::

1. <span data-ttu-id="0e2ea-164">Når du har startet oppgraderingsprosessen, vises en innlastingsindikator til oppgraderingen er fullført.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="0e2ea-165">Hvis det ikke finnes en nyere versjon, vises en feilmelding for oppgraderingen.</span><span class="sxs-lookup"><span data-stu-id="0e2ea-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]