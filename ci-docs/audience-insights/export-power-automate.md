---
title: Power Automate-kobling | Microsoft Docs
description: Opprett flyter i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406491"
---
# <a name="power-automate-connector-preview"></a>Power Automate-kobling (forhåndsvisning)

Utløs bestemte hendelser som skal skje automatisk når dataene endres og administrer mer komplekse flyter direkte i [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate-utløsere

Du kan bruke en rekke utløsere som gjør det mulig for deg å opprette flyter for å automatisere repeterende oppgaver, for eksempel varslinger eller mer avanserte handlinger. 

- Utløs når en oppdatering av datakilde mislykkes. 
- Utløs når en oppdatering av datakilde er vellykket.
- Utløs når en terskel blir overskredet i et segment. Utløseren er begrenset til overgang over grensen.
- Utløs når en terskel blir overskredet i et forretningsmål. Utløseren er begrenset til overgang over grensen.
- Utløses når en full oppdatering av (datakilder, segmenter, mål ...) er fullført.
- Utløs når en oppdatering av samlingsprosessen (tilordning, samsvar, sammenslåing) er fullført.

[Konfigurere utløsere i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate-handlinger
Power Automate-koblingen gir andre handlinger enn de tilgjengelige utløserne. Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Opprette en Power Automate-flyt i målgruppeinnsikt

1. I Målgruppeinnsikt går du til **Administrasjon** > **System**.

1. På **System**-siden velger du kategorien **Status**.

1. I **Datakilder**-delen velger du **Flyter** og deretter **Opprett en flyt** fra rullegardinlisten.
   > [!div class="mx-imgBorder"]
   > ![Power Automate-koblingen som viser Opprett en flyt-handlingen](media/power-automate-connector-create-flow.png "Power Automate-koblingen viser Opprett en flyt-handling")

1. I Power Automate velger du en av de tilgjengelige utløserne for å opprette den foretrukne flyten. Hvis du oppretter din første flyt, må du først godkjenne med Power Automate-koblingen.
