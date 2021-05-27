---
title: Power Automate-kobling | Microsoft Docs
description: Opprett flyter i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976100"
---
# <a name="power-automate-connector-preview"></a>Power Automate-kobling (forhåndsvisning)

Utløs bestemte hendelser som skal skje automatisk når dataene endres og administrer mer komplekse flyter direkte i [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate-utløsere

Bruk utløsere til å opprette skyflyter og automatisere repeterende oppgaver, for eksempel varsler eller mer avanserte handlinger. 

- Utløs når en oppdatering av datakilde mislykkes. 
- Utløs når en oppdatering av datakilde er vellykket.
- Utløs når en terskel blir overskredet i et segment. Utløseren er begrenset til overgang over grensen.
- Utløs når en terskel blir overskredet i et forretningsmål. Bare forretningsmål uten en dimensjon støttes. Utløseren er begrenset til overgang over grensen.
- Utløses når en full oppdatering av (datakilder, segmenter, mål ...) er fullført.
- Utløs når en oppdatering av samlingsprosessen (tilordning, samsvar, sammenslåing) er fullført.

[Konfigurere utløsere i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate-handlinger
Power Automate-koblingen gir andre handlinger enn de tilgjengelige utløserne. Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Opprett en Power Automate-flyt

1. I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.

1. Velg **Konfigurer** på **Power Automate**-flisen.

1. Customer Insights-koblingen (forhåndsversjon) i Power Automate åpnes. **Logg på** Power Automate.

1. Velg en av de tilgjengelige utløserne, og legg til flere trinn i den nye flyten. Hvis du vil ha mer informasjon, kan du se [Opprett en skyflyt i Power Automate](/power-automate/get-started-logic-flow).

Eksempler på hvordan du bruker flyter: 
- Publiser en melding på en Microsoft Teams-kanal hvis en datakildeoppdatering mislykkes. 
- Send en e-postmelding til dataeierne når en grense for et segment krysses.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
