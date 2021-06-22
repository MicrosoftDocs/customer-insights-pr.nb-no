---
title: Delte oppgaver for prediksjonsscenarioer
description: Finn ut hvordan du administrerer, feilsøker og forbedrer prediksjoner.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095736"
---
# <a name="manage-predictions"></a><span data-ttu-id="71c5f-103">Administrere prediksjoner</span><span class="sxs-lookup"><span data-stu-id="71c5f-103">Manage predictions</span></span>

<span data-ttu-id="71c5f-104">Denne artikkelen tar for seg noen oppgaver som de fleste prediksjonsscenarioene har til felles.</span><span class="sxs-lookup"><span data-stu-id="71c5f-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="71c5f-105">Feilsøke en mislykket prognose</span><span class="sxs-lookup"><span data-stu-id="71c5f-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="71c5f-106">Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.</span><span class="sxs-lookup"><span data-stu-id="71c5f-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="71c5f-107">Velg de loddrette ellipsene ved siden av prediksjonen du vil vise feillogger for.</span><span class="sxs-lookup"><span data-stu-id="71c5f-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="71c5f-108">Velg **Logger**.</span><span class="sxs-lookup"><span data-stu-id="71c5f-108">Select **Logs**.</span></span>

1. <span data-ttu-id="71c5f-109">Se gjennom alle feilene.</span><span class="sxs-lookup"><span data-stu-id="71c5f-109">Review all the errors.</span></span> <span data-ttu-id="71c5f-110">Det finnes flere typer feil som kan oppstå, og de beskriver hvilken betingelse som forårsaket feilen.</span><span class="sxs-lookup"><span data-stu-id="71c5f-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="71c5f-111">En feil på grunn av at det ikke er nok data til å forutsi nøyaktig, blir vanligvis løst ved å laste inn flere data i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="71c5f-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="71c5f-112">Brukbarhetsrapport for inndata</span><span class="sxs-lookup"><span data-stu-id="71c5f-112">Input data usability report</span></span>

<span data-ttu-id="71c5f-113">Brukbarhetsrapporten for inndata gir en konsolidert visning av feilene og advarslene som de bruksklare prediksjonene kan generere.</span><span class="sxs-lookup"><span data-stu-id="71c5f-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="71c5f-114">Den gir også anbefalinger om hvordan du kan forbedre modellytelsen.</span><span class="sxs-lookup"><span data-stu-id="71c5f-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="71c5f-115">Rapporten er tilgjengelig etter at en modell har fullført opplæringsprosessen.</span><span class="sxs-lookup"><span data-stu-id="71c5f-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="71c5f-116">Den opprettes for hver modell separat, uavhengig av om den ble fullført eller ikke.</span><span class="sxs-lookup"><span data-stu-id="71c5f-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="71c5f-117">Denne funksjonen fungerer for øyeblikket bare for modellen for transaksjonsfrafall.</span><span class="sxs-lookup"><span data-stu-id="71c5f-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="71c5f-118">Vise brukbarhetsrapporten for inndata</span><span class="sxs-lookup"><span data-stu-id="71c5f-118">View the input data usability report</span></span>

<span data-ttu-id="71c5f-119">Etter at en bruksklar modell har fullført opplæringstrinnet, kan du vise rapporten:</span><span class="sxs-lookup"><span data-stu-id="71c5f-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="71c5f-120">Velg ellipsen ved siden av modellnavnet, og velg **Brukbarhetsrapport for inndata**.</span><span class="sxs-lookup"><span data-stu-id="71c5f-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="71c5f-121">Velg statusen for en modell, og velg **Vis brukbarhetsrapport for inndata** i sideruten.</span><span class="sxs-lookup"><span data-stu-id="71c5f-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="71c5f-122">Velg en av modellene i listen, og velg **Brukbarhetsrapport for inndata** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="71c5f-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="71c5f-123">Åpne siden over modellresultater, og velg **Brukbarhetsrapport for inndata** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="71c5f-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="71c5f-124">Informasjon i brukbarhetsrapporten for inndata</span><span class="sxs-lookup"><span data-stu-id="71c5f-124">Information in the input data usability report</span></span>

<span data-ttu-id="71c5f-125">Følgende kolonner i rapporten inneholder nyttig informasjon for å forbedre dataene for modellen.</span><span class="sxs-lookup"><span data-stu-id="71c5f-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Eksempel på en brukbarhetsrapport for inndata som viser en tabell med feil, advarsler og anbefalinger.":::

- <span data-ttu-id="71c5f-127">Navn: Beskrivende navn på feilen, advarselen eller anbefalingen.</span><span class="sxs-lookup"><span data-stu-id="71c5f-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="71c5f-128">Trinn: Modellfasen (Lær opp eller Poengsum) som informasjonen refererer til.</span><span class="sxs-lookup"><span data-stu-id="71c5f-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="71c5f-129">Tilstand: Alvorsgraden til informasjonen (feil, advarsel, anbefaling).</span><span class="sxs-lookup"><span data-stu-id="71c5f-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="71c5f-130">Kolonnenavn: Kolonne i en enhet som må endres for at modellytelsen skal bli bedre.</span><span class="sxs-lookup"><span data-stu-id="71c5f-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="71c5f-131">Enhetsnavn: Navnet på enheten som må endres for at modellytelsen skal bli bedre.</span><span class="sxs-lookup"><span data-stu-id="71c5f-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="71c5f-132">Detaljer: Detaljer om feilen, advarselen eller anbefalingen.</span><span class="sxs-lookup"><span data-stu-id="71c5f-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="71c5f-133">Oppdatere en prediksjon</span><span class="sxs-lookup"><span data-stu-id="71c5f-133">Refresh a prediction</span></span>

<span data-ttu-id="71c5f-134">Prognoser oppdateres automatisk på samme [tidsplan som dataene dine oppdateres](system.md#schedule-tab), som konfigurert i innstillingene.</span><span class="sxs-lookup"><span data-stu-id="71c5f-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="71c5f-135">Du kan også oppdatere dem manuelt.</span><span class="sxs-lookup"><span data-stu-id="71c5f-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="71c5f-136">Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.</span><span class="sxs-lookup"><span data-stu-id="71c5f-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="71c5f-137">Velg de loddrette ellipsene ved siden av den forutsigelsen du vil oppdatere.</span><span class="sxs-lookup"><span data-stu-id="71c5f-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="71c5f-138">Velg **Oppdater**.</span><span class="sxs-lookup"><span data-stu-id="71c5f-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="71c5f-139">Slette en prediksjon</span><span class="sxs-lookup"><span data-stu-id="71c5f-139">Delete a prediction</span></span>

<span data-ttu-id="71c5f-140">Sletting av en prognose fjerner også utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="71c5f-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="71c5f-141">Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.</span><span class="sxs-lookup"><span data-stu-id="71c5f-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="71c5f-142">Velg de loddrette ellipsene ved siden av den forutsigelsen du vil slette.</span><span class="sxs-lookup"><span data-stu-id="71c5f-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="71c5f-143">Velg **Slett**.</span><span class="sxs-lookup"><span data-stu-id="71c5f-143">Select **Delete**.</span></span>
