---
title: Power Apps-kobling
description: Koble til med Power Apps og Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 2ab5a9059991611a2959a19cc688d232ec782e1e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554125"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps-kobling (forhåndsvisning)

Samle inn enhetlige kundeprofiler i de tilpassede appene med Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Koble sammen Power Apps og Dynamics 365 Customer Insights

Customer Insights er én av mange [tilgjengelige kilder for data i Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Se i Power Apps-dokumentasjonen for å lære hvordan du [legger til en datatilkobling til en app](/powerapps/maker/canvas-apps/add-data-connection). Vi anbefaler at du også ser gjennom [hvordan Power Apps bruker delegering til å håndtere store datasett i lerretsapper](/powerapps/maker/canvas-apps/delegation-overview).

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

- Hvis du vil ha mer informasjon om delegering, se [Power Apps-funksjoner og operasjoner som kan delegeres](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Eksempel på Galleri-kontroll

Du legger for eksempel til kundeprofiler i en [gallerikontroll](/powerapps/maker/canvas-apps/add-gallery).

1. Legg til en **Galleri**-kontroll i en app du skal bygge.

> [!div class="mx-imgBorder"]
> ![Legg til et gallerielement.](media/connector-powerapps9.png "Legge til et gallerielement")

1. Velg **Kunde** som datakilde for varer.

    > [!div class="mx-imgBorder"]
    > ![Velg en datakilde.](media/choose-datasource-powerapps.png "Velg en datakilde")

1. Du kan endre datapanelet til høyre for å velge hvilket felt kundeenheten skal vise i galleriet.

1. Hvis du vil vise et felt fra den valgte kunden i galleriet, fyller du ut tekstegenskapen for en etikett:  **{Name_of_the_gallery}.Selected.{property_name}**

    Eksempel: Gallery1.Selected.address1_city

1. Hvis du vil vise den enhetlige tidslinjen for en kunde, legger du til et gallerielement og legger til elementegenskapen: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Eksempel: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]