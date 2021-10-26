---
title: Oversikt over støttede prediksjonsscenarioer
description: Prediksjonsscenarioer og -alternativer som dekkes av Dynamics 365 Customer Insights.
ms.date: 09/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: be452e4f1515f637f6edbc3ae3aaf6a3d3471489
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618855"
---
# <a name="predictions-overview"></a>Oversikt over prediksjoner

Dynamics 365 Customer Insights leveres med en rekke alternativer som bruker kunstig intelligens og maskinlæring til å forutsi data. 

## <a name="out-of-box-models"></a>Bruksklare modeller

Den enkleste måten å begynne å forutsi data på er med forhåndsdefinerte modeller, som ofte kalles bruksklare modeller. De krever bare visse data og en viss struktur for å generere innsikt raskt. For øyeblikket er følgende modeller tilgjengelige: 

# <a name="individual-customers-b2c"></a>[Individuelle kunder (B2C)](#tab/b2c)

- [Kundens levetidsverdi](predict-customer-lifetime-value.md): Forutsier den potensielle omsetningen fra en kunde gjennom hele samhandlingen med en virksomhet.
- [Produktanbefaling](predict-product-recommendation.md): Foreslår sett med prediktive produktanbefalinger basert på kjøpsatferd og kunder med lignende kjøpsmønstre.
- [Abonnementsfrafall](predict-subscription-churn.md): Forutsier om en kunde er i faresonen for ikke lenger å bruke selskapets abonnementsprodukter eller -tjenester.
- [Transaksjonsfrafall](predict-transactional-churn.md): Forutsi om en kunde ikke lenger vil kjøpe produktene eller tjenestene dine innen et bestemt tidsramme.

# <a name="business-accounts-b2b"></a>[Forretningsforbindelser (B2B)](#tab/b2b)

- [Transaksjonsfrafall](predict-transactional-churn.md): Forutsi om en kunde ikke lenger vil kjøpe produktene eller tjenestene dine innen et bestemt tidsramme.

---


## <a name="azure-machine-learning-integration"></a>Integrering med Azure Machine Learning

Hvis en organisasjon allerede bruker maskinlæringsscenarioer basert på eksperimenter med Azure Machine Learning, bidrar funksjonen for egendefinerte modeller i Customer Insights til å skape et helhetlig bilde. Opprett arbeidsflyter som hjelper deg å velge dataene du vil generere innsikt fra, og tilordne resultatene til de enhetlige kundeprofilene. Hvis du vil ha mer informasjon, kan du se [Egendefinerte maskinlæringsmodeller](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder-prediksjon

Noen ganger er datasett ufullstendige, og noen verdier mangler. Customer Insights kan bidra til å forutsi manglende verdier for kundeenheten og segmentene. Hvis du vil ha mer informasjon, kan du se [Gjøre delvise data komplette med prediksjoner](predictions.md).
