---
title: Azure Machine Learning-eksperimenter
description: Bruk Azure Machine Learning-baserte modeller i Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597431"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="b7803-103">Bruk Azure Machine Learning-baserte modeller</span><span class="sxs-lookup"><span data-stu-id="b7803-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="b7803-104">De ensartede dataene i Dynamics 365 Customer Insights er en kilde for bygging av maskinlæringsmodeller som kan generere ytterligere forretningsinnsikt.</span><span class="sxs-lookup"><span data-stu-id="b7803-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="b7803-105">Customer Insights integreres med Machine Learning Studio (klassisk) og Azure Machine Learning, slik at du kan bruke dine egne, tilpassede modeller.</span><span class="sxs-lookup"><span data-stu-id="b7803-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="b7803-106">Se [Eksperimenter i Machine Learning Studio (klassisk)](machine-learning-studio-experiments.md) for eksempler på eksperimenter som er basert på Machine Learning Studio (klassisk).</span><span class="sxs-lookup"><span data-stu-id="b7803-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b7803-107">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="b7803-107">Prerequisites</span></span>

- <span data-ttu-id="b7803-108">Tilgang til Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b7803-108">Access to Customer Insights</span></span>
- <span data-ttu-id="b7803-109">Aktivt abonnement på Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="b7803-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="b7803-110">Enhetlige kundeprofiler</span><span class="sxs-lookup"><span data-stu-id="b7803-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="b7803-111">[Enhetsekspoert til Azure Blob Storage](export-azure-blob-storage.md) konfigurert</span><span class="sxs-lookup"><span data-stu-id="b7803-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="b7803-112">Konfigurer Azure Machine Learning-arbeidsområde</span><span class="sxs-lookup"><span data-stu-id="b7803-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="b7803-113">Se [Opprette et Azure Machine Learning-arbeidsområde](/azure/machine-learning/concept-workspace#-create-a-workspace) for alternativer for å opprette arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="b7803-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="b7803-114">For å få best mulig ytelse bør du opprette arbeidsområdet i et Azure-område som er geografisk nærmest Customer Insights-miljøet ditt.</span><span class="sxs-lookup"><span data-stu-id="b7803-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="b7803-115">Få tilgang til arbeidsområdet via [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="b7803-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="b7803-116">Det finnes flere [måter å samhandle](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) med arbeidsområdet på.</span><span class="sxs-lookup"><span data-stu-id="b7803-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="b7803-117">Arbeide med Azure Machine Learning-designer</span><span class="sxs-lookup"><span data-stu-id="b7803-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="b7803-118">Azure Machine Learning-designer har et visuelt lerret der du kan dra og slippe datasett og moduler, på samme måte som Machine Learning Studio (klassisk).</span><span class="sxs-lookup"><span data-stu-id="b7803-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="b7803-119">En bunkepipeline som opprettes fra designeren, kan integreres i Customer Insights hvis den er konfigurert i henhold til dette.</span><span class="sxs-lookup"><span data-stu-id="b7803-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="b7803-120">Arbeide med SDK-et for Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="b7803-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="b7803-121">Datateknikere og AI-utviklere bruker [SDK-et for Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) til å bygge Machine Learning-arbeidsflyter.</span><span class="sxs-lookup"><span data-stu-id="b7803-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="b7803-122">Modeller som er lært opp ved hjelp av SDK-et, kan for øyeblikket ikke integreres direkte med Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b7803-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="b7803-123">En bunkeslutningspipeline som bruker denne modellen, er nødvendig for å integrere med Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b7803-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="b7803-124">Krav til bunkepipeline for å integrere med Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b7803-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="b7803-125">Konfigurasjon av datasett</span><span class="sxs-lookup"><span data-stu-id="b7803-125">Dataset Configuration</span></span>

<span data-ttu-id="b7803-126">Du må opprette datasett for å bruke enhetsdata fra Customer Insights for bunkeslutningspipelinen.</span><span class="sxs-lookup"><span data-stu-id="b7803-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="b7803-127">Disse datasettene må registreres i arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="b7803-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="b7803-128">For øyeblikket støtter vi bare [tabelldatasett](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) i .csv-format.</span><span class="sxs-lookup"><span data-stu-id="b7803-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="b7803-129">Datasettene som tilsvarer enhetsdata, må ha parametere som en pipelineparameter.</span><span class="sxs-lookup"><span data-stu-id="b7803-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="b7803-130">Datasettparametere i designeren</span><span class="sxs-lookup"><span data-stu-id="b7803-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="b7803-131">I designeren åpner du **Velg kolonner i datasett** og velger deretter **Angi som pipelineparameter**, der du oppgir et navn for parameteren.</span><span class="sxs-lookup"><span data-stu-id="b7803-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="b7803-132">![Datasettparametrisering i designeren](media/intelligence-designer-dataset-parameters.png "Datasettparametrisering i designeren")</span><span class="sxs-lookup"><span data-stu-id="b7803-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="b7803-133">Datasettparameter i SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="b7803-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="b7803-134">Bunkebeslutningspipeline</span><span class="sxs-lookup"><span data-stu-id="b7803-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="b7803-135">I designeren kan en opplæringspipeline brukes til å opprette eller oppdatere en beslutningspipeline.</span><span class="sxs-lookup"><span data-stu-id="b7803-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="b7803-136">For øyeblikket støttes bare bunkebeslutningspipeliner.</span><span class="sxs-lookup"><span data-stu-id="b7803-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="b7803-137">Ved hjelp av SDK-et kan du publisere pipelinen til et endepunkt.</span><span class="sxs-lookup"><span data-stu-id="b7803-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="b7803-138">For øyeblikket integreres Customer Insights med standard pipeline i et endepunkt for bunkepipeliner i Machine Learning-arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="b7803-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="b7803-139">Importere pipelinedata til Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b7803-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="b7803-140">Designeren har [Eksporter data-modulen](/azure/machine-learning/algorithm-module-reference/export-data) som tillater at utdataene fra en pipeline kan eksporteres til Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="b7803-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="b7803-141">For øyeblikket må modulen bruke datalagertypen **Azure Blob Storage** og parametrisere **datalageret** og den relative **banen**.</span><span class="sxs-lookup"><span data-stu-id="b7803-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="b7803-142">Customer Insights overstyrer begge disse parameterne under kjøring av pipeline med et datalager og en bane som er tilgjengelig for produktet.</span><span class="sxs-lookup"><span data-stu-id="b7803-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b7803-143">![Eksportere datamodulkonfigurasjon](media/intelligence-designer-importdata.png "Eksportere datamodulkonfigurasjon")</span><span class="sxs-lookup"><span data-stu-id="b7803-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="b7803-144">Når du skriver beslultningsutdata ved hjelp av kode, kan du laste opp utdataene til en bane innenfor et *registrert datalager* i arbeidsområdet.</span><span class="sxs-lookup"><span data-stu-id="b7803-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="b7803-145">Hvis banen og datalageret er parametrisert i pipelinen, kan Customer Insights lese og importere beslutningsutdataene.</span><span class="sxs-lookup"><span data-stu-id="b7803-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="b7803-146">Det er for øyeblikket støtte for enkle tabellutdata i CSV-format.</span><span class="sxs-lookup"><span data-stu-id="b7803-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="b7803-147">Banen må inneholde navnet på katalogen og filnavnet.</span><span class="sxs-lookup"><span data-stu-id="b7803-147">The path must include the directory and filename.</span></span>

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]