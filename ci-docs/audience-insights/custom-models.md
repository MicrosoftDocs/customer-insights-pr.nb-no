---
title: Egendefinerte modeller for maskinlæring | Microsoft Docs
description: Arbeide med egendefinerte modeller fra Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305655"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="9628b-103">Egendefinerte modeller for maskinlæring</span><span class="sxs-lookup"><span data-stu-id="9628b-103">Custom machine learning models</span></span>

<span data-ttu-id="9628b-104">**Intelligens** > **Egendefinerte modeller** lar deg behandle arbeidsflyter basert på Azure Machine Learning-modeller.</span><span class="sxs-lookup"><span data-stu-id="9628b-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="9628b-105">Arbeidsflyter hjelper deg med å velge dataene du vil generere innsikt fra, og tilordne resultatene til dine ensartede kundedata.</span><span class="sxs-lookup"><span data-stu-id="9628b-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="9628b-106">Hvis du vil ha mer informasjon om utforming av egen definerte ML-modeller, kan du se [Bruk Azure Machine Learning-baserte modeller](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="9628b-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="9628b-107">Ansvarlig kunstig intelligens</span><span class="sxs-lookup"><span data-stu-id="9628b-107">Responsible AI</span></span>

<span data-ttu-id="9628b-108">Prognoser tilbyr funksjoner for å skape bedre kundeopplevelser, forbedre forretningsmulighetene og omsetningsstrømmer.</span><span class="sxs-lookup"><span data-stu-id="9628b-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="9628b-109">Vi anbefaler på det sterkeste at du balanserer verdien i prediksjon mot innvirkningen den har, og vektlegger det som blir introdusert, på en etisk måte.</span><span class="sxs-lookup"><span data-stu-id="9628b-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="9628b-110">Lær mer om hvordan Microsoft [håndterer ansvarlig kunstig intelligens](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="9628b-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="9628b-111">Du kan også lære om [teknikker og prosesser for ansvarlig maskinlæring](/azure/machine-learning/concept-responsible-ml) som er spesifikke for Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="9628b-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9628b-112">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="9628b-112">Prerequisites</span></span>

- <span data-ttu-id="9628b-113">Denne funksjonen støtter for øyeblikket nettjenester som publiseres via [Machine Learning Studio (klassisk)](https://studio.azureml.net) og [bunkepipeliner i Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="9628b-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="9628b-114">Du trenger en Azure Data Lake Gen2-lagringskonto som er tilknyttet Azure Studio-forekomsten, for å bruke denne funksjonen.</span><span class="sxs-lookup"><span data-stu-id="9628b-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="9628b-115">Hvis du vil ha mer informasjon, se [Opprett en Azure Data Lake Storage Gen2-lagringskonto](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="9628b-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="9628b-116">For Azure Machine Learning-arbeidsområder med pipeliner trenger du tillatelse som Eier eller Administrator for brukertilgang til Azure Machine Learning-arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="9628b-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9628b-117">Data overføres mellom Customer Insights-forekomstene dine og de valgte Azure-webtjenestene eller -pipelinene i arbeidsflyten.</span><span class="sxs-lookup"><span data-stu-id="9628b-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="9628b-118">Når du overfører data til en Azure-tjeneste, må du sørge for at tjenesten er konfigurert til å behandle data på måten og stedet som er nødvendig for å overholde eventuelle juridiske eller forskriftsmessige krav for disse dataene for organisasjonen din.</span><span class="sxs-lookup"><span data-stu-id="9628b-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="9628b-119">Legge til en ny arbeidsflyt</span><span class="sxs-lookup"><span data-stu-id="9628b-119">Add a new workflow</span></span>

1. <span data-ttu-id="9628b-120">Gå til **Intelligens** > **Egendefinerte modeller**, og velg **Ny arbeidsflyt**.</span><span class="sxs-lookup"><span data-stu-id="9628b-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="9628b-121">Gi den egendefinerte modellen et gjenkjennelig navn i **Navn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="9628b-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9628b-122">![Skjermbilde av ruten Ny arbeidsflyt](media/new-workflowv2.png "Skjermbilde av ruten Ny arbeidsflyt")</span><span class="sxs-lookup"><span data-stu-id="9628b-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="9628b-123">Velg organisasjonen som inneholder webtjenesten, i **Leier som inneholder webtjenesten**.</span><span class="sxs-lookup"><span data-stu-id="9628b-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="9628b-124">Hvis Azure Machine Learning-abonnementet ditt er i en annen leier enn Customer Insights, velger du **Logg på** med legitimasjonen din for den valgte organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="9628b-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="9628b-125">Velg **arbeidsområdene** som er knyttet til nettjenesten.</span><span class="sxs-lookup"><span data-stu-id="9628b-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="9628b-126">To deler vises, én for Azure Machine Learning v1 (Machine Learning Studio (klassisk)) og Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="9628b-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="9628b-127">Hvis du ikke er sikker på hvilket arbeidsområde som er det riktige for Machine Learning Studio (klassisk)-nettjenesten, velger du **Hvilken som helst**.</span><span class="sxs-lookup"><span data-stu-id="9628b-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="9628b-128">Velg Machine Learning Studio (klassisk)-nettjenesten eller Azure Machine Learning-pipelinen i rullegardinmenyen **Nettjeneste som inneholder modellen**.</span><span class="sxs-lookup"><span data-stu-id="9628b-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="9628b-129">Velg deretter **Neste**.</span><span class="sxs-lookup"><span data-stu-id="9628b-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="9628b-130">Lær mer om [publisering av en nettjeneste i Machine Learning Studio (klassisk)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="9628b-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="9628b-131">Lær mer om [publisering av en pipeline i Azure Machine Learning ved hjelp av designeren](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK-et](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="9628b-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="9628b-132">Pipelinen må publiseres under et [pipelineendepunkt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="9628b-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="9628b-133">For hver **nettjenesteinndata** velger du den samsvarende **enheten** fra målgruppeinnsikt og velger **Neste**.</span><span class="sxs-lookup"><span data-stu-id="9628b-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="9628b-134">Arbeidsflyten for egendefinert modell bruker heuristikk til å tilordne inndatafeltene for nettjenesten til enhetsattributtene basert på navnet og datatypen for feltet.</span><span class="sxs-lookup"><span data-stu-id="9628b-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="9628b-135">Det vises en feilmelding hvis et nettjenestefelt ikke kan tilordnes til en enhet.</span><span class="sxs-lookup"><span data-stu-id="9628b-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9628b-136">![Konfigurere en arbeidsflyt](media/intelligence-screen2-updated.png "Konfigurere en arbeidsflyt")</span><span class="sxs-lookup"><span data-stu-id="9628b-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="9628b-137">I trinnet **Parametere for modellutdata** angir du følgende egenskaper:</span><span class="sxs-lookup"><span data-stu-id="9628b-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="9628b-138">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="9628b-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="9628b-139">Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene fra nettjenesten skal flytes.</span><span class="sxs-lookup"><span data-stu-id="9628b-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="9628b-140">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="9628b-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="9628b-141">Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene for pilelinen skal flytes.</span><span class="sxs-lookup"><span data-stu-id="9628b-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="9628b-142">Velg **Navn på parameter for utdatalager** for bunkepipelinen fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="9628b-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="9628b-143">Velg **Navn på parameter for utdatabane** for bunkepipelinen fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="9628b-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="9628b-144">![Parameterrute for modelutdata](media/intelligence-screen3-outputparameters.png "Parameterrute for modelutdata")</span><span class="sxs-lookup"><span data-stu-id="9628b-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="9628b-145">Velg det tilsvarende attributtet fra rullegardinlisten **Kunde-ID i resultater** som identifiserer kunder, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="9628b-145">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9628b-146">![Relater resultater til kundedataruten](media/intelligence-screen4-relatetocustomer.png "Relater resultater til kundedataruten")</span><span class="sxs-lookup"><span data-stu-id="9628b-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="9628b-147">Du ser skjermbildet **Arbeidsflyt lagret** med detaljer om arbeidsflyten.</span><span class="sxs-lookup"><span data-stu-id="9628b-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="9628b-148">Hvis du har konfigurert en arbeidsflyt for en Azure Machine Learning-pipeline, vil målgruppe innsikt legge ved arbeidsområdet som inneholder pipelinen.</span><span class="sxs-lookup"><span data-stu-id="9628b-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="9628b-149">Målgruppeinnsikt får en **Bidragsyter**-rolle på Azure-arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="9628b-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="9628b-150">Velg **Ferdig**.</span><span class="sxs-lookup"><span data-stu-id="9628b-150">Select **Done**.</span></span>

1. <span data-ttu-id="9628b-151">Du kan nå kjøre arbeidsflyten fra siden **Egendefinerte modeller**.</span><span class="sxs-lookup"><span data-stu-id="9628b-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="9628b-152">Redigere en arbeidsflyt</span><span class="sxs-lookup"><span data-stu-id="9628b-152">Edit a workflow</span></span>

1. <span data-ttu-id="9628b-153">På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet, og deretter velger du **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="9628b-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="9628b-154">Du kan oppdatere det gjenkjennelige navnet på arbeidsflyten i **Visningsnavn**-feltet, men du kan ikke endre den konfigurerte nettjenesten eller pipelinen.</span><span class="sxs-lookup"><span data-stu-id="9628b-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="9628b-155">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="9628b-155">Select **Next**.</span></span>

1. <span data-ttu-id="9628b-156">For hver **nettjenesteinndata** kan du oppdatere den samsvarende **enheten** fra målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="9628b-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="9628b-157">Velg deretter **Neste**.</span><span class="sxs-lookup"><span data-stu-id="9628b-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="9628b-158">I trinnet **Parametere for modellutdata** angir du følgende egenskaper:</span><span class="sxs-lookup"><span data-stu-id="9628b-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="9628b-159">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="9628b-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="9628b-160">Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene fra nettjenesten skal flytes.</span><span class="sxs-lookup"><span data-stu-id="9628b-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="9628b-161">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="9628b-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="9628b-162">Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene for pilelinen skal flytes.</span><span class="sxs-lookup"><span data-stu-id="9628b-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="9628b-163">Velg **Navn på parameter for utdatalager** for testpipelinen.</span><span class="sxs-lookup"><span data-stu-id="9628b-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="9628b-164">Velg **Navn på parameter for utdatabane** for testpipelinen.</span><span class="sxs-lookup"><span data-stu-id="9628b-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="9628b-165">Velg det tilsvarende attributtet fra rullegardinlisten **Kunde-ID i resultater** som identifiserer kunder, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="9628b-165">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="9628b-166">Velg et attributt fra beslutningsutdataene med verdier som ligner på kunde-ID-kolonnen for kundeenheten.</span><span class="sxs-lookup"><span data-stu-id="9628b-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="9628b-167">Hvis du ikke har en slik kolonne i datasettet, velger du et attributt som unikt identifiserer raden.</span><span class="sxs-lookup"><span data-stu-id="9628b-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="9628b-168">Kjøre en arbeidsflyt</span><span class="sxs-lookup"><span data-stu-id="9628b-168">Run a workflow</span></span>

1. <span data-ttu-id="9628b-169">På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet.</span><span class="sxs-lookup"><span data-stu-id="9628b-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="9628b-170">Velg **Kjør**.</span><span class="sxs-lookup"><span data-stu-id="9628b-170">Select **Run**.</span></span>

<span data-ttu-id="9628b-171">Arbeidsflyten kjøres også automatisk med hver planlagte oppdatering.</span><span class="sxs-lookup"><span data-stu-id="9628b-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="9628b-172">Lær mer om [konfigurering av planlagte oppdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9628b-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="9628b-173">Slette en arbeidsflyt</span><span class="sxs-lookup"><span data-stu-id="9628b-173">Delete a workflow</span></span>

1. <span data-ttu-id="9628b-174">På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet.</span><span class="sxs-lookup"><span data-stu-id="9628b-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="9628b-175">Velg **Slett**, og bekreft slettingen.</span><span class="sxs-lookup"><span data-stu-id="9628b-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="9628b-176">Arbeidsflyten blir slettet.</span><span class="sxs-lookup"><span data-stu-id="9628b-176">Your workflow will be deleted.</span></span> <span data-ttu-id="9628b-177">[Enheten](entities.md) som ble opprettet da du opprettet arbeidsflyten, vedvarer og kan vises fra **Enheter**-siden.</span><span class="sxs-lookup"><span data-stu-id="9628b-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="9628b-178">Resultater</span><span class="sxs-lookup"><span data-stu-id="9628b-178">Results</span></span>

<span data-ttu-id="9628b-179">Resultater fra en arbeidsflyt lagres i enheten som er konfigurert under fasen Parameter for modellutdata.</span><span class="sxs-lookup"><span data-stu-id="9628b-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="9628b-180">Du kan få tilgang til disse dataene fra [enhetssiden](entities.md) eller med [API-tilgang](apis.md).</span><span class="sxs-lookup"><span data-stu-id="9628b-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="9628b-181">API-tilgang</span><span class="sxs-lookup"><span data-stu-id="9628b-181">API Access</span></span>

<span data-ttu-id="9628b-182">Bruk følgende format for den bestemte OData-spørringen for å hente data fra en egendefinert modellenhet:</span><span class="sxs-lookup"><span data-stu-id="9628b-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="9628b-183">Erstatt `<your instance id>` med ID-en for Customer Insights-miljøet ditt, som du finner på adresselinjen i nettleseren når du går til Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9628b-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="9628b-184">Erstatt `<custom model output entity>` med enhetsnavnet du oppgav under trinnet Parametere for modellutdata under konfigurasjonen av den egendefinerte modellen.</span><span class="sxs-lookup"><span data-stu-id="9628b-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="9628b-185">Erstatt `<guid value>` med kunde-ID-en for kunden du vil ha tilgang til oppføringen for.</span><span class="sxs-lookup"><span data-stu-id="9628b-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="9628b-186">Du finner vanligvis denne ID-en på [kundeprofilsiden](customer-profiles.md) i CustomerID-feltet.</span><span class="sxs-lookup"><span data-stu-id="9628b-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="9628b-187">Vanlige spørsmål</span><span class="sxs-lookup"><span data-stu-id="9628b-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="9628b-188">Hvorfor kan jeg ikke se pipelinjen min når jeg konfigurerer en arbeidsflyt for en egendefinert modell?</span><span class="sxs-lookup"><span data-stu-id="9628b-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="9628b-189">Dette problemet skyldes ofte et konfigurasjonsproblem i pipelinen.</span><span class="sxs-lookup"><span data-stu-id="9628b-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="9628b-190">Kontroller at [inndataparameteren er konfigurert](azure-machine-learning-experiments.md#dataset-configuration), og at [utdatadatalageret og baneparameterne](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) også er konfigurert.</span><span class="sxs-lookup"><span data-stu-id="9628b-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="9628b-191">Hva betyr feilmeldingen "Kunne ikke lagre en intelligensarbeidsflyt"?</span><span class="sxs-lookup"><span data-stu-id="9628b-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="9628b-192">Brukerne ser vanligvis denne feilmeldingen hvis de ikke har rettigheter som eier eller administrator for brukertilgang på arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="9628b-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="9628b-193">Brukeren må ha et høyere tillatelsesnivå for at Customer Insights skal kunne behandle arbeidsflyten som en tjeneste, i stedet for å bruke brukerlegitimasjonen for påfølgende kjøringer av arbeidsflyten.</span><span class="sxs-lookup"><span data-stu-id="9628b-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
