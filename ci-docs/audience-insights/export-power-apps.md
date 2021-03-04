---
title: Power Apps-kobling
description: Koble til med Power Apps og Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268928"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps-kobling (forhåndsvisning)

Samle inn enhetlige kundeprofiler i de tilpassede appene med Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Koble sammen Power Apps og Dynamics 365 Customer Insights

Customer Insights er én av mange [tilgjengelige kilder for data i Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Se i Power Apps-dokumentasjonen for å lære hvordan du [legger til en datatilkobling til en app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). Vi anbefaler at du også ser gjennom [hvordan Power Apps bruker delegering til å håndtere store datasett i lerretsapper](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Tilgjengelige enheter

Etter at du har lagt til Customer Insights som en datatilkobling, kan du velge følgende enheter i Power Apps:

- Kunde: for å bruke data fra den [enhetlige kundeprofilen](customer-profiles.md).
- UnifiedActivity: for å vise den [enhetlige tidslinjen](activities.md) på appen.

## <a name="limitations"></a>Begrensninger

### <a name="retrievable-entities"></a>Enheter som kan hentes

Du kan bare hente enhetene **Kunde**, **UnifiedActivity** og **Segmenter** via Power Apps-koblingen. Andre enheter vises fordi den underliggende koblingen støtter dem gjennom utløsere i Power Automate.  

### <a name="delegation"></a>Delegering

Delegering fungerer for kundeenhet og UnifiedActivity-enhet. 

- Delegering for **Kunde**-enhet: Hvis du vil bruke delegering for enheten, må feltene indekseres i [Søk- og filterindeks](search-filter-index.md).  

- Delegering for **UnifiedActivity**: Delegering for denne enheten fungerer bare for feltene **ActivityId** og **CustomerId**.  

- Hvis du vil ha mer informasjon om delegering, se [Power Apps-funksjoner og operasjoner som kan delegeres](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Eksempel på Galleri-kontroll

Du legger for eksempel til kundeprofiler i en [gallerikontroll](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Legg til en **Galleri**-kontroll i en app du skal bygge.

> [!div class="mx-imgBorder"]
> ![Legge til et gallerielement](media/connector-powerapps9.png "Legge til et gallerielement")

1. Velg **Kunde** som datakilde for varer.

    > [!div class="mx-imgBorder"]
    > ![Velg en datakilde](media/choose-datasource-powerapps.png "Velg en datakilde")

1. Du kan endre datapanelet til høyre for å velge hvilket felt kundeenheten skal vise i galleriet.

1. Hvis du vil vise et felt fra den valgte kunden i galleriet, fyller du ut tekstegenskapen for en etikett:  **{Name_of_the_gallery}.Selected.{property_name}**

    Eksempel: Gallery1.Selected.address1_city

1. Hvis du vil vise den enhetlige tidslinjen for en kunde, legger du til et gallerielement og legger til elementegenskapen: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Eksempel: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]