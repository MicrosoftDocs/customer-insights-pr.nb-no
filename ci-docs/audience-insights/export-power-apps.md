---
title: Power Apps-kobling
description: Koble til med Power Apps og Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 985e6c85795fba8ca3063cdffc7f9012e798856a
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623235"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps-kobling (forhåndsvisning)

Samle inn enhetlige kundeprofiler i de tilpassede appene med Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Koble sammen Power Apps og Dynamics 365 Customer Insights

Customer Insights er én av mange [tilgjengelige kilder for data i Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Se i Power Apps-dokumentasjonen for å lære hvordan du [legger til en datatilkobling til en app](/powerapps/maker/canvas-apps/add-data-connection). Vi anbefaler at du også ser gjennom [hvordan Power Apps bruker delegering til å håndtere store datasett i lerretsapper](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Tilgjengelige enheter

Etter at du har lagt til Customer Insights som en datatilkobling, kan du velge følgende enheter i Power Apps:

- **Kunde**: for å bruke data fra den [enhetlige kundeprofilen](customer-profiles.md).
- **UnifiedActivity**: for å vise [tidslinjen for aktivitet](activities.md) i appen.
- **ContactProfile**: for å vise kontaktene til en kunde. Denne enheten er bare tilgjengelig i målgruppeinnsiktmiljøer for forretningsforbindelser.

## <a name="limitations"></a>Begrensninger

### <a name="retrievable-entities"></a>Enheter som kan hentes

Du kan bare hente enhetene **Kunde**, **UnifiedActivity**, **Segmenter** og **ContactProfile** via Power Apps-koblingen. ContactProfile er bare tilgjengelig i målgruppeinnsiktforekomsten for forretningsforbindelser. Andre enheter vises fordi den underliggende koblingen støtter dem gjennom utløsere i Power Automate.

### <a name="delegation"></a>Delegering

Delegering fungerer for **Kunde**-enhet og **UnifiedActivity**-enhet. 

- Delegering for **Kunde**-enhet: Hvis du vil bruke delegering for enheten, må feltene indekseres i [Søk- og filterindeks](search-filter-index.md).  
- Delegering for **UnifiedActivity**: Delegering for denne enheten fungerer bare for feltene **ActivityId** og **CustomerId**.  
- Delegering for **ContactProfile**: Delegering for denne enheten fungerer bare for feltene **ContactId** og **CustomerId**. ContactProfile er bare tilgjengelig i målgruppeinnsiktmiljøene for forretningsforbindelser.

Hvis du vil ha mer informasjon om delegering, kan du gå til [Power Apps-delegerbare funksjoner og operasjoner](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Eksempel på Galleri-kontroll

Du kan legge til kundeprofiler i en [gallerikontroll](/powerapps/maker/canvas-apps/add-gallery).

1. Legg til en **galleri**-kontroll i en app du skal bygge.

    > [!div class="mx-imgBorder"]
    > ![Legg til et gallerielement.](media/connector-powerapps9.png "Legg til et gallerielement.")

2. Velg **Kunde** som datakilde for varer.

    > [!div class="mx-imgBorder"]
    > ![Velg en datakilde.](media/choose-datasource-powerapps.png "Velg en datakilde.")

3. Du kan endre datapanelet til høyre for å velge hvilket felt kundeenheten skal vise i galleriet.

4. Hvis du vil vise et felt fra den valgte kunden i galleriet, fyller du ut **Tekst**-egenskapen for en etikett ved hjelp av **{Name_of_the_gallery}.Selected.{property_name}**  
    - Eksempel: _Gallery1.Selected.address1_city_

5. Hvis du vil vise den enhetlige tidslinjen for en kunde, legger du til et gallerielement og legger til **Elementer**-egenskapen ved hjelp av **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - For eksempel: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
