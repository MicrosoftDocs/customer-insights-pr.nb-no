---
title: Power Automate-kobling | Microsoft Docs
description: Opprett flyter i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741191"
---
# <a name="power-automate-connector-preview"></a>Power Automate-kobling (forhåndsvisning)

Utløs bestemte hendelser som skal skje automatisk når dataene endres og administrer mer komplekse flyter direkte i [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan ringe maksimalt 100 samtaler per 60 sekunder. Du kan kalle api-endepunkt flere ganger ved å bruke $skip-parameteren. [Lær mer om $skip-parameteren](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automate-utløsere

Bruk utløsere til å opprette skyflyter og automatisere repeterende oppgaver, for eksempel varsler eller mer avanserte handlinger.

- Utløs når en oppdatering av datakilde mislykkes.
- Utløs når en oppdatering av datakilde er vellykket.
- Utløs når en terskel blir overskredet i et segment. Utløseren er begrenset til overgang over grensen.
- Utløs når en terskel blir overskredet i et forretningsmål. Bare forretningsmål uten en dimensjon støttes. Utløseren er begrenset til overgang over grensen.
- Utløses når en full oppdatering av (datakilder, segmenter, mål ...) er fullført.
- Utløs når en oppdatering av samlingsprosessen er fullført.

[Konfigurere utløsere i Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate-handlinger

Power Automate-koblingen gir andre handlinger enn de tilgjengelige utløserne. Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Opprett en Power Automate-flyt

1. Gå til **Admin** > **Eksporter mål**.

1. Velg **Konfigurer** på **Power Automate**-flisen.

1. Customer Insights-koblingen (forhåndsversjon) i Power Automate åpnes. **Logg på** Power Automate.

1. Velg en av de tilgjengelige utløserne, og legg til flere trinn i den nye flyten. Hvis du vil ha mer informasjon, kan du se [Opprett en skyflyt i Power Automate](/power-automate/get-started-logic-flow).

Eksempler på hvordan du bruker flyter: 
- Publiser en melding på en Microsoft Teams-kanal hvis en datakildeoppdatering mislykkes. 
- Send en e-postmelding til dataeierne når en grense for et segment krysses.



[!INCLUDE [footer-include](includes/footer-banner.md)]