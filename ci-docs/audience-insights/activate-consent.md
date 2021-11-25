---
title: Aktivere samtykkeregler for segmenter i målgruppeinnsikt
description: Trinn for å koble samtykkedata og aktivere samtykkekontroller i målgruppeinnsikt.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753073"
---
# <a name="activate-consent-rules"></a>Aktivere samtykkeregler

[Samtykkesenter (forhåndsversjon)](../consent-management/overview.md) hjelper deg med å avstemme samtykkedata fra ulike kilder. Bruk den enhetlige *Samtykke*-enheten for å ta i bruk standard samtykkekontroll. Når du har importert samtykkedata i Samtykkesenter og konfigurert reglene for de importerte samtykkedataene, synkroniseres *Samtykke*-enheten automatisk til målgruppeinnsikt.

## <a name="enable-consent-checks"></a>Aktiver samtykkekontroller

Når samtykkedata er importert til Samtykkesenter (forhåndsversjon) og regler er konfigurert, kan du aktivere samtykkekontroller i målgruppeinnsikt. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Samtykke-fanen i innstillinger for målgruppeinnsikt med aktiverte samtykkedata.":::

1. I Målgruppeinnsikt går du til **Administrasjon** > **System**.

1. Velg fanen **Samtykke (forhåndsvisning)**.

1. I delen **Aktiver samtykkekontroller** angir du veksleknappen for området du vil aktivere, til **På**.

1. Merk av for **Tillat overstyring av standard samtykkeregler** for å fjerne standard samtykkekontroller som håndheves av et bestemt segment. 

1. Velg hvor du vil tillate overstyringer, i rullegardinmenyen.     

1. I delen **Koble samtykke til kundeprofiler** velger du attributtet som brukes som en identifikator for å koble samtykkedata til kundedata. Det er sannsynligvis et telefonnummer eller en e-postadresse. 

1. Velg **Lagre** for å bruke innstillingene.

## <a name="disable-consent-checks"></a>Deaktivere samtykkekontroller

En administrator må oppdatere systeminnstillingene for å slutte å bruke samtykkedata i målgruppeinnsikt.

1. I Målgruppeinnsikt går du til **Administrasjon** > **System**.

1. Velg fanen **Samtykke (forhåndsvisning)**.

1. I delen **Aktiver samtykkekontroller** setter du veksleknappen til **Av**.
