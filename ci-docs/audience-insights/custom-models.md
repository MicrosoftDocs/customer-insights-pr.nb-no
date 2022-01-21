---
title: Egendefinerte modeller for maskinlæring | Microsoft Docs
description: Arbeide med egendefinerte modeller fra Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 8ca30193ae4f4ef3ed9c60f2d694cd11fad46c76
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967667"
---
# <a name="custom-machine-learning-models"></a>Egendefinerte modeller for maskinlæring

> [!NOTE]
> Støtte for Machine Learning Studio (klassisk) slutter 31. august 2024. Vi anbefaler at du går over til [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) innen denne datoen.
>
> Per 1. desember 2021 kan du ikke opprette nye Machine Learning Studio-ressurser (klassisk). Til og med 31. august 2024 kan du fortsette å bruke de eksisterende Machine Learning Studio-ressursene (klassisk). Hvis du vil ha mer informasjon, kan du se [Overføre til Azure Machine Learning](/azure/machine-learning/migrate-overview).


**Intelligens** > **Egendefinerte modeller** lar deg behandle arbeidsflyter basert på Azure Machine Learning-modeller. Arbeidsflyter hjelper deg med å velge dataene du vil generere innsikt fra, og tilordne resultatene til dine ensartede kundedata. Hvis du vil ha mer informasjon om utforming av egen definerte ML-modeller, kan du se [Bruk Azure Machine Learning-baserte modeller](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Ansvarlig kunstig intelligens

Prognoser tilbyr funksjoner for å skape bedre kundeopplevelser, forbedre forretningsmulighetene og omsetningsstrømmer. Vi anbefaler på det sterkeste at du balanserer verdien i prediksjon mot innvirkningen den har, og vektlegger det som blir introdusert, på en etisk måte. Lær mer om hvordan Microsoft [håndterer ansvarlig kunstig intelligens](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Du kan også lære om [teknikker og prosesser for ansvarlig maskinlæring](/azure/machine-learning/concept-responsible-ml) som er spesifikke for Azure Machine Learning.

## <a name="prerequisites"></a>Krav

- Denne funksjonen støtter webtjenester som er publisert via [Azure Machine Learning-gruppepipeliner](/azure/machine-learning/concept-ml-pipelines).

- Du trenger en Azure Data Lake Gen2-lagringskonto som er tilknyttet Azure Studio-forekomsten, for å bruke denne funksjonen. Hvis du vil ha mer informasjon, se [Opprett en Azure Data Lake Storage Gen2-lagringskonto](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- For Azure Machine Learning-arbeidsområder med pipeliner trenger du tillatelse som Eier eller Administrator for brukertilgang til Azure Machine Learning-arbeidsområdet.

   > [!NOTE]
   > Data overføres mellom Customer Insights-forekomstene dine og de valgte Azure-webtjenestene eller -pipelinene i arbeidsflyten. Når du overfører data til en Azure-tjeneste, må du sørge for at tjenesten er konfigurert til å behandle data på måten og stedet som er nødvendig for å overholde eventuelle juridiske eller forskriftsmessige krav for disse dataene for organisasjonen din.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Legge til en ny arbeidsflyt

1. Gå til **Intelligens** > **Egendefinerte modeller**, og velg **Ny arbeidsflyt**.

1. Gi den egendefinerte modellen et gjenkjennelig navn i **Navn**-feltet.

   > [!div class="mx-imgBorder"]
   > ![Skjermbilde av ruten Ny arbeidsflyt.](media/new-workflowv2.png "Skjermbilde av ruten Ny arbeidsflyt")

1. Velg organisasjonen som inneholder webtjenesten, i **Leier som inneholder webtjenesten**.

1. Hvis Azure Machine Learning-abonnementet ditt er i en annen leier enn Customer Insights, velger du **Logg på** med legitimasjonen din for den valgte organisasjonen.

1. Velg **arbeidsområdene** som er knyttet til nettjenesten. 

1. Velg Azure Machine Learning-pipelinen i rullegardinlisten **Nettjeneste som inneholder modellen**. Velg deretter **Neste**.    
   Lær mer om [publisering av en pipeline i Azure Machine Learning ved hjelp av designeren](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK-et](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Pipelinen må publiseres under et [pipelineendepunkt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. For hver **nettjenesteinndata** velger du den samsvarende **enheten** fra målgruppeinnsikt og velger **Neste**.
   > [!NOTE]
   > Arbeidsflyten for egendefinert modell bruker heuristikk til å tilordne inndatafeltene for nettjenesten til enhetsattributtene basert på navnet og datatypen for feltet. Det vises en feilmelding hvis et nettjenestefelt ikke kan tilordnes til en enhet.

   > [!div class="mx-imgBorder"]
   > ![Konfigurer en arbeidsflyt.](media/intelligence-screen2-updated.png "Konfigurere en arbeidsflyt")

1. I trinnet **Parametere for modellutdata** angir du følgende egenskaper:
      1. Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene for pilelinen skal flytes.
      1. Velg **Navn på parameter for utdatalager** for bunkepipelinen fra rullegardinmenyen.
      1. Velg **Navn på parameter for utdatabane** for bunkepipelinen fra rullegardinmenyen.

      > [!div class="mx-imgBorder"]
      > ![Parameterrute for modellutdata.](media/intelligence-screen3-outputparameters.png "Parameterrute for modelutdata")

1. Velg det tilsvarende attributtet fra rullegardinlisten **Kunde-ID i resultater** som identifiserer kunder, og velg **Lagre**.

   > [!div class="mx-imgBorder"]
   > ![Relater resultater til kundedataruten.](media/intelligence-screen4-relatetocustomer.png "Relater resultater til kundedataruten")

1. Du ser skjermbildet **Arbeidsflyt lagret** med detaljer om arbeidsflyten.    
   Hvis du har konfigurert en arbeidsflyt for en Azure Machine Learning-pipeline, vil målgruppe innsikt legge ved arbeidsområdet som inneholder pipelinen. Målgruppeinnsikt får en **Bidragsyter**-rolle på Azure-arbeidsområdet.

1. Velg **Ferdig**.

1. Du kan nå kjøre arbeidsflyten fra siden **Egendefinerte modeller**.

## <a name="edit-a-workflow"></a>Redigere en arbeidsflyt

1. På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet, og deretter velger du **Rediger**.

1. Du kan oppdatere det gjenkjennelige navnet på arbeidsflyten i **Visningsnavn**-feltet, men du kan ikke endre den konfigurerte nettjenesten eller pipelinen. Velg **Neste**.

1. For hver **nettjenesteinndata** kan du oppdatere den samsvarende **enheten** fra målgruppeinnsikt. Velg deretter **Neste**.

1. I trinnet **Parametere for modellutdata** angir du følgende egenskaper:
      1. Angi **enhetsnavnet** for utdataene der du vil at utdataresultatene for pilelinen skal flytes.
      1. Velg **Navn på parameter for utdatalager** for testpipelinen.
      1. Velg **Navn på parameter for utdatabane** for testpipelinen.

1. Velg det tilsvarende attributtet fra rullegardinlisten **Kunde-ID i resultater** som identifiserer kunder, og velg **Lagre**.
   Velg et attributt fra beslutningsutdataene med verdier som ligner på kunde-ID-kolonnen for kundeenheten. Hvis du ikke har en slik kolonne i datasettet, velger du et attributt som unikt identifiserer raden.

## <a name="run-a-workflow"></a>Kjøre en arbeidsflyt

1. På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet.

1. Velg **Kjør**.

Arbeidsflyten kjøres også automatisk med hver planlagte oppdatering. Lær mer om [konfigurering av planlagte oppdateringer](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Slette en arbeidsflyt

1. På siden **Egendefinerte modeller** velger du den loddrette ellipsen i **Handlinger**-kolonnen ved siden av en arbeidsflyt du tidligere har opprettet.

1. Velg **Slett**, og bekreft slettingen.

Arbeidsflyten blir slettet. [Enheten](entities.md) som ble opprettet da du opprettet arbeidsflyten, vedvarer og kan vises fra **Enheter**-siden.

## <a name="results"></a>Resultater

Resultater fra en arbeidsflyt lagres i enheten som er konfigurert under fasen Parameter for modellutdata. Du kan få tilgang til disse dataene fra [enhetssiden](entities.md) eller med [API-tilgang](apis.md).

### <a name="api-access"></a>API-tilgang

Bruk følgende format for den bestemte OData-spørringen for å hente data fra en egendefinert modellenhet:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Erstatt `<your instance id>` med ID-en for Customer Insights-miljøet ditt, som du finner på adresselinjen i nettleseren når du går til Customer Insights.

1. Erstatt `<custom model output entity>` med enhetsnavnet du oppgav under trinnet Parametere for modellutdata under konfigurasjonen av den egendefinerte modellen.

1. Erstatt `<guid value>` med kunde-ID-en for kunden du vil ha tilgang til oppføringen for. Du finner vanligvis denne ID-en på [kundeprofilsiden](customer-profiles.md) i CustomerID-feltet.

## <a name="frequently-asked-questions"></a>Vanlige spørsmål

- Hvorfor kan jeg ikke se pipelinjen min når jeg konfigurerer en arbeidsflyt for en egendefinert modell?    
  Dette problemet skyldes ofte et konfigurasjonsproblem i pipelinen. Kontroller at [inndataparameteren er konfigurert](azure-machine-learning-experiments.md#dataset-configuration), og at [utdatadatalageret og baneparameterne](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) også er konfigurert.

- Hva betyr feilmeldingen "Kunne ikke lagre en intelligensarbeidsflyt"?    
  Brukerne ser vanligvis denne feilmeldingen hvis de ikke har rettigheter som eier eller administrator for brukertilgang på arbeidsområdet. Brukeren må ha et høyere tillatelsesnivå for at Customer Insights skal kunne behandle arbeidsflyten som en tjeneste, i stedet for å bruke brukerlegitimasjonen for påfølgende kjøringer av arbeidsflyten.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
