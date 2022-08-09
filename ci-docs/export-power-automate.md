---
title: Power Automate-kobling (forhåndsversjon) | Microsoft Docs
description: Opprett flyter i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196130"
---
# <a name="power-automate-connector-preview"></a>Power Automate-kobling (forhåndsvisning)

Utløs bestemte hendelser som skal skje automatisk når dataene endres og administrer mer komplekse flyter direkte i [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Kjente begrensninger

- Maksimalt 100 samtaler per 60 sekunder. Bruk [$skip-parameteren](/connectors/customerinsights/#get-items-from-an-entity) til å kalle opp API-endepunktet flere ganger.

## <a name="power-automate-triggers"></a>Power Automate-utløsere

Bruk utløsere til å opprette skyflyter og automatisere repeterende oppgaver, for eksempel varsler eller mer avanserte handlinger. Bruk utløsere når følgende er tilfelle:

- En oppdatering av datakilde mislykkes.
- En oppdatering av datakilde fullføres.
- En terskel blir overskredet i et segment. Utløseren er begrenset til overgang over grensen.
- En terskel blir overskredet i et forretningsmål. Bare forretningsmål uten en dimensjon støttes. Utløseren er begrenset til overgang over grensen.
- En planlagt, fullstendig oppdatering fullføres. Denne utløseren fungerer ikke for oppdateringer som startes manuelt.
- En oppdatering av samlingsprosessen fullføres.

[Konfigurere utløsere i Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate-handlinger

Power Automate-koblingen gir andre handlinger enn de tilgjengelige utløserne. Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Opprett en Power Automate-flyt

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Konfigurer** på **Power Automate**-flisen.

1. Customer Insights-koblingen (forhåndsversjon) i Power Automate åpnes. **Logg på** Power Automate.

1. Velg en av de tilgjengelige utløserne, og legg til flere trinn i den nye flyten. Hvis du vil ha mer informasjon, kan du se [Opprett en skyflyt i Power Automate](/power-automate/get-started-logic-flow).

Eksempler på hvordan du bruker flyter: 
- Publiser en melding på en Microsoft Teams-kanal hvis en datakildeoppdatering mislykkes. 
- Send en e-postmelding til dataeierne når en grense for et segment krysses.

[!INCLUDE [footer-include](includes/footer-banner.md)]
