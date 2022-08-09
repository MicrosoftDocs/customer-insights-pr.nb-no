---
title: Power Apps-kobling (forhåndsvisning)
description: Koble til med Power Apps og Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196912"
---
# <a name="power-apps-connector-preview"></a>Power Apps-kobling (forhåndsvisning)

Samle inn enhetlige kundeprofiler i de tilpassede appene med Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Koble sammen Power Apps og Dynamics 365 Customer Insights

Customer Insights er én av mange [tilgjengelige kilder for data i Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Se i Power Apps-dokumentasjonen for å lære hvordan du [legger til en datatilkobling til en app](/powerapps/maker/canvas-apps/add-data-connection). Vi anbefaler at du også ser gjennom [hvordan Power Apps bruker delegering til å håndtere store datasett i lerretsapper](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Tilgjengelige enheter

Etter at du har lagt til Customer Insights som en datatilkobling, velger du følgende enheter i Power Apps:

- **Kunde**: for å bruke data fra den [enhetlige kundeprofilen](customer-profiles.md).
- **UnifiedActivity**: for å vise [tidslinjen for aktivitet](activities.md) i appen.
- **ContactProfile**: for å vise kontaktene til en kunde. Denne enheten er bare tilgjengelig i Customer Insights-miljøer for forretningsforbindelser.

## <a name="limitations"></a>Begrensninger

### <a name="retrievable-entities"></a>Enheter som kan hentes

Du kan bare hente enhetene **Kunde**, **UnifiedActivity**, **Segmenter** og **ContactProfile** via Power Apps-koblingen. ContactProfile er bare tilgjengelig i Customer Insights-miljøene for forretningsforbindelser. Andre enheter vises fordi den underliggende koblingen støtter dem gjennom utløsere i Power Automate.

Du kan ringe maksimalt 100 samtaler per 60 sekunder. Du kan kalle api-endepunkt flere ganger ved å bruke $skip-parameteren. [Lær mer om $skip-parameteren](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegering

Delegering fungerer for **Kunde**-enhet og **UnifiedActivity**-enhet.

- Delegering for **Kunde**-enhet: Hvis du vil bruke delegering for enheten, må feltene indekseres i [søke- og filterindeks](search-filter-index.md).  
- Delegering for **UnifiedActivity**: Delegering for denne enheten fungerer bare for feltene **ActivityId** og **CustomerId**.  
- Delegering for **ContactProfile**: Delegering for denne enheten fungerer bare for feltene **ContactId** og **CustomerId**. ContactProfile er bare tilgjengelig i Customer Insights-miljøene for forretningsforbindelser.

Hvis du vil ha mer informasjon om delegering, kan du gå til [Power Apps-delegerbare funksjoner og operasjoner](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Eksempel på Galleri-kontroll

Legg eventuelt til kundeprofiler i en [gallerikontroll](/powerapps/maker/canvas-apps/add-gallery).

1. Legg til en **galleri**-kontroll i en app du skal bygge.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Legg til et gallerielement.":::

1. Velg **Kunde** som datakilde for varer.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Velg en datakilde.":::

1. Endre datapanelet til høyre for å velge hvilket felt kundeenheten skal vise i galleriet.

1. Hvis du vil vise et felt fra den valgte kunden i galleriet, fyller du ut **Tekst**-egenskapen for en etikett ved hjelp av **{Name_of_the_gallery}.Selected.{property_name}**  
    - Eksempel: _Gallery1.Selected.address1_city_

1. Hvis du vil vise den enhetlige tidslinjen for en kunde, legger du til et gallerielement og legger til **Elementer**-egenskapen ved hjelp av **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - For eksempel: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
