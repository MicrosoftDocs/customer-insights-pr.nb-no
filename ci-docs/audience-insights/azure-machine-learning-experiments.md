---
title: Azure Machine Learning-eksperimenter
description: Bruk Azure Machine Learning-baserte modeller i Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668781"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="aadec-103">Bruk Azure Machine Learning-baserte modeller</span><span class="sxs-lookup"><span data-stu-id="aadec-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="aadec-104">De ensartede dataene i Dynamics 365 Customer Insights er en kilde for bygging av maskinlæringsmodeller som kan generere ytterligere forretningsinnsikt.</span><span class="sxs-lookup"><span data-stu-id="aadec-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="aadec-105">Customer Insights integreres med Machine Learning Studio (klassisk) og Azure Machine Learning, slik at du kan bruke dine egne, tilpassede modeller.</span><span class="sxs-lookup"><span data-stu-id="aadec-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="aadec-106">Se [Eksperimenter i Machine Learning Studio (klassisk)](machine-learning-studio-experiments.md) for eksempler på eksperimenter som er basert på Machine Learning Studio (klassisk).</span><span class="sxs-lookup"><span data-stu-id="aadec-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="aadec-107">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="aadec-107">Prerequisites</span></span>

- <span data-ttu-id="aadec-108">Tilgang til Customer Insights</span><span class="sxs-lookup"><span data-stu-id="aadec-108">Access to Customer Insights</span></span>
- <span data-ttu-id="aadec-109">Aktivt abonnement på Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="aadec-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="aadec-110">Enhetlige kundeprofiler</span><span class="sxs-lookup"><span data-stu-id="aadec-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="aadec-111">[Enhetsekspoert til Azure Blob Storage](export-azure-blob-storage.md) konfigurert</span><span class="sxs-lookup"><span data-stu-id="aadec-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="aadec-112">Konfigurer Azure Machine Learning-arbeidsområde</span><span class="sxs-lookup"><span data-stu-id="aadec-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="aadec-113">Se [Opprette et Azure Machine Learning-arbeidsområde](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for alternativer for å opprette arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="aadec-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="aadec-114">For å få best mulig ytelse bør du opprette arbeidsområdet i et Azure-område som er geografisk nærmest Customer Insights-miljøet ditt.</span><span class="sxs-lookup"><span data-stu-id="aadec-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="aadec-115">Få tilgang til arbeidsområdet via [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="aadec-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="aadec-116">Det finnes flere [måter å samhandle](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) med arbeidsområdet på.</span><span class="sxs-lookup"><span data-stu-id="aadec-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="aadec-117">Arbeide med Azure Machine Learning-designer</span><span class="sxs-lookup"><span data-stu-id="aadec-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="aadec-118">Azure Machine Learning-designer har et visuelt lerret der du kan dra og slippe datasett og moduler, på samme måte som Machine Learning Studio (klassisk).</span><span class="sxs-lookup"><span data-stu-id="aadec-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="aadec-119">En bunkepipeline som opprettes fra designeren, kan integreres i Customer Insights hvis den er konfigurert i henhold til dette.</span><span class="sxs-lookup"><span data-stu-id="aadec-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="aadec-120">Arbeide med SDK-et for Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="aadec-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="aadec-121">Datateknikere og AI-utviklere bruker [SDK-et for Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) til å bygge Machine Learning-arbeidsflyter.</span><span class="sxs-lookup"><span data-stu-id="aadec-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="aadec-122">Modeller som er lært opp ved hjelp av SDK-et, kan for øyeblikket ikke integreres direkte med Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="aadec-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="aadec-123">En bunkeslutningspipeline som bruker denne modellen, er nødvendig for å integrere med Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="aadec-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="aadec-124">Krav til bunkepipeline for å integrere med Customer Insights</span><span class="sxs-lookup"><span data-stu-id="aadec-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="aadec-125">Konfigurasjon av datasett</span><span class="sxs-lookup"><span data-stu-id="aadec-125">Dataset Configuration</span></span>

<span data-ttu-id="aadec-126">Du må opprette datasett for å bruke enhetsdata fra Customer Insights for bunkeslutningspipelinen.</span><span class="sxs-lookup"><span data-stu-id="aadec-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="aadec-127">Disse datasettene må registreres i arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="aadec-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="aadec-128">For øyeblikket støtter vi bare [tabelldatasett](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) i .csv-format.</span><span class="sxs-lookup"><span data-stu-id="aadec-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="aadec-129">Datasettene som tilsvarer enhetsdata, må ha parametere som en pipelineparameter.</span><span class="sxs-lookup"><span data-stu-id="aadec-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="aadec-130">Datasettparametere i designeren</span><span class="sxs-lookup"><span data-stu-id="aadec-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="aadec-131">I designeren åpner du **Velg kolonner i datasett** og velger deretter **Angi som pipelineparameter**, der du oppgir et navn for parameteren.</span><span class="sxs-lookup"><span data-stu-id="aadec-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="aadec-132">![Datasettparametrisering i designeren](media/intelligence-designer-dataset-parameters.png "Datasettparametrisering i designeren")</span><span class="sxs-lookup"><span data-stu-id="aadec-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="aadec-133">Datasettparameter i SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="aadec-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="aadec-134">Bunkebeslutningspipeline</span><span class="sxs-lookup"><span data-stu-id="aadec-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="aadec-135">I designeren kan en opplæringspipeline brukes til å opprette eller oppdatere en beslutningspipeline.</span><span class="sxs-lookup"><span data-stu-id="aadec-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="aadec-136">For øyeblikket støttes bare bunkebeslutningspipeliner.</span><span class="sxs-lookup"><span data-stu-id="aadec-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="aadec-137">Ved hjelp av SDK-et kan du publisere pipelinen til et endepunkt.</span><span class="sxs-lookup"><span data-stu-id="aadec-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="aadec-138">For øyeblikket integreres Customer Insights med standard pipeline i et endepunkt for bunkepipeliner i Machine Learning-arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="aadec-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="aadec-139">Importere pipelinedata til Customer Insights</span><span class="sxs-lookup"><span data-stu-id="aadec-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="aadec-140">Designeren har [Eksporter data-modulen](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) som tillater at utdataene fra en pipeline kan eksporteres til Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="aadec-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="aadec-141">For øyeblikket må modulen bruke datalagertypen **Azure Blob Storage** og parametrisere **datalageret** og den relative **banen**.</span><span class="sxs-lookup"><span data-stu-id="aadec-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="aadec-142">Customer Insights overstyrer begge disse parameterne under kjøring av pipeline med et datalager og en bane som er tilgjengelig for produktet.</span><span class="sxs-lookup"><span data-stu-id="aadec-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aadec-143">![Eksportere datamodulkonfigurasjon](media/intelligence-designer-importdata.png "Eksportere datamodulkonfigurasjon")</span><span class="sxs-lookup"><span data-stu-id="aadec-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="aadec-144">Når du skriver beslultningsutdata ved hjelp av kode, kan du laste opp utdataene til en bane innenfor et *registrert datalager* i arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="aadec-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="aadec-145">Hvis banen og datalageret er parametrisert i pipelinen, kan Customer Insights lese og importere beslutningsutdataene.</span><span class="sxs-lookup"><span data-stu-id="aadec-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="aadec-146">Det er for øyeblikket støtte for enkle tabellutdata i CSV-format.</span><span class="sxs-lookup"><span data-stu-id="aadec-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="aadec-147">Banen må inneholde navnet på katalogen og filnavnet.</span><span class="sxs-lookup"><span data-stu-id="aadec-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```
