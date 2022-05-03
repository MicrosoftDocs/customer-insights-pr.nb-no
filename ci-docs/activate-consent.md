---
title: Aktivere samtykkeregler for segmenter
description: Følg disse trinnene for å koble samtykkedata og aktivere samtykkekontroller i Dynamics 365 Customer Insights. En administrator kan også deaktivere samtykkekontroller.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646640"
---
# <a name="activate-consent-rules"></a>Aktivere samtykkeregler

[Samtykkesenter (forhåndsversjon)](consent-management/overview.md) hjelper deg med å avstemme samtykkedata fra ulike kilder. Bruk den enhetlige *Samtykke*-enheten for å ta i bruk standard samtykkekontroll. Når du har importert samtykkedata til Samtykkesenter og konfigurert reglene for dataene, synkroniseres *Samtykke*-enheten automatisk til Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Aktiver samtykkekontroller

Når samtykkedata er importert til Samtykkesenter (forhåndsversjon) og reglene er konfigurert, kan du aktivere samtykkekontroller. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Samtykke-fanen i Customer Insights-innstillinger med aktiverte samtykkedata.":::

1. Gå til **Admin** > **System** i Customer Insights.

1. Velg fanen **Samtykke (forhåndsvisning)**.

1. I delen **Aktiver samtykkekontroller** angir du veksleknappen til **På** for områdene du vil aktivere.

1. Merk av for **Tillat overstyring av standard samtykkeregler** for å fjerne standard samtykkekontroller som håndheves av et bestemt segment. 

1. Velg hvor du vil tillate overstyringer, i rullegardinmenyen.     

1. I delen **Koble samtykke til kundeprofiler** velger du attributtet som brukes som en identifikator for å koble samtykkedata til kundedata. Det er sannsynligvis et telefonnummer eller en e-postadresse. 

1. Velg **Lagre** for å bruke innstillingene.

## <a name="disable-consent-checks"></a>Deaktivere samtykkekontroller

En administrator må oppdatere systeminnstillingene for å slutte å bruke samtykkedata i Customer Insights.

1. Gå til **Admin** > **System** i Customer Insights.

1. Velg fanen **Samtykke (forhåndsvisning)**.

1. I delen **Aktiver samtykkekontroller** setter du veksleknappen til **Av**.

> [!TIP]
> Hvis du vil slutte å bruke funksjonen for samtykkebehandling, kan du se [Systeminnstillinger i Samtykkesenter (forhåndsersjon)](consent-management/system-settings.md).
