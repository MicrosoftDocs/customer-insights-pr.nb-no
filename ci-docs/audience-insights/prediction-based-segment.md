---
title: Segmenter basert på prediksjonsutdata
description: Opprett segmenter basert på utdataenheten for en prediksjonsmodell.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741441"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="8ef2f-103">Opprette et segment basert på en prediksjonsmodell (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="8ef2f-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="8ef2f-104">Resultatene av prognoser gjelder noen ganger bare for et delsett av kundene.</span><span class="sxs-lookup"><span data-stu-id="8ef2f-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="8ef2f-105">Øk tilpassingen av anbefalinger ved å opprette segmenter fra resultatene av prediksjonsmodeller.</span><span class="sxs-lookup"><span data-stu-id="8ef2f-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="8ef2f-106">Det kan for eksempel hende at du vil gi bestemte anbefalinger til kunder som foretrekker en bestemt type service.</span><span class="sxs-lookup"><span data-stu-id="8ef2f-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8ef2f-107">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="8ef2f-107">Prerequisites</span></span>

- <span data-ttu-id="8ef2f-108">Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8ef2f-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="8ef2f-109">En modell for produktanbefaling, transaksjonsfrafall, abonnementsfrafall eller kundelevetidsverdi konfigurert i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8ef2f-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="8ef2f-110">Gå gjennom kravene for å konfigurere de forskjellige modellene:</span><span class="sxs-lookup"><span data-stu-id="8ef2f-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="8ef2f-111">Produktanbefalingsmodell</span><span class="sxs-lookup"><span data-stu-id="8ef2f-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="8ef2f-112">Modell for abonnementsfrafall</span><span class="sxs-lookup"><span data-stu-id="8ef2f-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="8ef2f-113">Modell for transaksjonsfrafall</span><span class="sxs-lookup"><span data-stu-id="8ef2f-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="8ef2f-114">Modell for kundelevetidsverdi</span><span class="sxs-lookup"><span data-stu-id="8ef2f-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="8ef2f-115">Opprette et kundesegment basert på prediksjoner</span><span class="sxs-lookup"><span data-stu-id="8ef2f-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="8ef2f-116">Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.</span><span class="sxs-lookup"><span data-stu-id="8ef2f-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="8ef2f-117">Velg de loddrette ellipsene ved siden av modellen du vil se gjennom, og velg **Vis**.</span><span class="sxs-lookup"><span data-stu-id="8ef2f-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="8ef2f-118">Velg **Opprett segment** på resultatsiden.</span><span class="sxs-lookup"><span data-stu-id="8ef2f-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="8ef2f-119">Hvis du vil ha mer informasjon om resultatsiden, kan du se gjennom artikkelen om modellen.</span><span class="sxs-lookup"><span data-stu-id="8ef2f-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Skjermbilde av resultatsiden for prediksjon med utheving av Opprett segment-handlingen.":::

1. <span data-ttu-id="8ef2f-121">Opprett et nytt segment basert på utdataenheten for den valgte modellen.</span><span class="sxs-lookup"><span data-stu-id="8ef2f-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="8ef2f-122">Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8ef2f-122">For more information, see [Create and manage segments](segments.md).</span></span>