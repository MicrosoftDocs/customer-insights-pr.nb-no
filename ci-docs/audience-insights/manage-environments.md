---
title: Opprette og behandle miljøer
description: Lær hvordan du registrerer deg for tjenesten og hvordan du administrerer miljøer.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644145"
---
# <a name="manage-environments"></a><span data-ttu-id="f094c-103">Behandle miljøer</span><span class="sxs-lookup"><span data-stu-id="f094c-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f094c-104">Denne artikkelen forklarer hvordan du oppretter en ny organisasjon og hvordan du klargjør et miljø.</span><span class="sxs-lookup"><span data-stu-id="f094c-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="f094c-105">Registrere og opprette en organisasjon</span><span class="sxs-lookup"><span data-stu-id="f094c-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="f094c-106">Gå til [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/)-nettsted.</span><span class="sxs-lookup"><span data-stu-id="f094c-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="f094c-107">Velg **Komme i gang**.</span><span class="sxs-lookup"><span data-stu-id="f094c-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="f094c-108">Velg ønsket registreringsscenario, og velg den tilsvarende koblingen.</span><span class="sxs-lookup"><span data-stu-id="f094c-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="f094c-109">Godta vilkårene, og velg **Fortsett** for å starte opprettingen av organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="f094c-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="f094c-110">Når du har opprettet miljøet, blir du omdirigert til [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="f094c-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="f094c-111">Bruk demonstrasjonsmiljøet til å utforske appen, eller opprett et nytt miljø ved å følge fremgangsmåten i neste del.</span><span class="sxs-lookup"><span data-stu-id="f094c-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="f094c-112">Etter at du har angitt miljøinnstillingene, velger du **Opprett**.</span><span class="sxs-lookup"><span data-stu-id="f094c-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="f094c-113">Du blir logget på etter at miljøet er opprettet.</span><span class="sxs-lookup"><span data-stu-id="f094c-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="f094c-114">Opprette et miljø i en eksisterende organisasjon</span><span class="sxs-lookup"><span data-stu-id="f094c-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="f094c-115">Du kan opprette et nytt miljø på to måter.</span><span class="sxs-lookup"><span data-stu-id="f094c-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="f094c-116">Du kan enten spesifisere en helt ny konfigurasjon, eller du kan kopiere noen konfigurasjonsinnstillinger fra et eksisterende miljø.</span><span class="sxs-lookup"><span data-stu-id="f094c-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="f094c-117">Slik oppretter du et miljø:</span><span class="sxs-lookup"><span data-stu-id="f094c-117">To create an environment:</span></span>

1. <span data-ttu-id="f094c-118">Velg **Innstillinger**-symbolet i overskriften i appen.</span><span class="sxs-lookup"><span data-stu-id="f094c-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="f094c-119">Velg **Nytt miljø**.</span><span class="sxs-lookup"><span data-stu-id="f094c-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f094c-120">![Miljøinnstillinger](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="f094c-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="f094c-121">I dialogboksen **Opprett nytt miljø** velger du **Nytt miljø**.</span><span class="sxs-lookup"><span data-stu-id="f094c-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="f094c-122">Hvis du vil [kopiere data fra det gjeldende miljøet](#additional-considerations-for-copy-configuration-preview), velger du **Kopier fra eksisterende miljø**.</span><span class="sxs-lookup"><span data-stu-id="f094c-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="f094c-123">Det vises en liste over alle tilgjengelige miljøer i organisasjonen, der du kan kopiere data fra.</span><span class="sxs-lookup"><span data-stu-id="f094c-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="f094c-124">Angi følgende detaljer:</span><span class="sxs-lookup"><span data-stu-id="f094c-124">Provide the following details:</span></span>
   - <span data-ttu-id="f094c-125">**Navn**: Navnet på dette miljøet.</span><span class="sxs-lookup"><span data-stu-id="f094c-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="f094c-126">Dette feltet er allerede fylt ut hvis du har kopiert et eksisterende miljø, men du kan endre det.</span><span class="sxs-lookup"><span data-stu-id="f094c-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="f094c-127">**Område**: Området som servicen er distribuert i, og driftet.</span><span class="sxs-lookup"><span data-stu-id="f094c-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="f094c-128">**Type**: Velg om du vil opprette et produksjons- eller sandkassemiljø.</span><span class="sxs-lookup"><span data-stu-id="f094c-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="f094c-129">Du kan eventuelt velge **Avanserte innstillinger**:</span><span class="sxs-lookup"><span data-stu-id="f094c-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="f094c-130">**Lagre alle data i**: Angir hvor du vil lagre utdataene som er generert av Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f094c-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="f094c-131">Du har to alternativer: **Customer Insights-lagring** (en Azure Data Lake administrert av Customer Insights-teamet) og **Azure Data Lake Storage Gen2** (din egen Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="f094c-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="f094c-132">Som standard er det merket av for lagringsalternativet Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f094c-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f094c-133">Når du lagrer data i Azure Data Lake Storage, godtar du at dataene overføres til og lagres i den riktige geografiske plasseringen for denne Azure Storage-kontoen, som kan variere fra der dataene lagres i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f094c-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="f094c-134">Finn ut mer om Microsofts klareringssenter.</span><span class="sxs-lookup"><span data-stu-id="f094c-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="f094c-135">For øyeblikket lagres enheter alltid i den Customer Insights-administrerte datasjøen.</span><span class="sxs-lookup"><span data-stu-id="f094c-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="f094c-136">Vi støtter bare Azure Data Lake Gen2-lagringskontoer fra det samme Azure-området du valgte da du opprettet miljøet.</span><span class="sxs-lookup"><span data-stu-id="f094c-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="f094c-137">Vi støtter bare Azure Data Lake Gen2 Hierarkisk navneområde (HNS)-aktiverte lagringskontoer.</span><span class="sxs-lookup"><span data-stu-id="f094c-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="f094c-138">For Azure Data Lake Storage Gen2 kan du velge mellom et ressursbasert alternativ og et abonnementsbasert alternativ for godkjenning.</span><span class="sxs-lookup"><span data-stu-id="f094c-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="f094c-139">Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="f094c-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="f094c-140">**Beholder**-navnet kan ikke endres, og det vil være "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="f094c-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="f094c-141">Hvis du vil bruke [prognoser](predictions.md), skriver du inn URL-adressen til Common Data Service-forekomsten i **Serveradresse**-feltet under **Bruk prognoser**.</span><span class="sxs-lookup"><span data-stu-id="f094c-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="f094c-142">Når du kjører prosesser, for eksempel datainntak eller segmentopprettelse, blir tilsvarende mapper opprettet i lagringskontoen du angav ovenfor.</span><span class="sxs-lookup"><span data-stu-id="f094c-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="f094c-143">Datafiler og model.json-filer opprettes og legges til i de respektive undermappene basert på prosessen du kjører.</span><span class="sxs-lookup"><span data-stu-id="f094c-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="f094c-144">Hvis du oppretter flere miljøer i Customer Insights og velger å lagre enhetene fra disse miljøene i lagringskontoen, blir det opprettet separate mapper for hvert miljø med ci_<environmentid> i beholderen.</span><span class="sxs-lookup"><span data-stu-id="f094c-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="f094c-145">Tilleggshensyn for kopieringskonfigurasjon (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="f094c-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="f094c-146">Følgende konfigurasjonsinnstillinger kopieres:</span><span class="sxs-lookup"><span data-stu-id="f094c-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="f094c-147">Funksjonskonfigurasjoner</span><span class="sxs-lookup"><span data-stu-id="f094c-147">Feature configurations</span></span>
- <span data-ttu-id="f094c-148">Hentede/importerte datakilder</span><span class="sxs-lookup"><span data-stu-id="f094c-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="f094c-149">Konfigurasjon av forening av data (tilordning, samsvar, sammenslåing)</span><span class="sxs-lookup"><span data-stu-id="f094c-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="f094c-150">Segmenter</span><span class="sxs-lookup"><span data-stu-id="f094c-150">Segments</span></span>
- <span data-ttu-id="f094c-151">Mål</span><span class="sxs-lookup"><span data-stu-id="f094c-151">Measures</span></span>
- <span data-ttu-id="f094c-152">Relasjoner</span><span class="sxs-lookup"><span data-stu-id="f094c-152">Relationships</span></span>
- <span data-ttu-id="f094c-153">Aktiviteter</span><span class="sxs-lookup"><span data-stu-id="f094c-153">Activities</span></span>
- <span data-ttu-id="f094c-154">Søk- og filterindeks</span><span class="sxs-lookup"><span data-stu-id="f094c-154">Search & filter Index</span></span>
- <span data-ttu-id="f094c-155">Eksportmål</span><span class="sxs-lookup"><span data-stu-id="f094c-155">Export destinations</span></span>
- <span data-ttu-id="f094c-156">Planlagt oppdatering</span><span class="sxs-lookup"><span data-stu-id="f094c-156">Scheduled refresh</span></span>
- <span data-ttu-id="f094c-157">Suppleringer</span><span class="sxs-lookup"><span data-stu-id="f094c-157">Enrichments</span></span>
- <span data-ttu-id="f094c-158">Modelladministrasjon</span><span class="sxs-lookup"><span data-stu-id="f094c-158">Model management</span></span>
- <span data-ttu-id="f094c-159">Rolletildelinger</span><span class="sxs-lookup"><span data-stu-id="f094c-159">Role assignments</span></span>

<span data-ttu-id="f094c-160">Følgende innstillinger kopieres *ikke*:</span><span class="sxs-lookup"><span data-stu-id="f094c-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="f094c-161">Kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="f094c-161">Customer profiles.</span></span>
- <span data-ttu-id="f094c-162">Legitimasjon for datakilde.</span><span class="sxs-lookup"><span data-stu-id="f094c-162">Data source credentials.</span></span> <span data-ttu-id="f094c-163">Du må angi legitimasjonen for hver datakilde og oppdatere datakildene manuelt.</span><span class="sxs-lookup"><span data-stu-id="f094c-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="f094c-164">Datakilder fra Common Data Model-mappe og Common Data Service-administrert sjø.</span><span class="sxs-lookup"><span data-stu-id="f094c-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="f094c-165">Du må opprette disse datakildene manuelt med samme navn som i kildemiljøet.</span><span class="sxs-lookup"><span data-stu-id="f094c-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="f094c-166">Når du kopierer et miljø, vises en bekreftelsesmelding om at det nye miljøet er opprettet.</span><span class="sxs-lookup"><span data-stu-id="f094c-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="f094c-167">Velg **Gå til datakilder** for å vise listen over datakilder.</span><span class="sxs-lookup"><span data-stu-id="f094c-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="f094c-168">Alle datakildene vil vise statusen **Legitimasjon kreves**.</span><span class="sxs-lookup"><span data-stu-id="f094c-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="f094c-169">Rediger datakildene, og angi legitimasjonen for å oppdatere dem.</span><span class="sxs-lookup"><span data-stu-id="f094c-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f094c-170">![Kopierte datakilder](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="f094c-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="f094c-171">Etter at du har oppdatert datakildene, går du til **Data** > **Samle**.</span><span class="sxs-lookup"><span data-stu-id="f094c-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="f094c-172">Her finner du innstillinger fra kildemiljøet.</span><span class="sxs-lookup"><span data-stu-id="f094c-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="f094c-173">Rediger dem etter behov, eller velg **Kjør** for å starte prosessen med datasamling og opprette den enhetlige kundeenheten.</span><span class="sxs-lookup"><span data-stu-id="f094c-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="f094c-174">Når datasamlingen er fullført, kan du gå til **Mål** og **Segmenter** for å oppdatere dem også.</span><span class="sxs-lookup"><span data-stu-id="f094c-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="f094c-175">Redigere et eksisterende miljø</span><span class="sxs-lookup"><span data-stu-id="f094c-175">Edit an existing environment</span></span>

<span data-ttu-id="f094c-176">Du kan redigere noen av detaljene i eksisterende miljøer.</span><span class="sxs-lookup"><span data-stu-id="f094c-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="f094c-177">Gå til **Admin** > **System** > **Om**.</span><span class="sxs-lookup"><span data-stu-id="f094c-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="f094c-178">Velg **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="f094c-178">Select **Edit**.</span></span>

3. <span data-ttu-id="f094c-179">Du kan oppdatere miljøets **Visningsnavn**, men du kan ikke endre **Område** eller **Type**.</span><span class="sxs-lookup"><span data-stu-id="f094c-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="f094c-180">Hvis et miljø er konfigurert til å lagre data i Azure Data Lake Storage Gen2, kan du oppdatere **kontonøkkelen**.</span><span class="sxs-lookup"><span data-stu-id="f094c-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="f094c-181">Du kan imidlertid ikke endre **Kontonavn** eller **Beholder**-navn.</span><span class="sxs-lookup"><span data-stu-id="f094c-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="f094c-182">Du kan eventuelt oppdatere fra en tilkobling basert på en kontonøkkel til en ressursbasert eller abonnementsbasert tilkobling.</span><span class="sxs-lookup"><span data-stu-id="f094c-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="f094c-183">Når du har oppgradert, kan du ikke tilbakestille til kontonøkkelen etter oppdateringen.</span><span class="sxs-lookup"><span data-stu-id="f094c-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="f094c-184">Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="f094c-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="f094c-185">Du kan ikke endre informasjon om en **beholder** når du oppdaterer tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="f094c-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="f094c-186">Tilbakestille et eksisterende miljø</span><span class="sxs-lookup"><span data-stu-id="f094c-186">Reset an existing environment</span></span>

<span data-ttu-id="f094c-187">Du kan tilbakestille et miljø til en tom tilstand hvis du vil slette alle konfigurasjoner og fjerne data som er hentet inn.</span><span class="sxs-lookup"><span data-stu-id="f094c-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="f094c-188">Gå til **Admin** > **System** > **Om**.</span><span class="sxs-lookup"><span data-stu-id="f094c-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="f094c-189">Velg **Tilbakestill**.</span><span class="sxs-lookup"><span data-stu-id="f094c-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="f094c-190">Bekreft slettingen ved å skrive inn miljønavnet og velge **Tilbakestill**.</span><span class="sxs-lookup"><span data-stu-id="f094c-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="f094c-191">Slette et eksisterende miljø</span><span class="sxs-lookup"><span data-stu-id="f094c-191">Delete an existing environment</span></span>

1. <span data-ttu-id="f094c-192">Gå til **Admin** > **System** > **Om**.</span><span class="sxs-lookup"><span data-stu-id="f094c-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="f094c-193">Velg **Slett**.</span><span class="sxs-lookup"><span data-stu-id="f094c-193">Select **Delete**.</span></span>

1. <span data-ttu-id="f094c-194">Bekreft slettingen ved å angi miljønavnet og velge **Slett**.</span><span class="sxs-lookup"><span data-stu-id="f094c-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
