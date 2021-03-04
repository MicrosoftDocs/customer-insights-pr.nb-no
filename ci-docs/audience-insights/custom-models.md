---
title: Egendefinerte modeller for maskinlæring | Microsoft Docs
description: Arbeide med egendefinerte modeller fra Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267246"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="770a4-103">Egendefinerte modeller for maskinlæring</span><span class="sxs-lookup"><span data-stu-id="770a4-103">Custom machine learning models</span></span>

<span data-ttu-id="770a4-104">**Intelligens** > **Egendefinerte modeller** lar deg behandle arbeidsflyter basert på Azure Machine Learning-modeller.</span><span class="sxs-lookup"><span data-stu-id="770a4-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="770a4-105">Arbeidsflyter hjelper deg med å velge dataene du vil generere innsikt fra, og tilordne resultatene til dine ensartede kundedata.</span><span class="sxs-lookup"><span data-stu-id="770a4-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="770a4-106">Hvis du vil ha mer informasjon om utforming av egen definerte ML-modeller, kan du se [Bruk Azure Machine Learning-baserte modeller](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="770a4-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="770a4-107">Ansvarlig kunstig intelligens</span><span class="sxs-lookup"><span data-stu-id="770a4-107">Responsible AI</span></span>

<span data-ttu-id="770a4-108">Prognoser tilbyr funksjoner for å skape bedre kundeopplevelser, forbedre forretningsmulighetene og omsetningsstrømmer.</span><span class="sxs-lookup"><span data-stu-id="770a4-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="770a4-109">Vi anbefaler på det sterkeste at du balanserer verdien i prediksjon mot innvirkningen den har, og vektlegger det som blir introdusert, på en etisk måte.</span><span class="sxs-lookup"><span data-stu-id="770a4-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="770a4-110">Lær mer om hvordan Microsoft [håndterer ansvarlig kunstig intelligens](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="770a4-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="770a4-111">Du kan også lære om [teknikker og prosesser for ansvarlig maskinlæring](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) som er spesifikke for Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="770a4-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="770a4-112">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="770a4-112">Prerequisites</span></span>

- <span data-ttu-id="770a4-113">Denne funksjonen støtter for øyeblikket nettjenester som publiseres via [Machine Learning Studio (klassisk)](https://studio.azureml.net) og [bunkepipeliner i Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="770a4-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="770a4-114">Du trenger en Azure Data Lake Gen2-lagringskonto som er tilknyttet Azure Studio-forekomsten, for å bruke denne funksjonen.</span><span class="sxs-lookup"><span data-stu-id="770a4-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="770a4-115">Hvis du vil ha mer informasjon, se [Opprette en Azure Data Lake Storage Gen2-lagringskonto](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="770a4-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="770a4-116">Legge til en ny arbeidsflyt</span><span class="sxs-lookup"><span data-stu-id="770a4-116">Add a new workflow</span></span>

1. <span data-ttu-id="770a4-117">Gå til **Intelligens** > **Egendefinerte modeller**, og velg **Ny arbeidsflyt**.</span><span class="sxs-lookup"><span data-stu-id="770a4-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="770a4-118">Gi den egendefinerte modellen et gjenkjennelig navn i **Navn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="770a4-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="770a4-119">![Skjermbilde av ruten Ny arbeidsflyt](media/new-workflowv2.png "Skjermbilde av ruten Ny arbeidsflyt")</span><span class="sxs-lookup"><span data-stu-id="770a4-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="770a4-120">Velg organisasjonen som inneholder webtjenesten, i **Leier som inneholder webtjenesten**.</span><span class="sxs-lookup"><span data-stu-id="770a4-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="770a4-121">Hvis Azure Machine Learning-abonnementet ditt er i en annen leier enn Customer Insights, velger du **Logg på** med legitimasjonen din for den valgte organisasjonen.</span><span class="sxs-lookup"><span data-stu-id="770a4-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="770a4-122">Velg **arbeidsområdene** som er knyttet til nettjenesten.</span><span class="sxs-lookup"><span data-stu-id="770a4-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="770a4-123">To deler vises, én for Azure Machine Learning v1 (Machine Learning Studio (klassisk)) og Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="770a4-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="770a4-124">Hvis du ikke er sikker på hvilket arbeidsområde som er det riktige for Machine Learning Studio (klassisk)-nettjenesten, velger du **Hvilken som helst**.</span><span class="sxs-lookup"><span data-stu-id="770a4-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="770a4-125">Velg Machine Learning Studio (klassisk)-nettjenesten eller Azure Machine Learning-pipelinen i rullegardinmenyen **Nettjeneste som inneholder modellen**.</span><span class="sxs-lookup"><span data-stu-id="770a4-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="770a4-126">Velg deretter **Neste**.</span><span class="sxs-lookup"><span data-stu-id="770a4-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="770a4-127">Lær mer om [publisering av en nettjeneste i Machine Learning Studio (klassisk)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="770a4-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="770a4-128">Lær mer om [publisering av en pipeline i Azure Machine Learning ved hjelp av designeren](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK-et](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="770a4-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="770a4-129">Pipelinen må publiseres under et [pipelineendepunkt](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="770a4-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="770a4-130">For hver **nettjenesteinndata** velger du den samsvarende **enheten** fra målgruppeinnsikt og velger **Neste**.</span><span class="sxs-lookup"><span data-stu-id="770a4-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="770a4-131">Arbeidsflyten for egendefinert modell bruker heuristikk til å tilordne inndatafeltene for nettjenesten til enhetsattributtene basert på navnet og datatypen for feltet.</span><span class="sxs-lookup"><span data-stu-id="770a4-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="770a4-132">Det vises en feilmelding hvis et nettjenestefelt ikke kan tilordnes til en enhet.</span><span class="sxs-lookup"><span data-stu-id="770a4-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="770a4-133">![Konfigurere en arbeidsflyt](media/intelligence-screen2-updated.png "Konfigurere en arbeidsflyt")</span><span class="sxs-lookup"><span data-stu-id="770a4-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="770a4-134">I trinnet **Parametere for modellutdata** angir du følgende egenskaper:</span><span class="sxs-lookup"><span data-stu-id="770a4-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="770a4-135">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="770a4-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="770a4-136">Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene fra nettjenesten skal flytes.</span><span class="sxs-lookup"><span data-stu-id="770a4-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="770a4-137">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="770a4-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="770a4-138">Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene for pilelinen skal flytes.</span><span class="sxs-lookup"><span data-stu-id="770a4-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="770a4-139">Velg **Navn på parameter for utdatalager** for bunkepipelinen fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="770a4-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="770a4-140">Velg **Navn på parameter for utdatabane** for bunkepipelinen fra rullegardinmenyen.</span><span class="sxs-lookup"><span data-stu-id="770a4-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="770a4-141">![Parameterrute for modelutdata](media/intelligence-screen3-outputparameters.png "Parameterrute for modelutdata")</span><span class="sxs-lookup"><span data-stu-id="770a4-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="770a4-142">Velg det tilsvarende attributtet fra rullegardinlisten **Kunde-ID i resultater** som er identifiserer kunder, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="770a4-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="770a4-143">![Relater resultater til kundedataruten](media/intelligence-screen4-relatetocustomer.png "Relater resultater til kundedataruten")</span><span class="sxs-lookup"><span data-stu-id="770a4-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="770a4-144">Du ser skjermbildet **Arbeidsflyt lagret** med detaljer om arbeidsflyten.</span><span class="sxs-lookup"><span data-stu-id="770a4-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="770a4-145">Hvis du har konfigurert en arbeidsflyt for en Azure Machine Learning-pipeline, vil målgruppe innsikt legge ved arbeidsområdet som inneholder pipelinen.</span><span class="sxs-lookup"><span data-stu-id="770a4-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="770a4-146">Målgruppeinnsikt får en **Bidragsyter**-rolle på Azure-arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="770a4-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="770a4-147">Velg **Ferdig**.</span><span class="sxs-lookup"><span data-stu-id="770a4-147">Select **Done**.</span></span>

1. <span data-ttu-id="770a4-148">Du kan nå kjøre arbeidsflyten fra siden **Egendefinerte modeller**.</span><span class="sxs-lookup"><span data-stu-id="770a4-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="770a4-149">Redigere en arbeidsflyt</span><span class="sxs-lookup"><span data-stu-id="770a4-149">Edit a workflow</span></span>

1. <span data-ttu-id="770a4-150">På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet, og deretter velger du **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="770a4-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="770a4-151">Du kan oppdatere det gjenkjennelige navnet på arbeidsflyten i **Visningsnavn**-feltet, men du kan ikke endre den konfigurerte nettjenesten eller pipelinen.</span><span class="sxs-lookup"><span data-stu-id="770a4-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="770a4-152">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="770a4-152">Select **Next**.</span></span>

1. <span data-ttu-id="770a4-153">For hver **nettjenesteinndata** kan du oppdatere den samsvarende **enheten** fra målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="770a4-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="770a4-154">Velg deretter **Neste**.</span><span class="sxs-lookup"><span data-stu-id="770a4-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="770a4-155">I trinnet **Parametere for modellutdata** angir du følgende egenskaper:</span><span class="sxs-lookup"><span data-stu-id="770a4-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="770a4-156">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="770a4-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="770a4-157">Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene fra nettjenesten skal flytes.</span><span class="sxs-lookup"><span data-stu-id="770a4-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="770a4-158">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="770a4-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="770a4-159">Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene for pilelinen skal flytes.</span><span class="sxs-lookup"><span data-stu-id="770a4-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="770a4-160">Velg **Navn på parameter for utdatalager** for testpipelinen.</span><span class="sxs-lookup"><span data-stu-id="770a4-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="770a4-161">Velg **Navn på parameter for utdatabane** for testpipelinen.</span><span class="sxs-lookup"><span data-stu-id="770a4-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="770a4-162">Velg det tilsvarende attributtet fra rullegardinlisten **Kunde-ID i resultater** som er identifiserer kunder, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="770a4-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="770a4-163">Du må velge et attributt fra beslutningsutdataene med verdier som ligner på kunde-ID-kolonnen for kundeenheten.</span><span class="sxs-lookup"><span data-stu-id="770a4-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="770a4-164">Hvis du ikke har en slik kolonne i datasettet, velger du et attributt som unikt identifiserer raden.</span><span class="sxs-lookup"><span data-stu-id="770a4-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="770a4-165">Kjøre en arbeidsflyt</span><span class="sxs-lookup"><span data-stu-id="770a4-165">Run a workflow</span></span>

1. <span data-ttu-id="770a4-166">På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet.</span><span class="sxs-lookup"><span data-stu-id="770a4-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="770a4-167">Velg **Kjør**.</span><span class="sxs-lookup"><span data-stu-id="770a4-167">Select **Run**.</span></span>

<span data-ttu-id="770a4-168">Arbeidsflyten kjøres også automatisk med hver planlagte oppdatering.</span><span class="sxs-lookup"><span data-stu-id="770a4-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="770a4-169">Lær mer om [konfigurering av planlagte oppdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="770a4-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="770a4-170">Slette en arbeidsflyt</span><span class="sxs-lookup"><span data-stu-id="770a4-170">Delete a workflow</span></span>

1. <span data-ttu-id="770a4-171">På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet.</span><span class="sxs-lookup"><span data-stu-id="770a4-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="770a4-172">Velg **Slett**, og bekreft slettingen.</span><span class="sxs-lookup"><span data-stu-id="770a4-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="770a4-173">Arbeidsflyten blir slettet.</span><span class="sxs-lookup"><span data-stu-id="770a4-173">Your workflow will be deleted.</span></span> <span data-ttu-id="770a4-174">[Enheten](entities.md) som ble opprettet da du opprettet arbeidsflyten, vedvarer og kan vises fra **Enheter**-siden.</span><span class="sxs-lookup"><span data-stu-id="770a4-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]