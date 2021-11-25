---
title: Aktivere samtykkeregler for segmenter
description: Følg disse trinnene for å koble samtykkedata og aktivere samtykkekontroller i målgruppeinnsikt. En administrator kan også deaktivere samtykkekontroller.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790788"
---
# <a name="activate-consent-rules"></a>Aktivere samtykkeregler

[Samtykkesenter (forhåndsversjon)](../consent-management/overview.md) hjelper deg med å avstemme samtykkedata fra ulike kilder. Bruk den enhetlige *Samtykke*-enheten for å ta i bruk standard samtykkekontroll. Når du har importert samtykkedata til Samtykkesenter og konfigurert reglene for dataene, synkroniseres *Samtykke*-enheten automatisk til målgruppeinnsikt.

## <a name="enable-consent-checks"></a>Aktiver samtykkekontroller

Når samtykkedata er importert til Samtykkesenter (forhåndsversjon) og reglene er konfigurert, kan du aktivere samtykkekontroller. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Samtykke-fanen i innstillinger for målgruppeinnsikt med aktiverte samtykkedata.":::

1. I Målgruppeinnsikt går du til **Administrasjon** > **System**.

1. Velg fanen **Samtykke (forhåndsvisning)**.

1. I delen **Aktiver samtykkekontroller** angir du veksleknappen til **På** for områdene du vil aktivere.

1. Merk av for **Tillat overstyring av standard samtykkeregler** for å fjerne standard samtykkekontroller som håndheves av et bestemt segment. 

1. Velg hvor du vil tillate overstyringer, i rullegardinmenyen.     

1. I delen **Koble samtykke til kundeprofiler** velger du attributtet som brukes som en identifikator for å koble samtykkedata til kundedata. Det er sannsynligvis et telefonnummer eller en e-postadresse. 

1. Velg **Lagre** for å bruke innstillingene.

## <a name="disable-consent-checks"></a>Deaktivere samtykkekontroller

En administrator må oppdatere systeminnstillingene for å slutte å bruke samtykkedata i målgruppeinnsikt.

1. I Målgruppeinnsikt går du til **Administrasjon** > **System**.

1. Velg fanen **Samtykke (forhåndsvisning)**.

1. I delen **Aktiver samtykkekontroller** setter du veksleknappen til **Av**.
