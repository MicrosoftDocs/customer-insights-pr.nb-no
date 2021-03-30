---
title: Opprette og behandle miljøer
description: Lær hvordan du registrerer deg for tjenesten og hvordan du administrerer miljøer.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598305"
---
# <a name="manage-environments"></a><span data-ttu-id="ca792-103">Behandle miljøer</span><span class="sxs-lookup"><span data-stu-id="ca792-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ca792-104">Denne artikkelen forklarer hvordan du oppretter en ny organisasjon og hvordan du klargjør et miljø.</span><span class="sxs-lookup"><span data-stu-id="ca792-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="ca792-105">Registrere og opprette en organisasjon</span><span class="sxs-lookup"><span data-stu-id="ca792-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="ca792-106">Gå til [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/)-nettsted.</span><span class="sxs-lookup"><span data-stu-id="ca792-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="ca792-107">Velg **Komme i gang**.</span><span class="sxs-lookup"><span data-stu-id="ca792-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="ca792-108">Velg ønsket registreringsscenario, og velg den tilsvarende koblingen.</span><span class="sxs-lookup"><span data-stu-id="ca792-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="ca792-109">Godta vilkårene, og velg **Fortsett** for å starte opprettingen av organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="ca792-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="ca792-110">Når du har opprettet miljøet, blir du omdirigert til [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="ca792-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="ca792-111">Bruk demonstrasjonsmiljøet til å utforske appen, eller opprett et nytt miljø ved å følge fremgangsmåten i neste del.</span><span class="sxs-lookup"><span data-stu-id="ca792-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="ca792-112">Etter at du har angitt miljøinnstillingene, velger du **Opprett**.</span><span class="sxs-lookup"><span data-stu-id="ca792-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="ca792-113">Du blir logget på etter at miljøet er opprettet.</span><span class="sxs-lookup"><span data-stu-id="ca792-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="ca792-114">Opprette et miljø i en eksisterende organisasjon</span><span class="sxs-lookup"><span data-stu-id="ca792-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="ca792-115">Du kan opprette et nytt miljø på to måter.</span><span class="sxs-lookup"><span data-stu-id="ca792-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="ca792-116">Du kan enten spesifisere en helt ny konfigurasjon, eller du kan kopiere noen konfigurasjonsinnstillinger fra et eksisterende miljø.</span><span class="sxs-lookup"><span data-stu-id="ca792-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="ca792-117">Slik oppretter du et miljø:</span><span class="sxs-lookup"><span data-stu-id="ca792-117">To create an environment:</span></span>

1. <span data-ttu-id="ca792-118">Velg **Miljø**-velgeren i overskriften i appen.</span><span class="sxs-lookup"><span data-stu-id="ca792-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="ca792-119">Velg **Ny**.</span><span class="sxs-lookup"><span data-stu-id="ca792-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ca792-120">![Miljøinnstillinger](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="ca792-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="ca792-121">I dialogboksen **Opprett nytt miljø** velger du **Nytt miljø**.</span><span class="sxs-lookup"><span data-stu-id="ca792-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="ca792-122">Hvis du vil [kopiere data fra det gjeldende miljøet](#additional-considerations-for-copy-configuration-preview), velger du **Kopier fra eksisterende miljø**.</span><span class="sxs-lookup"><span data-stu-id="ca792-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="ca792-123">Det vises en liste over alle tilgjengelige miljøer i organisasjonen, der du kan kopiere data fra.</span><span class="sxs-lookup"><span data-stu-id="ca792-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="ca792-124">Angi følgende detaljer:</span><span class="sxs-lookup"><span data-stu-id="ca792-124">Provide the following details:</span></span>
   - <span data-ttu-id="ca792-125">**Navn**: Navnet på dette miljøet.</span><span class="sxs-lookup"><span data-stu-id="ca792-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="ca792-126">Dette feltet er allerede fylt ut hvis du har kopiert et eksisterende miljø, men du kan endre det.</span><span class="sxs-lookup"><span data-stu-id="ca792-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="ca792-127">**Område**: Området som servicen er distribuert i, og driftet.</span><span class="sxs-lookup"><span data-stu-id="ca792-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="ca792-128">**Type**: Velg om du vil opprette et produksjons- eller sandkassemiljø.</span><span class="sxs-lookup"><span data-stu-id="ca792-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="ca792-129">Du kan eventuelt velge **Avanserte innstillinger**:</span><span class="sxs-lookup"><span data-stu-id="ca792-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="ca792-130">**Lagre alle data i**: Angir hvor du vil lagre utdataene som er generert av Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ca792-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="ca792-131">Du har to alternativer: **Customer Insights-lagring** (en Azure Data Lake administrert av Customer Insights-teamet) og **Azure Data Lake Storage Gen2** (din egen Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="ca792-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="ca792-132">Som standard er det merket av for lagringsalternativet Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ca792-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ca792-133">Når du lagrer data i Azure Data Lake Storage, godtar du at dataene overføres til og lagres i den riktige geografiske plasseringen for denne Azure Storage-kontoen, som kan variere fra der dataene lagres i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ca792-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="ca792-134">Finn ut mer om Microsofts klareringssenter.</span><span class="sxs-lookup"><span data-stu-id="ca792-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="ca792-135">For øyeblikket lagres enheter alltid i den Customer Insights-administrerte datasjøen.</span><span class="sxs-lookup"><span data-stu-id="ca792-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="ca792-136">Vi støtter bare Azure Data Lake Gen2-lagringskontoer fra det samme Azure-området du valgte da du opprettet miljøet.</span><span class="sxs-lookup"><span data-stu-id="ca792-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="ca792-137">Vi støtter bare Azure Data Lake Gen2 Hierarkisk navneområde (HNS)-aktiverte lagringskontoer.</span><span class="sxs-lookup"><span data-stu-id="ca792-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="ca792-138">For Azure Data Lake Storage Gen2 kan du velge mellom et ressursbasert alternativ og et abonnementsbasert alternativ for godkjenning.</span><span class="sxs-lookup"><span data-stu-id="ca792-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="ca792-139">Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="ca792-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="ca792-140">**Beholder**-navnet kan ikke endres, og det vil være "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="ca792-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="ca792-141">Hvis du vil bruke [prediksjoner](predictions.md) eller konfigurere datadeling med programmer og løsninger basert på Microsoft Dataverse, må du oppgi URL-adressen for Microsoft Dataverse-miljøet under **Konfigurere datadeling med Microsoft Dataverse og aktivere flere funksjoner**.</span><span class="sxs-lookup"><span data-stu-id="ca792-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="ca792-142">Velg **Aktiver datadeling** for å dele Customer Insights-utdata med en Microsoft Dataverse-administrert datasjø.</span><span class="sxs-lookup"><span data-stu-id="ca792-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="ca792-143">Det er for øyeblikket ikke støtte for datadeling med Microsoft Dataverse-styrt datasjø når du lagrer alle dataene i din egen Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="ca792-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="ca792-144">[Prediksjon av manglende miljøer i en enhet](predictions.md) støttes for øyeblikket ikke når du aktiverer datadeling med Microsoft Dataverse-administrert datasjø.</span><span class="sxs-lookup"><span data-stu-id="ca792-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="ca792-145">![Konfigurasjonsalternativer for å aktivere datadeling med Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="ca792-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="ca792-146">Når du kjører prosesser, for eksempel datainntak eller segmentopprettelse, blir tilsvarende mapper opprettet i lagringskontoen du angav ovenfor.</span><span class="sxs-lookup"><span data-stu-id="ca792-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="ca792-147">Datafiler og model.json-filer opprettes og legges til i de respektive undermappene basert på prosessen du kjører.</span><span class="sxs-lookup"><span data-stu-id="ca792-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="ca792-148">Hvis du oppretter flere miljøer i Customer Insights og velger å lagre enhetene fra disse miljøene i lagringskontoen, blir det opprettet separate mapper for hvert miljø med ci_<environmentid> i beholderen.</span><span class="sxs-lookup"><span data-stu-id="ca792-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="ca792-149">Tilleggshensyn for kopieringskonfigurasjon (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="ca792-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="ca792-150">Følgende konfigurasjonsinnstillinger kopieres:</span><span class="sxs-lookup"><span data-stu-id="ca792-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="ca792-151">Funksjonskonfigurasjoner</span><span class="sxs-lookup"><span data-stu-id="ca792-151">Feature configurations</span></span>
- <span data-ttu-id="ca792-152">Samlede/importerte datakilder</span><span class="sxs-lookup"><span data-stu-id="ca792-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="ca792-153">Konfigurasjon av forening av data (tilordning, samsvar, sammenslåing)</span><span class="sxs-lookup"><span data-stu-id="ca792-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="ca792-154">Segmenter</span><span class="sxs-lookup"><span data-stu-id="ca792-154">Segments</span></span>
- <span data-ttu-id="ca792-155">Mål</span><span class="sxs-lookup"><span data-stu-id="ca792-155">Measures</span></span>
- <span data-ttu-id="ca792-156">Relasjoner</span><span class="sxs-lookup"><span data-stu-id="ca792-156">Relationships</span></span>
- <span data-ttu-id="ca792-157">Aktiviteter</span><span class="sxs-lookup"><span data-stu-id="ca792-157">Activities</span></span>
- <span data-ttu-id="ca792-158">Søk- og filterindeks</span><span class="sxs-lookup"><span data-stu-id="ca792-158">Search & filter Index</span></span>
- <span data-ttu-id="ca792-159">Eksportmål</span><span class="sxs-lookup"><span data-stu-id="ca792-159">Export destinations</span></span>
- <span data-ttu-id="ca792-160">Planlagt oppdatering</span><span class="sxs-lookup"><span data-stu-id="ca792-160">Scheduled refresh</span></span>
- <span data-ttu-id="ca792-161">Suppleringer</span><span class="sxs-lookup"><span data-stu-id="ca792-161">Enrichments</span></span>
- <span data-ttu-id="ca792-162">Modelladministrasjon</span><span class="sxs-lookup"><span data-stu-id="ca792-162">Model management</span></span>
- <span data-ttu-id="ca792-163">Rolletildelinger</span><span class="sxs-lookup"><span data-stu-id="ca792-163">Role assignments</span></span>

<span data-ttu-id="ca792-164">Følgende innstillinger kopieres *ikke*:</span><span class="sxs-lookup"><span data-stu-id="ca792-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="ca792-165">Kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="ca792-165">Customer profiles.</span></span>
- <span data-ttu-id="ca792-166">Legitimasjon for datakilde.</span><span class="sxs-lookup"><span data-stu-id="ca792-166">Data source credentials.</span></span> <span data-ttu-id="ca792-167">Du må angi legitimasjonen for hver datakilde og oppdatere datakildene manuelt.</span><span class="sxs-lookup"><span data-stu-id="ca792-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="ca792-168">Datakilder fra Common Data Model-mappe og Common Data Service-administrert sjø.</span><span class="sxs-lookup"><span data-stu-id="ca792-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="ca792-169">Du må opprette disse datakildene manuelt med samme navn som i kildemiljøet.</span><span class="sxs-lookup"><span data-stu-id="ca792-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="ca792-170">Når du kopierer et miljø, vises en bekreftelsesmelding om at det nye miljøet er opprettet.</span><span class="sxs-lookup"><span data-stu-id="ca792-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="ca792-171">Velg **Gå til datakilder** for å vise listen over datakilder.</span><span class="sxs-lookup"><span data-stu-id="ca792-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="ca792-172">Alle datakildene vil vise statusen **Legitimasjon kreves**.</span><span class="sxs-lookup"><span data-stu-id="ca792-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="ca792-173">Rediger datakildene, og angi legitimasjonen for å oppdatere dem.</span><span class="sxs-lookup"><span data-stu-id="ca792-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca792-174">![Kopierte datakilder](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="ca792-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="ca792-175">Etter at du har oppdatert datakildene, går du til **Data** > **Samle**.</span><span class="sxs-lookup"><span data-stu-id="ca792-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="ca792-176">Her finner du innstillinger fra kildemiljøet.</span><span class="sxs-lookup"><span data-stu-id="ca792-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="ca792-177">Rediger dem etter behov, eller velg **Kjør** for å starte prosessen med datasamling og opprette den enhetlige kundeenheten.</span><span class="sxs-lookup"><span data-stu-id="ca792-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="ca792-178">Når datasamlingen er fullført, kan du gå til **Mål** og **Segmenter** for å oppdatere dem også.</span><span class="sxs-lookup"><span data-stu-id="ca792-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="ca792-179">Redigere et eksisterende miljø</span><span class="sxs-lookup"><span data-stu-id="ca792-179">Edit an existing environment</span></span>

<span data-ttu-id="ca792-180">Du kan redigere noen av detaljene i eksisterende miljøer.</span><span class="sxs-lookup"><span data-stu-id="ca792-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="ca792-181">Velg **Miljø**-velgeren i overskriften i appen.</span><span class="sxs-lookup"><span data-stu-id="ca792-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="ca792-182">Velg **Rediger**-ikonet.</span><span class="sxs-lookup"><span data-stu-id="ca792-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="ca792-183">I **Rediger miljø**-boksen kan du oppdatere miljøets **visningsnavn**, men du kan ikke endre **område** eller **type**.</span><span class="sxs-lookup"><span data-stu-id="ca792-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="ca792-184">Hvis et miljø er konfigurert til å lagre data i Azure Data Lake Storage Gen2, kan du oppdatere **kontonøkkelen**.</span><span class="sxs-lookup"><span data-stu-id="ca792-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="ca792-185">Du kan imidlertid ikke endre **Kontonavn** eller **Beholder**-navn.</span><span class="sxs-lookup"><span data-stu-id="ca792-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="ca792-186">Du kan eventuelt oppdatere fra en tilkobling basert på en kontonøkkel til en ressursbasert eller abonnementsbasert tilkobling.</span><span class="sxs-lookup"><span data-stu-id="ca792-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="ca792-187">Når du har oppgradert, kan du ikke tilbakestille til kontonøkkelen etter oppdateringen.</span><span class="sxs-lookup"><span data-stu-id="ca792-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="ca792-188">Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="ca792-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="ca792-189">Du kan ikke endre informasjon om en **beholder** når du oppdaterer tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="ca792-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="ca792-190">Tilbakestille et eksisterende miljø</span><span class="sxs-lookup"><span data-stu-id="ca792-190">Reset an existing environment</span></span>

<span data-ttu-id="ca792-191">Som en administrator kan du tilbakestille et miljø til en tom tilstand hvis du vil slette alle konfigurasjoner og fjerne data som er hentet inn.</span><span class="sxs-lookup"><span data-stu-id="ca792-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="ca792-192">Velg **Miljø**-velgeren i overskriften i appen.</span><span class="sxs-lookup"><span data-stu-id="ca792-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="ca792-193">Velg miljøet du vil tilbakestille, og velg ellipsen **...**.</span><span class="sxs-lookup"><span data-stu-id="ca792-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="ca792-194">Velg **Tilbakestill**-alternativet.</span><span class="sxs-lookup"><span data-stu-id="ca792-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="ca792-195">Bekreft slettingen ved å skrive inn miljønavnet og velge **Tilbakestill**.</span><span class="sxs-lookup"><span data-stu-id="ca792-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="ca792-196">Slett et eksisterende miljø (tilgjengelig bare for administratorer)</span><span class="sxs-lookup"><span data-stu-id="ca792-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="ca792-197">Som en administrator kan du slette et miljø du administrerer.</span><span class="sxs-lookup"><span data-stu-id="ca792-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="ca792-198">Velg **Miljø**-velgeren i overskriften i appen.</span><span class="sxs-lookup"><span data-stu-id="ca792-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="ca792-199">Velg miljøet du vil tilbakestille, og velg ellipsen **...**.</span><span class="sxs-lookup"><span data-stu-id="ca792-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="ca792-200">Velg **Slett**-alternativet.</span><span class="sxs-lookup"><span data-stu-id="ca792-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="ca792-201">Bekreft slettingen ved å angi miljønavnet og velge **Slett**.</span><span class="sxs-lookup"><span data-stu-id="ca792-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]