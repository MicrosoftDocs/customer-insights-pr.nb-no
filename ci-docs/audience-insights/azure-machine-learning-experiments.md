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
# <a name="use-azure-machine-learning-based-models"></a>Bruk Azure Machine Learning-baserte modeller

De ensartede dataene i Dynamics 365 Customer Insights er en kilde for bygging av maskinlæringsmodeller som kan generere ytterligere forretningsinnsikt. Customer Insights integreres med Machine Learning Studio (klassisk) og Azure Machine Learning, slik at du kan bruke dine egne, tilpassede modeller. Se [Eksperimenter i Machine Learning Studio (klassisk)](machine-learning-studio-experiments.md) for eksempler på eksperimenter som er basert på Machine Learning Studio (klassisk). 

## <a name="prerequisites"></a>Forutsetninger

- Tilgang til Customer Insights
- Aktivt abonnement på Azure Enterprise
- [Enhetlige kundeprofiler](data-unification.md)
- [Enhetsekspoert til Azure Blob Storage](export-azure-blob-storage.md) konfigurert

## <a name="set-up-azure-machine-learning-workspace"></a>Konfigurer Azure Machine Learning-arbeidsområde

1. Se [Opprette et Azure Machine Learning-arbeidsområde](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for alternativer for å opprette arbeidsområdet. For å få best mulig ytelse bør du opprette arbeidsområdet i et Azure-område som er geografisk nærmest Customer Insights-miljøet ditt.

1. Få tilgang til arbeidsområdet via [Azure Machine Learning Studio](https://ml.azure.com/). Det finnes flere [måter å samhandle](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) med arbeidsområdet på.

## <a name="work-with-azure-machine-learning-designer"></a>Arbeide med Azure Machine Learning-designer

Azure Machine Learning-designer har et visuelt lerret der du kan dra og slippe datasett og moduler, på samme måte som Machine Learning Studio (klassisk). En bunkepipeline som opprettes fra designeren, kan integreres i Customer Insights hvis den er konfigurert i henhold til dette. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Arbeide med SDK-et for Azure Machine Learning

Datateknikere og AI-utviklere bruker [SDK-et for Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) til å bygge Machine Learning-arbeidsflyter. Modeller som er lært opp ved hjelp av SDK-et, kan for øyeblikket ikke integreres direkte med Customer Insights. En bunkeslutningspipeline som bruker denne modellen, er nødvendig for å integrere med Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Krav til bunkepipeline for å integrere med Customer Insights

### <a name="dataset-configuration"></a>Konfigurasjon av datasett

Du må opprette datasett for å bruke enhetsdata fra Customer Insights for bunkeslutningspipelinen. Disse datasettene må registreres i arbeidsområdet. For øyeblikket støtter vi bare [tabelldatasett](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) i .csv-format. Datasettene som tilsvarer enhetsdata, må ha parametere som en pipelineparameter.
   
* Datasettparametere i designeren
   
     I designeren åpner du **Velg kolonner i datasett** og velger deretter **Angi som pipelineparameter**, der du oppgir et navn for parameteren.

     > [!div class="mx-imgBorder"]
     > ![Datasettparametrisering i designeren](media/intelligence-designer-dataset-parameters.png "Datasettparametrisering i designeren")
   
* Datasettparameter i SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Bunkebeslutningspipeline
  
* I designeren kan en opplæringspipeline brukes til å opprette eller oppdatere en beslutningspipeline. For øyeblikket støttes bare bunkebeslutningspipeliner.

* Ved hjelp av SDK-et kan du publisere pipelinen til et endepunkt. For øyeblikket integreres Customer Insights med standard pipeline i et endepunkt for bunkepipeliner i Machine Learning-arbeidsområdet.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importere pipelinedata til Customer Insights

* Designeren har [Eksporter data-modulen](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) som tillater at utdataene fra en pipeline kan eksporteres til Azure Storage. For øyeblikket må modulen bruke datalagertypen **Azure Blob Storage** og parametrisere **datalageret** og den relative **banen**. Customer Insights overstyrer begge disse parameterne under kjøring av pipeline med et datalager og en bane som er tilgjengelig for produktet.
   > [!div class="mx-imgBorder"]
   > ![Eksportere datamodulkonfigurasjon](media/intelligence-designer-importdata.png "Eksportere datamodulkonfigurasjon")
   
* Når du skriver beslultningsutdata ved hjelp av kode, kan du laste opp utdataene til en bane innenfor et *registrert datalager* i arbeidsområdet. Hvis banen og datalageret er parametrisert i pipelinen, kan Customer Insights lese og importere beslutningsutdataene. Det er for øyeblikket støtte for enkle tabellutdata i CSV-format. Banen må inneholde navnet på katalogen og filnavnet.

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
