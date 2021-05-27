---
title: Kundekort-tillegget for Dynamics 365-apper
description: Vis data fra målgruppeinnsikt i Dynamics 365-apper med dette tillegget.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059600"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="c77c4-103">Tillegg for kundekort (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="c77c4-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c77c4-104">Få en 360-graders visning av kundene direkte i Dynamics 365-apper.</span><span class="sxs-lookup"><span data-stu-id="c77c4-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="c77c4-105">Når tillegget for kundekort installert i en støttet Dynamics 365-app, kan du velge å vise demografi, innsikt og aktivitetstidslinjer.</span><span class="sxs-lookup"><span data-stu-id="c77c4-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="c77c4-106">Tillegget henter data fra Customer Insights uten at det påvirker dataene i den tilkoblede Dynamics 365-appen.</span><span class="sxs-lookup"><span data-stu-id="c77c4-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c77c4-107">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="c77c4-107">Prerequisites</span></span>

- <span data-ttu-id="c77c4-108">Tillegget fungerer bare med modelldrevne Dynamics 365-apper, for eksempel Sales eller Customer Service, versjon 9.0 og nyere.</span><span class="sxs-lookup"><span data-stu-id="c77c4-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="c77c4-109">Hvis Dynamics 365-dataene skal tilordnes til kundeprofilene for målgruppeinnsikten, må de være [hentet fra Dynamics 365-appen ved hjelp av Common Data Service-koblingen](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c77c4-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="c77c4-110">Alle Dynamics 365-brukere av tillegget for kundekort må [legges til som brukere](permissions.md) i målgruppeinnsikt for å se dataene.</span><span class="sxs-lookup"><span data-stu-id="c77c4-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="c77c4-111">[Konfigurerte søke- og filterfunksjoner](search-filter-index.md) i målgruppeinnsikt er nødvendig for at oppslag av data skal fungere.</span><span class="sxs-lookup"><span data-stu-id="c77c4-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="c77c4-112">Hver tilleggskontroll er avhengig av bestemte data i målgruppeinnsikt:</span><span class="sxs-lookup"><span data-stu-id="c77c4-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="c77c4-113">Målkontroll: Krever [konfigurerte mål](measures.md).</span><span class="sxs-lookup"><span data-stu-id="c77c4-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="c77c4-114">Intelligenskontroll: Krever data generert ved hjelp av [prediksjoner](predictions.md) eller [egendefinerte modeller](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="c77c4-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="c77c4-115">Demografisk kontroll: Demografiske felter (for eksempel alder eller kjønn) er tilgjengelige i den enhetlige kundeprofilen.</span><span class="sxs-lookup"><span data-stu-id="c77c4-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="c77c4-116">Suppleringskontroll: Krever at aktive [suppleringer](enrichment-hub.md) er brukt på kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="c77c4-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="c77c4-117">Tidslinjekontroll: Krever [konfigurerte aktiviteter](activities.md).</span><span class="sxs-lookup"><span data-stu-id="c77c4-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="c77c4-118">Installere tillegget Kundekort</span><span class="sxs-lookup"><span data-stu-id="c77c4-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="c77c4-119">Kundekorttillegget er en løsning for Customer Engagement-apper i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c77c4-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="c77c4-120">Gå til AppSource og søk etter **Dynamics-kundekort** for å installere løsningen.</span><span class="sxs-lookup"><span data-stu-id="c77c4-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="c77c4-121">Velg [Tillegg for kundekort på AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) og velg **Hent det nå**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="c77c4-122">Det kan hende at du må logge på med administratorlegitimasjonen for Dynamics 365-appen for å kunne installere løsningen.</span><span class="sxs-lookup"><span data-stu-id="c77c4-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="c77c4-123">Det kan ta litt tid før løsningen installeres i miljøet ditt.</span><span class="sxs-lookup"><span data-stu-id="c77c4-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="c77c4-124">Konfigurere tillegget for kundekort</span><span class="sxs-lookup"><span data-stu-id="c77c4-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="c77c4-125">Som administrator kan du gå til delen **Innstillinger** i Dynamics 365 og velge **Løsninger**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="c77c4-126">Velg **Visningsnavn**-koblingen for løsningen **Dynamics 365 Customer Insights-kundekorttillegg (forhåndsversjon)**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c77c4-127">![Velg visningsnavn](media/select-display-name.png "Velg visningsnavn")</span><span class="sxs-lookup"><span data-stu-id="c77c4-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="c77c4-128">Velg **Logg på**, og angi legitimasjonen for administratorkontoen du bruker til å konfigurere Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c77c4-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c77c4-129">Kontroller at popup-blokkeringen i nettleseren ikke blokkerer godkjenningsvinduet når du velger knappen **Logg på**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="c77c4-130">Velg Customer Insights-miljøet du vil hente data fra.</span><span class="sxs-lookup"><span data-stu-id="c77c4-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="c77c4-131">Definer felttilordningen til oppføringer i Dynamics 365-appen.</span><span class="sxs-lookup"><span data-stu-id="c77c4-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="c77c4-132">Avhengig av dataene i Customer Insights kan du velge å tilordne følgende alternativer:</span><span class="sxs-lookup"><span data-stu-id="c77c4-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="c77c4-133">Hvis du vil tilordne med en kontakt, velger du feltet i kundeenheten som samsvarer med ID-en til kontaktenheten.</span><span class="sxs-lookup"><span data-stu-id="c77c4-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="c77c4-134">Hvis du vil tilordne med en forretningsforbindelse, velger du feltet i kundeenheten som samsvarer med ID-en til forretningsforbindelsesenheten.</span><span class="sxs-lookup"><span data-stu-id="c77c4-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c77c4-135">![Kontakt-ID-felt](media/contact-id-field.png "Kontakt-ID-felt")</span><span class="sxs-lookup"><span data-stu-id="c77c4-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="c77c4-136">Velg **Lagre konfigurasjon** for å lagre innstillingene.</span><span class="sxs-lookup"><span data-stu-id="c77c4-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="c77c4-137">Deretter må du tilordne sikkerhetsroller i Dynamics 365 slik at brukere kan tilpasse og se kundekortet.</span><span class="sxs-lookup"><span data-stu-id="c77c4-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="c77c4-138">I Dynamics 365 går du til **Innstillinger** > **Sikkerhet** > **Brukere**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="c77c4-139">Velg brukerne du vil redigere brukerroller for, og velg **Behandle roller**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="c77c4-140">Tilordne rollen **Korttilpasser for Customer Insights** til brukere som skal tilpasse innholdet som vises på kortet for hele organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="c77c4-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="c77c4-141">Legge til Kundekort-kontroller i skjemaer</span><span class="sxs-lookup"><span data-stu-id="c77c4-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="c77c4-142">Hvis du vil legge til kundekortkontrollene i kontaktskjemaet, går du til **Innstillinger** > **Tilpassinger** i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c77c4-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="c77c4-143">Velg **Tilpasse systemet**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="c77c4-144">Bla til **Kontakt**-enheten, utvid den, og velg deretter **Skjemaer**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="c77c4-145">Velg kontaktskjemaet du vil legge til kundekortkontrollene i.</span><span class="sxs-lookup"><span data-stu-id="c77c4-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c77c4-146">![Velg kontaktskjemaet](media/contact-active-forms.png "Velg kontaktskjemaet")</span><span class="sxs-lookup"><span data-stu-id="c77c4-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="c77c4-147">Hvis du vil legge til en kontroll, drar du et felt fra **Feltutforsker** i skjemaredigeringsprogrammet til stedet der du vil at kontrollen skal vises.</span><span class="sxs-lookup"><span data-stu-id="c77c4-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="c77c4-148">Velg feltet i skjemaet du nettopp la til, og velg deretter **Endre egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="c77c4-149">Gå til kategorien **Kontroller**, og velg **Legg til kontroll**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="c77c4-150">Velg en av de tilgjengelige egendefinerte kontrollene, og velg **Legg til**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="c77c4-151">I dialogboksen **Feltegenskaper** fjerner du merket for **Vis etikett i skjemaet**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="c77c4-152">Velg **Web**-alternativet for kontrollen.</span><span class="sxs-lookup"><span data-stu-id="c77c4-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="c77c4-153">For suppleringskontrollen må du velge hvilken suppleringstype du vil skal vises, ved å konfigurere **enrichmentType**-feltet.</span><span class="sxs-lookup"><span data-stu-id="c77c4-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="c77c4-154">Legg til en separat suppleringskontroll for hver suppleringstype.</span><span class="sxs-lookup"><span data-stu-id="c77c4-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="c77c4-155">Velg **Lagre** og **Publiser** for å publisere det oppdaterte kontaktskjemaet.</span><span class="sxs-lookup"><span data-stu-id="c77c4-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="c77c4-156">Gå til det publiserte kontaktskjemaet.</span><span class="sxs-lookup"><span data-stu-id="c77c4-156">Go to the published contact form.</span></span> <span data-ttu-id="c77c4-157">Du vil se den nylig tillagte kontrollen.</span><span class="sxs-lookup"><span data-stu-id="c77c4-157">You'll see the newly added control.</span></span> <span data-ttu-id="c77c4-158">Det kan hende du må logge på første gang du bruker den.</span><span class="sxs-lookup"><span data-stu-id="c77c4-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="c77c4-159">Hvis du vil tilpasse det du vil vise på den egendefinerte kontrollen, velger du Rediger-knappen øverst i høyre hjørne.</span><span class="sxs-lookup"><span data-stu-id="c77c4-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="c77c4-160">Oppgrader tillegg for kundekort</span><span class="sxs-lookup"><span data-stu-id="c77c4-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="c77c4-161">Tillegget for kundekort oppgraderes ikke automatisk.</span><span class="sxs-lookup"><span data-stu-id="c77c4-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="c77c4-162">Hvis du vil oppgradere til den nyeste versjonen, følger du denne fremgangsmåten i Dynamics 365-appen der tillegget er installert.</span><span class="sxs-lookup"><span data-stu-id="c77c4-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="c77c4-163">Gå til **Innstillinger** > **Tilpasning** i Dynamics 365-appen, og velg **Løsninger**.</span><span class="sxs-lookup"><span data-stu-id="c77c4-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="c77c4-164">Se etter **CustomerInsightsCustomerCard** i tabellen med tillegg, og velg raden.</span><span class="sxs-lookup"><span data-stu-id="c77c4-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="c77c4-165">Velg **Bruk løsningsoppgradering** på handlingslinjen.</span><span class="sxs-lookup"><span data-stu-id="c77c4-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Oppgrader løsningen i Tilpasning-området i Dynamics 365-appene":::

1. <span data-ttu-id="c77c4-167">Når du har startet oppgraderingsprosessen, vises en innlastingsindikator til oppgraderingen er fullført.</span><span class="sxs-lookup"><span data-stu-id="c77c4-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="c77c4-168">Hvis det ikke finnes en nyere versjon, vises en feilmelding for oppgraderingen.</span><span class="sxs-lookup"><span data-stu-id="c77c4-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
