---
title: Egendefinerte modeller for maskinlæring | Microsoft Docs
description: Arbeide med egendefinerte modeller fra Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668915"
---
# <a name="custom-machine-learning-models"></a>Egendefinerte modeller for maskinlæring

**Intelligens** > **Egendefinerte modeller** lar deg behandle arbeidsflyter basert på Azure Machine Learning-modeller. Arbeidsflyter hjelper deg med å velge dataene du vil generere innsikt fra, og tilordne resultatene til dine ensartede kundedata. Hvis du vil ha mer informasjon om utforming av egen definerte ML-modeller, kan du se [Bruk Azure Machine Learning-baserte modeller](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Ansvarlig kunstig intelligens

Prognoser tilbyr funksjoner for å skape bedre kundeopplevelser, forbedre forretningsmulighetene og omsetningsstrømmer. Vi anbefaler på det sterkeste at du balanserer verdien i prediksjon mot innvirkningen den har, og vektlegger det som blir introdusert, på en etisk måte. Lær mer om hvordan Microsoft [håndterer ansvarlig kunstig intelligens](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Du kan også lære om [teknikker og prosesser for ansvarlig maskinlæring](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) som er spesifikke for Azure Machine Learning.

## <a name="prerequisites"></a>Forutsetninger

- Denne funksjonen støtter for øyeblikket nettjenester som publiseres via [Machine Learning Studio (klassisk)](https://studio.azureml.net) og [bunkepipeliner i Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Du trenger en Azure Data Lake Gen2-lagringskonto som er tilknyttet Azure Studio-forekomsten, for å bruke denne funksjonen. Hvis du vil ha mer informasjon, se [Opprette en Azure Data Lake Storage Gen2-lagringskonto](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Legge til en ny arbeidsflyt

1. Gå til **Intelligens** > **Egendefinerte modeller**, og velg **Ny arbeidsflyt**.

1. Gi den egendefinerte modellen et gjenkjennelig navn i **Navn**-feltet.

   > [!div class="mx-imgBorder"]
   > ![Skjermbilde av ruten Ny arbeidsflyt](media/new-workflowv2.png "Skjermbilde av ruten Ny arbeidsflyt")

1. Velg organisasjonen som inneholder webtjenesten, i **Leier som inneholder webtjenesten**.

1. Hvis Azure Machine Learning-abonnementet ditt er i en annen leier enn Customer Insights, velger du **Logg på** med legitimasjonen din for den valgte organisasjonen.

1. Velg **arbeidsområdene** som er knyttet til nettjenesten. To deler vises, én for Azure Machine Learning v1 (Machine Learning Studio (klassisk)) og Azure Machine Learning v2 (Azure Machine Learning). Hvis du ikke er sikker på hvilket arbeidsområde som er det riktige for Machine Learning Studio (klassisk)-nettjenesten, velger du **Hvilken som helst**.

1. Velg Machine Learning Studio (klassisk)-nettjenesten eller Azure Machine Learning-pipelinen i rullegardinmenyen **Nettjeneste som inneholder modellen**. Velg deretter **Neste**.
   - Lær mer om [publisering av en nettjeneste i Machine Learning Studio (klassisk)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Lær mer om [publisering av en pipeline i Azure Machine Learning ved hjelp av designeren](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK-et](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > Pipelinen må publiseres under et [pipelineendepunkt](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. For hver **nettjenesteinndata** velger du den samsvarende **enheten** fra målgruppeinnsikt og velger **Neste**.

   > [!div class="mx-imgBorder"]
   > ![Konfigurere en arbeidsflyt](media/intelligence-screen2-updated.png "Konfigurere en arbeidsflyt")

1. I trinnet **Parametere for modellutdata** angir du følgende egenskaper:
   - Machine Learning Studio (klassisk)
      1. Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene fra nettjenesten skal flytes.
   - Azure Machine Learning
      1. Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene for pilelinen skal flytes.
      1. Velg **Navn på parameter for utdatalager** for bunkepipelinen fra rullegardinmenyen.
      1. Velg **Navn på parameter for utdatabane** for bunkepipelinen fra rullegardinmenyen.
      
      > [!div class="mx-imgBorder"]
      > ![Parameterrute for modelutdata](media/intelligence-screen3-outputparameters.png "Parameterrute for modelutdata")

1. Velg det tilsvarende attributtet fra rullegardinlisten **Kunde-ID i resultater** som er identifiserer kunder, og velg **Lagre**.
   
   > [!div class="mx-imgBorder"]
   > ![Relater resultater til kundedataruten](media/intelligence-screen4-relatetocustomer.png "Relater resultater til kundedataruten")

1. Du ser skjermbildet **Arbeidsflyt lagret** med detaljer om arbeidsflyten.    
   Hvis du har konfigurert en arbeidsflyt for en Azure Machine Learning-pipeline, vil målgruppe innsikt legge ved arbeidsområdet som inneholder pipelinen. Målgruppeinnsikt får en **Bidragsyter**-rolle på Azure-arbeidsområdet.

1. Velg **Ferdig**.

1. Du kan nå kjøre arbeidsflyten fra siden **Egendefinerte modeller**.

## <a name="edit-a-workflow"></a>Redigere en arbeidsflyt

1. På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet, og deretter velger du **Rediger**.

1. Du kan oppdatere det gjenkjennelige navnet på arbeidsflyten i **Visningsnavn**-feltet, men du kan ikke endre den konfigurerte nettjenesten eller pipelinen. Velg **Neste**.

1. For hver **nettjenesteinndata** kan du oppdatere den samsvarende **enheten** fra målgruppeinnsikt. Velg deretter **Neste**.

1. I trinnet **Parametere for modellutdata** angir du følgende egenskaper:
   - Machine Learning Studio (klassisk)
      1. Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene fra nettjenesten skal flytes.
   - Azure Machine Learning
      1. Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene for pilelinen skal flytes.
      1. Velg **Navn på parameter for utdatalager** for testpipelinen.
      1. Velg **Navn på parameter for utdatabane** for testpipelinen.

1. Velg det tilsvarende attributtet fra rullegardinlisten **Kunde-ID i resultater** som er identifiserer kunder, og velg **Lagre**.
   Du må velge et attributt fra beslutningsutdataene med verdier som ligner på kunde-ID-kolonnen for kundeenheten. Hvis du ikke har en slik kolonne i datasettet, velger du et attributt som unikt identifiserer raden.

## <a name="run-a-workflow"></a>Kjøre en arbeidsflyt

1. På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet.

1. Velg **Kjør**.

Arbeidsflyten kjøres også automatisk med hver planlagte oppdatering. Lær mer om [konfigurering av planlagte oppdateringer](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Slette en arbeidsflyt

1. På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet.

1. Velg **Slett**, og bekreft slettingen.

Arbeidsflyten blir slettet. [Enheten](entities.md) som ble opprettet da du opprettet arbeidsflyten, vedvarer og kan vises fra **Enheter**-siden.
