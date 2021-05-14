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
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Opprette et segment basert på en prediksjonsmodell (forhåndsvisning)

Resultatene av prognoser gjelder noen ganger bare for et delsett av kundene. Øk tilpassingen av anbefalinger ved å opprette segmenter fra resultatene av prediksjonsmodeller. Det kan for eksempel hende at du vil gi bestemte anbefalinger til kunder som foretrekker en bestemt type service. 

## <a name="prerequisites"></a>Forutsetninger

- Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.

- En modell for produktanbefaling, transaksjonsfrafall, abonnementsfrafall eller kundelevetidsverdi konfigurert i Customer Insights. Gå gjennom kravene for å konfigurere de forskjellige modellene:

  - [Produktanbefalingsmodell](predict-product-recommendation.md)
  - [Modell for abonnementsfrafall](predict-subscription-churn.md)
  - [Modell for transaksjonsfrafall](predict-transactional-churn.md)
  - [Modell for kundelevetidsverdi](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Opprette et kundesegment basert på prediksjoner

1. Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.

1. Velg de loddrette ellipsene ved siden av modellen du vil se gjennom, og velg **Vis**.

1. Velg **Opprett segment** på resultatsiden. Hvis du vil ha mer informasjon om resultatsiden, kan du se gjennom artikkelen om modellen.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Skjermbilde av resultatsiden for prediksjon med utheving av Opprett segment-handlingen.":::

1. Opprett et nytt segment basert på utdataenheten for den valgte modellen. Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).