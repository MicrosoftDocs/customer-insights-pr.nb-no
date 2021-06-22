---
title: Oversikt over støttede prediksjonsscenarioer
description: Prediksjonsscenarioer og -alternativer som dekkes av Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095735"
---
# <a name="predictions-overview"></a><span data-ttu-id="cfe8a-103">Oversikt over prediksjoner</span><span class="sxs-lookup"><span data-stu-id="cfe8a-103">Predictions overview</span></span>

<span data-ttu-id="cfe8a-104">Dynamics 365 Customer Insights leveres med en rekke alternativer som bruker kunstig intelligens og maskinlæring til å forutsi data.</span><span class="sxs-lookup"><span data-stu-id="cfe8a-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="cfe8a-105">Bruksklare modeller</span><span class="sxs-lookup"><span data-stu-id="cfe8a-105">Out-of-box models</span></span>

<span data-ttu-id="cfe8a-106">Den enkleste måten å begynne å forutsi data på er med forhåndsdefinerte modeller, som ofte kalles bruksklare modeller.</span><span class="sxs-lookup"><span data-stu-id="cfe8a-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="cfe8a-107">De krever bare visse data og en viss struktur for å generere innsikt raskt.</span><span class="sxs-lookup"><span data-stu-id="cfe8a-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="cfe8a-108">For øyeblikket er følgende modeller tilgjengelige:</span><span class="sxs-lookup"><span data-stu-id="cfe8a-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="cfe8a-109">[Kundens levetidsverdi](predict-customer-lifetime-value.md): Forutsier den potensielle omsetningen fra en kunde gjennom hele samhandlingen med en virksomhet.</span><span class="sxs-lookup"><span data-stu-id="cfe8a-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="cfe8a-110">[Produktanbefaling](predict-product-recommendation.md): Foreslår sett med prediktive produktanbefalinger basert på kjøpsatferd og kunder med lignende kjøpsmønstre.</span><span class="sxs-lookup"><span data-stu-id="cfe8a-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="cfe8a-111">[Abonnementsfrafall](predict-subscription-churn.md): Forutsier om en kunde er i faresonen for ikke lenger å bruke selskapets abonnementsprodukter eller -tjenester.</span><span class="sxs-lookup"><span data-stu-id="cfe8a-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="cfe8a-112">[Transaksjonsfrafall](predict-transactional-churn.md): Forutsi om en kunde ikke lenger vil kjøpe produktene eller tjenestene dine innen et bestemt tidsramme.</span><span class="sxs-lookup"><span data-stu-id="cfe8a-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="cfe8a-113">Integrering med Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="cfe8a-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="cfe8a-114">Hvis en organisasjon allerede bruker maskinlæringsscenarioer basert på eksperimenter med Azure Machine Learning, bidrar funksjonen for egendefinerte modeller i Customer Insights til å skape et helhetlig bilde.</span><span class="sxs-lookup"><span data-stu-id="cfe8a-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="cfe8a-115">Opprett arbeidsflyter som hjelper deg å velge dataene du vil generere innsikt fra, og tilordne resultatene til de enhetlige kundeprofilene.</span><span class="sxs-lookup"><span data-stu-id="cfe8a-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="cfe8a-116">Hvis du vil ha mer informasjon, kan du se [Egendefinerte maskinlæringsmodeller](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="cfe8a-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="cfe8a-117">AI Builder-prediksjon</span><span class="sxs-lookup"><span data-stu-id="cfe8a-117">AI Builder prediction</span></span>

<span data-ttu-id="cfe8a-118">Noen ganger er datasett ufullstendige, og noen verdier mangler.</span><span class="sxs-lookup"><span data-stu-id="cfe8a-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="cfe8a-119">Customer Insights kan bidra til å forutsi manglende verdier for kundeenheten og segmentene.</span><span class="sxs-lookup"><span data-stu-id="cfe8a-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="cfe8a-120">Hvis du vil ha mer informasjon, kan du se [Gjøre delvise data komplette med prediksjoner](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="cfe8a-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
