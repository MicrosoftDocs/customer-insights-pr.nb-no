---
title: Egendefinerte modeller for maskinlæring | Microsoft Docs
description: Arbeide med egendefinerte modeller fra Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609758"
---
# <a name="custom-machine-learning-models"></a>Egendefinerte modeller for maskinlæring

> [!NOTE]
> Støtte for Machine Learning Studio (klassisk) slutter 31. august 2024. Vi anbefaler at du går over til [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) innen denne datoen.
>
> Per 1. desember 2021 kan du ikke opprette nye Machine Learning Studio-ressurser (klassisk). Til og med 31. august 2024 kan du fortsette å bruke de eksisterende Machine Learning Studio-ressursene (klassisk). Hvis du vil ha mer informasjon, kan du se [Overføre til Azure Machine Learning](/azure/machine-learning/migrate-overview).

Egendefinerte modeller lar deg administrere arbeidsflyter basert på Azure Machine Learning-modeller. Arbeidsflyter hjelper deg med å velge dataene du vil generere innsikt fra, og tilordne resultatene til dine ensartede kundedata. Hvis du vil ha mer informasjon om utforming av egen definerte ML-modeller, kan du se [Bruk Azure Machine Learning-baserte modeller](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Forutsetning

- Denne funksjonen støtter nettjenester som er publisert via [bunkepipeliner i Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).
- Pipeline må publiseres under et [pipelineendepunkt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- En [Azure Data Lake Gen2-lagringskonto](/azure/storage/blobs/data-lake-storage-quickstart-create-account) som er knyttet til Azure Studio-forekomsten.
- Tillatelsen Eier eller Administrator for brukertilgang til Azure Machine Learning-arbeidsområdet for Azure Machine Learning-arbeidsområder med pipeliner.

  > [!NOTE]
  > Data overføres mellom Customer Insights-forekomstene dine og de valgte Azure-webtjenestene eller -pipelinene i arbeidsflyten. Når du overfører data til en Azure-tjeneste, må du sørge for at tjenesten er konfigurert til å behandle data på måten og stedet som er nødvendig for å overholde eventuelle juridiske eller forskriftsmessige krav for disse dataene for organisasjonen din.

## <a name="add-a-new-workflow"></a>Legge til en ny arbeidsflyt

1. Gå til **Intelligens** > **Egendefinerte modeller**, og velg **Ny arbeidsflyt**.

1. Oppgi et gjenkjennelig **Navn**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Skjermbilde av ruten Ny arbeidsflyt.":::

1. Velg organisasjonen som inneholder webtjenesten, i **Leier som inneholder webtjenesten**.

1. Hvis Azure Machine Learning-abonnementet ditt er i en annen leier enn Customer Insights, velger du **Logg på** med legitimasjonen din for den valgte organisasjonen.

1. Velg **arbeidsområdene** som er knyttet til nettjenesten.

1. Velg Azure Machine Learning-pipelinen i rullegardinlisten **Nettjeneste som inneholder modellen**. Velg deretter **Neste**.
   Lær mer om [publisering av en pipeline i Azure Machine Learning ved hjelp av designeren](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK-et](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. For hver **Webtjenesteinndata** velger du den samsvarende **enheten** fra Customer Insights. Velg deretter **Neste**.
   > [!NOTE]
   > Arbeidsflyten for egendefinert modell bruker heuristikk til å tilordne inndatafeltene for nettjenesten til enhetsattributtene basert på navnet og datatypen for feltet. Det vises en feilmelding hvis et nettjenestefelt ikke kan tilordnes til en enhet.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfigurer en arbeidsflyt.":::

1. For **Parametere for modellutdata** angir du følgende egenskaper:
   - **Enhetsnavn** for utdataresultatene for pipeline
   - **Navn på parameter for utdatalager** for bunkepipelinen
   - **Navn på parameter for utdatabane** for bunkepipelinen

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Parameterrute for modellutdata.":::

1. Velg det tilsvarende attributtet fra **Kunde-ID i resultater** som identifiserer kunder, og velg **Lagre**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Relater resultater til kundedataruten.":::

   Skjermen **Arbeidsflyt lagret** vises med detaljer om arbeidsflyten. Hvis du konfigurerte en arbeidsflyt for en Azure Machine Learning-forløp, knyttes Customer Insights til arbeidsområdet som inneholder forløpet. Customer Insights får en **bidragsyterrolle** i Azure-arbeidsområdet.

1. Velg **Ferdig**. Siden **Egendefinerte modeller** vises.

1. Velg den loddrette ellipsen (&vellip;) for arbeidsflyten, og velg **Kjør**. Arbeidsflyten kjøres også automatisk med hver [planlagte oppdatering](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Administrer en eksisterende arbeidsflyt

Gå til **Intelligens** > **Egendefinerte modeller** for å vise arbeidsflytene du opprettet.

Velg en arbeidsflyt for å vise tilgjengelige handlinger.

- **Rediger** en arbeidsflyt
- **Kjør** en arbeidsflyt
- [**Slett**](#delete-a-workflow) en arbeidsflyt

### <a name="edit-a-workflow"></a>Redigere en arbeidsflyt

1. Gå til **Intelligens** > **Egendefinerte modeller**.

1. Ved siden arbeidsflyten du vil oppdatere, velger du den loddrette ellipsen (&vellip;) og **Rediger**.

1. Endre **Visningsnavn** om nødvendig, og velg **Neste**.

1. For hver **Nettjenesteinndata** oppdaterer du den samsvarende **enheten** fra Customer Insights om nødvendig. Velg deretter **Neste**.

1. Endre et av det følgende for **Parametere for modellutdata**:
   - **Enhetsnavn** for utdataresultatene for pipeline
   - **Navn på parameter for utdatalager** for bunkepipelinen
   - **Navn på parameter for utdatabane** for bunkepipelinen

1. Endre det tilsvarende attributtet fra **Kunde-ID i resultater** for å identifisere kunder. Velg et attributt fra beslutningsutdataene med verdier som ligner på kunde-ID-kolonnen for kundeenheten. Hvis du ikke har en slik kolonne i datasettet, velger du et attributt som unikt identifiserer raden.

1. Velg **Lagre**

### <a name="delete-a-workflow"></a>Slette en arbeidsflyt

1. Gå til **Intelligens** > **Egendefinerte modeller**.

1. Ved siden arbeidsflyten du vil slette, velger du den loddrette ellipsen (&vellip;) og deretter **Slett**.

1. Bekreft slettingen.

Arbeidsflyten blir slettet. [Enheten](entities.md) som ble opprettet da du opprettet arbeidsflyten, vedvarer og kan vises fra siden **Data** > **Enheter**.

## <a name="view-the-results"></a>Vis resultatene

Resultater fra en arbeidsflyt lagres i enhetsnavnet som er definert for **Parametere for modellutdata**. Få tilgang til disse dataene fra [**Data** > **Enheter**-siden](entities.md) eller med [API-tilgang](apis.md).

### <a name="api-access"></a>API-tilgang

Bruk følgende format for den bestemte OData-spørringen for å hente data fra en egendefinert modellenhet:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Erstatt `<your instance id>` med ID-en for Customer Insights-miljøet ditt, som vises på adresselinjen i nettleseren når du går til Customer Insights.

1. Erstatt `<custom model output entity>` med enhetsnavnet du angav for **Parametere for modellutdata**.

1. Erstatt `<guid value>` med kunde-ID-en for kunden du vil ha tilgang til. Denne ID-en vises på [kundeprofilsiden](customer-profiles.md) i CustomerID-feltet.

## <a name="frequently-asked-questions"></a>Vanlige spørsmål

- Hvorfor kan jeg ikke se pipelinjen min når jeg konfigurerer en arbeidsflyt for en egendefinert modell?
  Dette problemet skyldes ofte et konfigurasjonsproblem i pipelinen. Kontroller at [inndataparameteren er konfigurert](azure-machine-learning-experiments.md#dataset-configuration), og at [utdatadatalageret og baneparameterne](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) også er konfigurert.

- Hva betyr feilmeldingen "Kunne ikke lagre en intelligensarbeidsflyt"? 
  Brukerne ser vanligvis denne feilmeldingen hvis de ikke har rettigheter som eier eller administrator for brukertilgang på arbeidsområdet. Brukeren må ha et høyere tillatelsesnivå for at Customer Insights skal kunne behandle arbeidsflyten som en tjeneste, i stedet for å bruke brukerlegitimasjonen for påfølgende kjøringer av arbeidsflyten.

- Er det støtte for et privat endepunkt / en privat kobling for arbeidsflyten for egendefinert modell?
  Customer Insights har for øyeblikket ikke bruksklar støtte for privat endepunkt for egendefinerte modeller, men en manuell løsning er tilgjengelig. Kontakt kundestøtte hvis du vil ha mer informasjon.

## <a name="responsible-ai"></a>Ansvarlig kunstig intelligens

Prognoser tilbyr funksjoner for å skape bedre kundeopplevelser, forbedre forretningsmulighetene og omsetningsstrømmer. Vi anbefaler på det sterkeste at du balanserer verdien i prediksjon mot innvirkningen den har, og vektlegger det som blir introdusert, på en etisk måte. Lær mer om hvordan Microsoft [håndterer ansvarlig kunstig intelligens](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Du kan også lære om [teknikker og prosesser for ansvarlig maskinlæring](/azure/machine-learning/concept-responsible-ml) som er spesifikke for Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
