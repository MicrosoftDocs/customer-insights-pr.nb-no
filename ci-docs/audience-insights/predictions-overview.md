---
title: Oversikt over støttede prediksjonsscenarioer
description: Prediksjonsscenarioer og -alternativer som dekkes av Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: a5e4503cf9ce0cea562bab9389748d8ca1451f9d
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487547"
---
# <a name="predictions-overview"></a>Oversikt over prediksjoner

Dynamics 365 Customer Insights leveres med en rekke alternativer som bruker kunstig intelligens og maskinlæring til å forutsi data. 

## <a name="out-of-box-models"></a>Bruksklare modeller

Den enkleste måten å begynne å forutsi data på er med forhåndsdefinerte modeller, som ofte kalles bruksklare modeller. De krever bare visse data og en viss struktur for å generere innsikt raskt. For øyeblikket er følgende modeller tilgjengelige: 

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

- [Kundens levetidsverdi](predict-customer-lifetime-value.md): Forutsier den potensielle omsetningen fra en kunde gjennom hele samhandlingen med en virksomhet.
- [Produktanbefaling](predict-product-recommendation.md): Foreslår sett med prediktive produktanbefalinger basert på kjøpsatferd og kunder med lignende kjøpsmønstre.
- [Abonnementsfrafall](predict-subscription-churn.md): Forutsier om en kunde er i faresonen for ikke lenger å bruke selskapets abonnementsprodukter eller -tjenester.
- [Transaksjonsfrafall](predict-transactional-churn.md): Forutsi om en kunde ikke lenger vil kjøpe produktene eller tjenestene dine innen et bestemt tidsramme.
- [Sentimentanalyse](sentiment-analysis.md): Analyser sentiment i tilbakemelding fra kunder, og identifiser forretningsaspekter som ofte blir nevnt.

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

- [Transaksjonsfrafall](predict-transactional-churn.md): Forutsi om en kunde ikke lenger vil kjøpe produktene eller tjenestene dine innen et bestemt tidsramme.

---

> [!TIP]
> Vi anbefaler at du oppdaterer standardmodeller jevnlig med oppdaterte data for å sikre at de informerer virksomhetens brukssak nøyaktig. Data oppdateres ad hoc når nye eller oppdaterte datakilder brukes i systemet. Modellene vil imidlertid bare endre poengsummen i dette tilfellet og fortsette å bruke de eksisterende opplæringsdataene.
> 
> Du kan konfigurere en **Oppdateringsplan** ved å angi tidsplanen for omplanlegging av modellen i konfigurasjonsopplevelsen. Modellen beholder og endrer poengsummen for denne tidsplanen, noe som du kan endre når som helst.


## <a name="azure-machine-learning-integration"></a>Integrering med Azure Machine Learning

Hvis en organisasjon allerede bruker maskinlæringsscenarioer basert på eksperimenter med Azure Machine Learning, bidrar funksjonen for egendefinerte modeller i Customer Insights til å skape et helhetlig bilde. Opprett arbeidsflyter som hjelper deg å velge dataene du vil generere innsikt fra, og tilordne resultatene til de enhetlige kundeprofilene. Hvis du vil ha mer informasjon, kan du se [Egendefinerte maskinlæringsmodeller](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder-prediksjon

Noen ganger er datasett ufullstendige, og noen verdier mangler. Customer Insights kan bidra til å forutsi manglende verdier for kundeenheten og segmentene. Hvis du vil ha mer informasjon, kan du se [Gjøre delvise data komplette med prediksjoner](predictions.md).
